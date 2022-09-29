<template>
  <!-- @TODO: 
          add dropdown notifications
          change color on badge
  -->
  <header
    class="flex lg:hidden flex-row align-items-center p-3 raisin-black-bg fixed z-5 w-full"
    style="height: 64px"
  >
    <div
      class="topnav-wrapper w-full flex justify-content-between align-items-center px-2"
    >
      <div
        class="menu-toggle-wrapper"
        title="Menu"
        aria-label="Menu"
        @click="toggleNav()"
      >
        <i class="pi pi-bars casper text-xl" />
      </div>
      <div
        class="logo-wrapper flex justify-content-center align-items-center col-4"
      >
        <img
          alt="Vue logo"
          class="logo cursor-pointer"
          src="@/assets/logo.svg"
          width="20"
          height="20"
        />
      </div>
      <!-- add menu for this -->
      <div class="nav-icon cursor-pointer" @click="toggleMenu()">
        <account-circle-icon
          class="casper"
          title="Profile"
          aria-label="Profile"
        />
      </div>
    </div>
  </header>
  <div class="fixed">
    <div class="w-screen h-screen absolute flex lg:hidden" @click="away()"></div>
  </div>
  <SideNavMobile v-if="showNav" />
  <ProfileMenuMobile v-if="showMenu" />
</template>

<script>
import ProfileMenuMobile from './ProfileMenuMobile.vue';
import SideNavMobile from './SideNavMobile.vue';

export default {
  components: {
    ProfileMenuMobile,
    SideNavMobile,
  },
  data() {
    return {
      showNav: false,
      showMenu: false,
    };
  },
  methods: {
    toggleNav() {
      this.showMenu = false;
      this.showNav = !this.showNav;
    },
    toggleMenu() {
      this.showNav = false;
      this.showMenu = !this.showMenu;
    },
    away() {
      console.log('clicking away');
      this.showMenu = false;
      this.showNav = false;
    }
  },
};
</script>

<style lang="scss" scoped>
header {
  .menu-toggle-wrapper {
    &:focus,
    &:hover {
      i {
        color: #d9d9d9;
        transition: color 200ms linear;
      }
    }
  }
  .nav-icon {
    .casper {
      &:hover,
      &:focus {
        color: #d9d9d9;
        transition: color 200ms linear;
      }
    }
  }
}
</style>
