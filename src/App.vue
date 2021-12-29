<template>
  <div class="container">
    <div class="card card-body text-center p-5 mt-5">
      <!-- <div>
        <i class="fa fa-star text-warning fa-6x" @click="setRatings(1)"></i>
        <i class="fa fa-star text-warning fa-6x" @click="setRatings(2)"></i>
        <i class="fa fa-star text-warning fa-6x" @click="setRatings(3)"></i>
        <i class="fa fa-star text-warning fa-6x" @click="setRatings(4)"></i>
        <i class="fa fa-star text-warning fa-6x" @click="setRatings(5)"></i>
      </div>
      <h1 v-if="rating === 1" class="text-success mt-4">
        Sorry to hear that rating
      </h1>
      <h1 v-else-if="rating === 2" class="text-success mt-4">
        Oww what can we do better!
      </h1>
      <h1 v-else-if="rating === 3" class="text-success mt-4">
        we will come back to you
      </h1>
      <h1 v-else class="text-success mt-4">
        Thank you for your motivation
      </h1> -->
      <!-- add card -->
      <div class="d-flex">
        <div class="col-6">
          <div class="ml-1 row justify-content-start align-items-center">
            <p class="badge bg-success">EUR</p>
            <p class="ml-2">3.000,00</p>
          </div>
        </div>
        <div class="col-6">
          <div class="mr-1 row justify-content-end align-items-center">
            <div
              class="button-primary"
              data-toggle="modal"
              data-target=".bd-example-modal-lg"
            >
              <a>
                <img class="mr-1" src="@/assets/add.svg" />
                New card
              </a>
            </div>
            <!-- <button type="button" class="btn btn-info" data-toggle="modal" data-target=".bd-example-modal-lg">Large modal</button> -->
          </div>
        </div>
      </div>

      <!-- modal -->
      <div
        class="modal fade bd-example-modal-lg"
        tabindex="-1"
        role="dialog"
        aria-labelledby="myLargeModalLabel"
        aria-hidden="true"
      >
        <div class="modal-dialog modal-lg">
          <add-card :add-card="addCard"></add-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import AddCard from "@/components/AddCard.vue";
export default {
  name: "App",
  data() {
    return {
      cards: [],
    };
  },
  components: {
    AddCard
  },
  methods: {
    addCard(card) {
      console.log(card);
      this.cards.push(card)
      localStorage.setItem('@cards', JSON.stringify(this.cards))
    },
  },
};
</script>

<style>
body {
  background-color: #333;
}
.card-size {
  width: 358px;
  height: 220px;
  border-radius: 0.3rem;
  background-color: #01d167;
}
</style>