<template>
  <section class="potential">
    <div class="wrap _container">
      <div class="title">
        <SvgDriveTitle class="title-svg" />
        <h2 class="h2">
          <div>Partners in</div>
          <div><span class="accent">Innovation</span></div>
        </h2>

        <CommonSubtitle>
          <p class="p2">Partners</p>
        </CommonSubtitle>
      </div>

      <div class="title2">
        <SvgDrivePlus />
        Ecosystem partners
      </div>
      <div class="box1">
        <SvgPartnersBox class="desk" />
        <SvgPartnersBoxMob class="mob" />

        <div class="items">
          <div v-for="(item, i) in items" :key="i" class="item">
            <img class="item-img" :src="item.image" alt="" />
          </div>
        </div>
      </div>

      <div class="title3">
        <SvgDrivePlus />
        Backed By
      </div>
      <div class="box2">
        <SvgPartnersBox2 class="desk" />
        <SvgPartnersBox2Mob class="mob" />

        <div class="swiper">
          <div class="swiper-wrapper">
            <div v-for="(item, i) in items2" :key="i" class="swiper-slide">
              <img class="swiper-img" :class="`swiper-img-${(i % 5) + 1}`" :src="item.image" alt="" />
            </div>
          </div>
        </div>
      </div>

      <div class="nav-wrap">
        <div class="nav">
          <div class="swiper-button-prev">
            <IconButton />
            <IconArrow class="icon-arrow" />
          </div>
          <div class="swiper-pagination" />
          <div class="swiper-button-next">
            <IconButton />
            <IconArrow class="icon-arrow" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup lang="ts">
import Swiper from "swiper";
import { Navigation, Pagination } from "swiper/modules";

const items = [
  { image: "/images/partner-1.svg" },
  { image: "/images/partner-2.svg" },
  { image: "/images/partner-3.svg" },
];

const items2 = [
  { image: "/images/logo-1.svg" },
  { image: "/images/logo-2.svg" },
  { image: "/images/logo-3.svg" },
  { image: "/images/logo-4.svg" },
  { image: "/images/logo-5.svg" },
  { image: "/images/logo-1.svg" },
  { image: "/images/logo-2.svg" },
  { image: "/images/logo-3.svg" },
  { image: "/images/logo-4.svg" },
  { image: "/images/logo-5.svg" },
];

const initSwiper = () => {
  new Swiper(".swiper", {
    modules: [Navigation, Pagination],
    loop: true,
    navigation: {
      nextEl: ".swiper-button-next",
      prevEl: ".swiper-button-prev",
    },
    pagination: {
      el: ".swiper-pagination",
      clickable: true,
    },
		breakpoints: {
			0: {
				slidesPerView: 2,
			},
			1024: {
				slidesPerView: 5,
			}
		}
  });
};

onMounted(() => {
  initSwiper();
});
</script>
<style scoped lang="scss">
.potential {
  padding-top: 8.5rem;
	@include mobile {
		padding-top: 4.875rem;
	}
}
.title {
  position: relative;
  margin-bottom: 3.75rem;
  text-align: right;
  display: flex;
  flex-direction: column;
  align-items: flex-end;
	@include mobile {
		margin-bottom: 2.5rem;
	}
}
.title-svg {
  margin-bottom: 1rem;
  width: 3.4375rem;
}
:deep(.subtitle) {
  position: absolute;
  top: 0;
  left: 0;
	@include mobile {
		top: -1rem;
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
.item {
  display: flex;
  align-items: center;
  justify-content: center;
  padding-top: 2rem;

	@include mobile {
		height: 8.5rem;
		padding: 0;
	}
}
.item:nth-child(1) img {
	width: 7.6875rem;
}
.item:nth-child(2) img {
	width: 9rem;
}
.item:nth-child(3) img {
	width: 10.0625rem;
}
.item img {
	@include mobile {
		transform: scale(0.7);
	}
}
.box1 {
  position: relative;
  margin-bottom: 3.75rem;
}
.title2,
.title3 {
  margin-bottom: 2.25rem;
  display: flex;
  align-items: center;
  gap: 0.625rem;
  text-transform: uppercase;
  font-size: 1.375rem;

	@include mobile {
		font-size: 1rem;
		margin-bottom: 1.5rem;
	}
}
.title2:deep(svg),
.title3:deep(svg) {
  width: 1.375rem;
	@include mobile {
		width: 1rem;
	}
}
.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 10rem;
	@include mobile {
		height: 9.5rem;
	}
}
.swiper-img {
	@include mobile {
		transform: scale(0.7);
	}
}
.swiper-img-1 {
	width: 10.375rem;
}
.swiper-img-2 {
	width: 9.3125rem;
}
.swiper-img-3 {
	width: 6rem;
}
.swiper-img-4 {
	width: 7rem;
}
.swiper-img-5 {
	width: 10.875rem;
}
.swiper {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
}
.box2 {
  position: relative;
}
.nav-wrap {
  display: flex;
  justify-content: flex-end;
  margin-top: 2.1875rem;
	@include mobile {
		margin-top: 1.375rem;
		justify-content: center;
	}
}
.nav {
  display: flex;
  align-items: center;
  position: relative;
  z-index: 2;
	gap: 2rem;
	@include mobile {
		gap: 1rem;
	}
}
.swiper-button-prev,
.swiper-button-next {
  width: 2.875rem;
  position: relative;
  cursor: pointer;
}
.icon-arrow {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 1.25rem;
  opacity: 0.2;
}
.swiper-button-prev .icon-arrow {
  transform: translate(-50%, -50%) rotate(180deg);
}
@include hover {
  .swiper-button-prev:hover .icon-arrow,
  .swiper-button-next:hover .icon-arrow {
    opacity: 1;
  }
}
.swiper-pagination {
  display: flex;
  gap: 1rem;
	@include mobile {
		gap: 0.5rem;
	}
}
:deep(.swiper-pagination-bullet) {
  width: 0.5rem;
  height: 0.5rem;
  background: #383838;
  cursor: pointer;
}
:deep(.swiper-pagination-bullet-active) {
  background: var(--c-white);
}
</style>
