---
emoji: 😂
title: 인스타그램 클론
date: '2022-04-01 00:00:00'
author: sangzun
tags: html,css,media query
categories: 프로젝트
---

```Html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="main.css">
    <title>Document</title>
</head>
<body>
    <section id="container">
        <header id="header">
            <section class="inner">
                <h1 class="logo">
                    <a href="main.html">
                        <div class="sprite_insta_icon"></div>
                        <div class="sprite_write_logo"></div>
                    </a>
                </h1>

                <div class="search_box">
                    <input type="text" placeholder="검색" id="search-field">
                    <div class="fake_field">
                        <span class="sprite_small_search_icon"></span>
                        <span>검색</span>
                    </div>
                </div>

                <div class="right_icons">
                    <div class="sprite_camera_icon"></div>
                    <div class="sprite_compass_icon"></div>
                    <div class="sprite_heart_icon_outline"></div>
                    <div class="sprite_user_icon_outline"></div>
                </div>
            </section>
        </header>
        <div class="hidden_menu">
            <div class="scroll_inner">
                <div class="user">
                    <div class="thumb_img"><img src="imgs/img06.png" alt="img"></div>
                    <div class="id">닉네임</div>
                </div>

                <div class="user">
                    <div class="thumb_img"><img src="imgs/img06.png" alt="img"></div>
                    <div class="id">닉네임</div>
                </div>

                <div class="user">
                    <div class="thumb_img"><img src="imgs/img06.png" alt="img"></div>
                    <div class="id">닉네임</div>
                </div>

                <div class="user">
                    <div class="thumb_img"><img src="imgs/img06.png" alt="img"></div>
                    <div class="id">닉네임</div>
                </div>
            </div>
        </div>
        <section id="main_container">
            <div class="inner">
                <div class="contents_box">
                    <article class="contents">
                        <header class="top">
                            <div class="user_container">
                                <div class="profile_img">
                                    <img src="imgs/img02.jpg" alt="">
                                </div>
                                <div class="user_name">
                                    <div class="nick_name m_tet">닉네임</div>
                                    <div class="country s_text">서울</div>
                                </div>
                            </div>
                            <div class="sprite_more_icon"></div>
                        </header>
                        <div class="img_section">
                            <div class="trans_inner">
                                <img src="imgs/img02.jpg" alt="">
                            </div>
                        </div>
                        <div class="bottom_icon">
                            <div class="left_icons">
                                <div class="herat_btn">
                                    <div class="sprite_heart_icon_outline"></div>
                                </div>
                                <div class="sprite_bubble_icon"></div>
                                <div class="sprite_share_icon"></div>
                            </div>
                            <div class="right_icons">
                                <div class="sprite_bookmark_outline"></div>
                            </div>
                        </div>
                        <div class="likes m_text">
                            좋아요
                            <span class="count">1328</span>
                            개
                        </div>
                        <div class="comment_container">
                            <div class="comment">
                                <div class="nick_name m_text">닉네임</div>
                                <div>댓글@@@</div>
                            </div>
                            <div class="small_heart">
                                <div class="sprite_small_heart_icon_outline"></div>
                            </div>
                        </div>
                        <div class="timer">1시간 전</div>
                        <div class="comment_field">
                            <input type="text" placeholder="댓글달기..">
                            <div class="upload_btn">게시</div>
                        </div>
                    </article>
                <div class="side_box">
                    <div class="user_profile">
                        <div class="profile_thumb">
                            <img src="imgs/img02.jpg" alt="">
                        </div>
                        <div class="detail">
                            <div class="id m_text">아이디</div>
                            <div class="ko_name">한글이름</div>
                        </div>
                    </div>
                    <article class="story">
                        <header class="story_header">
                            <div>스토리</div>
                            <div class="more">모두 보기</div>
                        </header>
                        <div class="scroll_inner">
                            <div class="thumb_user">
                                <div class="profile_thumb">
                                    <img src="imgs/img02.jpg" alt="">
                                </div>
                                <div class="detail">
                                    <div class="id">닉네임</div>
                                    <div class="time">1시간 전</div>
                                </div>
                            </div>
                            <div class="thumb_user">
                                <div class="profile_thumb">
                                    <img src="imgs/img02.jpg" alt="">
                                </div>
                                <div class="detail">
                                    <div class="id">닉네임</div>
                                    <div class="time">1시간 전</div>
                                </div>
                            </div>
                            <div class="thumb_user">
                                <div class="profile_thumb">
                                    <img src="imgs/img02.jpg" alt="">
                                </div>
                                <div class="detail">
                                    <div class="id">닉네임</div>
                                    <div class="time">1시간 전</div>
                                </div>
                            </div>
                            <div class="thumb_user">
                                <div class="profile_thumb">
                                    <img src="imgs/img02.jpg" alt="">
                                </div>
                                <div class="detail">
                                    <div class="id">닉네임</div>
                                    <div class="time">1시간 전</div>
                                </div>
                            </div>
                        </div>
                    </article>
                    <article class="recommend">
                        <header class="reco_header">
                            <div>회원님을 위한 추천</div>
                            <div class="more">모두 보기</div>
                        </header>
                        <div class="thumb_user">
                            <div class="profile_thumb">
                                <img src="imgs/img02.jpg" alt="">
                            </div>
                            <div class="detail">
                                <div class="id">닉네임</div>
                                <div class="time">1시간 전</div>
                            </div>
                        </div>
                        <div class="thumb_user">
                            <div class="profile_thumb">
                                <img src="imgs/img02.jpg" alt="">
                            </div>
                            <div class="detail">
                                <div class="id">닉네임</div>
                                <div class="time">1시간 전</div>
                            </div>
                        </div>

                    </article>
                </div>
                </div>
            </div>
        </section>
</body>
</html>
```

```Css
.sprite_insta_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -53px -235px;
  width: 22px;
  height: 22px;
}

.sprite_write_logo {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -94px -72px;
  width: 103px;
  height: 29px;
}

.sprite_compass_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -130px -286px;
  width: 23px;
  height: 23px;
}

.sprite_user_icon_outline {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -272px -182px;
  width: 22px;
  height: 24px;
}

.sprite_heart_icon_outline {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -52px -261px;
  width: 24px;
  height: 22px;
}

.sprite_small_search_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -337px -246px;
  width: 10px;
  height: 10px;
}

.sprite_more_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -301px -218px;
  width: 15px;
  height: 3px;
}

.sprite_bubble_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -239px -202px;
  width: 24px;
  height: 24px;
}

.sprite_share_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -324px -52px;
  width: 21px;
  height: 24px;
}

.sprite_bookmark_outline {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -237px -286px;
  width: 19px;
  height: 24px;
}
.sprite_bookmark_outline.on {
  background: url("imgs/background01.png") no-repeat -159px -286px;
  width: 19px;
  height: 24px;
}

.sprite_small_heart_icon_outline {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -323px -274px;
  width: 12px;
  height: 11px;
}

.sprite_camera_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -271px -104px;
  width: 24px;
  height: 22px;
}

.sprite_insta_big_logo {
  display: inline-block;
  background: url("imgs/background02.png") no-repeat -98px -150px;
  width: 175px;
  height: 51px;
}

.sprite_plus_icon {
  display: inline-block;
  background: url("imgs/background01.png") no-repeat -187px -202px;
  width: 23px;
  height: 23px;
}
.m_text {
  font-size: 14px;
  font-weight: bold;
}
.s_text {
  font-size: 12px;
}
body {
  background: #fafafa;
}
#header {
  width: 100%;
  position: absolute;
  left: 0;
  top: 0;
  z-index: 999;
  background: white;
  border-bottom: 1px solid rgba(0, 0, 0, 0.09);
}

#header .inner {
  width: 975px;
  height: 77px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#header .inner a {
  color: transparent;
}
#header .inner div {
  vertical-align: middle;
}
#header .inner .logo div:nth-child(2) {
  transform: translateY(2px);
}
#header .inner .logo .sprite_insta_icon {
  margin-right: 30px;
  position: relative;
}

#header .inner .logo .sprite_insta_icon::after {
  content: "";
  width: 1px;
  height: 28px;
  background: black;
  position: absolute;
  right: -15px;
  top: -4px;
}
#search-field {
  width: 185px;
  height: 28px;
  background: #fafafa;
  border: 1px solid #dbdbdb;
  border-radius: 3px;
  padding: 3px 30px;
  color: #999;
  font-weight: 400;
  text-align: left;
  font-size: 14px;
  outline: none;
}

#header .search_box {
  position: relative;
}

#header .search_box .fake_field {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  pointer-events: none;
}

#search-field::placeholder {
  font-size: 0;
}

#search-field:focus::placeholder {
  font-size: 14px;
}

#search-field:focus ~ .fake_field > span:nth-child(1) {
  transform: translateX(-105px);
}
#search-field:focus ~ .fake_field > span:nth-child(2) {
  display: none;
}

#header .right_icons {
  width: 132px;
  display: flex;
  justify-content: space-between;
}

#main_container {
  padding-top: 130px;
  display: flex;
  justify-content: center;
}

#main_container .inner {
  width: 935px;
  /* height:500px; */
  position: relative;
}

.contents_box {
}

.contents {
  max-width: 614px;
  /* height: 500px; */
  border: 1px solid rgba(0, 0, 0, 0.09);
  border-radius: 3px;
  margin-bottom: 60px;
  background: white;
}
.contents .top {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}

.contents .top .profile_img {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  overflow: hidden;
}

.contents .top .profile_img img {
  width: 100%;
}

.contents .top .user_container {
  display: flex;
}
.contents .img_section {
  overflow: hidden;
}

.contents .img_section img {
  width: 100%;
}

.contents .bottom_icon {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
}
.contents .left_icons {
  display: flex;
}
.contents .bottom_icon .left_icons > div {
  margin-right: 10px;
  cursor: pointer;
}
.contents .bottom_icon .right_icons > div {
  cursor: pointer;
}
.contents .likes {
  padding: 5px 20px;
  color: #262626;
}
.contents .comment_container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 5px 20px;
}
.contents .comment_container .comment {
  display: flex;
  font-size: 14px;
}
.contents .comment_container .comment .nick_name {
  margin-right: 10px;
}

.contents .timer {
  font-size: 10px;
  letter-spacing: 0.2px;
  color: #999;
  border-bottom: 1px solid rgba(0, 0, 0, 0.09);
  padding: 10px 20px;
}
.contents .comment_field {
  min-height: 56px;
  padding: 0px 20px;
  position: relative;
}
.contents .comment_field input {
  width: 100%;
  height: 56px;
  border: none;
  outline: none;
  background: transparent;
}
.contents .comment_field input:focus ~ .upload_ btn {
  pointer-events: initial;
  opacity: 1;
}

.contents .comment_field .upload_btn {
  color: #3897f0;
  position: absolute;
  right: 20px;
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
  pointer-events: none;
  opacity: 0.5;
}
.side_box {
  width: 293px;
  /* height: 300px; */
  position: absolute;
  right: 0;
  top: 0;
}
.side_box .profile_thumb {
  width: 50px;
  /* height:50px; */
  border-radius: 50%;
  overflow: hidden;
  margin-right: 10px;
}
.side_box .profile_thumb img {
  width: 100%;
}

.side_box .user_profile {
  display: flex;
  align-items: center;
  font-size: 14px;
  color: #262626;
}

.side_box .detail .ko_name {
  font-size: 12px;
  color: #999;
}
.side_box > article {
  border: 1px solid rgba(0, 0, 0, 0.09);
  border-radius: 3px;
  margin-bottom: 20px;
  width: 291px;
  font-size: 14px;
  color: #262626;
  font-weight: bold;
  background: white;
}
.side_box > article > header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 15px 20px;
  color: #999;
}
.side_box > article > header .more {
  font-size: 12px;
  color: #262626;
  cursor: pointer;
}
.thumb_user {
  display: flex;
  align-items: center;
  padding: 10px 20px;
  overflow: hidden;
}
.thumb_user .profile_thumb {
  width: 34px;
  height: 34px;
}

.thumb_user .time {
  font-size: 10px;
  letter-spacing: 0.2px;
  color: #999;
}
.side_box .detail .id {
  margin-bottom: 5px;
}
.side_box .scroll_inner {
  height: 182px;
  overflow: auto;
}

.hidden_menu .thumb_img {
  width: 56px;
  height: 56px;
  border-radius: 50%;
  overflow: hidden;
}

.hidden_menu .thumb_img img {
  width: 100%;
}

.hidden_menu {
  display: none;
  width: 600px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  top: 100px;
  overflow: hidden;
  border: 1px solid rgba(0, 0, 0, 0.09);
}

.hidden_menu .scroll_inner {
  height: 100px;
  width: auto;
  overflow-x: auto;
  overflow-y: hidden;
  display: flex;
  align-items: center;
  padding: 0 10px;
}

.hidden_menu .scroll_inner .user {
  width: 80px;
  height: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-contnet: space-between;
  margin-left: 15px;
}

.hidden_menu .scroll_inner .user .id {
  font-size: 12px;
  color: #262626;
}

@media screen and (max-width: 1000px) {
  #header .inner {
    width: 97.5%;
  }

  #main_container {
    padding-top: 220px;
  }
  #main_container .inner {
    width: 93.5%;
  }

  .contents {
    max-width: 614px;
    border: 1px solid rgba(0, 0, 0, 0.09);
    border-radius: 3px;
    margin-bottom: 60px;
    background: white;
  }

  .contents_box {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .side_box {
    display: none;
  }

  .hidden_menu {
    display: block;
  }
}

@media screen and (max-width: 650px) {
  #header .search_box {
    display: none;
  }
}

```
