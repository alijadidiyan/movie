<template>
  <div class="card mt-3">
    <div class="card-body d-flex align-items-center gap-2">
      <span class="fw-bold">User Rating:</span>
      <div>
        <span
          v-for="n in 5"
          :key="n"
          @click="rate(n)"
          :class="n <= userRating ? 'text-warning' : 'text-secondary'"
          class="fs-4 me-1"
          role="button"
        >★</span>
      </div>
      <span class="text-muted ms-2">(Average: {{ average }})</span>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
// eslint-disable
defineProps(['average'])

const userRating = ref(0)
function rate(n) {
  userRating.value = n
  alert(`You rated ${n} stars!`)
}
</script>
