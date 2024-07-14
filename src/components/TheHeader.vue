<template>
    <header class="header">
        <h1><slot name="title"></slot></h1>
        <slot name="description"></slot>
        
        <slot></slot>
    </header>
    
</template>

<script>
    export default{
        name: 'TheHeader',
        mounted(){
            console.log(this.$slots);
        }
    }

</script>

<style scoped>
    .header{
        background: white;
    }
</style>