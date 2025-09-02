<script setup>
import { inject } from 'vue'

const notificationState = inject('notificationState')
</script>

<template>
  <div v-if="notificationState.isShow" class="position-fixed top-0 end-0 p-3" style="z-index: 1050">
    <div
      :class="[
        'toast show align-items-center text-white border-0',
        notificationState.type === 'success' ? 'bg-success' : 'bg-danger',
      ]"
    >
      <div class="d-flex">
        <div class="toast-body">{{ notificationState.message }}</div>
        <button type="button" class="btn-close btn-close-white me-2 m-auto"></button>
      </div>
    </div>
  </div>
</template>
