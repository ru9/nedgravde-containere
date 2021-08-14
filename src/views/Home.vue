<template>
  <v-container>
    <h1>Molberget v/ 130</h1>
    <v-container d-flex flex-wrap>
      <container
        v-for="container in containere"
        :key="container._id"
        :id="container._id"
        :fraction="container.FRACTION"
        :fullCount="container._full_count"
        :counter="container.COUNTER"
        :fillHeight="container.FILLHEIGHT"
      />
    </v-container>
  </v-container>
</template>

<script>
import container from "../components/container.vue";

export default {
  components: { container },

  data() {
    return {
      containere: [],
    };
  },

  created() {
    const axios = require("axios");
    axios
      .get(
        "https://opencom.no/api/3/action/datastore_search?resource_id=1207f3c9-d8a9-44f8-b320-154493b9157d&q=moldberget_v_130"
      )
      .then((response) => {
        console.log(response.data.result.records);
        this.containere = response.data.result.records;
      });
  },
};
</script>