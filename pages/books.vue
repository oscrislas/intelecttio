<template>
  <v-container>
    <v-layout row>
      <v-flex>
        <h1> El cueneto de los amigos</h1>
        <h2> Por que los amigos </h2>
        <p>Al abuelo Ussumane, siempre que podia, le gustaba recordad a sus nietos la grandeza de lso reinos de Africa, antes de la llegada del hombre blanco a su litoral.</p>
        <p>Al abuelo Ussumane, siempre que podia, le gustaba recordad a sus nietos la grandeza de lso reinos de Africa, antes de la llegada del hombre blanco a su litoral.</p>
      </v-flex>
    </v-layout>
    <v-layout row>
      <v-flex xs5>
        <v-btn :style="{backgroundColor: '#F7C122', width: '100%', padding: 0, marginLeft: 0, marginRight: 0}" large>
          <v-icon dark left>arrow_back</v-icon>
          Atras
        </v-btn>
      </v-flex>
      <v-flex xs2>
        <div class="num-page">
          10
        </div>
      </v-flex>
      <v-flex xs5>
        <v-btn :style="{backgroundColor: '#62D4D4', width: '100%', padding: 0, marginLeft: 0, marginRight: 0}" large>
          Continuar
          <v-icon dark right>arrow_forward</v-icon>
        </v-btn>
      </v-flex>
    </v-layout>
  </v-container>
</template>


<script>

export default {
  data() {
    return {
      numPage: 0
    }
  }
}

</script>


<style scoped>

p {
   font-family:'Futura Std Condensed';
    line-height: 2;
    font-size: 16px;
    color: #000000;
}

h1 {
  font-size: 2.747em;
}
h3 {
  font-size: 0.874em;
}
h2 {
  font-size:1.229em;
}

.num-page {
    width: 100%;
    text-align: center;
    font-size: 20px;
    padding: 10px
}



</style>
