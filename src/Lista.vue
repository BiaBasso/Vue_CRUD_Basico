<template>
    <div class="container">

        <numeros-lista :lista="lista"></numeros-lista>
        
        <button type="button" class="button is-info" @click.prevent="adicionarUm()">Adicionar 1</button>
        <button type="button" class="button is-success" @click.prevent="adicionarDois()">Adicionar 2</button>
        <button type="button" class="button is-warning" @click.prevent="removerElemento()">Remover Um Elemento</button>
        <button type="button" class="button is-danger" @click.prevent="limparLista()">Limpar Lista</button>
    </div>
</template>

<script>

    import NumerosLista from './NumerosLista.vue'

    export default {
        data() {
            return {
                lista: [],
            }            
        },

        components: {
           NumerosLista,
        },

        methods: {
            adicionarUm: function(){                
                let self = this;

                self.lista.push("a");
            },

            adicionarDois: function(){
                let self = this;

                self.lista.push("b");
            },

            removerElemento: function(){
                let self = this;

                self.lista.pop();
            },

            limparLista: function(){
                let self = this;

                self.lista = []
            },

        }

    }
</script>