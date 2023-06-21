<template>
    <div>
        <h3>FormularioValidacion</h3>
        <div>
            <vue-form @submit.prevent="onSubmit" :state="formstate">
                <validate tag="label">
                    <span> Nombre*</span>
                    <input type="text" id="firstname" required name="firstname" v-model="model.firstname">
                    <field-messages name="firstname" show="$touched">
                        <div slot="required">El nombre es requerido</div>
                    </field-messages>
                </validate>
                <validate tag="label">
                    <span> Apellido*</span>
                    <input type="text" id="lastname" required name="lastname" v-model="model.lastname">
                    <field-messages name="lastname" show="$touched">
                        <div slot="required">El apellido es requerido</div>
                    </field-messages>
                </validate>
                <validate tag="label">
                    <span> Email*</span>
                    <input type="email" id="email" required name="email" v-model="model.email">
                    <field-messages name="email" show="$touched">
                        <div slot="required">El mail es requerido</div>
                        <div slot="email">El mail no es válido</div>
                    </field-messages>
                </validate>
                <validate tag="label">
                    <span> Edad*</span>
                    <input type="number" id="age" required name="age" v-model.number="model.age">
                    <field-messages name="age" show="$touched">
                        <div slot="required">La edad es requerida</div>
                    </field-messages>
                </validate>
                <validate tag="label" :custom="{ 'check-password': checkPassword }">
                    <span> Password*</span>
                    <input type="password" id="password" required name="password" v-model="model.password">
                    <field-messages name="password" show="$touched">
                        <div slot="check-password">Ingrese un password von al menos 8 caracteres, una mayúscula, una
                            minúscula y
                            un número</div>
                    </field-messages>
                </validate>



                <button type="submit">Mostrar Datos</button>
            </vue-form>

        </div>


    </div>
</template>

<script>
export default {
    name: 'FormularioValidacion',
    props: {
        msg: String
    },
    data() {
        return {

            formstate: {},
            model: {
                firstname: "",
                lastname: "",
                email: "",
                age: 0,
                password: "",
            },

        }

    },
    methods: {
        submitHandler() {
            if (this.firstname === "") {
                alert("El nombre es obligatorio");
                return;
            }
            else if (this.lastname === "") {
                alert("El apellido es obligatorio");
                return;
            }
            alert("Formulario Enviado")
        },
        onSubmit() {
            console.log(this.formstate)
            if (this.formstate.$valid) {
                alert("Form Sent!")
                this.$emit('formulario', this.model);
                return;
            }
        },
        checkPassword(value) {

            const regex = /^(?=.*[a-z])(?=.*[A-Z])(?=.*[0-9])(?=.*[^A-Za-z0-9])(?=.{8,})/;
            return regex.test(value);

        }
    },
}

</script>


<style></style>