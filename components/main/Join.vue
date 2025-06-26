<template>
  <section class="join">
    <div class="wrap _container">
      <div class="title">
        <SvgJoinTitle class="title-svg" />
        <h2 class="h2">
          <div>How <span class="accent">To Join</span></div>
          <div>The Giveaway</div>
        </h2>
      </div>

      <div class="items-wrap">
        <SvgJoinBg class="bg-svg" />

        <div class="items">
          <div v-for="(item, i) in items" :key="i" class="item">
            <SvgJoinFirstItem v-if="i === 0" class="item-svg" />
            <SvgJoinSecondItem v-if="i === 1" class="item-svg" />
            <SvgJoinThirdItem v-if="i === 2" class="item-svg" />
            <SvgJoinFourthItem v-if="i === 3" class="item-svg" />

            <SvgJoinItemBgMob class="item-svg-mob" />

            <div class="item-content">
              <h4 class="h4">{{ item.title }}</h4>
              <p class="p1 item-descr">{{ item.text }}</p>
            </div>
          </div>
        </div>
      </div>

			<div class="btn-wrap">
        <a
          href="https://buy2.web3ai.com/"
          target="_blank"
        >
          <CommonButton text="Enter the Giveaway" accent />
        </a>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
const items = [
  {
    title: "Visit the Official Website",
    text: "Go to the official Web3AI website at web3ai.com and join the presale at buy.web3ai.com. Make sure to check the URL to avoid scams.",
  },
  {
    title: "Connect Your Wallet",
    text: "Create an account using the wallet connect option.",
  },
  {
    title: "Choose Payment Currency",
    text: "Choose your payment method in crypto (BTC, ETH, USDT, etc.)",
  },
  {
    title: "Complete Your Purchase",
    text: "Confirm your payment in your wallet. To get a chance to join the $770,000 Giveaway, you must purchase tokens for at least $100. The Giveaway will run over a period of three months.",
  },
];
</script>
<style scoped lang="scss">
.join {
  padding-top: 5.9375rem;
  @include mobile {
    padding-top: 5rem;
  }
}
.title {
  position: relative;
  text-align: right;
  margin-bottom: 3.75rem;
  @include mobile {
    text-align: left;
    margin-bottom: 2rem;
  }
}
.title h2 div:nth-child(1) {
  margin-right: 8.4375rem;
  @include mobile {
    margin-right: 0;
  }
}
.title h2 div:nth-child(2) {
  @include mobile {
    margin-left: 2.875rem;
  }
}
.title-svg {
  position: absolute;
  width: 6rem;
  top: 0.4375rem;
  right: 0;
  @include mobile {
    width: 4rem;
    top: 0.2rem;
    right: 3.25rem;
  }
}
.items {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.75rem;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;

  @include mobile {
    grid-template-columns: 1fr;
    position: static;
  }
}
.item {
  height: 22.5rem;
  padding: 3.5625rem 3.3125rem;
  display: flex;
  flex-direction: column;

  @include mobile {
    height: 13.75rem;
    position: relative;
    padding: 0;
  }
}
.item-svg {
  width: 11.3125rem;
  margin-bottom: auto;
  @include mobile {
    margin-top: 1.375rem;
    margin-left: 1.6875rem;
    width: 7.5625rem;
  }
}
.item-descr {
  color: var(--c-grey);
  margin-top: 1rem;
  width: 34.125rem;

  @include mobile {
    width: 18rem;
    margin-top: 0.5rem;
  }
}
.items-wrap {
  position: relative;
}
.bg-svg {
  @include mobile {
    display: none;
  }
}
.item-svg-mob {
  display: none;
  @include mobile {
    display: block;
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
  }
}
.item-content {
  @include mobile {
    position: absolute;
    bottom: 0;
    left: 0;
    padding-left: 1.6875rem;
    padding-bottom: 1rem;
  }
}

.btn-wrap {
  display: flex;
  justify-content: center;
	margin-top: 2.5rem;
}
.btn-wrap a {
  @include mobile {
    width: 100%;
  }
}
</style>
