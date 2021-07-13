<template>

  <section class="src-componentes-estructura">
      <div class="jumbotron">
            <input v-model="texto" placeholder="">
              <div v-if="obtenerCantidadLetras > 0">
              <p>Cantidad: {{obtenerCantidadLetras}}</p>
              <p>{{texto | codificando }}</p>
              <p>{{texto | mayuscula }}</p>
              <p>{{texto | minuscula }}</p>
              <p>{{texto | mayusminus }}</p>
              <p>{{texto | minusmayus }}</p>
              </div>
              <hr>
              <p>Respuestas: 1:b | 2:b | 3:c | 4:a,b | 5:b,c </p>
      </div>
  </section>

</template>

<script lang="js">

  export default  {
    name: 'src-components-codificacion',
    props: [],
    mounted () {

    },
    data () {
      return {
        texto: ''
      }
    },
    filters: {
      minuscula: function (texto) {
      return texto.toLowerCase()
      },
      mayuscula: function (texto) {
      return texto.toUpperCase()
      },
      mayusminus: function (texto) {
        let textoADevolver = '';
        for (let i = 0; texto.length > i; i++) {
          if (i % 2 == 0)
            {
          textoADevolver += texto[i].toUpperCase();
           }
          else
          {
          textoADevolver += texto[i].toLowerCase();
          }
      }
        return textoADevolver; 
      },
      minusmayus: function (texto) {
        let textoADevolver = '';
        for (let i = 0; texto.length > i; i++) {
          if (i % 2 == 0) textoADevolver += texto[i].toLowerCase();
          else
          {
            textoADevolver += texto[i].toUpperCase();
          }
      }
        return textoADevolver; 
      },
      codificando: function (texto) {
        let textoADevolver = ''
        let textoMinuscula = texto.toLowerCase()

        const cambioLetras = {
            'a':'u',
            'e':'o',
            'o':'e',
            'u':'a'
          }

        for(const letra of textoMinuscula) {
            if (cambioLetras[letra]) {
              textoADevolver += cambioLetras[letra]
            } else {
              textoADevolver += letra
            }
          }
          return textoADevolver
       },
    },
      

    methods: {
       
    },
    computed: {
        obtenerCantidadLetras() {
            let cant = this.texto.length;
            return cant;
        } 
    }
}


</script>

<style scoped lang="css">
  .src-components-codificacion {

  }

  .jumbotron {
    background-color: white;
    color: black;
  }
  
</style>
