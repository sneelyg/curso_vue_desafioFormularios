<template>
    <div>
        <h3>Modificadores de Entrada</h3>
<div>
    <label for="age">Edad</label>
    <input type="number" id="age" v-model.number="age" >
    <h1>{{ age }}</h1>
</div>
<div>
    <label for="pueblo">Pueblo</label>
    <input type="text" id="pueblo" v-model.trim="pueblo" >
    <h1>{{ pueblo }}</h1>
</div>
<div>
    <label for="lazytext">Lazy</label>
    <!-- Lazy se cambia al on-change, no en el input mismo -->
    <input type="text" id="lazytext" v-model.lazy="lazytext" >
    <h1>{{ lazytext }}</h1>
</div>


    </div>
</template>

<script>
export default {
    name: "ModificadoresEntrada",
    data(){
        return{
            age:0,
            pueblo: "",
            lazytext:"",
        }
    },
    props: {},
    methods: {}
}


</script>

<style></style>