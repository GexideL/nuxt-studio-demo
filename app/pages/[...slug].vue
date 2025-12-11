<script setup lang="ts">
const route = useRoute()
const { data: page } = await useAsyncData(() => queryCollection('content').path(route.path).first())

useSeoMeta({
	title: page.value?.title,
})
</script>

<template>
	<div>
		<ContentRenderer :value="page" v-if="page" />
	</div>
</template>
