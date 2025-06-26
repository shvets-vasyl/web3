<template>
  <section class="drive">
		<div class="wrap _container">
			<div class="title">
				<CommonSubtitle>
					<p class="p2">Tokenomics</p>
				</CommonSubtitle>

				<SvgDriveTitle class="title-svg" />
				<SvgDrivePlus class="plus-svg" />

				<h2 class="h2">
					<div>drive</div>
					<div>transparency</div>
					<div>and <span class="accent">growth</span></div>
				</h2>
			</div>

			<div class="content">
				<img class="decor" src="/images/drive-decor.png" alt="">
				<img class="coins" src="/images/coins.png" alt="">

				<div class="box-1">
					<a href="https://buy2.web3ai.com/" target="_blank">
						<CommonButton text="Buy $WAI" accent />
					</a>
					<a href="https://buy2.web3ai.com/" target="_blank">
						<CommonButton text="Whitepapper" grey />
					</a>
				</div>
				<div class="box-2">
					<SvgDriveItemsBg class="box-svg-mob" />
					<div v-for="item, i in items" :key="i" class="item">
						<p class="item-title p2">{{ item.title }}</p>
						<p class="item-text p2">
							<span>{{ item.text }}</span>
							<span>{{ item.percent }}</span>
						</p>
					</div>
				</div>

				<SvgDriveBg class="drive-bg" />
			</div>
		</div>
  </section>
</template>
<script setup lang="ts">
const items = [
	{
		title: "Presale",
		text: "75B $WAI",
		percent: "50%",
	},
	{
		title: "Liquidity & Ecosystem",
		text: "37.5B $WAI",
		percent: "25%",
	},
	{
		title: "Treasury & Rewards",
		text: "22.5B $WAI",
		percent: "20%",
	},
	{
		title: "Team & Strategic growth",
		text: "15B $WAI",
		percent: "5%",
	}
]
</script>
<style scoped lang="scss">
.drive {
  padding-top: 9.0625rem;
	@include mobile {
		padding-top: 4.8125rem;
	}
}
.title {
	position: relative;
	margin-bottom: 5.5rem;
	padding-left: calc(50% + .375rem);

	@include mobile {
		margin-bottom: 1.5rem;
		padding-left: 0;
	}
}
.title-svg {
	width: 3.75rem;
	margin-bottom: 1.5rem;
	position: relative;
}
.plus-svg {
	position: absolute;
	bottom: 0;
	right: 0;
	width: 1.375rem;
	@include mobile {
		width: 1rem;
		bottom: .3125rem;
	}
}
:deep(.subtitle) {
	position: absolute;
	left: 0;
	top: 0;
	@include mobile {
		left: auto;
		right: 0;
	}
}
:deep(.subtitle .p2) {
	@include mobile {
		font-size: .75rem;
	}
}
.box-1:deep(.btn-template) {
	width: 15.625rem;
	@include mobile {
		width: 100%;
	}
}
.content {
	position: relative;
}
.box-1 {
	position: absolute;
	bottom: 2rem;
	left: 0;
	display: flex;
	gap: .75rem;
	@include mobile {
		position: relative;
		bottom: 0;
		flex-direction: column;
		gap: 0.5rem;
	}
}
.coins {
	width: 33.5625rem;
	position: absolute;
	bottom: 6.0625rem;
	pointer-events: none;
	left: -2.5rem;

	@include mobile {
		position: relative;
		bottom: 0;
		left: 0;
		width: 22.6875rem;
		margin-left: -1.2rem;
	}
}
.box-2 {
	display: grid;
	grid-template-columns: 1fr 1fr;
	gap: .5rem;
	position: absolute;
	bottom: 2rem;
	right: 0;
	width: 46.75rem;

	@include mobile {
		position: relative;
		bottom: 0;
		width: 100%;
		grid-template-columns: 1fr;
		margin-top: 1rem;
	}
}
.item {
	display: flex;
	flex-direction: column;
	justify-content: center;
	padding: 0 1rem;
	height: 9.5rem;
	@include mobile {
		height: 5.75rem;
		padding: 1.5rem;
	}
}
.item-text {
	display: flex;
	justify-content: space-between;
	margin-top: .5rem;
}
.item-text span:nth-child(1) {
	color: var(--c-grey);
}
.item-text span:nth-child(2) {
	color: var(--c-accent);
	font-size: 1.25rem;
	@include mobile {
		font-size: 1rem;
	}
}
.decor {
	width: 27.125rem;
	position: absolute;
	bottom: 7rem;
	left: 7rem;
	pointer-events: none;
	opacity: 0.6;
	@include mobile {
		bottom: auto;
		top: 0;
		width: 21.9375rem;
		left: 0rem;
	}
}
.drive-bg {
	@include mobile {
		display: none;
	}
}
.box-svg-mob {
	display: none;
	@include mobile {
		display: block;;
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		pointer-events: none;
	}
}
</style>
