<template>
  <div class="card w-70">
    <template v-if="elements.length">
      <component
        v-for="element in elements"
          :key="element.id"
          :="{value:element.value}"
          :is="'App-' + element.type"
      >
      
      </component>
    </template>
   
    <h2 v-else>Добавьте первый блок, чтобы увидеть результат</h2>
  </div>
</template>

<script>
import AppAvatar from "./elements/AppAvatar.vue";
import AppSubtitle from "./elements/AppSubtitle.vue";
import AppText from "./elements/AppText.vue";
import AppTitle from "./elements/AppTitle.vue";

export default {
  props: ["elements"],
  components: {
    AppAvatar,
    AppSubtitle,
    AppText,
    AppTitle,
  },

};
</script>

<style></style>
