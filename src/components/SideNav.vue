<template>
  <!-- @TODO: 
          change logo 
          fix color for active nav
          add marker to active nav
  -->
  <div class="sidenav-wrapper fixed z-5 h-screen hidden lg:flex overflow-x-hidden" style="width: 117px">
    <div
      class="logo-wrapper fixed flex justify-content-center align-items-center"
      style="height: 64px; background-color: #2b2d46"
    >
      <img
        alt="Vue logo"
        class="logo cursor-pointer"
        src="@/assets/logo.svg"
        width="20"
        height="20"
      />
    </div>
    <div class="sidenav-links raisin-black-bg py-2 px-2">
      <div class="sidenav-link py-3 px-1 active">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-home mb-2 text-lg casper"></i> Dashboard</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-book mb-2 text-lg casper"></i> Courses</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-calendar mb-2 text-lg casper"></i> Schedule</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-volume-down mb-2 text-lg casper"></i>
          Announcements</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-users mb-2 text-lg casper"></i> Students</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-check-circle mb-2 text-lg casper"></i> Grades</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-comments mb-2 text-lg casper"></i> Discussion</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-folder mb-2 text-lg casper"></i> Files</a
        >
      </div>
      <div class="sidenav-link py-3 px-1">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-chart-line mb-2 text-lg casper"></i> Reports</a
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
.sidenav-wrapper {
  overflow-y: scroll;
  &::-webkit-scrollbar {
    background: transparent;
    width: 0px;
  }
  .logo-wrapper {
    width: inherit;
  }
  .sidenav-links {
    margin-top: 64px;
    .sidenav-link {
      &:hover,
      &:focus {
        a.shadow-blue {
          color: #acbacc;
          transition: color 200ms linear;
          .casper {
            color: #d1e1f6;
            transition: color 200ms linear;
          }
        }
      }
      &.active {
        a,
        i {
          color: #00bfff;
          transition: color 200ms linear;
        }
        &:hover,
        &:focus {
          a,
          i {
            color: #00bfffa8 !important;
            transition: color 200ms linear;
          }
        }
      }
    }
  }
}
</style>
