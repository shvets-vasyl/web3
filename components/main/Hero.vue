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
          <div><span class="accent">WEB3AI</span> $777K</div>
          <div>GIVEAWAY</div>
          <div>— <span class="accent">GET IN</span> BEFORE</div>
          <div><span class="accent">IT’S</span> GONE!</div>
        </h1>

        <p class="p1 descr">
          10 winners. 3 months. Don’t miss your shot to claim your share and
          join the future of Web3.
        </p>
      </div>

      <div class="foot">
        <div class="left">
          <p class="text p1">PRESALE <span>ACTIVE NOW</span></p>
          <div class="btn-wrap">
            <div class="coins">
              <IconCoins class="coins-icons" />
              <SvgButtonTemplateTransparent class="desk" />
              <SvgButtonTemplateTransparentMob class="mob" />
            </div>

            <a class="btn-buy" href="https://web3ai.com/product/defi-yield-farming-advisor?utm_source=meta&utm_medium=ppc1" target="_blank">
              <CommonButton text="BUY NOW" accent />
            </a>
          </div>
        </div>
        <div class="right">
					<SvgHeroBox class="box-svg" />
					<SvgHeroBoxMob class="box-svg-mob" />

					<div class="box-content">
						<div class="progress-bar">
							<div class="bar" />
						</div>

						<div class="box-info">
							<p>USD Raised</p>
							<p><span>3,439,934 USD</span> / 5,000,000 USD</p>
						</div>

						<div class="prices">
							<div class="price-item">
								<SvgHeroPriceBox class="price-box" />
								<SvgHeroPriceBoxMob class="price-box-mob" />

								<div class="price-content">
									<p class="price-text">current price</p>
									<p class="price p1">$0.0056</p>
								</div>
							</div>

							<div class="price-item">
								<SvgHeroPriceBox class="price-box" />
								<SvgHeroPriceBoxMob class="price-box-mob" />

								<div class="price-content">
									<p class="price-text">listing price</p>
									<p class="price p1">$0.086</p>
								</div>

							</div>
						</div>
					</div>

        </div>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts"></script>
<style scoped lang="scss">
.hero {
  position: relative;
  height: 100vh;
  padding-bottom: 3.125rem;

	@include mobile {
		padding-bottom: 1rem;
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
		bottom: 150px
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
		text-align: right;
	}
}
.title div:nth-child(4) span {
	@include mobile {
		display: none;
	}
}
.descr {
  width: 17.8rem;
  color: #51525c;
  margin-top: 1rem;
  margin-left: 5.625rem;

	@include mobile {
		width: 12.9375rem;
		margin-left: 0;
		margin-top: -1.875rem;
	}
}
.foot {
  display: flex;
  margin-top: auto;

	@include mobile {
		flex-direction: column;
	}
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
		height: 1rem;
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
	width: 31%;
}
.box-info {
	display: flex;
	justify-content: space-between;
	font-size: .875rem;
	line-height: 120%;
	text-transform: uppercase;
	margin-bottom: 1rem;

	@include mobile {
		font-size: .625rem;
		margin-bottom: .75rem;
	}
}
.box-info p span {
	color: var(--c-grey);
}
.prices {
	display: grid;
	grid-template-columns: 1fr 1fr;
	gap: .5rem;
}
.price-item {
	position: relative;
}
.price-box {
	width: 100%;
	@include mobile {
		display: none;
	}
}
.price-box-mob {
	display: none;
	@include mobile {
		display: block;
	}
}
.price-content {
	position: absolute;
	top: 0.5rem;
	left: 1rem;
}
.price-text {
	text-transform: uppercase;
	font-size: .75rem;
	line-height: 140%;
	color: var(--c-grey);
	@include mobile {
		font-size: .625rem;
	}
}
.price {
	@include mobile {
		font-size: .75rem;
	}
}
.price-item:first-child .price {
	color: var(--c-accent)
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
