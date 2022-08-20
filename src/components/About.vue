<template>
  <div class="hello">
    <label>About</label>
    <select  v-model="$i18n.locale" class="nav__lang-switcher">
  <option v-for="(lang, i) in ['en','in']" :key="`lang${i}`"
   :value="lang">{{lang}}</option>
</select>
    {{ count }}
  </div>
</template>

<script>
import { computed } from 'vue';
import { useStore } from 'vuex';

export default {
  name: 'HelloWorld',
  setup() {
    const store = useStore();
    const count = computed(() => store.state.count);
    return {
      count,
      store,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
