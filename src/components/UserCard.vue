<template>
    <div class="card">
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
.card {
    @apply w-40 text-white bg-blue-700 p-3 flex flex-col rounded-lg;
    
}    
</style>

