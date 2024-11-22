<script>
import axios from "axios";
export default {
  data() {
    return {
      selectedArchetype: "",
    };
  },
  props: {
    archetypesList: {
      type: Array,
      required: true,
    },
  },
  methods: {
    onArchetypeChange() {
      this.$emit("archetype-changed", this.selectedArchetype);
    },
  },
};
</script>
<template>
  <select
    class="form-select mb-4"
    v-model="selectedArchetype"
    @change="onArchetypeChange"
  >
    <option value="">Tutti gli Archetypes</option>
    <option
      v-for="archetype in archetypesList"
      :key="archetype.archetype_name"
      :value="archetype.archetype_name"
    >
      {{ archetype.archetype_name }}
    </option>
  </select>
</template>

<style lang="scss" scoped>
@use "bootstrap/scss/bootstrap.scss" as *;
select.form-select {
  background-color: white;
}
</style>
