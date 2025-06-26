<template>
  <section class="sum">
    <img class="pil" src="/images/pil.png" alt="" />
    <div class="wrap _container">
      <h2 class="h2 title">
        <div>sum <span class="accent">your profit</span></div>
        <div>in the near <br class="mob" />future</div>
      </h2>

      <div class="box">
        <SvgSumBox class="desk" />
        <SvgSumBoxMob class="mob" />

        <div class="content">
          <div class="field">
            <p class="field-text">USD Amount</p>
            <div class="input-wrap">
              <SvgInputBg class="desk" />
              <SvgInputBgMob class="mob" />
              <input
                class="input"
                type="number"
                placeholder="Enter amount"
                v-model="inputValue"
              />
            </div>
          </div>

          <div class="calculate">
            <p class="calculate-text">calculated profit</p>

            <div class="number"><span>$</span> {{ result.toFixed(2) }}</div>
          </div>

          <div class="progress-content">
            <div class="progress-wrap" ref="progressWrap">
              <div class="progress-box" @click="onProgressClick">
                <div
                  class="progress"
                  :style="{ width: progressPercent + '%' }"
                />
              </div>
              <div class="slide-btn-wrap"></div>
              <div
                class="slide-btn"
                ref="slideBtn"
                :style="{ left: progressPercent + '%' }"
                @mousedown.prevent="startDrag"
                @touchstart.prevent="startDrag"
              >
                <SvgSlideBtn class="slide-btn-icon" />

                <div class="percent-view">
                  <div class="percent-view-text">
                    {{ progressPercent.toFixed(0) + "%" }}
                  </div>

                  <SvgPercentProgress />
                </div>
              </div>
            </div>

            <p class="progress-text">Move slider to see profit</p>
          </div>

          <div class="info">
            <SvgInputBg class="desk" />
            <SvgInputBgMob class="mob" />

            <div class="info-text">
              <p class="p2">STAGE: {{ currentStageIndex + 9 }}</p>
              <p>
                <span>Price: </span
                ><span class="p2">${{ currentStagePrice.toFixed(6) }}</span>
              </p>
            </div>
          </div>

          <div class="buttons">
            <button class="reset-btn" @click="resetAll">
              <CommonButton text="reset" grey />
            </button>

            <CommonSubtitle class="predicted-price">
              <div>
                <p class="p2">Listing Price</p>
                <p class="p2">0.005242</p>
              </div>
            </CommonSubtitle>
          </div>
        </div>
      </div>

      <div class="btn-wrap">
        <a
          href="https://buy2.web3ai.com/"
          target="_blank"
        >
          <CommonButton text="BUY WEB3AI" accent />
        </a>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
import { ref, computed, onBeforeUnmount } from "vue";
const inputValue = ref("");
const progressPercent = ref(0);
const progressWrap = ref<HTMLElement | null>(null);

// 🔹 Ціни на етапах (stage 9 до 50), останній — Lunch
const stagePrices = [
  0.000443,
  0.000465,
  0.000489,
  0.000513,
  0.000539,
  0.000566,
  0.000594,
  0.000624,
  0.000655,
  0.000688,
  0.000722,
  0.000758,
  0.000796,
  0.000836,
  0.000878,
  0.000921,
  0.000968,
  0.001016,
  0.001067,
  0.00112,
  0.001176,
  0.001235,
  0.001297,
  0.001361,
  0.001429,
  0.001501,
  0.001576,
  0.001655,
  0.001738,
  0.001824,
  0.001916,
  0.002011,
  0.002112,
  0.002218,
  0.002328,
  0.002445,
  0.002567,
  0.002696,
  0.00283,
  0.002972,
  0.00312,
  0.003276,
  0.005242, // Lunch
];

const currentStageIndex = computed(() => {
  const index = Math.round(
    (progressPercent.value / 100) * (stagePrices.length - 1)
  );
  return Math.min(stagePrices.length - 1, Math.max(0, index));
});
const currentStagePrice = computed(() => stagePrices[currentStageIndex.value]);

const listingPrice = 0.000443; // 🔹 активний стейдж

const tokens = computed(() => {
  const investment = parseFloat(inputValue.value) || 0;
  return investment / currentStagePrice.value;
});

const result = computed(() => {
  return tokens.value * listingPrice;
});

// 🔹 Скидання
const resetAll = () => {
  inputValue.value = "";
  progressPercent.value = 0;
};

// 🔹 Drag
const stopDrag = () => {
  window.removeEventListener("mousemove", onMouseMove);
  window.removeEventListener("mouseup", stopDrag);
};

const startDrag = (e: MouseEvent | TouchEvent) => {
  if (e.type === "touchstart") {
    window.addEventListener("touchmove", onTouchMove);
    window.addEventListener("touchend", stopTouchDrag);
  } else {
    window.addEventListener("mousemove", onMouseMove);
    window.addEventListener("mouseup", stopDrag);
  }
};

const stopTouchDrag = () => {
  window.removeEventListener("touchmove", onTouchMove);
  window.removeEventListener("touchend", stopTouchDrag);
};

// 🔹 Оновлення прогресу
const updateProgress = (clientX: number) => {
  if (!progressWrap.value) return;
  const rect = progressWrap.value.getBoundingClientRect();
  const x = clientX - rect.left;
  const percent = Math.max(0, Math.min(x / rect.width, 1));
  progressPercent.value = percent * 100;
};

const onTouchMove = (e: TouchEvent) => {
  if (e.touches.length) updateProgress(e.touches[0].clientX);
};

const onMouseMove = (e: MouseEvent) => {
  updateProgress(e.clientX);
};

const onProgressClick = (e: MouseEvent) => {
  updateProgress(e.clientX);
};

onBeforeUnmount(stopDrag);
</script>

<style scoped lang="scss">
.sum {
  padding-top: 9.375rem;
  position: relative;

  @include mobile {
    padding-top: 4.875rem;
  }
}
.title {
  text-align: center;
  margin-bottom: 3.4375rem;
  @include mobile {
    text-align: left;
    margin-bottom: 2.375rem;
  }
}
.pil {
  position: absolute;
  width: 7.5rem;
  top: 12.625rem;
  right: 6.375rem;
  @include mobile {
    width: 4rem;
    right: 2rem;
    top: 8rem;
  }
}
.box {
  width: 55.0625rem;
  margin: 0 auto 3.75rem;
  position: relative;

  @include mobile {
    width: 100%;
    margin-bottom: 1rem;
  }
}
.btn-wrap {
  display: flex;
  justify-content: center;
}
.btn-wrap a {
  @include mobile {
    width: 100%;
  }
}
.content {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 2.25rem 3.6875rem 0 2.25rem;

  @include mobile {
    padding: 1.5rem 1rem 0;
  }
}
.field-text {
  font-size: 0.875rem;
  line-height: 100%;
  margin-bottom: 0.75rem;
}
.input {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  color: var(--c-white);
  padding-left: 0.75rem;
  font-size: 0.875rem;
  padding-right: 0.75rem;
}
.input::placeholder {
  color: var(--c-grey);
}
.input-wrap {
  position: relative;
  margin-bottom: 2.1875rem;
  @include mobile {
    margin-bottom: 1.375rem;
  }
}
.calculate-text {
  font-size: 0.875rem;
  color: var(--c-grey);
  position: relative;
  text-transform: uppercase;
  display: inline-flex;

  @include mobile {
    font-size: 0.625rem;
  }
}
.calculate-text:after {
  content: "";
  position: absolute;
  top: 0.5rem;
  left: 100%;
  margin-left: 0.5rem;
  width: 0.375rem;
  height: 0.375rem;
  background: var(--c-grey);
}
.calculate {
  margin-bottom: 1.5rem;
}
.number {
  font-size: 2.625rem;
  text-transform: uppercase;
  margin-top: 0.75rem;
  line-height: 100%;
  @include mobile {
    font-size: 1.75rem;
    margin-top: 0.25rem;
  }
}
.number span {
  color: var(--c-grey);
}
.progress-wrap {
  background: #1f1f24;
  height: 2.25rem;
  padding: 0.25rem;
  border-radius: 0.5rem;
  position: relative;
}
.progress-box {
  width: 100%;
  height: 100%;
  overflow: hidden;
  border-radius: 0.375rem;
}
.progress-content {
  margin-bottom: 1rem;
  @include mobile {
    margin-bottom: 0.75rem;
  }
}
.progress-text {
  font-size: 0.875rem;
  text-transform: uppercase;
  color: var(--c-grey);
  margin-top: 0.75rem;
  @include mobile {
    font-size: 0.75rem;
    text-align: center;
  }
}
.progress {
  display: flex;
  height: 100%;
  background-image: url("/images/progress-bar.svg");
  background-size: 233.8125rem 208.875rem;
  background-repeat: no-repeat;
  background-position: 50%;
  position: relative;
  width: 31%;
}
.slide-btn {
  width: 2.375rem;
  position: absolute;
  top: 50%;
  transform: translateY(-50%) translateX(-45%);
  left: 0;
  cursor: pointer;
}
.slide-btn-icon {
  position: relative;
  z-index: 2;
}
.predicted-price p:nth-child(2) {
  color: var(--c-accent);
  font-family: var(--font-medium);
  @include mobile {
    order: 1;
  }
}
.predicted-price div {
  @include mobile {
    margin-right: auto;
  }
}
.reset-btn {
  @include mobile {
    order: 2;
    margin-top: 1.375rem;
    width: 100%;
  }
}
.buttons {
  display: flex;
  align-items: center;
  justify-content: space-between;

  @include mobile {
    flex-direction: column;
  }
}
.progress {
  width: v-bind("progressPercent + '%'");
}
.predicted-price .p2 {
  @include mobile {
    font-size: 0.75rem;
  }
}
.predicted-price {
  @include mobile {
    width: 100%;
    padding-left: 0.125rem;
    padding-right: 0.125rem;
  }
}
.info {
  position: relative;
  margin-bottom: 2.9375rem;
  @include mobile {
    margin-bottom: 1.5rem;
  }
}
.info-text {
  position: absolute;
  left: 0;
  width: 100%;
  height: 100%;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 1rem;
  top: 0;

  @include mobile {
    justify-content: space-between;
    padding-left: 1rem;
    padding-right: 1rem;
  }
}
.info-text p:nth-child(2) span:nth-child(1) {
  font-size: 0.875rem;
  color: var(--c-grey);
}
.info-text p:nth-child(2) {
  display: flex;
  gap: 0.5rem;
}
.info-text p:nth-child(2) span:nth-child(2) {
  color: var(--c-accent);
}
.info-text .p2 {
  @include mobile {
    font-size: 0.875rem;
  }
}
.percent-view {
  position: absolute;
  right: 100%;
  top: 50%;
  transform: translateY(-50%);
  width: 3rem;
  margin-right: 0.25rem;
}
.percent-view-text {
  font-size: 0.875rem;
  font-family: var(--font-medium);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: var(--c-black);
}
</style>
