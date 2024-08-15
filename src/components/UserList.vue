<template>
    <div class="list">
        <h3 class=" text-2xl">{{ props.content.name }}</h3>
        <p>{{ props.content.age }} years</p>
        <p>{{ capitalize(props.content.position) }}</p>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'
import { capitalize } from '@/utils/stringUtils'

const props = defineProps(['content'])
</script>

<style lang="scss" scoped>
.list {
    width: 100vw;
    @apply text-white bg-orange-600 flex flex-row justify-center items-center gap-2 p-4
}
</style>
