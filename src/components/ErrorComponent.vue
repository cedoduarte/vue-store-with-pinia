<template>
    <div v-if="message" class="alert alert-warning alert-dismissible fade show" role="alert">
        <strong>{{ message }}</strong>
        <button @click="errorStore.resetMessage" type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
    </div>
</template>

<script setup lang="ts">
import { storeToRefs } from 'pinia';
import { useErrorStore } from '../store/error';

const errorStore = useErrorStore();
const { message } = storeToRefs(errorStore);
</script>