<template >
    <v-card class="cardLogin">
        <v-card-title class="title">
           
                    <img class="top" src="~/assets/images/LoginTop.png" alt=""><!--Aqui va la imagen de el logo-->
              
        </v-card-title>
        <v-card-text>
                <v-form ref="formLogin">
                <v-text-field label="Email" 
                            placeholder="Email"
                            v-model="CorreoElectonico"
                            :rules="ValidarCorreo"/>
            
                <v-text-field label="Password"
                            placeholder="Password"
                            v-model="Password"
                            :rules="validarPassword"/>

               <!-- <v-text-field label="Email"
                            placeholder="Email"
                            v-model="Email"/>

                <v-text-field label="Password"
                            placeholder="Password"
                            v-model="Password"/>
                
                <v-text-field label="Number"
                            plaeholder="Number"
                            v-model="Numero"/>
                            -->
            </v-form>
        </v-card-text>
        <v-card-actions>
           <!--aqui va la imagen de la flecha-->
           <v-btn class="btnLogin"
           rounded
           block
           @click="loginBackend">
            Login
           </v-btn>
        </v-card-actions>
    </v-card>
</template>

<script>
export default {
    data() {
        return {
             
            CorreoElectonico: '',
            ValidarCorreo: [
            v => !v || /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) || 'E-mail must be valid'
            ],
            Password: '',
            validarPassword: [
                value => value.length >= 8 || 'Min 6 characters' 
            ]
        }
    },
    methods: {
        loginBackend () {
            const valid = this.$refs.formLogin.validate() 
            if (valid) {
                alert('presionaste el boton')
            }else {
                alert('no cumpliste las reglas')
            }
             
        }
    }   
}
</script>


<style scoped>
.cardLogin {
    background: linear-gradient(#F6D7E8, #A9C9C5, #AF90A2);
    border-radius: 10px;
    width: 500px;
    height: 300px;
}
.title {
    
    justify-content: center;
}
.top {
    width: 300px;
}
.btnLogin {
    color: #AF90A2;
}
</style>