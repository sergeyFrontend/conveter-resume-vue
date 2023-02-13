<template>
  <form @submit.prevent="submit" class="card w-30">
    <div class="form-control">
      <label for="type">Выбор блока</label>
      <select v-model="type" id="type">
        <option value="title">Заголовок</option>
        <option value="avatar">Аватарка</option>
        <option value="subtitle">Подзаголовок</option>
        <option value="text">Текст</option>
      </select>
    </div>
    <div class="form-control">
      <label for="value">Выберите значение</label>
      <textarea v-model="value" id="value" rows="3"></textarea>
    </div>

    <button class="btn primary" :disabled="!isValid">Создать</button>
  </form>
</template>

<script>
export default {
  emits:['add-element'],
  data() {
    return {
      type: "title",
      value: "",
    };
  },
  methods: {
    submit() {
       this.$emit("add-element", {
        type: this.type,
        value: this.value,
        id: new Date(),
      })
       this.type = "title";
       this.value = "";
    },
  },
  computed: {
    isValid() {
      return this.value.length > 3;
    },
 
   },
 
};
</script>

<style></style>
