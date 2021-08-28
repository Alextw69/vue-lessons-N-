<template>
    <li class="theItem"> {{xyz}} </li>
</template>

<script>
    export default {
        props: ['xyz'],
    }
</script>

<style>
    .theItem{
        background: rgb(75, 211, 57);
        font: 18px Calibri;
        margin: 5px;
        padding: 5px;
    }
    .theItem:hover{
        background: rgb(212, 138, 63);
        cursor: pointer;
    }
</style>