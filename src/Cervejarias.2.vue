<template>
  
  <div class="container">
    <h1 class="title">{{title}}</h1>

    <form>
      <div class="form-group">
        <label for="username">Username:</label>
        <input type="text" class="form-control" id="username" v-model="username">
      </div>

      <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" class="form-control" id="password" v-model="password">
      </div>

      <div class="form-group">
        <a class="btn btn-primary" @click="enterUser">Entrar</a>
      </div>      

    </form>

</template>  
<script>

    // import Pagination from './Pagination.vue'

  export default {
    data () {
      return {
        isLoading: false,
        title: 'Login de Usuário',
        search: '',
        breweries: [],
        page: 1,
        total: 0,
        selected: {},
        itensPerPage: 10,
        showModal:false,        
        username: '',
        password: '',
                
      }
    },

    components: {
        // Pagination
    },

    methods: {

      enterUser(){

        let user2 = {}
        user2.credentials = {}
        user2.credentials.username = this.username;
        user2.credentials.tenant_identifier = "234rfw4f";
        user2.password = this.password;

        this.$http.post("http://localhost:8080/api/login",user2)
        .then(function(response){
          alert("Bem vindo");
          console.log(response.body.access_token);
        }, function(error){
          alert("Usuário ou senha inválidos");
          console.log(error.body);
        })        
      },

    //   onChangePage(page) {
    //   this.page = page;
    //   this.loadBreweries();
    //   },

    //   showLoading(){
    //     this.isLoading=true;
    //   },
    //   hideLoading(){
    //     this.isLoading=false;
    //   },
    //   loadBreweries(){

    //     let t = this
    //     this.showLoading()

    //     let start = (this.page * this.itensPerPage) - (this.itensPerPage - 1)
    //     let end = this.page * this.itensPerPage
    //     let qString = "";

    //     if(this.search){
    //         qString = `&q=${this.search}`
    //     }

    //     this.$http.get(`/breweries?_start=${start}&_end=${end}${qString}`).then(
    //      response=>{
    //        t.breweries = response.body;
    //        t.total = response.headers.get('X-Total-Count')

    //      },
    //      error=>{
    //        console.log(error)
    //      }).finally(function () {
    //       t.hideLoading();
    //     })

    //    },
    //    searchBreweries(){

    //        this.loadBreweries()
    //    },

    //    newBreweries(){
    //     this.selected={}
    //     this.showModal = true;
    //    },

    //    editBrewery(brewery){
    //     this.selected=brewery
    //     this.showModal = true;
    //    },

    //    saveBrewery(){  
    //     if (this.selected.id!=null){  //EDIT
    //       this.$http.put(`/breweries/${this.selected.id}`,this.selected).then(
    //         response=>{
    //           this.$set('selected',{})
    //           this.$set('showModal',false)
    //         },
    //         error=>{
    //           console.error(error)
    //         }
    //         ).finally(
    //           this.loadBreweries()
    //         )
    //       }
    //       else
    //       { //NEW
    //         this.$http.post(`/breweries`,this.selected).then(
    //         response=>{
    //           this.$set('selected',{})
    //           this.$set('showModal',false)
    //         },
    //         error=>{
    //           console.error(error)
    //         }
    //         ).finally(
    //           this.loadBreweries()
    //         )
    //       }
    //    },
    //  },

    //  created(){

    //   this.loadBreweries();
     }
  }
</script>  
<style>  
  .fixo{float: right; margin-right: 10px; margin-top: 0px; z-index: 1000;}
</style>