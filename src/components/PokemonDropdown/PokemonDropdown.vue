<script>
export default {
  props: {
    categories: Array,
    selectHandler: Function,
  },
};
</script>
<template>
  <label for="dropdown">
    <select id="dropdown" @change="selectHandler">
        <option
            v-for='(category, index) in categories'
            v-bind:key='index'
            v-bind:value='category'
            >
            {{category}}
        </option>
    </select>
  </label>
</template>
