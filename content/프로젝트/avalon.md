---
emoji: 😂
title: 아발론
date: '2023-05-24 00:00:00'
author: sangzun
tags: 타입스크립트,react
categories: 프로젝트
---

react, typescript vite, redux-toolkit을 이용해서 보드게임 아발론을 웹으로 구현했습니다.

## 리팩토링 이유

- 이전에 진행한 아발론 프로젝트는 발표를 위해 정말 급하게 만들었고 그러다보니 특정 상황에 대해서는 에러도 많고, 렌더링도 너무 많이 일어나는 일이 발생했습니다. 프로젝트의 아쉬움을 많이 느껴 프로젝트를 진행한 모두가 다시 모여 2주간 리팩토링을 진행했습니다.

- 이전에는 게임 데이터 전체를 보내고 받았기 때문에 예외처리에 대한 부분이 너무 많았고 그에 따라 관리해야 할 상태가 많았습니다. 또 의도하지 않게 동작하는 부분이 많았습니다.
    ```javascript
    updateGameState: (state, action) => {
      const {
        status,
        roomId,
        playerList,
        round,
        voteRound,
        prevRound,
        agreeDisagree,
        guilty,
        notGuilty,
        script,
      } = action.payload;
      state.status = status;
      state.roomId = roomId;
      state.playerList = playerList;
      state.round = round;
      state.voteRound = voteRound;
      state.prevRound = prevRound;
      state.agreeDisagree = agreeDisagree;
      state.guilty = guilty;
      state.notGuilty = notGuilty;
      state.script = script;
    },
    ```
- `Context API`를 이용해서 모달을 전역으로 관리했지만 급하게 프로젝트를 마무리 하는 과정에서 `Context API`는 사용하지 않고 컴포넌트 안에서 관리하게 되면서 누구도 알아보기 힘든 코드로 변했습니다.
    ```javascript
     if (type === "under") {
      // 유무죄 투표창 열기
      setModalOpen({
        under: true,
        select: false,
        role: false,
        agree: false,
        guilty: false,
        result: false,
      });
    } 
    ```

- 프로젝트 과정중 데이터를 받아올 때 `undefined`와 관련된 에러가 계속해서 발생했습니다. 당시에는 아래와 같이 모두 예외처리를 하면서 진행을 해나갔고 좋지 않은 코드라 생각해 `typescript`를 도입하고 `optional chaining`을 이용하면 더 간결한 코드로 작성할 수 있을것 같았습니다.

    ```javascript
    {gameStatus.playerList !== undefined &&
            gameStatus.playerList.map((player) => (
                <CardBack
                key={player.nickname}
                player={player}
                selectPeople={selectPeople}
                onClick={handleSelectChange}
                />
            ))}
    ```

## 리팩토링 과정