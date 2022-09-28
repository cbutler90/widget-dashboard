<template>
  <div class="flex flex-row">
    <SideNav />
    <div class="main-content-wrapper flex flex-column w-full">
      <TopNav style="box-shadow: 0px 15px 10px -15px #111" />
      <TopNavMobile style="box-shadow: 0px 15px 10px -15px #111" />
      <Main style="padding-top: 64px" />
    </div>
  </div>
</template>

<script>
import Main from '@/components/Main.vue';
import SideNav from '@/components/SideNav.vue';
import TopNav from '@/components/TopNav.vue';
import TopNavMobile from '@/components/TopNavMobile.vue';

export default {
  components: {
    Main,
    SideNav,
    TopNav,
    TopNavMobile,
  }
};
</script>

<style lang="scss">
@media (min-width: 992px) {
  .main-content-wrapper {
    margin-left: 117px;
  }
}
</style>
