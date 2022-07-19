<template>
  <h1>Dahsboard</h1>
  <v-table fixed-header height="300px">
    <thead>
      <tr>
        <th class="text-left">Name</th>
        <th class="text-left">Calories</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="item in desserts" :key="item.name" @click="onSelectRow(item)">
        <td>{{ item.name }}</td>
        <td>{{ item.calories }}</td>
      </tr>
    </tbody>
  </v-table>
  <v-snackbar v-model="snackbar" color="info" dark>
    {{ selectedDessert.name }}
    <template v-slot:actions>
      <v-btn variant="text" @click="snackbar = false"> Close </v-btn>
    </template>
  </v-snackbar>
</template>
<script>
export default {
  data() {
    return {
      snackbar: false,
      selectedDessert: null,
      desserts: [
        {
          name: "Frozen Yogurt",
          calories: 159,
        },
        {
          name: "Ice cream sandwich",
          calories: 237,
        },
        {
          name: "Eclair",
          calories: 262,
        },
        {
          name: "Cupcake",
          calories: 305,
        },
        {
          name: "Gingerbread",
          calories: 356,
        },
        {
          name: "Jelly bean",
          calories: 375,
        },
        {
          name: "Lollipop",
          calories: 392,
        },
        {
          name: "Honeycomb",
          calories: 408,
        },
        {
          name: "Donut",
          calories: 452,
        },
        {
          name: "KitKat",
          calories: 518,
        },
      ],
    };
  },
  methods: {
    onSelectRow(item) {
      this.snackbar = true;
      this.selectedDessert = item;
    },
  },
};
</script>
