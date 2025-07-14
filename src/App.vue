<template>
  <div id="app">
    <!-- 视频背景 -->
    <div class="banner">
      <video autoplay muted loop>
        <source src="<%= BASE_URL %>video/Murasame2kv86.mp4" type="video/mp4" />
        您的浏览器不支持 video 标签
      </video>
    </div>

    <!-- 前景内容 -->
    <div class="content">
      <h1>This is title</h1>
      <p>
        She is an easygoing and kind woman with bright eyes and a lovely smile.
        Although she is often busy, I still feel that I am taken good care of by her.
        It's a great pleasure to chat with her when I get into troubles.
        She always encourages me not to give up and tries to cheer me up by coming up with good solutions.
        In addition, I am fascinated by her cooking and writing.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
/* 1. 全局重置 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
html, body {
  height: 100%;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}

/* 2. 视频背景：始终铺满视口 */
.banner {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  z-index: -1;
}
.banner video {
  width: 100%;
  height: 100%;
  object-fit: cover;     /* 保证视频填满屏幕且不变形 */
}

/* 3. 前景内容：弹性布局 + 自动折行 */
.content {
  position: relative;
  max-width: 90vw;       /* 最大宽度随屏宽变化 */
  margin: 0 auto;
  padding: 10vh 5vw;     /* 上下留白随屏高变化 */
  color: #fff;
  text-shadow: 0 0 4px rgba(0, 0, 0, 0.6);
  line-height: 1.6;
}

/* 4. 文字大小自适应：使用 clamp() */
h1 {
  font-size: clamp(1.5rem, 5vw, 3rem);   /* 手机 24px 起，桌面最大 48px */
  margin-bottom: 1rem;
}
p {
  font-size: clamp(1rem, 3vw, 1.25rem);
}

/* 5. 超小屏微调（可选） */
@media (max-width: 480px) {
  .content {
    padding: 8vh 4vw;
  }
}
</style>