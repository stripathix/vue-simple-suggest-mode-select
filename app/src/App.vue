<template>
  <div id="app">
    <auto-suggest
      id="input-live"
      v-model="model"
      value-attribute="id"
      mode="select"
      display-attribute="name"
      :list="simpleSuggestionList"
      @select="onSuggestSelect">
    </auto-suggest>
    <p v-if="selected">Selected element ({{ typeof selected }}): <pre class="selected hljs"><code v-html="selected"></code></pre></p>
      <p v-if="model">v-model ({{ typeof model }}): <pre class="selected hljs"><code v-html="model"></code></pre></p>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import AutoSuggest from './components/AutoSuggest.vue';
export default {
  name: 'app',
  components: {
    HelloWorld,
    AutoSuggest,
  },
  data() {
    return {
      selected: null,
      model: null,
    };
  },
  methods: {
    onSuggestSelect (suggest) {
      this.selected = suggest ? suggest.id : null;
    },
    simpleSuggestionList() {
      return [
        {name: 'Afghanistan', id: 'AF'},
        {name: 'Åland Islands', id: 'AX'},
        {name: 'Albania', id: 'AL'},
        {name: 'Algeria', id: 'DZ'},
        {name: 'American Samoa', id: 'AS'},
        {name: 'AndorrA', id: 'AD'},
        {name: 'Angola', id: 'AO'},
        {name: 'Anguilla', id: 'AI'},
        {name: 'Antarctica', id: 'AQ'},
        {name: 'Antigua and Barbuda', id: 'AG'},
        {name: 'Argentina', id: 'AR'},
      ];
    },
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
