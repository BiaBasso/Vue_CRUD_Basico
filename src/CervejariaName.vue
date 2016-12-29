<template>
    <div>
        {{ id }} - {{ cervejariaName }}
    </div>  

</template>

<script>
    export default{
        data(){
            return{
                cervejariaName: ""
            }
        },

        props: ["id"],           

        ready: function(){

                 let self = this;

                 console.log("test")
                
                 this.$http.get("http://localhost:3000/breweries/" + this.id)
                    .then (function(response){
                        console.log(response.body.name);

                        self.cervejariaName = response.body.name;
                    },

                    function(error){
                        console.log(error);
                    })
             
        },
        methods: {

        }
    }
</script>