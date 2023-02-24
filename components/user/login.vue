<template>
    <v-card class="cardLogin">
        <v-card-title>Login</v-card-title>
        <v-card-text>
            <v-form v-model="formularioValido">
                <v-text-field label="Correo elctronico" 
                            placeholder="Correo electronico"
                            v-model="CorreoElectonico"/>
            </v-form>
            <v-form v-model="passwordValido">
                <v-text-field class="Color" label="Contraseña"
                            placeholder="Contraseña"
                            v-model="Contraseña"/>
            </v-form>
        </v-card-text>
        <v-card-actions>
            Boton para iniciar sesion
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
    data() {
        return {
            formularioValido: false, 
            CorreoElectonico: ''
        }
    }   
}
</script>


<style scoped>
.cardLogin {
    background: linear-gradient(#CD5F77, #2C0D06, #7A50A1);
    border-radius: 10px;
    width: 500px;
    height: 300px;
    color: white;
}
.Color {
    color: white;
}
</style>