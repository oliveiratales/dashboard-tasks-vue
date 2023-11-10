<template>
  <div class="ranking">
    <h2 class="ranking-title">Ranking</h2>
    <div class="indicadores slick-carousel">
      <div class="sidebar-item" v-for="(item, index) in items" :key="index">
        <span class="sidebar-number">{{ item.number }}</span>
        <p class="open">{{ item.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import $ from 'jquery';
import 'slick-carousel/slick/slick.min.js';

export default {
  data() {
    return {
      items: [
        { number: 18, name: "João Alves" },
        { number: 16, name: "Pedro Alves" },
        { number: 9, name: "José Roberto" },
        { number: 7, name: "Kleber Machado" },
        { number: 4, name: "Lorem Ipsum" },
      ],
    };
  },
  mounted() {
    this.initializeCarousel();
  },
  methods: {
    initializeCarousel() {
      $(".slick-carousel").slick({
        slidesToShow: 1,
        infinite: true,
        autoplay: true,
        autoplaySpeed: 5000,
        dots: true,
        arrows: false,
      });
    },
  },
};
</script>

<style scoped>
.ranking-title {
  color: var(--light-color);
  font-weight: 800;
  font-size: 1.2em;
  text-align: center;
  margin-bottom: 0.5em;
}

.sidebar-number {
  font-weight: 800;
  font-size: 3.5em;
  color: white;
}

.sidebar-item p {
  margin-top: 1rem;
  font-size: 1.2em;
  font-weight: 700;
}

.open {
  color: var(--primary-priority);
  margin-bottom: 0.5em;
}

.indicadores-ranking {
  display: flex;
  flex-direction: column;
  gap: 0.5em;
  width: 100%;
  text-align: center;
}
</style>
