<template>
	<section class="potential">
		<div class="wrap _container">
			<div class="title">
				<SvgDriveTitle class="title-svg" />
				<h2 class="h2">
					<div>Unlocking</div>
					<div>the Full <br class="mob" />Potential</div>
					<div>of <span class="accent">Your Token</span></div>
				</h2>

				<CommonSubtitle>
					<p class="p2">Token Utility</p>
				</CommonSubtitle>
			</div>

			<div class="box">
				<SvgPotentialBox class="desk" />
				<SvgPotentialBoxMob class="mob" />

				<div class="items">
					<div v-for="item, i in items" :key="i" class="item">
						<div class="title-wrap">
							<h3 class="h3 item-title" v-html="item.title" />
							<p class="item-count p1">0{{ i + 1 }}</p>
						</div>

						<img class="item-img" :src="item.image" alt="">
						<p class="p1 item-descr">{{ item.descr }}</p>
					</div>
				</div>

				<div class="counts">
					<p class="p2">01</p>
					<p class="p2">02</p>
					<p class="p2">03</p>
				</div>
			</div>
		</div>
	</section>
</template>
<script setup lang='ts'>
const items = [
	{
		title: "Use $WAI within <br />the project",
		descr: "Use $WAI to pay for Web3 AI product subscriptions for access to advanced features like AI analytics and trading signals, and receive discounts.",
		image: "/images/potential-1.png"
	},
	{
		title: "Receive Web3 AI<br />revenue share",
		descr: "Stake $WAI to receive a revenue share proportional to your contribution – this will provide you with passive income within the project.",
		image: "/images/potential-2.png"
	},
	{
		title: "Contribute to the<br />project development",
		descr: "Participate in the fundamental decisions for Web3 AI like adopting new products and partnerships to determine its future development.",
		image: "/images/potential-3.png"
	}
]
</script>
<style scoped lang='scss'>
.potential {
	padding-top: 8.5rem;

	@include mobile {
		padding-top: 5.75rem;
	}
}
.title {
	position: relative;
	margin-bottom: 3.75rem;

	@include mobile {
		margin-bottom: 2rem;
	}
}
.title-svg {
	margin-bottom: 1rem;
	width: 3.4375rem;
}
:deep(.subtitle) {
	position: absolute;
	bottom: 0;
	right: 0;
	@include mobile {
		bottom: auto;
		top: -1rem;
	}
}
.counts {
	display: flex;
	justify-content: space-between;
	color: var(--c-grey);
	margin-top: .5rem;
	@include mobile {
		display: none;
	}
}
.items {
	display: grid;
	grid-template-columns: 1fr 1fr 1fr;
	position: absolute;
	inset: 0;

	@include mobile {
		display: block;
		padding-top: 1.5rem;
	}
}
.item-img {
	width: 100%;
	margin-top: 3.3125rem;
	@include mobile {
		order: 1;
		margin-top: 0;
	}
}
.box {
	position: relative;
}
.item {
	padding: 3.3125rem 2rem 3.8rem;
	display: flex;
	flex-direction: column;
	position: relative;
	@include mobile {
		height: 23.15rem;
		padding: 2rem 2.25rem 2rem 0;
	}
}
.item-descr {
	padding-right: 1.875rem;
	color: var(--c-grey);
	margin-top: auto;
	@include mobile {
		order: 3;
		margin-top: .5rem;
	}
}
.title-wrap {
	@include mobile {
		order: 2;
		margin-top: auto;
		position: relative;
	}
}
.item-count {
	position: absolute;
	top: 0;
	right: 0;
	color: var(--c-grey);
	margin-right: -0.875rem;
}
</style>