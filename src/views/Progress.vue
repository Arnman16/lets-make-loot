<template>
  <v-container fill-height justify-center>
    <v-col>
      <v-row class="justify-center">
        <p class="text-center text-h4">Progress</p></v-row
      >
      <v-row class="justify-center"
        ><GChart
          type="ColumnChart"
          :data="chartData"
          :options="makeOptions('Loot Earned', 'Sales, Expenses, and Profit')"
      /></v-row>
      <v-row class="justify-center">
        <p class="text-center ma-5">Goal</p></v-row
      >
      <v-row class="justify-center">
        <GChart
          type="LineChart"
          :options="makeOptions('Profit Gained', 'In Canadian Dollars (CAD)')"
          :data="collectionData"
        />
      </v-row>
    </v-col>
  </v-container>
</template>

<script>
import { GChart } from "vue-google-charts";
export default {
  name: "Progress",
  components: {
    GChart,
  },
  computed: {
    chartWidth() {
      switch (this.$vuetify.breakpoint.name) {
        case "xs":
          return "90%";
        case "sm":
          return "90%";
        case "md":
          return 600;
        case "lg":
          return 700;
        case "xl":
          return 600;
        default:
          return 400;
      }
    },
  },
  data() {
    return {
      // Array will be automatically processed with visualization.arrayToDataTable function
      chartData: [
        ["Episode", "Sales", "Expenses", "Profit"],
        ["Episode 1", 1000, 400, 200],
        ["Episode 2", 1170, 460, 250],
        ["Episode 3", 660, 1120, 300],
        ["Episode 4", 1030, 540, 350],
      ],
      collectionData: [
        ["Day", "Sanity", "Profit"],
        ["Day 1", 90.5, 0],
        ["Day 2", 68.4, 0],
        ["Day 3", 47, 55.5],
        ["Day 4", 52, 14.5],
        ["Day 5", 30, 10.3],
        ["Day 6", 14.5, 6.7],
        ["Day 7", 11.2, 19.6],
      ],
    };
  },
  methods: {
    makeOptions(title, subtitle) {
      return {
        chart: {
          title: title,
          subtitle: subtitle,
        },
        backgroundColor: {
          fill: "#222",
          fillOpacity: 0.3,
        },
        legendTextStyle: { color: "#FFF" },
        titleTextStyle: { color: "#FFF" },
        hAxis: {
          textStyle: { color: "#FFF" },
        },
        vAxis: {
          textStyle: { color: "#FFF" },
        },
        width: this.chartWidth,
      };
    },
  },
};
</script>
<style scoped>
rect {
  background-color: black !important;
}
</style>
