<template>
  <form @submit.prevent="submitForm">
    <fieldset>
      <legend>Thông tin cá nhân</legend>

      <div class="form-group">
        <label for="name">Họ tên:</label>
        <input type="text" id="name" v-model="formData.name" />
      </div>

      <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="formData.email" />
      </div>

      <div class="form-group">
        <button type="submit">Lưu</button>
        <button type="button" @click="resetForm">Hủy</button>
      </div>
    </fieldset>
  </form>
</template>

<script setup lang="ts">
import { ref } from 'vue';

interface FormData {
  name: string;
  email: string;
}

const formData = ref<FormData>({ name: '', email: '' });
const originalFormData = { ...formData.value };

function submitForm() {
  // Do something with form data, e.g. submit to server
  console.log(formData.value);
}

function resetForm() {
  // Reset form data to original values
  formData.value = { ...originalFormData };
}
</script>

<style>
/* CSS styles for form */
</style>
