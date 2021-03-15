<template>
  <nav class="navbar navbar-expand-lg">
    <div class="container-fluid">
      <div class="collapse navbar-collapse">
      <a class="navbar-brand nav-button-top" href="#"><i class="fa fa-chevron-left" aria-hidden="true"></i></a>
      <a class="navbar-brand nav-button-top" href="#"><i class="fa fa-chevron-right" aria-hidden="true"></i></a>
      </div>
     
    </div>
  </nav>
</template>
<script>
  export default {
    computed: {
      routeName () {
        const {name} = this.$route
        return this.capitalizeFirstLetter(name)
      }
    },
    data () {
      return {
        activeNotifications: false
      }
    },
    methods: {
      capitalizeFirstLetter (string) {
        return string.charAt(0).toUpperCase() + string.slice(1)
      },
      toggleNotificationDropDown () {
        this.activeNotifications = !this.activeNotifications
      },
      closeDropDown () {
        this.activeNotifications = false
      },
      toggleSidebar () {
        this.$sidebar.displaySidebar(!this.$sidebar.showSidebar)
      },
      hideSidebar () {
        this.$sidebar.displaySidebar(false)
      }
    }
  }

</script>
<style>
.nav-button-top{
  background-color: #000;
  padding: 7px;
  border-radius: 100px;
  font-size: 13px !important;
}
.navbar-brand{
  margin: 11px 0px !important;
  margin-right: 15px !important;
}
</style>
