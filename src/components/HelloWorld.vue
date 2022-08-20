<template>
  <div class="hello">
    <label>{{$t('hello')}}</label>
    <select  v-model="$i18n.locale" class="nav__lang-switcher">
  <option v-for="(lang, i) in ['en','in']" :key="`lang${i}`"
   :value="lang">{{lang}}</option>
</select>
    {{ count }}
 <button @click="store.commit('INCREMENT_COUNT', 1)">Increment</button>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
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
