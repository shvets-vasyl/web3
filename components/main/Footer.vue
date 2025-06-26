<template>
  <footer class="footer">
    <div class="wrap _container">
      <SvgFooterTop class="desk" />
      <SvgFooterTopMob class="mob" />

      <div class="content">
        <div class="logo desk">
          <IconLogo />
        </div>

        <div class="about col" :class="{ active: activeContent === 'about' }">
          <SvgAccordeonBg class="mob acc-top" />
          <SvgAccordeonBg class="mob acc-bot" />
          <p class="p1 col-title" @click="toggleSection('about')">
            About
            <IconCarret class="caret-icon mob" />
          </p>

          <div class="col-content">
            <a
              v-for="{ link, text } in about"
              :key="text"
              :href="link"
							target="_blank"
              class="col-link p1"
            >
              {{ text }}
            </a>
          </div>
        </div>

        <div
          class="products col"
          :class="{ active: activeContent === 'products' }"
        >
          <SvgAccordeonBg class="mob acc-top" />
          <SvgAccordeonBg class="mob acc-bot" />
          <p class="p1 col-title" @click="toggleSection('products')">
            products
            <IconCarret class="caret-icon mob" />
          </p>

          <div class="products-content col-content">
            <div class="left">
              <a
                v-for="{ link, text } in products.slice(0, 7)"
                :key="text"
                :href="link"
								target="_blank"
                class="col-link p1"
              >
                {{ text }}
              </a>
            </div>
            <div class="right">
              <a
                v-for="{ link, text } in products.slice(7)"
                :key="text"
                :href="link"
                class="col-link p1"
              >
                {{ text }}
              </a>
            </div>
          </div>
        </div>

        <div
          class="community col"
          :class="{ active: activeContent === 'community' }"
        >
          <SvgAccordeonBg class="mob acc-top" />
          <SvgAccordeonBg class="mob acc-bot" />
          <p class="p1 col-title" @click="toggleSection('community')">
            community
            <IconCarret class="caret-icon mob" />
          </p>

          <div class="col-content">
            <a
              v-for="{ link, text } in community"
              :key="text"
							target="_blank"
              :href="link"
              class="col-link p1"
            >
              {{ text }}
            </a>
          </div>
        </div>

        <div class="learn col" :class="{ active: activeContent === 'learn' }">
          <SvgAccordeonBg class="mob acc-top" />
          <SvgAccordeonBg class="mob acc-bot" />
          <p class="p1 col-title" @click="toggleSection('learn')">
            learn
            <IconCarret class="caret-icon mob" />
          </p>

          <div class="col-content">
            <a
              v-for="{ link, text } in learn"
              :key="text"
              :href="link"
							target="_blank"
              class="col-link p1"
            >
              {{ text }}
            </a>
          </div>
        </div>
      </div>

      <div class="foot">
        <div class="logo mob">
          <IconLogo />
        </div>
        <div class="title">
          <h2 class="h2">
            Together <br /><span class="accent">to innovate!</span>
          </h2>
          <a href="https://buy2.web3ai.com/" class="join-btn" target="_blank">
            <CommonButton text="Join Presale" accent />
          </a>
        </div>

        <div class="btn-wrap">
          <a href="https://buy2.web3ai.com/" target="_blank">
            <CommonButton text="contact us" grey />
          </a>
        </div>
      </div>

      <div class="copy">
        <SvgCopyTop class="desk" />
        <SvgCopyTopMob class="mob" />

        <p class="p2">© Copyright {{ new Date().getFullYear() }} - Web3 AI</p>
      </div>
    </div>
  </footer>
</template>
<script setup lang="ts">
const activeContent = ref<string>("");
const toggleSection = (name: string) => {
  if (activeContent.value === name) {
    gsap.to(".col-content", {
      height: 0,
    });

    activeContent.value = "";
    return;
  }
  gsap.to(".col-content", {
    height: 0,
  });

  gsap.to(`.footer .${name} .col-content`, {
    height: "auto",
  });

  activeContent.value = name;
};

const about = [
  {
    text: "Tokenomics",
    link: "https://web3ai.com/tokenomics?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Whitepapper",
    link: "https://web3ai.com/web3ai-whitepaper.pdf?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Litepapper",
    link: "https://web3ai.com/web3ai-litepaper.pdf?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Road-map",
    link: "https://web3ai.com/roadmap?utm_source=meta&utm_medium=ppc1",
  },
];

const products = [
  {
    text: "AI-Powered Risk Management",
    link: "https://web3ai.com/product/ai-powered-risk-management?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Crypto Arbitrage Bot",
    link: "https://web3ai.com/product/crypto-arbitrage-bot?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Crypto Staking Advisor",
    link: "https://web3ai.com/product/crypto-staking-advisor?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Crypto Lending & Borrowing Advisor",
    link: "https://web3ai.com/product/crypto-lending-borrowing-advisor?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Crypto Price Prediction Tool",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
  {
    text: "Crypto Scam Detector",
    link: "https://web3ai.com/product/crypto-scam-detector?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "ICO & Token Sale Advisor",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
  {
    text: "Crypto Trading Assistant",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
  {
    text: "Crypto Portfolio Optimizer",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
  {
    text: "DeFi Yield Farming Advisor",
    link: "https://web3ai.com/product/defi-yield-farming-advisor?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "AI Crypto Trading Bot",
    link: "https://web3ai.com/product/ai-crypto-trading-bot?utm_source=meta&utm_medium=ppc1",
  },
  {
    text: "Crypto News Aggregator",
    link: "https://web3ai.com/product/crypto-news-aggregator?utm_source=meta&utm_medium=ppc1",
  },
];

const community = [
  {
    text: "Twitter",
    link: "https://x.com/Web3Ai_Token",
  },
  {
    text: "Telegram",
    link: "https://t.me/Web3Ai_Token",
  },
  {
    text: "Instagram",
    link: "https://www.instagram.com/web3ai_token/",
  },
];

const learn = [
  {
    text: "Wiki",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
  {
    text: "Blog",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
  {
    text: "Brand Kit",
    link: "https://buy2.web3ai.com/?utm_source=meta&utm_medium=ppc1 (https://web3ai.com/?utm_source=meta&utm_medium=ppc1)",
  },
];
</script>
<style scoped lang="scss">
.footer {
  margin-top: 5.8125rem;
  @include mobile {
    margin-top: 4.875rem;
  }
}
.content {
  display: flex;
  padding-top: 3.625rem;
  @include mobile {
    padding-top: 2.5rem;
    display: block;
    order: 2;
  }
}
.wrap {
  @include mobile {
    display: flex;
    flex-direction: column;
  }
}
.logo:deep(svg) {
  width: 2.5rem;
  @include mobile {
    width: 2rem;
  }
}
.logo {
  flex: 0 0 20.9375rem;
  @include mobile {
    flex: 1 1 auto;
    margin-bottom: 1.5rem;
  }
}
.title {
  display: flex;
  flex-direction: column;
  @include mobile {
    width: 100%;
    margin-bottom: 0.5rem;
  }
}
.title .h2 {
  margin-bottom: 2.25rem;
}
.title:deep(.btn-template) {
  font-size: 1.125rem;
  @include mobile {
    font-size: 0.875rem;
  }
}
.col-title {
  font-family: var(--font-medium);
  margin-bottom: 2rem;
  text-transform: uppercase;
  @include mobile {
    padding: 1rem;
    margin-bottom: 0;
    width: 100%;
    position: relative;
  }
}
.col-title:deep(svg) {
  @include mobile {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
  }
}
.col-link {
  font-family: var(--font-medium);
  color: rgba(white, 0.37);
  transition: all 0.3s ease;
}
.col-link:not(:last-child) {
  margin-bottom: 1.5rem;
}
.col-link {
  @include mobile {
    margin-bottom: 1.5rem;
  }
}
@include hover {
  .col-link:hover {
    color: var(--c-white);
  }
}
.col {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  @include mobile {
    margin-bottom: 0.375rem;
    position: relative;
  }
}
.col-content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  @include mobile {
    height: 0;
    overflow: hidden;
    padding-left: 1rem;
    padding-right: 1rem;
  }
}
.about {
  flex: 0 0 12.75rem;
}
.products {
  flex: 0 0 24.1875rem;
  display: block;
  margin-right: 6.9375rem;
  @include mobile {
    margin-right: 0;
  }
}
.products-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  @include mobile {
    display: block;
  }
}
.learn {
  margin-left: auto;
}
.foot {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  margin-top: -6.25rem;
  padding-bottom: 3.6875rem;
  @include mobile {
    order: 1;
    margin-top: 0;
    flex-direction: column;
    align-items: flex-start;
    padding-top: 1.5rem;
    padding-bottom: 0;
  }
}
.copy {
  text-align: center;
  color: var(--c-grey);
  @include mobile {
    order: 3;
		margin-top: 2.4375rem;
  }
}
.copy p {
  padding: 0.5rem 0 2.25rem;
	@include mobile {
		font-size: .75rem;
		padding: 0 0 .875rem;
	}
}
.join-btn,
.btn-wrap,
.btn-wrap a {
  @include mobile {
    display: block;
    width: 100%;
  }
}
.col-title .caret-icon {
  width: 0.625rem;
  position: absolute;
  top: 50%;
  transform: translateY(-50%) rotate(180deg);
  pointer-events: none;
  left: auto;
  right: 1.125rem;
  opacity: 0.3;
  transition: all 0.3s ease;
}
.active .caret-icon {
  opacity: 1;
  transform: translateY(-50%) rotate(0deg);
}
.acc-top {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
}
.acc-bot {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  transform: rotate(180deg);
}
</style>
