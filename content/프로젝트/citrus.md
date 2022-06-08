---
emoji: 😂
title: 당근마켓 클론
date: '2022-04-01 00:00:00'
author: sangzun
tags: 자바스크립트,react
categories: 프로젝트
---

리액트를 이용하여 간단히 당근마켓 클론코딩을 진행했습니다.

## 구현사항

[구현사항](https://silver-lumber-2a3.notion.site/8a9f27e26ce042d4b68f9ec86ce67cc9)

[Github](https://github.com/sangzun-han/citrus-market)

## 정리

1. components 폴더 안에 모든 컴포넌트가 존재하다보니 컴포넌트들을 찾는 일이 번거로워졌다. 이후에 componets, pages 폴더로 나누긴 했지만 조금 더 세세하게 컴포넌트들을 분리할 필요성을 느꼈다.

### 변경 후

```
├── app.css
├── app.jsx
├── components
│   ├── 404
│   │   ├── notFound.jsx
│   │   └── notFound.module.css
│   ├── chatList
│   │   ├── chatList.jsx
│   │   └── chatList.module.css
│   ├── deleteModal
│   │   ├── deleteModal.jsx
│   │   └── deleteModal.module.css
│   ├── editor
│   │   ├── editor.jsx
│   │   ├── editorHeader.jsx
│   │   ├── editorHeader.module.css
│   │   ├── editorInfo.jsx
│   │   ├── editorInfo.module.css
│   │   ├── image.jsx
│   │   ├── image.module.css
│   │   ├── moreImage.jsx
│   │   └── moreImage.module.css
│   ├── follower
│   │   ├── follower.jsx
│   │   ├── followerHeader.jsx
│   │   ├── followerHeader.module.css
│   │   ├── followerInfo.jsx
│   │   └── followerInfo.module.css
│   ├── following
│   │   ├── following.jsx
│   │   ├── followingInfo.jsx
│   │   └── followingInfo.module.css
│   ├── header
│   │   ├── header.jsx
│   │   └── header.module.css
│   ├── home
│   │   ├── feed.jsx
│   │   ├── feedInfo.jsx
│   │   ├── feedInfo.module.css
│   │   ├── home.jsx
│   │   └── home.module.css
│   ├── login
│   │   ├── login.jsx
│   │   └── login.module.css
│   ├── loginEmail
│   │   ├── loginEmail.jsx
│   │   └── loginEmail.module.css
│   ├── logoutModal
│   │   ├── logoutModal.jsx
│   │   └── logoutModal.module.css
│   ├── nav
│   │   ├── nav.jsx
│   │   └── nav.module.css
│   ├── postDetail
│   │   ├── comment.jsx
│   │   ├── comment.module.css
│   │   ├── commentInfo.jsx
│   │   ├── commentInfo.module.css
│   │   ├── commentInput.jsx
│   │   ├── commentInput.module.css
│   │   ├── postDetail.jsx
│   │   ├── postDetailInfo.jsx
│   │   └── postDetailInfo.module.css
│   ├── postModal
│   │   ├── postModal.jsx
│   │   └── postModal.module.css
│   ├── productUpload
│   │   ├── productHeader.jsx
│   │   ├── productHeader.module.css
│   │   ├── productUpload.jsx
│   │   ├── productUploadInfo.jsx
│   │   └── productUploadInfo.module.css
│   ├── profile
│   │   ├── album.jsx
│   │   ├── album.module.css
│   │   ├── albumInfo.jsx
│   │   ├── albumInfo.module.css
│   │   ├── postArea.jsx
│   │   ├── postArea.module.css
│   │   ├── postAreaInfo.jsx
│   │   ├── postAreaInfo.module.css
│   │   ├── postAreaTop.jsx
│   │   ├── postAreaTop.module.css
│   │   ├── product.jsx
│   │   ├── product.module.css
│   │   ├── productInfo.jsx
│   │   ├── productInfo.module.css
│   │   ├── profile.jsx
│   │   ├── profile.module.css
│   │   ├── profileHeader.jsx
│   │   ├── profileHeader.module.css
│   │   ├── profileInfo.jsx
│   │   └── profileInfo.module.css
│   ├── profileUpdate
│   │   ├── profileUpdate.jsx
│   │   ├── profileUpdate.module.css
│   │   ├── profileUpdateHeader.jsx
│   │   ├── profileUpdateHeader.module.css
│   │   ├── profileUpdateInfo.jsx
│   │   └── profileUpdateInfo.module.css
│   ├── serach
│   │   ├── search.jsx
│   │   ├── search.module.css
│   │   ├── searchBody.jsx
│   │   ├── searchBody.module.css
│   │   ├── searchHeader.jsx
│   │   ├── searchHeader.module.css
│   │   └── searchResult.jsx
│   ├── settingModal
│   │   ├── settingModal.jsx
│   │   └── settingModal.module.css
│   ├── signup
│   │   ├── membership.jsx
│   │   ├── membership.module.css
│   │   ├── profile.jsx
│   │   ├── profile.module.css
│   │   └── signup.jsx
│   ├── splash
│   │   ├── splash.jsx
│   │   └── splash.module.css
│   └── userProfile
│       ├── album.jsx
│       ├── album.module.css
│       ├── albumInfo.jsx
│       ├── albumInfo.module.css
│       ├── postArea.jsx
│       ├── postArea.module.css
│       ├── postAreaInfo.jsx
│       ├── postAreaInfo.module.css
│       ├── postAreaTop.jsx
│       ├── postAreaTop.module.css
│       ├── product.jsx
│       ├── product.module.css
│       ├── productInfo.jsx
│       ├── productInfo.module.css
│       ├── userProfile.jsx
│       ├── userProfile.module.css
│       ├── userProfileInfo.jsx
│       └── userProfileInfo.module.css
├── constants
│   └── index.js
├── index.css
├── index.js
├── pages
│   ├── chat.jsx
│   ├── feed.jsx
│   ├── followers.jsx
│   ├── followings.jsx
│   ├── index.jsx
│   ├── login.jsx
│   ├── otherProfile.jsx
│   ├── post.jsx
│   ├── product.jsx
│   ├── profiles.jsx
│   ├── profilesUpdate.jsx
│   ├── register.jsx
│   ├── search.jsx
│   └── writing.jsx
└── service
    ├── cookie.js
    └── fetcher.js

```

2. state관리에서 번번한 오류가 계속해서 발생하고 현재의 값 확인이 복잡해졌다. 중간에 redux를 배워서 넣을까 라는 생각을 했지만 거의 완성단계에 와서 넣으면 리팩토링하는데 더 시간을 쏟을거 같아서 그대로 진행했다. redux가 됐든 mobx가 됐든 전역상태관리 라이브러리를 배워두도록 해야겠다.

3. Follow,Following 목록에서 팔로우,팔로잉을 취소할 경우 팔로우 리스트, 팔로잉 리스트의 값이 변해야 하지만 변하지 않는다. useEffect를 이용해서 해결할 수 있을 줄 알았지만 아직 해결하지 못했다.

![follow](/follow.gif)

4. 게시글을 작성할 때 그 글의 길이가 얼마나 될지 모르기 때문에 textarea의 height를 자동으로 높이가 변경되는 방법을 사용했다. 처음엔 css를 조절을 시도했지만 실패해서 useRef를 이용해서 직접 dom에 접근하여 변경해주었다.

```
const handleResizeHeight = useCallback(() => {
    if (textAreaRef.current.value === null) return;
    textAreaRef.current.style.height = "38px";
    textAreaRef.current.style.height = textAreaRef.current.scrollHeight + "px";

    if (textAreaRef.current.scrollHeight > 400) {
      textAreaRef.current.style.height = 400 + "px";
      textAreaRef.current.style.overflowY = "auto";
    }
    checkValid();
}, []);
```

5. map을 사용할때 index값을 key로 사용하면 안되는 이유 -> 데이터가 추가,삭제,정렬될 경우 배열이 새로 바뀌게 되면서 컴포넌트가 재렌더링 되고 이때 index값을 다시 매핑하게된다. 만약 가장 앞에 데이터를 추가한다면 기존에 index 0번에 있던 값이 추가된 데이터가 0번째 요소가 된다.

---
