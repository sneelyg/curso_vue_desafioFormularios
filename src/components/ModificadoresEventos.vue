<template>
    <div>
        <h2>.Stop</h2>
        <div @click="handleClick">
            <button @click.stop="handleButton">
                <span @click="handleClickSpan">Stop Propagation</span>
            </button>
        </div>
        <hr/>
        <h2>.capture       </h2>
        <!-- un evento dirijido a un elemento hijo se maneja primero por el elemento padre -->
        <div @click.capture="handleClick">
            <button @click="handleButton">
                <span @click="handleClickSpan">Capture</span>
            </button>
        </div>
        <hr/>
        <div>
            <h2>.self</h2>
            <div style="{padding: 10px}" @click="handleClick">
                <button> No Self </button>
            </div>
            <div style="{padding: 10px}" @click.self="handleClick">
                <button> Self </button>
                <!-- Self solo toma el evento si fue en ese elemento, no en uno de sus hijos -->
            </div>
        </div>

    </div>
</template>

<script>
export default {
    name: 'ModificadoresEventos',
    props: {
    },
    data() {
        return {


        }

    },
    methods: {
handleClick(){
    console.log("Abuelo: CLick en el padre");
},
handleButton(){
    console.log("Padre: CLick en el boton");
},
handleClickSpan(){
    console.log("Hijo: Click en el span")
}
    },
}

</script>


<style></style>