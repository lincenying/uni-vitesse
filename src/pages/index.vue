<template>
    <div>
        <TheLogo />
        <div py-32px />
        <TheInput v-model:value="name" placeholder="What's your name?" />
        <div>
            <button m-24px text-sm btn :disabled="!name" @click="router.push(`/hi?name=${name}`)"> Go </button>
        </div>
    </div>
</template>

<script setup lang="ts">
const name = $ref('')

async function getData() {
    const data = await $api.get('api/index/getLeftTop')
    console.log(data)
}

getData()
</script>

<route lang="yaml">
layout: home
</route>
