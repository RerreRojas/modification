<template>
  <div class="container">
    <form class="form">
      <div>
        <span>Escribe un color de fondo en inglés</span>
        <input class="form-control" v-model="colorCuadrado" />
      </div>
      <div>
        <span>Escribe un color de letra en inglés</span>
        <input class="form-control" v-model="colorLetra" />
      </div>
      <div>
        <label>Mostrar texto</label>
        <input v-model="show" type="checkbox">
      </div>
      <div>
        <label for="customRange2" class="form-label">Borde</label>
        <input v-model="border" type="range" class="form-range" :min="minimo" :max="maximo" step="0.5"
          id="customRange2">
      </div>
      <div>
        <label>Contenido textual: </label>
        <textarea v-model="texto"></textarea>
      </div>
      <select v-model="typography">
        <option :key="tipografia" v-for="tipografia in tipografias" :value="tipografia">{{ tipografia }}</option>
      </select>
      <div>
        <label>Opaco</label>
        <input v-model="opaco" type="checkbox">
      </div>
      <div>
        <span>Tamaño de letra</span>
        <div class="form-check">
              <input class="form-check-input" type="radio" name="flexRadioDefault" id="p" value="0.5rem"
                v-model="size" />
              <label class="form-check-label fw-normal" for="p"> Pequeño </label>
            </div>
            <div class="form-check">
              <input class="form-check-input" type="radio" name="flexRadioDefault" id="m" value="1rem"
                v-model="size" />
              <label class="form-check-label fw-normal" for="m"> Mediano </label>
            </div>
            <div class="form-check">
              <input class="form-check-input" type="radio" name="flexRadioDefault" id="g" value="5rem"
                v-model="size" />
              <label class="form-check-label fw-normal" for="g"> Grande </label>
            </div>
      </div>
      


    </form>

    <div id="cuadrado"
      :style="{ background: colorCuadrado, color: colorLetra, borderRadius: radioCompleto, fontFamily: typography, fontSize: size, opacity: opaco,}">
      <h1 v-if="show"> {{ texto }}</h1>
    </div>


  </div>

</template>

<script>
export default {
  name: 'ModidicarCuadro',
  data() {
    return {
      colorCuadrado: "",
      colorLetra: "",
      show: "",
      border: "",
      minimo: "",
      maximo: "",
      texto: "",
      typography: "",
      opaco: "",
      size: "",
      tipografias: ["Times New Roman", "Georgia", "Arial", "Verdana", "Tahoma", "Sanvito", "Courier",],

    };
  },
  computed: {
    radioCompleto() {
      return this.border + "px"
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#cuadrado {
  height: 300px;
  width: 300px;
  
  

}
</style>
