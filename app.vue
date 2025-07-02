<template>
  <div class="layout">
    <NuxtPage />
  </div>
</template>

<script setup lang="ts">

const initAnim = () => {
	const titles = document.querySelectorAll(".text-anim")

	titles.forEach((el) => {
		ScrollTrigger.create({
			trigger: el,
			animation: gsap.from(el, {
				y: "1rem",
				opacity: 0,
				duration: 1,
				delay: 0.1
			})
		})
	})
}
onMounted(() => {
	initAnim()
})
</script>
<style lang="scss" scoped></style>
