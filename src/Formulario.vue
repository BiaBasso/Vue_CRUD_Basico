<template>
    <div class="container">
        <form>
            <label class="label">Nome</label>
                <p class="control">
                    <input class="input is-info" type="text" placeholder="Digite aqui..." v-model="name">
                </p>
            <p class="control">
                <button class="button is-warning" @click.prevent="enviar()">Enviar</button>             
            </p>
        </form>    
    </div>
</template>

<script>
    export default {
        data() {
            return {
                name: '',
            }
        },

        methods: {
            enviar: function() {
                let self = this;

                alert("Olá " + self.name + " !");

                self.name = ''
            }

        },
    }
</script>