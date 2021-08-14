<template>
  <v-flex xs6 sm4 xl2>
    <v-card class="text-center ma-3">
      <v-card-title class="justify-center">{{ fraction }}</v-card-title>

      <v-card-text class="hidden-md-and-up"
        ><v-progress-circular
          :rotate="-90"
          :size="120"
          :width="60"
          :value="fullCount * 10"
          :color="barColor(fraction)"
        >
        </v-progress-circular>
        <v-card-text>
          Id: {{ id }} <br />
          Full Count: {{ fullCount }} <br />
          Counter: {{ counter }} <br />
          Fill Height: {{ fillHeight }}
        </v-card-text>
      </v-card-text>

      <v-card-text class="hidden-sm-and-down"
        ><v-progress-circular
          :rotate="-90"
          :size="220"
          :width="30"
          :value="fullCount * 10"
          :color="barColor(fraction)"
        >
          Id: {{ id }} <br />
          Full Count: {{ fullCount }} <br />
          Counter: {{ counter }} <br />
          Fill Height: {{ fillHeight }}
        </v-progress-circular></v-card-text
      >
    </v-card>
  </v-flex>
</template>

<script>
export default {
  props: {
    fraction: String,
    fullCount: String,
    counter: String,
    fillHeight: String,
    id: Number,
  },

  mounted() {},
  methods: {
    barColor(n) {
      if (n == "Papir") {
        return "blue";
      } else if (n == "Bio") {
        return "brown";
      } else if (n == "Glass/metall") {
        return "orange";
      } else {
        return "black";
      }
    },
  },
};
</script>