<template>
    <form class="form-component mx-auto my-3" @submit.prevent="processForm">
        <ErrorComponent />
        <input required v-model="name" type="text" placeholder="Enter task" class="form-control" />
    </form>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { useTaskStore } from "../store/tasks";
import ErrorComponent from "./ErrorComponent.vue";

const name = ref<string>("");
const { createTask } = useTaskStore();

const processForm = () => {
    createTask(name.value);
    name.value = "";
}
</script>

<style scoped>
.form-component {
    width: 350px;
}
</style>