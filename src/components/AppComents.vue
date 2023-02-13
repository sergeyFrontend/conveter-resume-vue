<template>
  <div class="card" v-if="coments.length">
    <h2>комментарии !</h2>
    <ul class="list">
      <li class="list-item" v-for="coment in coments" :key="coment.id">
        <p>
          <strong>{{ coment.email }}</strong>
        </p>
    
        <small>{{ coment.body }}</small>
      </li>
    </ul>
  </div>
  <div>
    <button class="btn primary" @click="$emit('load')">
       комментарии !!!
    </button>
  </div>
</template>

<script>
export default {
  emits: ["load"],
  props: ["coments"],
};
</script>

<style></style>
