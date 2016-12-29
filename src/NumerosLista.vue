<template>
    
    <p v-show="semElemento">A lista esta vazia</p>
    <p v-show="comElemento">A lista contem: {{ tamanho }} elementos.</p>
      
</template>

<script>
    export default {
        props: ["lista"],

        data() {
            return {
                tamanho: 0,
                semElemento: true,
                comElemento: false,
            }
        },

        watch: {
            lista: function(val) {
                let self = this;

                if(val.length > 0){
                    self.tamanho = val.length;

                    self.semElemento = false;
                    self.comElemento = true;
                }
                else {
                    self.tamanho = 0;

                    self.semElemento = true;
                    self.comElemento = false;
                }
            },
        },
    }
</script>