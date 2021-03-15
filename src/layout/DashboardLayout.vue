<template>
  <div class="wrapper">
    <side-bar>
      <mobile-menu slot="content"></mobile-menu>
      <sidebar-link to="/web/inicio">
        <i class="fa fa-home" aria-hidden="true"></i>
        <p>Início</p>
      </sidebar-link>
      <sidebar-link to="/web/buscar">
        <i class="nc-icon nc-zoom-split"></i>
        <p>Buscar</p>
      </sidebar-link>
      <sidebar-link to="/web/biblioteca" >
        <i class="nc-icon nc-align-left-2"></i>
        <p>Sua Biblioteca</p>
      </sidebar-link>

      <div style='border-bottom: 1px solid rgba(255, 255, 255, 0.2);padding-bottom: 15px;'>
        <p class="playlist">PLAYLISTS</p>
        <div class="row" style="padding: 0px 40px 0px 40px;">
           <a href="#" class="row" style="color:#fff">
              <div class="col-md-3">
                <div 
                style="background-color: rgb(165 165 165);
                color:#000;width:35px;height:35px">
                  <i class="fa fa-plus" aria-hidden="true"
                  style="padding: 11px;"></i>
                </div>
              </div>
              <div class="col-md-9">
                <p style="padding-top: 5px;">Criar playlist</p>
              </div>
           </a>
           
           <a href="#" class="row" style="color:#fff">
              <div class="col-md-3">
                <div style="
                background-image: linear-gradient(140deg, #3462e6 0%, #8670bc 50%, #b19ada 75%);
                width:35px;height:35px;color:#fff">
                  <i class="fa fa-heart" aria-hidden="true"
                  style="padding: 10px;"></i>
                </div>
              </div>
              <div class="col-md-9">
                <p style="padding-top: 5px;">Músicas Curtidas</p>
              </div>
           </a>
        </div>
      </div>
      
      <template slot="bottom-links">
        <sidebar-link class="active"
          to="/app" style="margin-top: -108px;"> 
           <i class="fa fa-arrow-circle-o-down" aria-hidden="true" style="font-size: 21px;margin-top: 5px;color: #989a9c;"></i>
           <p>Instalar aplicativo</p>
        </sidebar-link>
      </template>
    </side-bar>
    <div class="main-panel">
      <top-navbar></top-navbar>

      <dashboard-content @click="toggleSidebar">

      </dashboard-content>

      <content-footer></content-footer>
    </div>

    <div class="music">

    </div>
  </div>
</template>
<style lang="scss">

</style>
<script>
  import TopNavbar from './TopNavbar.vue'
  import ContentFooter from './ContentFooter.vue'
  import DashboardContent from './Content.vue'
  import MobileMenu from './MobileMenu.vue'
  export default {
    components: {
      TopNavbar,
      ContentFooter,
      DashboardContent,
      MobileMenu
    },
    methods: {
      toggleSidebar () {
        if (this.$sidebar.showSidebar) {
          this.$sidebar.displaySidebar(false)
        }
      }
    }
  }

</script>

<style>
  .sidebar .nav .nav-link, body > .navbar-collapse .nav .nav-link {
    text-transform: unset !important;
  }
  .sidebar .nav li .nav-link p, body > .navbar-collapse .nav li .nav-link p {
    text-transform: unset !important;
  }
  .playlist{
    padding: 15px 30px 0px 30px;
    font-size: 13px;
  }
  p{
    font-family: -webkit-pictograph;
  }
  .sidebar:before, body > .navbar-collapse:before {
    opacity: 10 !important;
  }

  .music{
    height: 90px;
    width: 100%;
    background-color: #3c3c3c;
    position: fixed;
    bottom: -4px;
    z-index: 90;
  }

  .nav-bottom li.active .nav-link, body > .navbar-collapse .nav li.active .nav-link {
    background: rgb(255 255 255 / 0%)!important;
  }
</style>

