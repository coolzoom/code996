<template>
  <div class="footer">
    <div class="wrapper">
      <p>
        切换镜像节点：
        <template v-for="item in mirrorList">
          <a :href="item.url">{{ item.label }}</a>
          <span>&nbsp;</span>
        </template>
      </p>
      <p>
        自豪的采用
        <a target="_blank" href="https://unlicense.org/">Unlicense</a>
        协议 | 源码：
        <a target="_blank" href="https://github.com/hellodigua/code996">Github</a>
      </p>
      <p>
        Inspiration comes from ❤️
        <a target="_blank" href="https://996.icu/">996.icu</a>
      </p>
    </div>
  </div>
</template>
<script setup lang="ts">
let url = window.location.href
let hash = window.location.hash

const mirrorList = [
  {
    host: 'github.io',
    url: `https://hellodigua.github.io/code996/${hash}`,
    label: 'GitHub',
  },
  {
    host: 'gitee.io/',
    url: `https://hellodigua.gitee.io/code996/${hash}`,
    label: 'Gitee',
  },
  {
    host: 'code996.vercel.app',
    url: `https://code996.vercel.app/${hash}`,
    label: 'Vercel',
  },
].filter((item) => !url.includes(item.host))
</script>
