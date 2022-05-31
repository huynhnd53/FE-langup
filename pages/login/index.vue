<template>
    <v-container>
        <v-layout row wrap>
            <v-flex xs12 sm4 offset-sm4 align-center justify-center>
                <img src="https://checkin.mor.com.vn/img/logo-mor-coloring.69ebf7e7.svg" alt="">
                <v-card class="elevation-12" light>
                    <v-toolbar dark color="primary">
                        <v-toolbar-title>
                            <h3>Sign in</h3>
                        </v-toolbar-title>
                    </v-toolbar>
                    <div class="pa-9">
                        <v-form ref="form" v-model="valid" lazy-validation>
                            <v-text-field v-model="email" :rules="emailRules" label="E-mail" required></v-text-field>
                            <v-text-field v-model="password" :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
                                :rules="[rules.required, rules.min]" :type="show1 ? 'text' : 'password'"
                                name="input-10-1" label="Password" hint="At least 8 characters"
                                @click:append="show1 = !show1">
                            </v-text-field>
                            <v-card-actions class="float-right">
                                <a href="/forgotPassword"> Quên mật khẩu?</a>
                            </v-card-actions>
                            <br></br>
                            <v-card-actions class="justify-center">
                                <v-btn block color="primary" @click="login">
                                    Đăng nhập
                                </v-btn>
                            </v-card-actions>
                        </v-form>
                    </div>
                </v-card>
            </v-flex>
        </v-layout>
    </v-container>
</template>


<script>
export default {
    layout: 'login',
    data: () => ({
        valid: true,
        email: '',
        emailRules: [
            v => !!v || 'E-mail is required',
            v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
        ],
        show1: false,
        password: 'Password',
        rules: {
            required: value => !!value || 'Password is Required.',
            min: v => v.length >= 8 || 'Min 8 characters',
            emailMatch: () => (`The email and password you entered don't match`),
        },
    }),

    methods: {
        login() {
            this.$refs.form.validate()
        },
    },
}
</script>
<style lang="scss" scoped>
.col-style-custom {
    border: 2px solid red;
    border-radius: 5px;
}
</style>