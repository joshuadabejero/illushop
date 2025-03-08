<script setup>
import Icon from "./Icon.vue";

const props = defineProps({
  brand: { type: String, default: "MyApp" },
  links: {
    type: Array,
    default: () => [
      { name: "Home", href: "/" },
      { name: "About", href: "/about" },
      { name: "Services", href: "/services" },
      { name: "Contact", href: "/contact" },
    ],
  },
});

const isOpen = ref(false);
</script>

<template>
  <nav class="bg-white-800 p-4 text-black">
    <div class="container mx-auto flex justify-between items-center">
      <div class="brand text-lg font-bold">{{ brand }}</div>

      <button @click="isOpen = !isOpen" class="md:hidden">
        <Icon name="Menu" size="24" />
      </button>

      <ul
        :class="['md:flex md:space-x-4', isOpen ? 'block' : 'hidden']"
        class="absolute md:static bg-white-800 w-full left-0 top-14 md:w-auto"
      >
        <li v-for="(link, index) in links" :key="index">
          <NuxtLink :to="link.href" class="block p-2">{{ link.name }}</NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
nav {
  .container {
    .brand {
      background-color: #ff9b50;
    }
  }
}
</style>
