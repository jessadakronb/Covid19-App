<template>
  <select
    @change="onChange()"
    v-model="selected"
    class="form-select mt-1 block w-full border p-3 rounded"
  >
    <option value="0">Select Country</option>
    <option
      v-for="(country, key) in countries"
      v-bind:key="key"
      :value="country.ID"
    >
      {{ country.Country }}
    </option>
  </select>

</template>

<script>
export default {
  name: "CountrySelect",
  props: ["countries"],
  data() {
    return {
      selected: 0,
    };
  },
  created() {
    console.log("countries:", this.countries);
  },
  methods: {
    onChange() {
      const country = this.countries.find((item) => item.ID === this.selected);
      console.log("Change:", country);
      this.$emit("get-country", country);
    },
  },
};
</script>

<style></style>
