<template>
  <section id="sidebar">
    <div class="sidebar">
      <div class="indicadores">
        <div class="sidebar-item">
          <span class="sidebar-number">15</span>
          <p class="open">Abertos</p>
        </div>
        <div class="sidebar-item">
          <span class="sidebar-number">9</span>
          <p class="opennow">Abertos</p>
          <span class="today">Hoje</span>
        </div>
        <div class="sidebar-item">
          <span class="sidebar-number">6</span>
          <p class="finished">Finalizados</p>
          <span class="today">Hoje</span>
        </div>
        <div class="sidebar-item">
          <span class="sidebar-number">8</span>
          <p class="planning">Planejados</p>
        </div>
        <div class="sidebar-item">
          <span class="sidebar-number">40</span>
          <p class="open">Total de Chamados</p>
        </div>
      </div>
    </div>

    <ranking-component></ranking-component>

  </section>
</template>

<script>
import RankingComponent from "@/components/RankingComponent.vue";

export default {
  components: {
    RankingComponent,
  },
};
</script>

<style>
#sidebar {
  background-color: var(--background-color);
  width: 10%;
  box-sizing: border-box;
  min-height: 100%;
  display: flex;
  flex-direction: column;
}

.sidebar {
  display: flex;
  flex-direction: column;
  margin-bottom: 0.5em;
  flex-grow: 1;
}

.title {
  background-color: #2d3035;
  padding: 0.8em;
  font-weight: 800;
  color: white;
  font-size: 1.4em;
  text-align: center;
  width: 100%;
  border-radius: 15px;
  text-transform: uppercase;
}

.sidebar-item {
  padding: 1em;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 0.5em;
  align-items: center;
  background-color: #494a4d63;
  border-radius: 15px;
  flex-grow: 1;
}

.indicadores,
.indacadores-ranking {
  display: flex;
  flex-direction: column;
  gap: 0.5em;
  width: 100%;
  text-align: center;
  flex-grow: 1;
}

.today {
  font-weight: 600;
  background-color: var(--danger-priority);
  color: var(--light-color);
  padding: 0.3em 0.5em;
  border-radius: 15px;
}

.sidebar-number {
  font-weight: 800;
  font-size: 3.5em;
  color: white;
  line-height: 1;
}

.sidebar-item p {
  font-size: 1.2em;
  font-weight: 700;
}

.open {
  color: var(--primary-priority);
}

.opennow {
  color: var(--medium-priority);
}

.finished {
  color: var(--safe-priority);
}

.planning {
  color: var(--info-priority);
}

.slick-dots li button::before {
  color: var(--primary-priority);
  font-size: 8px;
}

.slick-dots li.slick-active button::before {
  color: var(--danger-priority);
  font-size: 12px;
}
</style>