<template>
    
    <p v-show="ocultarMensagem">...</p>
    <p v-show="exibirCarregando">Carregando...</p>
    <p v-show="numNegativo">Não pode haver números negativos</p>
    
</template>

<script>

    export default {
        data() {
            return {
                exibirCarregando: false,
                ocultarMensagem: true,
                numNegativo: false,
            }
        },

        props: ["contador"],

        watch: {
            contador: function(val){
                let self = this; 

                if(val > 0){
                    self.exibirCarregando = true;
                    self.ocultarMensagem = false;
                    self.numNegativo = false;
                }
                else if(val < 0){
                    self.exibirCarregando = false;
                    self.ocultarMensagem = false;
                    self.numNegativo = true;
                }
                else {
                    self.exibirCarregando = false;
                    self.ocultarMensagem = true;
                    self.numNegativo = false;
                }
            },

        },
    }

</script>