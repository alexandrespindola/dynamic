<template>
    <h1 class="text-center">Component List</h1>
    <div class="conteiner">
        <UserList v-for="item in props.content" :key=item.name :content="item" />
    </div>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue'
import UserList from '@/components/UserList.vue'

const props = defineProps(['content'])
</script>

<style lang="scss" scoped>
.conteiner {
width: 100vw;
display: flex;
flex-direction: column;
justify-content: space-around;
align-items: center;
}
</style>