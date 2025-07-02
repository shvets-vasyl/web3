<template>
  <section class="hero">
    <img class="inner-img" src="/images/hero-bg.png" alt="" />
    <img class="image" src="/images/hero-img.png" alt="" />

		<div class="gradient" />

    <div class="wrap _container">
      <div class="head">
        <div class="logo">
          <IconLogo />
        </div>
      </div>

      <div class="body">
        <h1 class="title h1">
          <div>Not Another</div>
					<div>Hype Token</div>
          <div><span class="accent">— $WAI Unlocks</span></div>
          <div>a Real AI</div>
					<div>Ecosystem</div>
          <div>for <span class="accent">Crypto Investors</span></div>
        </h1>

        <p class="p1 descr">
          Join the Presale and Get Access to 8 AI-Powered Tools to Help You Analyze, Protect, and Grow Your Crypto
        </p>
      </div>

      <div class="foot">
        <div class="left">
          <p class="text p2">PRESALE <span>ACTIVE NOW</span></p>
          <div class="btn-wrap">
            <div class="coins">
              <IconCoins class="coins-icons" />
              <SvgButtonTemplateTransparent class="desk" />
              <SvgButtonTemplateTransparentMob class="mob" />
            </div>

            <a class="btn-buy" href="https://buy2.web3ai.com/" target="_blank">
              <CommonButton text="BUY NOW" accent />
            </a>
          </div>
        </div>
        <div class="right">
					<SvgHeroBox class="box-svg" />
					<SvgHeroBoxMob2 class="box-svg-mob" />

					<div class="box-content">
						<div class="progress-wrap">
						<div class="progress-bar">
							<div class="bar" />
						</div>
						<div class="percent-progress">
							<SvgPercentProgress2 class="desk" />
							<SvgPercentProgress2Mob class="mob" />
							<p>32%</p>
						</div>
						</div>

						<div class="box-info">
							<p><span>Current stage:</span> 9</p>
						</div>

						<div class="amounts">
							<div v-for="amount, i in amounts" :key="i" class="amount">
								<p class="amount-title">{{ amount.title }}</p>
								<p class="amount-text p1">{{ amount.text }}</p>
							</div>
						</div>
					</div>

        </div>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
const amounts = [
	{
		title: "Tokens sold",
		text: "23.4B"
	},
	{
		title: "amount raised",
		text: "$8.48M"
	},
	{
		title: "current price",
		text: "$0.000443"
	},
	{
		title: "Launch price",
		text: "$0.00524"
	},
]

</script>
<style scoped lang="scss">
.hero {
  position: relative;
  min-height: 100vh;
  padding-bottom: 3.125rem;

	@include mobile {
		padding-bottom: 1rem;
		height: 100vh;
	}
}
.logo {
  width: 2.5rem;
	@include mobile {
		width: 2rem;
	}
}
.image {
  position: absolute;
  bottom: 0;
  right: 1.25rem;
  width: 47.5625rem;
	@include mobile {
		width: 100%;
		right: 0;
		bottom: 9.375rem;
	}
}
.head {
  padding-top: 1.6875rem;
  padding-bottom: 1.6875rem;
  border-bottom: 0.0625rem solid rgba(white, 0.08);
  margin-bottom: 2.9375rem;

	@include mobile {
		padding-top: 1.5rem;
		padding-bottom: 1rem;
		margin-bottom: .75rem;
	}
}
.title {
	@include mobile {
		font-size: 1.5rem;
	}
}
.wrap {
  position: relative;
  display: flex;
  flex-direction: column;
  height: 100%;
}
.title div:nth-child(3) {
  margin-left: 1rem;
	@include mobile {
		margin-left: 0;
	}
}
.title div:nth-child(4) {
  margin-left: 5.625rem;
	@include mobile {
		margin-left: 0;
		text-align: left;
	}
}
.descr {
  width: 17.8rem;
  color: #fff;
  margin-top: 1rem;
  margin-left: 5.625rem;

	@include mobile {
		width: 12.9375rem;
		margin-left: 0;
	}
}
.foot {
  display: flex;
  margin-top: auto;

	@include mobile {
		flex-direction: column;
	}
}
.amount-title {
	font-size: .75rem;
	font-family: var(--font-medium);
	text-transform: uppercase;
	color: var(--c-grey)
}
.amount:nth-child(3) .amount-text {
	color: var(--c-accent);
}
.left {
  display: flex;
  align-items: flex-end;
  margin-right: 11.6875rem;
	@include mobile {
		order: 2;
		flex-direction: column;
		margin-right: 0;
		position: relative;
		margin-top: 1rem;
	}
}
.right {
	position: relative;
	@include mobile {
		order: 1;
	}
}
.coins {
  position: relative;
	@include mobile {
		width: 10.6875rem;
		margin-left: auto;
	}
}
.progress-wrap {
	display: flex;
	gap: .75rem;
}
.percent-progress {
	flex: 0 0 3rem;
	position: relative;
}
.percent-progress p {
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	color: var(--c-black);
	line-height: 1;
	margin-top: -0.1875rem;
	font-size: .875rem;
	text-transform: uppercase;
	font-family: var(--font-medium);
}
.coins-icons {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
	width: 13.5rem;

	@include mobile {
		width: 9rem;
		margin-left: auto;
	}
}
.text {
  text-transform: uppercase;
  font-family: var(--font-medium);
  margin-right: 3.0625rem;
  margin-bottom: 1.3rem;
	@include mobile {
		margin-right: 0;
		margin-left: 0;
		margin-bottom: 0;
		position: absolute;
		top: 1.3125rem;
		left: 0;
	}
}
.text span {
  color: var(--c-accent);
}
.btn-wrap {
  width: 16.25rem;
	@include mobile {
		width: 100%;
		display: flex;
		flex-direction: column;
	}
}
.btn-buy {
  margin-top: 1rem;
  width: 100%;
}
.box-svg {
  width: 34.125rem;
	@include mobile {
		display: none;
	}
}
.box-svg-mob {
	display: none;
	@include mobile {
		display: block;
	}
}
.box-content {
	width: 32.125rem;
	margin-left: 1rem;
	padding-top: 1.1875rem;
	position: absolute;
	top: 0;
	left: 0;

	@include mobile {
		width: 19.8rem;
	}
}
.progress-bar {
	height: 1.5rem;
	padding: .25rem;
	width: 100%;
	background: rgba(250, 250, 250, .04);
	margin-bottom: .5rem;

	@include mobile {
		height: 1.4rem;
		padding: .125rem;
		margin-bottom: .25rem;
	}
}
.bar {
	display: flex;
	height: 100%;
	background-image: url("/images/progress-bar.svg");
	background-size: 133.8125rem 108.875rem;
	background-repeat: no-repeat;
	background-position: 50%;
	position: relative;
	width: 32%;
}
.box-info {
	font-size: .875rem;
	line-height: 120%;
	text-transform: uppercase;
	margin-bottom: 1rem;
	text-align: center;

	@include mobile {
		font-size: .625rem;
		margin-bottom: .75rem;
	}
}
.box-info p span {
	color: var(--c-grey);
}
.amounts {
	display: flex;

	@include mobile {
		display: grid;
		grid-template-columns: 1fr 1fr;
	}
}
.amount:not(:last-child) {
	padding-right: .75rem;
	margin-right: .75rem;
	border-right: .0625rem solid var(--c-grey);
	@include mobile {
		margin-right: 0;
		padding-right: 0;
	}
}
.amount {
	@include mobile {
margin-bottom: .75rem;
text-align: center;
	}
}
.amount:nth-child(2) {
	@include mobile {
		border: none;
	}
}
.gradient {
	height: 14.125rem;
	width: 100%;
	left: 0;
	bottom: 0;
	position: absolute;
	background: linear-gradient(transparent, var(--c-black));
}
</style>
