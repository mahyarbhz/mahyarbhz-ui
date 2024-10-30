<script setup lang="ts">
	const { data: ping } = await useFetch('http://localhost:8000/api/ping')
</script>

<template>
	<div>
		Testing api:
		We say ping!
		They say:
		{{ ping }}
	</div>
</template>