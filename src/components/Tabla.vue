<template>
  <div class="row">
    <div class="container">
      <div class="inputs">
        <Input campo="Concepto" id="concep" />
        <Input campo="Precio" id="prec" expresion="^[0-9]+([.][0-9]+)?$" />
        <Input campo="Cantidad" id="cant" expresion="[0-9]" />
        <button @click="agregar">Agregar</button>
      </div>
    </div>
  </div>

  <table class="tabla">
    <thead>
      <tr>
        <th>indice</th>
        <th>concepto</th>
        <th>precio</th>
        <th>cantidad</th>
        <th>subtotal</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(producto, i) in datos" :key="i">
        <td>{{ i + 1 }}</td>
        <td>{{ producto.concepto }}</td>
        <td>{{ producto.precio }}</td>
        <td>{{ producto.cantidad }}</td>
        <td>{{ subTotal(producto.precio, producto.cantidad) }}</td>
      </tr>
    </tbody>
  </table>
  <div class="total">
    <div colspan="3">
      TOTAL: <span>{{ total }}</span>
    </div>
  </div>
</template>

<script>
import { ref, reactive, onMounted } from "vue";
import Input from "@/components/Input";

export default {
  name: "Tabla",
  components: {
    Input,
  },
  props: {},
  setup() {
    const datos = reactive([
      { concepto: "pantalones", cantidad: 2, precio: 30 },
      { concepto: "gorro", cantidad: 1, precio: 7 },
      { concepto: "zapatillas", cantidad: 4, precio: 30 },
      { concepto: "sudadera", cantidad: 2, precio: 10 },
      { concepto: "camiseta", cantidad: 5, precio: 12 },
    ]);
    let total = ref(0);
    const subTotal = (cant, precio) => cant * precio;
    const calcTotal = () => {
      datos.forEach(
        (producto) => (total.value += producto.cantidad * producto.precio)
      );
    };
    const agregar = () => {
      let nuevo = {
        concepto: concep.lastChild.lastChild.value,
        cantidad: cant.lastChild.lastChild.value,
        precio: prec.lastChild.lastChild.value,
      };

      datos.push(nuevo);
      total.value = 0;
      calcTotal();
    };

    onMounted(() => calcTotal());
    return {
      datos,
      subTotal,
      total,
      agregar,
    };
  },
};
</script>

<style lang="scss">
.inputs {
  display: flex;
  margin: 0 auto;
  margin-top: 20px;
  padding: 20px;
  border-radius: round;
  border-style: double;
  border-color: black;
  color: black;
  background-color: darkslateblue;
  font-size: medium;
  font-weight: bold;
  width: 60%;
  align-content: center;
}

.total {
  border: 1px solid black;
  background-color: black;
  width: 20%;
  color: orange;
  margin: 0 auto;
  margin-top: 20px;
}
.tabla {
  margin: 0 auto;
  margin-top: 20px;

  th {
    border: 1px solid black;
    background-color: black;
    color: orange;
  }
  td {
    border: 1px solid black;
  }
}
</style>