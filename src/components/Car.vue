<template>
  <h2>Car</h2>
  <p>Marca: {{fabricante}} </p>
  <p>Model:{{model}}</p> 
  <p>V-For en bucle</p>
 <p>Color:
     <span v-for="(color, index) in color_Array" :key="index">
        {{index}}- {{color+' '}} 
     </span>
 </p>
 <ul>
     <p>V-For en lista</p>
     <li v-for="(color, index) in color_Array" :key="index">
          {{index}}- {{color+' '}} 
     </li>
 </ul>
  <p>Tipo_Objeto: {{objeto_msg.titulo}} - {{objeto_msg.texto}}      
     </p>

    <p>Totas las potencias</p>
     <p>
         
         <span v-for="(cc, index) in potencias" :key="index">
            {{cc+', '}} 
         </span>
        
     </p>
     <!--
    <p>Potencias para uso urbano menor de 400cc</p>
    
        <template v-for="(cc, index) in potencias" :key="index">
            <li v-if="cc < 500">
                {{cc}}
            </li>
            
        </template>
-->
    <p>Potencias y sus usos</p>

      <template v-for="(cc, index) in potencias" :key="index">
            <li v-if="cc < 500">Uso Urbano {{cc}}</li>
            <li v-else-if="cc ===500">Hibrida {{500}}</li>
            <li v-else>Uso Ilimitado {{cc}}</li>
            
        </template>
    
    
    
</template>

<script>


export default {
 /*   data() {
        return {
            fabricante: "Audi",
            model: "Q5",
            // color: "Blanco",
            color_Array: ['azul', 'gris', 'blanco', 'negro'],
            precio: "35000 Euros",
            // objeto
            objeto_msg: {
                titulo:"Hola Audi",
                texto: "Adios",
            },

        };
    },
   */ 

  setup (){
      const fabricante = 'Audi';
      const model = " Q5";
      const color_Array = ['Amarillo','azul', 'gris', 'blanco', 'negro'];
      const potencias = [125, 250, 300, 400, 500, 650, 750, 850, 950, 1000, 1100, 1200];
      const objeto_msg = {
                titulo:"Esto es un Objeto",
                texto: "Texto del Objeto",
            };

      return {
          fabricante,
          model,
          color_Array,
          objeto_msg,
          potencias,
          
      }
  }
};

</script>

<style>

</style>