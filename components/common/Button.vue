<template>
  <span class="btn-template p1" :class="{ accent, grey }">
		<SvgButtonTemplateAccent v-if="accent" class="desk" />
		<SvgButtonTemplateAccentMob v-if="accent" class="mob" />
		<SvgButtonTemplateGrey v-if="grey" class="desk" />
		<SvgButtonTemplateGreyMob v-if="grey" class="mob" />

    <span class="text">{{ text }}</span>
  </span>
</template>
<script setup lang="ts">
defineProps<{
  accent?: boolean;
  grey?: boolean;
  text: string;
}>();
</script>
<style scoped lang="scss">
.btn-template {
  font-family: var(--font-medium);
  font-size: 1rem;
  line-height: 100%;
  width: 16.25rem;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
	transition: all .3s ease;
	text-transform: uppercase;
	@include mobile {
		width: 100%;
		font-size: .875rem;
	}
}
@include hover {
	.btn-template:hover {
		opacity: 0.5;
	}
}
.btn-template.accent {
	color: var(--c-black);
}
.btn-template.grey {
	color: var(--c-white);
}
.text {
  position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
}
</style>
