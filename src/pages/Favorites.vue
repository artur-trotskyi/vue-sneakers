<script setup>
import { onMounted } from 'vue'
import { useFavorites } from '@/composables/useFavorites'
import CardList from '../components/CardList.vue'

const { favorites, fetchFavorites, addToFavorite } = useFavorites()

onMounted(async () => {
  await fetchFavorites()
})
</script>

<template>
  <h2 class="text-3xl font-bold mb-8">Мои закладки</h2>

  <CardList :items="favorites" is-favorites @add-to-favorite="addToFavorite" />
</template>
