<template>
    <v-row>
        <v-col cols="12" md="5">
            <v-card class="pa-10">
                <h2>Login</h2>
                <div class="grey--text">Masukkan username dan password untuk masuk</div>

                <form class="my-10" @submit.prevent="handleSubmit">
                    <v-text-field 
                        v-model="req.username" 
                        :rules="textRules('username')"
                        label="Username"
                        filled
                        required
                    ></v-text-field>

                    <v-text-field
                        v-model="req.password"
                        :rules="textRules('password')"
                        label="Password"
                        type="password"
                        filled
                        required
                    >
                    </v-text-field>

                    <v-btn type="submit" block color="primary">Submit</v-btn>
                </form>

                <v-card-text>Result: {{ result }}</v-card-text>
            </v-card>
        </v-col>
    </v-row>
</template>

<script>
    export default {
        layout: 'default',
        data() {
            return {
                req: {},
                result: ''
            }
        },
        methods: {
            textRules(text) {
                return [
                    v => !!v || `${text} harus diisi`
                ]
            },
            handleSubmit() {
                this.result = `{username: '${this.req.username}', password: '${this.req.password}'}`
                // this.req = {}
            }
        }
    }
</script>