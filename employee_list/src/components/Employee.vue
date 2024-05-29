<template>
  <div class="container">
    <h1>Vendre Members</h1>
    <div class="employees">
      <div v-for="employee in employees" :key="employee.id" class="employee">
        <img :src="employee.avatar" alt="employee" class="portrait" />
        <p>{{ employee.first_name }} {{ employee.last_name }}</p>
        <a :href="'mailto:' + employee.email">{{ employee.email }}</a>
      </div>
    </div>
    <button @click="loadMore" ref="loadMoreButton">SE MER</button>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      employees: [],
      currentPage: 1,
    };
  },
  async created() {
    await this.fetchEmployees();
  },
  methods: {
    async fetchEmployees() {
      try {
        const response = await axios.get(
          `https://reqres.in/api/users?page=${this.currentPage}`
        );
        this.employees = [...this.employees, ...response.data.data];
      } catch (error) {
        console.error("Error fetching data:", error);
      }
    },
    async loadMore() {
      this.currentPage += 1;
      await this.fetchEmployees();
      this.$refs.loadMoreButton.remove();
    },
  },
};
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  margin: var(--space-72) auto;
  padding-top: var(--space-48);
  gap: var(--space-24);
  background: linear-gradient(to bottom, var(--color-4), var(--color-1));
}

h1 {
  font-family: "Oswald";
  font-size: 42px;
}
p {
  font-family: "Oswald";
}

.employees {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

.employee {
  width: 100%;
  margin: var(--space-24);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-8);
}

p {
  font-weight: bold;
}

.portrait {
  width: 50vw;
  aspect-ratio: 1 / 1;
  border-radius: 50%;
  margin: var(--space-4);
  object-fit: cover;
}

button {
  background-color: var(--color-2);
}

a {
  text-decoration: none;
  color: var(--color-3);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    color: var(--color-2);
  }
}

@media (min-width: 768px) {
  .employees {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    flex-wrap: wrap;
  }
  .employee {
    width: 25%;
  }
  .portrait {
    width: 15vw;
  }
}
</style>
