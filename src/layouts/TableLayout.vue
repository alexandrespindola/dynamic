<template>
    <h1 class="text-center">Component Table</h1>
    <div class="conteiner">
        <UserRow v-for="item in props.content" :key=item.name :content="item" />
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'
import UserRow from '@/components/UserRow.vue'

const props = defineProps(['content'])
</script>

<style lang="scss" scoped>
.conteiner {
width: 100vw;
display: flex;
justify-content: space-around;
align-items: center;
flex-wrap: wrap
}
</style>