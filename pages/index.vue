<template>
  <main class="main-page">
		<MainHero />
		<!-- <MainJoin /> -->
		<MainDrive class="text-anim" />
		<MainSum class="text-anim" />
		<MainPotential class="text-anim" />
		<MainPartners class="text-anim" />
		<MainFooter class="text-anim" />
  </main>
</template>
<script setup lang="ts">
onMounted(() => {
	gsap.to(".main-page", {
		opacity: 1,
	})
})
</script>
<style scoped lang="scss">
.main-page {
	overflow: hidden;
	position: relative;
	opacity: 0;
}
</style>
