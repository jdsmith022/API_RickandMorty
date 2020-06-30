<template>
  <div class="character-filter">
    <div class="filter-content box filter-box">
      <div class="filter-text">
        <p>
          Filter by character status:
        </p>
      </div>
      <div class="select is-rounded">
        <select v-model="selected" @change="getFilter">
          <option
            v-for="(option, index) in options"
            v-bind:value="option.value"
            v-bind:key="index"
          >
            {{ option.text }}
          </option>
        </select>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CharacterFilter",
  data() {
    return {
      selected: "Alive",
      options: [
        { text: "Alive", value: "Alive" },
        { text: "Dead", value: "Dead" },
        { text: "Unknown", value: "unknown" }
      ]
    };
  },
  methods: {
    getFilter: function() {
      this.$emit("statusChange", this.selected);
    }
  }
};
</script>
