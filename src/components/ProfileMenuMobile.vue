<template>
  <!-- @TODO: 
          add dropdown notifications
          change color on badge
  -->
  <ul class="flex flex-column fixed z-4 w-screen p-3" style="margin-top: 64px; background: #131422e3;">
    <li class="nav-icon cursor-pointer flex flex-row mb-2">
      <account-circle-icon
        class="casper mr-3"
        title="Profile"
        aria-label="Profile"
      />
      <span>Profile</span>
    </li>
    <li class="nav-icon cursor-pointer flex flex-row mb-2">
      <bell-icon
        class="casper mr-3"
        title="Notifications"
        aria-label="Notifications"
      />
      <span>Notifications</span>
      <Badge value="2" class="ml-2 mt-1"></Badge>
    </li>
    <li class="nav-icon cursor-pointer flex flex-row mb-2">
      <cog-icon class="casper mr-3" title="Settings" aria-label="Settings" />
      <span>Settings</span>
    </li>
    <li class="nav-icon pr-3 cursor-pointer flex flex-row">
      <power-icon class="casper mr-3" title="Logout" aria-label="Logout" />
      <span>Logout</span>
    </li>
  </ul>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.nav-icon {
  list-style-type: none;
  .casper {
    &:hover,
    &:focus {
      color: #d9d9d9;
      transition: color 200ms linear;
    }
  }
}
</style>
