<template>
    <div :class="['alert', {'alert-success' : variant == 'success'}]">
        Seu formulario foi sucesso 
        <button @click="closeAlert()">X</button>
    </div>
    <div :class="baseClass">
        alert 2 {{variant}}
    </div>
</template>

<script>
export default {
    props: {
        variant: {
            type: String,
            default : ''
        },
    },
    methods:{
        closeAlert(){
          this.$emit('close');
        },
    },

    computed: {
        baseClass(){
            console.log("baseclass");
            return [
                'alert', 
                this.variant ? 'alert-${this.variant}' : ''
            ]
        },
    },
}
</script>

<style scoped>
    .alert{
        display: flex;
        justify-content: space-between;
        padding: 5px;
        border: 6px;
        color: grey;
        background: #ddd;
    }
    .alert-success{
        background: #42b983;
        color: #fff;
    }
    .alert-danger{
        background: #b40808;
        color: #fff;
    }
</style>
