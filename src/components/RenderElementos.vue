<template >
    <div>
        <table>
        <tr v-for="(elements, i) in datos" :key="i" >
        {{ elements }}</tr>
        </table>
    </div>
</template>

<script>
export default {
    name: 'RenderElementos',
    props:{
        datos:{
            required: true,
            type: {}
        }

    }

}

</script>

<style></style>