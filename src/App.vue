<script setup>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from '@/components/install-coms/HelloWorld.vue'
import Main from '@/components/Main.vue'
import SideNav from '@/components/SideNav.vue'
import TopNav from '@/components/TopNav.vue'
</script>

<template>
  <!-- @TODO: responsiveness -->
  <div class="flex flex-row">
    <SideNav class="w-auto" />
    <div class="flex flex-column w-full" style="margin-left: 117px;">
      <TopNav style="box-shadow: 0px 15px 10px -15px #111;" />
      <Main style="padding-top: 64px;" />
    </div>
  </div>
</template>