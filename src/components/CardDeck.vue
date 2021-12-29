<template>
  <div class="col pb-3">
    <div class="card-container d-flex">
      <Card
        class="card-item"
        v-for="card in cards"
        :key="card.id"
        :cardHolderName="card.cardName"
        :cardNumber="card.cardNumber"
        :validThru="card.validity"
        :cardPass="card.cardCode"
      />
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";
import { mapState } from "vuex";
export default {
  name: "CardDeck",
  components: {
    Card,
  },
  computed: {
    ...mapState(["cards"]),
  },
  created() {
    this.$store.dispatch("fetchCards");
  },
};
</script>

<style>
.card-container {
  overflow-x: auto;
  overflow-y: hidden;
  white-space: nowrap;
  /* flex-wrap: nowrap; */
  -webkit-overflow-scrolling: touch;
}

.card-container .card-item {
  flex: 0 0 auto;
}

/* .card-container::-webkit-scrollbar {
  display: none;
} */
</style>
