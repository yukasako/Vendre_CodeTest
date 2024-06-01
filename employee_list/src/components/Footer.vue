<template>
  <footer>
    <div class="container">
      <div class="empty"></div>
      <div class="optimisers">
        <Optimisers />
        <p>
          Vendre är ett företag inom
          <a target="_blank" href="https://www.optimizers.nl/">Optimizers</a>
        </p>
      </div>
      <img src="./icons/gasell.png" alt="gasell-image" class="gasell-image" />
    </div>
  </footer>
</template>

<script>
import Optimisers from "./icons/optimisers.vue";
export default {
  components: {
    Optimisers,
  },
};
</script>

<style scoped>
footer {
  width: 100%;
}

.container {
  width: 100%;
  background: var(--color-1);
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 30px;
  gap: var(--space-8);
}
.empty {
  display: none;
}
.optimisers {
  text-align: center;
}
.gasell-image {
  width: 40px;
  height: auto;
}

@media (min-width: 768px) {
  .container {
    width: 100%;
    flex-direction: row;
    justify-content: space-around;
    align-items: center;
  }
  .empty {
    display: block;
    width: 40px;
  }
}
</style>
