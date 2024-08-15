<template>
    <div class="table">
        <h3 class=" text-2xl">{{props.content.name}}</h3>
        <p>{{props.content.age}} years</p>
        <p>{{capitalize(props.content.position)}}</p>
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'
import { capitalize } from '@/utils/stringUtils'

const props = defineProps(['content'])
</script>

<style lang="scss" scoped>
.table {
    width: 100vw;
    @apply text-white bg-gray-600 flex flex-row justify-center items-center gap-10 p-4
}    

h3, p {
    @apply w-40 text-center
}
</style>