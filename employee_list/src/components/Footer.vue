<template>
  <footer>
    <div class="optimisers">
      <Optimisers />
      <p>
        Vendre är ett företag inom
        <a target="_blank" href="https://www.optimizers.nl/">Optimizers</a>
      </p>
    </div>
    <img src="./icons/gasell.png" alt="gasell-image" class="gasell-image" />
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
  background: var(--color-1);
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 30px;
  gap: var(--space-8);
}
.optimisers {
  text-align: center;
}
.gasell-image {
  width: 40px;
  height: auto;
}

@media (min-width: 768px) {
  footer {
    width: 60%;
    flex-direction: row;
    justify-content: space-between;
    margin-left: auto;
    margin-right: var(--space-72);
  }
}
</style>
