<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row" v-for="m in grupos" :key="m.id">
          <div class="col-md-12">
            <h4 style="color: #fff;">{{m.titulo}}</h4>
            <p style="color: rgb(132 130 130);" v-if="m.subTitulo !=''">{{m.subTitulo}}</p>
            <p style="color: rgb(132 130 130);margin-top:35px" v-else ></p>
          </div>
        
          <div class="col-md-2" v-for="m in m.casts" :key="m.id">
            <div 
            style="background-color:rgb(47 47 47); color:#fff;padding: 20px;border-radius: 3px;
            ">
              <img :src="'/img/'+m.thumb"
              style="width:100%;height:150px; border-radius:8px;">
              <h5 style="margin-top:10px;">{{m.titulo}}</h5>
              <p style="color: rgb(132 130 130);margin-top:-10px">{{m.subTitulo}}</p>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    components: {
    },
    data () {
      return {
        grupos:[],
      }
    },
    methods: {
      gerarGrupos(){
        try {
          this.grupos =[
            {
              "id":1, 
              "titulo":"Programas para conhecer",
              "subTitulo":"Podcasts que achamos que você vai adorar.",
              "casts":[
                {
                  "id":1,
                  "titulo":"Primocast",
                  "subTitulo":"O Primo Rico",
                  "thumb":"cast/cast01.jpg"
                },
                {
                  "id":2,
                  "titulo":"NerdCast",
                  "subTitulo":"Jovem Nerd",
                  "thumb":"cast/cast02.jpg"
                },
                {
                  "id":3,
                  "titulo":"Primocast",
                  "subTitulo":"O Primo Rico",
                  "thumb":"cast/cast01.jpg"
                },
                {
                  "id":4,
                  "titulo":"NerdCast",
                  "subTitulo":"Jovem Nerd",
                  "thumb":"cast/cast02.jpg"
                },
                {
                  "id":5,
                  "titulo":"Primocast",
                  "subTitulo":"O Primo Rico",
                  "thumb":"cast/cast01.jpg"
                },
                {
                  "id":6,
                  "titulo":"NerdCast",
                  "subTitulo":"Jovem Nerd",
                  "thumb":"cast/cast02.jpg"
                }
              ]
            },
            { 
              "id":2, 
              "titulo":"Top",
              "subTitulo":"",
              "casts":[
                {
                  "id":1,
                  "titulo":"Primocast",
                  "subTitulo":"O Primo Rico",
                  "thumb":"cast/cast01.jpg"
                },
                {
                  "id":2,
                  "titulo":"Piano",
                  "subTitulo":"Os 100 melhores",
                  "thumb":"cast/mozart.jpg"
                },
                {
                  "id":3,
                  "titulo":"Primocast",
                  "subTitulo":"O Primo Rico",
                  "thumb":"cast/cast01.jpg"
                },
                {
                  "id":4,
                  "titulo":"NerdCast",
                  "subTitulo":"Jovem Nerd",
                  "thumb":"cast/cast02.jpg"
                }
              ]
            },
            { 
              "id":3, 
              "titulo":"Piano de fundo",
              "subTitulo":"",
              "casts":[
                {
                  "id":1,
                  "titulo":"Piano",
                  "subTitulo":"Os 100 melhores",
                  "thumb":"cast/mozart.jpg"
                }
              ]
            },
          ];    
        } catch (e) {
          console.log(e);
        }
      },
    },   
    beforeMount(){
       this.gerarGrupos();
    }
  }
</script>
<style>
  ::-webkit-scrollbar {
      width: 12px;
  }
  
  ::-webkit-scrollbar-track {
      -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3); 
      background-color:rgb(39 39 39);
      /*border-radius: 10px;*/
  }
  
  ::-webkit-scrollbar-thumb {
      border-radius: 0px;
      background-color: #59595a;
      -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.5); 
  }

  .main-panel {
    background: rgb(39 39 39);
  }
  .navbar {
    background-color: #1d1d1d;
  }
  .card {
    border-radius: 4px;
    background-color: #3c3c3c;
  }

  .main-panel > .footer {
    border-top: 1px solid #3c3c3c;
  }
  .footer {
    background-color: #272727;
  }
  .main-panel > .content {
    background-color: #1d1d1d;
  }
  .card .card-header {
    background-color: #3c3c3c;
  }

  h4{
    line-height: 5px!important;
  }
  .col-md-2{
    max-width: 13.666667%;
  }
</style>
