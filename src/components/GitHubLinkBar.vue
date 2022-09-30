<template>
  <div id="github-link-bar" class="p-3">
    <span class="casper">See GitHub: </span>
    <a href="https://github.com/cbutler90/widget-dashboard" class="capri" target="_blank">https://github.com/cbutler90/widget-dashboard</a>
  </div>
</template>

<script>
export default {
  name: 'GitHubLinkBar'
}
</script>

<style>
#github-link-bar {
  background: rgba(0, 0, 0, 0.75);
  position: fixed;
  bottom: 0;
  z-index: 99;
  width: 100%;
  text-align: center;
}
</style>