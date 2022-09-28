<template>
  <!-- @TODO: 
          change logo 
          fix color for active nav
          add marker to active nav
  -->
  <div class="sidenav-wrapper fixed z-4 w-screen">
    <div class="sidenav-links py-2 px-2 flex flex-wrap">
      <div class="sidenav-link py-3 px-1 col-4 active">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-home mb-2 text-lg casper"></i> Dashboard</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-book mb-2 text-lg casper"></i> Courses</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-calendar mb-2 text-lg casper"></i> Schedule</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-volume-down mb-2 text-lg casper"></i>
          Announcements</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-users mb-2 text-lg casper"></i> Students</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-check-circle mb-2 text-lg casper"></i> Grades</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-comments mb-2 text-lg casper"></i> Discussion</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
        <a
          href="#"
          class="flex flex-column align-items-center text-xs shadow-blue no-underline"
          ><i class="pi pi-folder mb-2 text-lg casper"></i> Files</a
        >
      </div>
      <div class="sidenav-link py-3 px-1 col-4">
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
    background: #131422e3;
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
