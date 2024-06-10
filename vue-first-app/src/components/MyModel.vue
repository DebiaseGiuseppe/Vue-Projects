<template>
    <div class="backdrop" @click.self="closeModule">
        <div class="model" :class="{ sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>


<script>
export default{
    props: ['theme'],
    methods: {
        closeModule(){
            this.$emit('close')
        }
    }
}

</script>


<style>
.model{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop{
    top: 0;
    position: fixed;
    background: rgba(0,0,0,0.5);
    width: 100%;
    height: 100%;
}

.model p{
    font-style: normal;
}


.model.sale {
    background: red;
    color: white;
}
.model.sale h1 {
    color: white;
}

</style>