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
          <div class="modal-content ">
            <!-- add form -->
            <form novalidate @submit.prevent="onAdd">
              <div class="row mx-0 p-3">
                <div class="col-md-6">
                  <article class="card p-3 mx-2 mt-3 card-size">
                    <div
                      class="
                        d-flex
                        flex-row
                        justify-content-end
                        align-items-center
                        mb-3
                      "
                    >
                      <img src="@/assets/Visa_Logo.svg" alt="card-logo" />
                    </div>
                    <div class="d-flex mb-2">
                      <h4 class="mx-0">cardHolderName</h4>
                    </div>
                    <div class="d-flex mt-3">cardnumber</div>
                    <div class="d-flex mt-2">
                      <div class="d-flex justify-content-start">
                        <p class="m-0">
                          Thru:
                          <span> validity </span>
                        </p>
                      </div>
                      <div class="d-flex ml-2 justify-content-end">
                        <p class="m-0">
                          CVV:
                          <span>pass</span>
                        </p>
                      </div>
                    </div>
                  </article>
                </div>
                <div class="col-md-6">
                  <div class="form-container p-3">
                    <div class="field-container">
                      <label for="name" class="pr-2">Name:</label>
                      <input id="name" maxlength="20" type="text"
                      name="name"
                      v-model="cardInfo.name"/>
                    </div>
                    <div class="field-container">
                      <label for="cardnumber" class="pr-2" >Card Number:</label>
                      <input
                        id="cardnumber"
                        type="text"
                        pattern="[0-9]*"
                        inputmode="numeric"
                        v-model="cardInfo.number"
                      />
                      <!-- <svg id="ccicon" class="ccicon" width="750" height="471" viewBox="0 0 750 471" version="1.1" xmlns="http://www.w3.org/2000/svg"
                xmlns:xlink="http://www.w3.org/1999/xlink">

            </svg> -->
                    </div>
                    <div class="field-group">
                      <label for="expirationdate" class="mr-2">Expiry (mm/yy):</label>
                      <input
                        id="expirationdate"
                        type="text"
                        pattern="[0-9]*"
                        inputmode="numeric"
                        v-model="cardInfo.expiry"
                      />
                    </div>
                    <div class="field-group">
                      <label for="securitycode" class="pr-2">Security Code:</label>
                      <input
                        id="securitycode"
                        type="text"
                        pattern="[0-9]*"
                        inputmode="numeric"
                        v-model="cardInfo.passNumber"
                      />
                    </div>
                    <div class="form-group">
                      <input
                        type="submit"
                        value="Add"
                        class="btn btn-success"
                      />
                    </div>
                  </div>
                  <pre>{{cardInfo}}</pre>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      cardInfo: {
        name: null,
        number: null,
        expiry: null,
        passNumber: null,
      },
    };
  },
  methods: {
    setRatings(rating) {
      this.rating = rating;
    },
    onAdd: function() {
      this.addCard({
        name: this.name,
        number: this.number,
        expiry: this.expiry
      })
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