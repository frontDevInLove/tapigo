<template>
  <div class="max-w-md mx-auto mt-10 px-4">
    <form @submit.prevent="handleSubmit" class="flex flex-col space-y-4">
      <input
        v-model="form.fullName"
        @blur="validateFullName"
        type="text"
        placeholder="ФИО"
        class="input"
        :class="{ 'border-red-500': errors.fullName }"
      />
      <div v-if="errors.fullName" class="text-red-500 text-sm">
        {{ errors.fullName }}
      </div>

      <input
        v-model="form.phone"
        @blur="validatePhone"
        type="tel"
        placeholder="Номер телефона"
        class="input"
        :class="{ 'border-red-500': errors.phone }"
      />
      <div v-if="errors.phone" class="text-red-500 text-sm">
        {{ errors.phone }}
      </div>

      <input
        v-model="form.email"
        @blur="validateEmail"
        type="email"
        placeholder="Email"
        class="input"
        :class="{ 'border-red-500': errors.email }"
      />
      <div v-if="errors.email" class="text-red-500 text-sm">
        {{ errors.email }}
      </div>

      <input
        v-model="form.password"
        @blur="validatePassword"
        type="password"
        placeholder="Пароль"
        class="input"
        :class="{ 'border-red-500': errors.password }"
      />
      <div v-if="errors.password" class="text-red-500 text-sm">
        {{ errors.password }}
      </div>

      <button :disabled="isFormInvalid" class="btn">Отправить</button>
    </form>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

// Определение интерфейса для объекта errors
interface Errors {
  fullName: string | null;
  phone: string | null;
  email: string | null;
  password: string | null;
}

const form = ref({
  fullName: "",
  phone: "",
  email: "",
  password: "",
});

const errors = ref<Errors>({
  fullName: null,
  phone: null,
  email: null,
  password: null,
});

const validateFullName = () => {
  errors.value.fullName =
    /^[А-Яа-яёЁ\s]+$/u.test(form.value.fullName) &&
    form.value.fullName.trim().split(/\s+/).length === 2
      ? null
      : "Неверный формат ФИО.";
};

const validatePhone = () => {
  errors.value.phone = /^\+7[0-9]{10}$/.test(form.value.phone)
    ? null
    : "Номер должен начинаться с +7 и содержать 11 цифр.";
};

const validateEmail = () => {
  errors.value.email = /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(form.value.email)
    ? null
    : "Неверный формат email.";
};

const validatePassword = () => {
  errors.value.password = /^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$/.test(
    form.value.password,
  )
    ? null
    : "Пароль должен содержать минимум 8 символов, включая буквы и цифры.";
};

const isFormInvalid = computed(() => {
  return Object.values(errors.value).some((error) => error !== null);
});

const handleSubmit = () => {
  // Логика отправки формы
  if (isFormInvalid.value) {
    return;
  }

  alert("Форма отправлена");
};
</script>

<style scoped>
.input {
  @apply px-4 py-2 border rounded;
}
.input:focus {
  @apply outline-none border-blue-500;
}
.btn {
  @apply px-4 py-2 bg-blue-500 text-white rounded cursor-pointer disabled:bg-blue-300;
}
</style>
