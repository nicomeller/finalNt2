<template>
  <div>
    <hr />
    <table border="2">
      <tr>
        <th>Preguntas</th>
        <th>Respuestas</th>
      </tr>
      <tr>
        <td>1.¿Que es Axios?</td>
        <td>b.Es una biblioteca de cliente http</td>
      </tr>
      <tr>
        <td>2.Con Axios se pueden implementar los verbos</td>
        <td>c.Get, Post, Put y Delete</td>
      </tr>
      <tr>
        <td>3.¿Que es Vuex?</td>
        <td>b.Es una librería que maneja el estado de nuestras aplicaciones</td>
      </tr>
      <tr>
        <td>4.Las acciones en su implementación permiten lógica ...</td>
        <td>d.Asincrónica y sincrónica</td>
      </tr>
      <tr>
        <td>5.Las mutaciones...</td>
        <td>
          d. Alteran directamente el estado de nuestra aplicación
        </td>
      </tr>
    </table>
  </div>

  <section class="src-components-texto">
    <div>
      <table border="1">
        <thead>
          <label for="text">
            <strong>Color del texto:</strong>
          </label>
          <input type="text" id="text" class="form-control" v-model="color" />

          <label for="text">
            <strong>Color de Fondo:</strong>
          </label>
          <input type="text" id="text" class="form-control" v-model="fondo" />
          <label for="text">
            <strong>Tamaño de la letra: </strong>
          </label>
          <input type="text" id="text" class="form-control" v-model="size" />
        </thead>
        <tbody>
          <label for="text">
            <strong>Ingrese el texto:</strong>
          </label>
          <input
            type="text"
            id="text"
            class="form-control"
            v-model="texto"
            :style="{
              color: color,
              'background-color': fondo,
              'font-size': size,
            }"
          />
          <p v-if="calPal >= 1">La cantidad total de palabras: {{ calPal }}</p>

        </tbody>
      </table>
    </div>
  </section>
</template>

<script>
export default {
  name: "src-components-texto",
  props: [],
  mounted() {},
  data() {
    return {
      texto: "Ingrese aquí las palabras:",
      color: "black",
      fondo: "white",
      size: "12px",
    };
  },
  methods: {},
  computed: {
    calPal() {
      let text = this.texto.trim();
      let totalPalabras = 0;
      if (text != "") {
        let espacios = /[ ]+/g;
        text = text.replace(espacios, " ");
        let auxiliar = text.split(" ");
        
        totalPalabras = auxiliar.length;
      }

      return totalPalabras;
    },
  },
};
</script>

<style scoped lang="css">
.src-components-texto {
}
</style>
