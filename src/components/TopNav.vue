<template>
  <!-- @TODO: 
          add dropdown notifications
          change color on badge
  -->
  <header class="hidden lg:flex flex-row align-items-center p-3 raisin-black-bg fixed z-4" style="height: 64px;">
    <div class="topnav-wrapper w-full flex justify-content-between align-items-center">
      <span class="p-input-icon-left w-full flex flex-row align-items-center pl-3">
        <i class="pi pi-search pl-3" />
        <InputText
          type="text"
          v-model="value1"
          placeholder="Search..."
          class="search-input pl-5 py-2 pr-2"
        />
      </span>
      <nav class="flex flex-row">
        <div class="nav-icon px-3 cursor-pointer">
          <account-circle-icon class="casper" title="Profile" aria-label="Profile" />
        </div>
        <div class="nav-icon px-3 cursor-pointer">
          <bell-icon class="casper" v-badge="2" title="Notifications" aria-label="Notifications" />
        </div>
        <div class="nav-icon px-3 cursor-pointer">
          <cog-icon class="casper" title="Settings" aria-label="Settings" />
        </div>
        <div class="nav-icon px-3 cursor-pointer">
          <power-icon class="casper" title="Logout" aria-label="Logout" />
        </div>
      </nav>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
  header {
    width: calc(100% - 117px);
    .nav-icon {
      .casper {
        &:hover, &:focus {
          color: #d9d9d9;
          transition: color 200ms linear;
        }
      }
    }
  }
</style>
