<template>
  <div class="container column">
    <AppForm @add-element="addElement" />
    <AppViews  :elements="elements"/>
 </div>


<div class="container">
   <AppLoader v-if="loading" />
    <AppComents v-else :coments="coments" @load="loadComents" />
</div>
 
</template>

<script>
import AppLoader from "./components/AppLoader.vue";
import AppComents from "./components/AppComents.vue";
import AppForm from './components/AppForm.vue';
import AppViews from './components/AppViews.vue'

export default {
  components: {
    AppLoader,
    AppComents,
    AppViews,
    AppForm
  },
  data() {
    return {
      loading: false,
      coments: [],
      elements:[]
    };
  },
  methods: {
    async loadComents() {
      this.loading = true;
      const response = await fetch(
        "https://jsonplaceholder.typicode.com/comments?_limit=42"
      );
      this.coments = await response.json();
      this.loading = false;
    },
    addElement(element){
     this.elements.push(element)
     console.log(element.value)
    }
  },
};
</script>

<style></style>
