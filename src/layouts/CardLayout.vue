<template>
    <h1 class="text-center">Component Card</h1>
    <div class="conteiner">
        <UserCard v-for="item in props.content" :key=item.name :content="item" />
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'
import UserCard from '@/components/UserCard.vue'

const props = defineProps(['content'])
</script>

<style lang="scss" scoped>
.conteiner {
    width: 100vw;
    display: flex;
    justify-content: space-around;
    align-items: flex-start;
    flex-wrap: wrap
}
</style>