<template>
    <div class="backdrop" @click.self="closeModal">
        <div class="modal" :class="{ sale: theme === 'sale'}">
            <slot></slot>
            <div class="actions">
                <slot name="links"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default{
    name:'Modal',
    props:['theme'],  
    methods: {
        closeModal(){    //this function will be executed from the parent component.
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
.modal{
    width: 400px;
    padding:20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
}

.backdrop{
top: 0;
position: fixed;
background: rgba(0,0,0,0.5);
width:100%;
height: 100%;
}
h1{
    color:#03cfb4;
    border:none;
    padding:0;
}

.sale{
    background: crimson;
    color:white;
}
.sale h1{
    color:white;
}

.modal .actions {
    text-align: center;
    margin: 30px 0 10px 0;
}
</style>