<template>
    <v-container fluid id="main_container">
        <v-jumbotron color="grey lighten-2" height="200px">
            <v-container>
                <h3 class="display-3">Contato</h3>
                <span class="subheading">
                    Lorem ipsum dolor sit amet, pri veniam forensibus id. Vis maluisset molestiae id, ad semper lobortis cum. At impetus detraxit incorrupte usu, repudiare assueverit ex eum, ne nam essent vocent admodum.
                </span>
            </v-container>
        </v-jumbotron>
        <v-form v-model="valid" ref="contactForm">
            <v-container fluid px-0>
                <v-layout row wrap>
                    <v-flex xs12 sm6 pr-3>
                        <v-card  elevation-6>
                            <v-card-media src="/static/img/img2.jpg" height="430px">
                            </v-card-media>
                        </v-card>
                    </v-flex>
                    <v-flex xs12 sm6>
                        <v-text-field
                            label="Nome"
                            v-model="name"
                            :rules="nameRules"
                            required
                        ></v-text-field>
                        <v-text-field
                        label="E-mail"
                        v-model="email"
                        :rules="emailRules"
                        required
                        ></v-text-field>
                        <v-layout row wrap>
                            <v-flex xs12 sm6 pr-2>
                                <v-text-field
                                label="Telefone"
                                v-model="telephone"
                                :rules="telephoneRules"
                                mask="(##)####-####"
                                type="phone"
                                required
                                ></v-text-field>
                            </v-flex>
                            <v-flex xs12 sm6 pl-2>
                                <v-text-field
                                label="Celular"
                                v-model="cellphone"
                                :rules="cellphoneRules"
                                mask="(##)#####-####"
                                type="phone"
                                required
                                ></v-text-field>
                            </v-flex>
                            <v-flex xs12>
                                <v-text-field
                                label="Descrição"
                                v-model="description"
                                :rules="descriptionRules"
                                multi-line
                                :counter="255"
                                required
                                ></v-text-field>
                            </v-flex>
                            <v-btn
                                block
                                @click="submit"
                                :disabled="!valid"
                                color="success"
                                elevation-6
                            >
                                Enviar
                                <v-icon right>email</v-icon>
                            </v-btn>
                        </v-layout>
                    </v-flex>
                </v-layout>
            </v-container>
        </v-form>
    </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: false,
    name: '',
    nameRules: [
      v => !!v || 'Informe seu Nome'
    ],
    email: '',
    emailRules: [
      v => !!v || 'Informe seu E-mail',
      v =>
        /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) ||
        'E-mail inválido'
    ],
    telephone: '',
    telephoneRules: [
      v => !!v || 'Informe seu Telefone',
      v => v.length === 10 || 'Telefone inválido'
    ],
    cellphone: '',
    cellphoneRules: [
      v => !!v || 'Informe seu Celular',
      v => (v.length >= 10 && v.length <= 11) || 'Celular inválido'],
    description: '',
    descriptionRules: [
      v => !!v || 'Informe a Descrição do seu pedido',
      v => v.length <= 255 || 'Sua descrição deve conter no máximo 255 caracteres'
    ]
  }),
  methods: {
    submit () {
      console.log('SUBMIT')
      return true
    }
  }
}
</script>

<style scoped>
#main_container {
  max-width: 1260px;
}
.img {
    border-radius: 8px;
    -webkit-filter: grayscale(100%); /* Safari 6.0 - 9.0 */
    filter: grayscale(100%);
}
</style>


