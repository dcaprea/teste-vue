<template>
    <div>
        <input type="text" :value="valor" :class="cor" @input="$emit('meutexto')" />
    </div>
</template>

<script>

export default{
    props:{
        valor:{
            type: String,
            required: false,
            default: 'Xuxa'
        },
        cor: {
            type: String,
            required: false,
            default:'verde'
        }
    }
}
</script>

<style>
    .vermelho{
        background:#ff0000;
        color: #ffffff
    }
    .verde{
        background:#00ff00;
        color: #000;
    }
</style>