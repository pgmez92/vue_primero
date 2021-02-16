<template>
  <div>
    <select name="provincia" id="prov" @change="ver">
      <option
        v-for="(Provincias, i) in ArrProv"
        :key="i"
        :value="Provincias.nm"
      >
        {{ Provincias.nm }}
      </option>
    </select>
    <select name="municipio" id="mun">
      <option v-for="(item, i) in select_mun" :key="i" :value="item">
        {{ item.nm }}
      </option>
    </select>
  </div>
  <div>
    <img src="@/assets/sun.png" alt="solecito" />
  </div>
</template>


<script>
import Provincias from "@/assets/models/Provincias.json";
import Municipios from "@/assets/models/Municipios.json";
import { reactive } from "vue";

export default {
  name: "Select",
  setup() {
    let select_mun = reactive([]);
    const ver = () => {
      select_mun = [];
      let valor_busqueda = prov.value;
      let id_prov = Provincias.find((province) => province.nm == valor_busqueda)
        .id;
      Municipios.filter((muni) => {
        if (muni.id.substring(0, 2) == id_prov) {
          select_mun.push(muni.nm);
        }
      });
      console.log(select_mun);
      return select_mun;
    };

    return {
      ver,
      ArrProv: Provincias,
    };
  },
};
</script>

<style>
</style>