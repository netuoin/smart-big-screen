<template>
  <div class="module">
    <div
      class="item"
      v-for="(item, index) in lists"
      :key="index"
      :style="{
        '--color': item.color
      }"
    >
      <div class="icon" v-html="item.svg"></div>
      <div class="info">
        <div class="value">{{ item.value }}</div>
        <div class="title">{{ item.title }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
const lists = [
  {
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M6 20c1.1 0 2-.9 2-2v-7c0-1.1-.9-2-2-2s-2 .9-2 2v7c0 1.1.9 2 2 2m10-5v3c0 1.1.9 2 2 2s2-.9 2-2v-3c0-1.1-.9-2-2-2s-2 .9-2 2m-4 5c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2s-2 .9-2 2v12c0 1.1.9 2 2 2"/></svg>',
    value: 2311,
    title: '总数',
    color: '#0ac472'
  },
  {
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M12 5.99L19.53 19H4.47zM2.74 18c-.77 1.33.19 3 1.73 3h15.06c1.54 0 2.5-1.67 1.73-3L13.73 4.99c-.77-1.33-2.69-1.33-3.46 0zM11 11v2c0 .55.45 1 1 1s1-.45 1-1v-2c0-.55-.45-1-1-1s-1 .45-1 1m0 5h2v2h-2z"/></svg>',
    value: 123,
    title: 'AI 告警',
    color: '#f8a035'
  },
  {
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M17.59 3.41L15 6V5c0-1.1-.9-2-2-2H9C6.24 3 4 5.24 4 8h5v3h6V8l2.59 2.59c.26.26.62.41 1 .41h.01c.77 0 1.4-.63 1.4-1.41V4.41C20 3.63 19.37 3 18.59 3h-.01c-.37 0-.73.15-.99.41M9 13v7c0 .55.45 1 1 1h4c.55 0 1-.45 1-1v-7z"/></svg>',
    value: 1143,
    title: '人工广播',
    color: '#02fdff'
  },
  {
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M12 9c-3.15 0-6 2.41-6 6.15c0 2.35 1.78 5.11 5.34 8.27c.37.33.95.33 1.33 0C16.22 20.25 18 17.5 18 15.15C18 11.41 15.15 9 12 9m0 7.5c-.83 0-1.5-.67-1.5-1.5s.67-1.5 1.5-1.5s1.5.67 1.5 1.5s-.67 1.5-1.5 1.5m4.18-9.68c-.35.35-.89.38-1.3.09C14.07 6.34 13.07 6 12 6s-2.07.34-2.88.91c-.41.28-.95.26-1.3-.09c-.43-.43-.39-1.15.09-1.5C9.06 4.49 10.48 4 12 4s2.94.49 4.09 1.32c.49.35.52 1.07.09 1.5M4.97 3.97c-.42-.43-.38-1.12.08-1.5C6.95.93 9.37 0 12.01 0c2.64 0 5.06.93 6.95 2.48c.46.38.5 1.07.08 1.49c-.36.36-.93.39-1.32.07a9.027 9.027 0 0 0-11.43 0c-.39.32-.96.28-1.32-.07"/></svg>',
    value: 112,
    title: '应急广播',
    color: '#ff6b4e'
  },
  {
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><path fill="currentColor" d="M14.17 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V9.83c0-.53-.21-1.04-.59-1.41l-4.83-4.83c-.37-.38-.88-.59-1.41-.59M8 15h8c.55 0 1 .45 1 1s-.45 1-1 1H8c-.55 0-1-.45-1-1s.45-1 1-1m0-4h8c.55 0 1 .45 1 1s-.45 1-1 1H8c-.55 0-1-.45-1-1s.45-1 1-1m0-4h5c.55 0 1 .45 1 1s-.45 1-1 1H8c-.55 0-1-.45-1-1s.45-1 1-1"/></svg>',
    value: 444,
    title: '文本广播',
    color: '#fca235'
  },
  {
    svg: '<svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24"><circle cx="10" cy="9" r="4" fill="currentColor"/><path fill="currentColor" d="M16.39 15.56C14.71 14.7 12.53 14 10 14s-4.71.7-6.39 1.56A2.97 2.97 0 0 0 2 18.22V19c0 1.1.9 2 2 2h12c1.1 0 2-.9 2-2v-.78c0-1.12-.61-2.15-1.61-2.66m4.72-13.71a.997.997 0 0 0-1.5-.09c-.35.35-.39.91-.09 1.3c1.17 1.5 2.64 5.23 0 8.61c-.3.39-.26.95.09 1.3c.43.43 1.13.38 1.5-.09c1.5-1.93 3.35-6.72 0-11.03m-2.8 2.99a1.01 1.01 0 0 0-1.58-.21c-.33.33-.36.84-.13 1.25c.25.44.74 1.69-.01 2.99c-.23.4-.19.9.14 1.22c.47.47 1.25.35 1.58-.22c1.16-1.99.58-4.02 0-5.03"/></svg>',
    value: 553,
    title: '音频广播',
    color: '#22c6c8'
  }
]
</script>

<style lang="scss" scoped>
.module {
  height: 100%;
  padding: 20px;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: repeat(3, 1fr);
  gap: 20px;
  .item {
    display: flex;
    align-items: center;
    gap: 20px;
    .icon {
      width: 60px;
      height: 60px;
      border: 1px solid var(--color);
      display: flex;
      justify-content: center;
      align-items: center;
      :deep(svg) {
        width: 36px;
        height: 36px;
        color: var(--color);
      }
    }
    .info {
      .value {
        font-size: 24px;
        margin-bottom: 6px;
        color: var(--color);
      }
      .title {
        font-size: 16px;
        color: #fff;
      }
    }
  }
}
</style>
