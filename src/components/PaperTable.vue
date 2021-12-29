<template>
  <table class="table" :class="tableClass">
    <thead>
      <slot name="columns">
        <th v-for="column in columns" :key="column">{{ column }}</th>
      </slot>
    </thead>
    <tbody>
      <tr v-for="(item, index) in data" :key="index">
        <slot :row="item">
          <td v-for="(column, index) in columns" :key="index">
            <div v-if="!isTitle(column)">{{ itemValue(item, column) }}</div>
            <div v-else>
              <a target="_blank" :href="getURL(item)">{{
                itemValue(item, column)
              }}</a>
            </div>
            <div v-if="isScore(item, column)">
              <input placeholder="Input score from 0 to 5" />
            </div>
            <div v-if="isAction(item, column)">
              <p-button type="info" round>Submit</p-button>
            </div>
          </td>
        </slot>
      </tr>
    </tbody>
  </table>
</template>
<script>
export default {
  name: "paper-table",
  props: {
    columns: Array,
    data: Array,
    type: {
      type: String, // striped | hover
      default: "striped",
    },
    title: {
      type: String,
      default: "",
    },
    subTitle: {
      type: String,
      default: "",
    },
  },
  computed: {
    tableClass() {
      return `table-${this.type}`;
    },
  },
  data: () => ({
    rating: 4,
  }),
  methods: {
    getURL(item) {
      return item["url"] || "";
    },
    isTitle(column) {
      return column.toLowerCase() === "title";
    },
    isScore(item, column) {
      if (item["score"] >= 0) return false;
      return column.toLowerCase() === "score";
    },
    isAction(item, column) {
      if (item["score"] >= 0) return false;
      return column.toLowerCase() === "action";
    },

    itemValue(item, column) {
      return item[column.toLowerCase()];
    },
  },
};
</script>
<style>
</style>
