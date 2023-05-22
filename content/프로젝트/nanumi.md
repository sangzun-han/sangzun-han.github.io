---
emoji: 😂
title: 나누미
date: '2023-05-22 00:00:00'
author: sangzun
tags: javascript,typescript,react,react-native
categories: 프로젝트
---

리액트 네이티브를 이용한 무료나눔 앱을 만들었습니다.

[nanumi App](https://play.google.com/store/apps/details?id=com.nanumimobile)

## 프로젝트 컨셉

- 14:00에 물품을 나눔받을 수 있고 나눔받을 수 있는 사람은 선착순 3명으로 지정된다.
- 물건을 올린 사람은 3명 중 마음에 드는 사람에 채팅을 하여 거래를 한다.

## 구현사항

- react-query의 useInfinityQuery 이용한 무한스크롤, useQuery를 이용한 데이터 fetching
- reocil을 이용한 유저정보, 모달 전역상태관리
- axios interceptor를 이용해서 access_token 재발급
- Webview를 이용해서 카카오 소셜 로그인 구현
- AsyncStorage를 이용해서 로그인이 풀리지 않도록 구현
- stomp/stompjs를 이용한 1:1 채팅 구현

### 트러블 슈팅

- EC2를 제공받아서 하는만큼 서버에 API요청을 보낼 수 있는 시간은 프로젝트 기간동안이었습니다. 리팩토링을 따로 할 시간은 없었기 때문에 구현하면서 이건 아니다 싶은건 백엔드와 소통하면서 바로바로 코드를 고쳐나갔지만 6주라는 짧은시간동안 생각한대로 구현하지 못한 부분이 있습니다.

1. 카카오 소셜 로그인

   - react-native에는 자체적으로 카카오에 로그인하고 로그아웃하는 `react-native-kakao-login`이라는 라이브러리가 존재합니다. 하지만 백엔드쪽에서 이미 소셜로그인을 구현한 상태였고 그에 따라서 Webview를 이용해서 웹처럼 소셜 로그인을 구현했습니다.

   - 카카오 로그인 시 redirect되는것을 막을 방법을 못찾아서 로그인, 필수활용동의서에 취소를 누를 때에는 Webview의 투명도를 0으로 만들어서 사용자에게는 에러페이지가 보이지않게하고 다시 앱으로 redirect되도록 해결은 했습니다만 올바른 방법은 아니라고 생각합니다.

   ```javacsript
   <View style={{flex: 1, opacity: opacity ? 0 : 1}}>
      <WebView source={{ uri: `kakao`}}
        injectedJavaScript={INJECTED_JAVASCRIPT}
        onMessage={handleMessage}
        onNavigationStateChange={handleNavigationStataChange}
      />
   </View>
   ```

   ### 변경 전 -> 변경 후

   <div style="display:flex">
      <img src="/nanumi_kakao_visible.gif" width="250" height="500" />
      <img src="/nanumi_kakao_novisible.gif" width="250" height="500" />
   </div>

2. recoil을 통한 모달 전역관리

   - 사실 이 프로젝트에서 전역으로 상태할 변수는 상품데이터, 유저, 모달정도였습니다. 프로젝트를 진행하면서 상품데이터는 어디서도 같은 데이터를 쓰는곳이 없어서 전역으로 상태관리를 하지 않아도 된다고 판단했고 모달,유저정보 정도만 전역으로 상태를 관리했습니다.

   - 기존의 모두 각각 모달이 열리는 부모 컴포넌트쪽에서 props를 내려서 관리하고 있었습니다. 모달은 약 10개정도의 모달이 존재했고 모달의 개수가 많아질수록 관리해야 할 상태들과 코드들이 많아져 관리가 힘들어졌습니다. 띠라서 모달의 상태는 따로 관심사를 나눠야 한다는 생각이 들었습니다.

   - 모달은 한개의 버튼이 있는 모달, 두개의 버튼이 있는 모달, 카테고리 모달이 존재했고 버튼이 한개인 모달은 `OneButtonModal`, 두개의 버튼이 있는 모달은 `TwoButtonModal`로 선언하여 props로 각 버튼에 대한 이벤트와 해당 모달에 들어갈 title, content, event를 받아서 처리했습니다..

   ```javascript
   // useModal.jsx
   import { useMemo } from 'react';
   import { useRecoilState } from 'recoil';
   import { modalState } from './../state/modal';

   export const useModal = () => {
     const [modal, setModal] = useRecoilState(modalState);

     const showModal = ({ modalType, modalProps }) => {
       setModal({ modalType, modalProps });
     };

     const hideModal = () => {
       setModal({
         modalType: null,
         modalProps: {
           visible: false,
         },
       });
     };

     return useMemo(() => ({ modal, setModal, showModal, hideModal }), [modal, setModal]);
   };
   ```

   ```javascript
   // profile.jsx
   const handleOpenWithdrawalModal = () => {
     showModal({
       modalType: 'TwoButtonModal',
       modalProps: {
         title: '회원탈퇴',
         content: '정말 탈퇴하시겠어요?',
         visible: true,
         onConfirm: handleDeleteUser,
         onCancel: hideModal,
       },
     });
   };
   ```

   ```javascript
   const MODAL_TYPES = {
     TransactionCompleteModal: 'TransactionCompleteModal',
     MatchingUserModal: 'MatchingUserModal',
     HomeCategoryModal: 'HomeCategoryModal',
     CreateCategoryModal: 'CreateCategoryModal',
     OneButtonModal: 'OneButtonModal',
     TwoButtonModal: 'TwoButtonModal',
   };

   const MODAL_COMPONENTS = {
     [MODAL_TYPES.TransactionCompleteModal]: TransactionCompleteModal,
     [MODAL_TYPES.MatchingUserModal]: MatchingUserModal,
     [MODAL_TYPES.HomeCategoryModal]: HomeCategoryModal,
     [MODAL_TYPES.CreateCategoryModal]: CreateCategoryModal,
     [MODAL_TYPES.OneButtonModal]: OneButtonModal,
     [MODAL_TYPES.TwoButtonModal]: TwoButtonModal,
   };

   const GlobalModal = () => {
     const [modal] = useRecoilState(modalState);
     if (!modal?.modalType) return null;

     const ModalComponent = MODAL_COMPONENTS[modal.modalType];
     return ModalComponent ? <ModalComponent {...modal?.modalProps} /> : null;
   };

   export default GlobalModal;
   ```

3. 소켓 연결

- 백엔드쪽에서 `STOMP`를 이용해서 소켓을 구현했습니다. 프론트에서는 `stomp/stompjs`를 이용해서 소켓 연결을 시도했으나 연결이 되지 않았습니다. 같은 코드로 웹에서 테스트해보니 웹쪽에서는 문제없이 연결이 되었습니다.

  [stomp-js](https://stomp-js.github.io/workaround/stompjs/rx-stomp/react-native-additional-notes.html)

- `stomp-js` 공식문서에서 문제점을 찾을 수 있었습니다. 디버그 모드에서는 실제 브라우저에서 실행되어 TextEncoder/TextDecoder가 사용 가능하지만 프로덕션 모드에서는 TextEncoder/TextDecoder가 사용 불가능하기 때문에 동작하지 않는다고 합니다.
  `text-encoding`을 설치하고 import하는 것으로 간단하게 해결할 수 있었습니다.

  ```javascript
  npm install text-encoding

  import * as encoding from 'text-encoding';
  ```

4. 플레이 스토어 배포
   <img src="/google_reject.png" />

- 플레이 스토어의 배포 과정중 약 7번의 reject를 당했습니다.
- 배포를 처음 해보기도 하지만 앱의 환경에 대해 무지하다 보니 아무리 거절 사유를 찾아봐도 뭐를 뜻하는지 몰랐습니다. 특히나
  아래와 같은 거절 사유를 받았는데 제 `AndroidManifest.xml`에는 MANAGE_EXTERNAL_STORAGE 권한을 요청한 코드를 찾지 못했습니다.

  ```markdown
  기능이 이 권한을 사용하지 않도록 앱을 업데이트하세요.
  앱에서 MANAGE_EXTERNAL_STORAGE 권한 액세스가 필요하지 않은 경우,
  정책 검토 요구사항을 충족하려면 앱의 매니페스트에서 이 권한을 삭제해야 합니다.
  ```

- 며칠을 찾아본 결과 저는 이미지 업로드를 위해 `@baronha/react-native-multiple-image-picker`를 사용하고 있었습니다. 이 라이브러리 안에 `MANAGE_EXTERNAL_STORAGE` 권한을 요청하고 있었고 이 것을 제거하고 다시 심사를 받아본 결과 승인을 받을 수 있었습니다.

### 아쉬웠던 점

- 데이터베이스로 `mongodb`와 `mysql`을 사용했습니다. 그 중에 채팅방과 채팅과 관련된 내용만 `mongodb`에 저장하고 그 외 모든 정보는 mysql에 저장했습니다.

- 회원정보를 수정하면 `mysql`의 유저정보가 업데이트 되고 `mongodb`에 있는 채팅과 관련된 유저들의 정보는 따로 업데이트가 이루어지지 않았습니다. 데이터의 불일치가 있었기 때문에 프론트에서는 채팅에서 회원과 관련된 정보를 제거했습니다. 기간이 조금 더 있었다면 해결 할 수 있는 문제라 아쉬웠습니다.
