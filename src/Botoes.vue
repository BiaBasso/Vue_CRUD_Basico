<template>
    <div class="container">

        <botoes-mensagem :contador="contador"></botoes-mensagem>

        <!--<button type="button" class="button is-info" @click.prevent="add()">Adicionar 1</button>-->
        <!--<button type="button" class="button is-danger" @click.prevent="remove()">Remover 1</button>-->

        <button type="button" class="button is-info" @click="contador += 1">Add 1</button>
        <button type="button" class="button is-danger" @click="contador -= 1">Remove 1</button>

    </div>
</template>

<script>

    import BotoesMensagem from './BotoesMensagem.vue';

    export default {
        components: {
            BotoesMensagem,
        },

        data() {
            return {
                contador: 0,
            }            
        },

        methods: {
            add: function(){
                let self = this;

                self.contador += 1;                
            },

            remove: function(){
                let self = this;

                self.contador -= 1;                
            },
        },
    }

</script>