<template>
    <div>
        <label :for="id">{{ label }} </label>
        <select :id="id" @input="inputHandler">
            <option 
            v-for="(option) in options" 
            :value="option.value" 
            :key="option.value"
        
            >
                {{ option.name }}
            </option>
        </select>

        <p>________________</p>
    </div>
</template>

<script>
export default {
    name: 'SelectDinamico',
    props: {
        options: {
            type: Array,
            required: true,
        },
        label: {
            type: String,
            required: true,
        },
        value: {
            type: String,
            required: true,
        }
    },
    data() {
        return {


        }

    },
    methods: {
        inputHandler(e){
            this.$emit("input",e.target.value)
        }
    },
}

</script>


<style></style>