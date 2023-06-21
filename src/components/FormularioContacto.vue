<template>
    <div>
        <div>
            <form action="">
                <div>
                    <label for="firstname">Nombre: </label>
                    <input type="text" id="firstname" v-model="firstname">
                </div>
                <div>
                    <label for="lastname">Apellido: </label>
                    <input type="text" id="lastname" v-model="lastname">
                </div>
                <div>
                    <label for="age">Edad: </label>
                    <input type="number" id="age" v-model="age">
                </div>
                <div>
                    <label for="adress">Dirección: </label>
                    <input type="text" id="adress" v-model="adress">
                </div>
                <div>
                    <input type="checkbox" value="underageCheck" id="underageCheck" v-model="checks">
                    <label for="underage">Confirmo que soy mayor de edad</label>
                </div>
                <div>
                    <input type="checkbox" value="termsCheck" id="termsCheck" v-model="checks">
                    <label for="underage">Confirmo que ley términos y condiciones</label>
                </div>
                <div>
                    <input type="checkbox" value="weandoCheck" id="weandoCheck" v-model="checks">
                    <label for="underage">Confirmo que estoy puro weando</label>
                </div>
                <div>
                    <label for="country">País</label>
                    <select id="country" v-model="country">
                        <option value="es">España</option>
                        <option value="fr">Francia</option>
                        <option value="cl">Chile</option>
                        <option value="pe">Perú</option>

                    </select>
                </div>
                <div>
                    <div>
                        <input type="radio" name="documentType" id="documentDNI" v-model="document" value="dni" />
                        <label for="documentDNI">DNI</label>
                    </div>
                    <div>
                        <input type="radio" name="documentType" id="documentPassport" v-model="document" value="passport" />
                        <label for="documentPassport">Pasaporte</label>
                    </div>
                    <div>
                        <input type="radio" name="documentType" id="documentVisa" v-model="document" value="visa" />
                        <label for="documentVisa">VISA</label>
                    </div>
                </div>
                <button>Enviar</button>
            </form>
        </div>
        <div>
            <p>{{ firstname }}</p>
            <p>{{ lastname }}</p>
            <p>{{ age }}</p>
            <p>{{ adress }}</p>
            <p>{{ adress }}</p>
        </div>

    </div>
</template>

<script>
export default {
    name: 'FormularioContacto',
    props: {
        msg: String
    },
    data() {
        return {
            firstname: "",
            lastname: "",
            age: "",
            adress: "",
            checks: [],
            country: "",
            document: "",

        }

    },
    methods: {},
}

</script>


<style></style>