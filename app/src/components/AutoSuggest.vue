<template>
  <vue-simple-suggest
      :value="value"
      :styles="autoCompleteStyle"
      v-bind="$attrs"
      v-on="$listeners"
      autocomplete="off"
      :filter-by-query="true">
  </vue-simple-suggest>
</template>
<script>
import 'vue-simple-suggest/dist/styles.css'
import vueSimpleSuggest  from 'vue-simple-suggest';

export default {
  components: {
    vueSimpleSuggest,
  },
  inheritAttrs: false,
  props: {
    value: {
      type: String,
      default: null,
    },
  },
  data() {
    return {
      autoCompleteStyle: {
        vueSimpleSuggest: 'position-relative',
        inputWrapper: '',
        defaultInput : 'form-control',
        suggestions: 'dropdown-menu show',
        suggestItem: 'dropdown-item'
      },
    };
  },
};
</script>
