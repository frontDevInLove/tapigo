<template>
  <div class="Container">
    <div class="Wrapper">
      <div
        class="Card"
        v-for="n in 3"
        :key="n"
        :class="{ 'Card--reverse': n % 2 }"
      >
        <img src="/assets/images/img_1.png" alt="" class="Card__img" />

        <div class="Card__wrapper">
          <div class="Card__content">
            <h3 class="Card__title">We make films that stick in your heart</h3>

            <p class="Card__description">
              This exclusive service provided by our team of professional
              content creators is available for global use. Our clients will
              have access to standout creative control throughout the process of
              production, with resources and talent supplied by us.
            </p>

            <a href="#" class="Card__link">I have an idea for film →</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
// Скриптовая часть, если нужна логика
</script>

<style scoped lang="scss">
.Container {
  @apply bg-gray-900 px-4 py-5;
  @apply lg:py-36;
}

.Wrapper {
  @apply max-w-screen-2xl mx-auto;

  > *:not(:first-child) {
    @apply mt-32;
  }
}

.Card {
  @apply grid grid-cols-1;
  @apply lg:grid-cols-2 lg:gap-16;

  &--reverse {
    .Card__img {
      @apply lg:order-last;
    }

    .Card__content {
      &::before {
        @apply top-0 left-0 border-b-0 border-r-0 rounded-tl-xl;
      }

      &::after {
        @apply bottom-0 right-0 border-t-0 border-l-0 rounded-br-xl;
      }
    }
  }

  &__img {
    @apply w-full;
  }

  &__wrapper {
    @apply lg:flex lg:items-center;
  }

  &__content {
    @apply lg:px-12 lg:py-8 relative;

    &::before,
    &::after {
      content: "";
      @apply absolute w-12 h-12 border border-solid border-gray-500 hidden;
      @apply lg:block;
    }

    .Card:not(.Card--reverse) &::before {
      @apply top-0 right-0 border-b-0 border-l-0 rounded-tr-xl;
    }

    .Card:not(.Card--reverse) &::after {
      @apply bottom-0 left-0 border-t-0 border-r-0 rounded-bl-xl;
    }
  }

  &__title {
    @apply mt-8 text-3xl text-gray-50;
    @apply lg:text-5xl lg:mt-0;
  }

  &__description {
    @apply mt-4 text-gray-200 text-lg;
    @apply lg:text-xl;
  }

  &__link {
    @apply mt-8 text-lg inline-block text-transparent;
    background: linear-gradient(45deg, rgb(99, 102, 241), rgb(172, 84, 241));
    background-clip: text;
    color: transparent;

    &:hover {
      background: linear-gradient(45deg, #f44336, #8bc34a);
      background-clip: text;
    }
  }
}
</style>
