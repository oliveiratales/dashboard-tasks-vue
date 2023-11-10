<template>
  <section id="main-section">
    <div class="table-container">
      <table id="main-table">
        <thead>
          <tr>
            <th class="header-item lowspace">ID</th>
            <th class="header-item lowspace">Status</th>
            <th class="header-item">Descrição</th>
            <th class="header-item">Localidade</th>
            <th class="header-item">Responsável</th>
            <th class="header-item">Data</th>
            <th class="header-item" id="prio">Prioridade</th>
          </tr>
        </thead>
        <tbody>
          <tr class="item" v-for="chamado in chamados" :key="chamado.id">
            <td>{{ chamado.id }}</td>
            <td>
              <i :class="getStatusIconClass(chamado.status)"></i>
            </td>
            <td>{{ chamado.descricao }}</td>
            <td>{{ chamado.localidade }}</td>
            <td>{{ chamado.responsavel }}</td>
            <td>{{ formatDate(chamado.data) }}</td>
            <td :id="getPriorityClass(chamado.prioridade)">
              {{ chamado.prioridade }}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>

<script>
import chamadosData from "@/chamados.json";

export default {
  name: "MainTable",
  data() {
    return {
      chamados: chamadosData,
      currentPage: 1,
      pageSize: 10,
    };
  },
  created() {
    this.chamados = chamadosData;
    this.chamados.sort((a, b) => new Date(b.data) - new Date(a.data));
  },
  methods: {
    getPriorityClass(priority) {
      if (priority === "Alta") {
        return "urgent";
      } else if (priority === "Média") {
        return "medium";
      } else if (priority === "Baixa") {
        return "safe";
      }
    },
    getStatusIconClass(status) {
      if (status === "Novo") {
        return "fa-solid fa-star";
      } else if (status === "Atribuído") {
        return "fa-solid fa-user";
      } else if (status === "Aguardando") {
        return "fa-solid fa-clock";
      }
    },
    formatDate(date) {
      var dateExtracted = new Date(date)
      var dateFormated = dateExtracted.toLocaleDateString('pt-BR', {
        timeZone: 'UTC',
      });
      return dateFormated;
    }
  },
};
</script>

<style>
#main-section {
  width: 90%;
  box-sizing: border-box;
}

.table-container {
  width: 100%;
  overflow-x: auto;
}

#main-table {
  border-collapse: collapse;
  width: 100%;
  height: 94vh;
}

.header-item {
  text-align: center;
  background-color: #494a4d63;
  padding: 1.5em;
  font-weight: 800;
  color: white;
  font-size: 1.3em;
}

.lowspace {
  max-width: 90px;
}

td {
  word-wrap: break-word;
}

.item td {
  padding: 0 1rem;
  text-align: center;
  font-weight: 800;
  font-size: 1.1em;
  background-color: #f2f2f244;
  color: var(--light-color);
  border-bottom: 0.5px solid var(--secundary-color);
  max-width: 250px;
}

.item td span {
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}

#loadMore {
  display: block;
  padding: 0.8em;
  border: none;
  background-color: #8a8d93;
  color: var(--light-color);
  cursor: pointer;
  font-weight: 600;
  font-size: 1.2em;
  border-radius: 15px;
  transition: 0.3s;
  margin: 10px auto;
}

#loadMore:hover {
  opacity: 0.8;
  transition: 0.3s;
}

.date-time {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.time {
  font-weight: 800;
  font-size: 1.1em;
}

.date {
  font-size: 1em;
}
</style>
