<template>
  <div>
    <div class="modal-content">
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
                <input
                  id="name"
                  maxlength="20"
                  type="text"
                  name="name"
                  v-model="cardInfo.name"
                />
              </div>
              <div class="field-container">
                <label for="cardnumber" class="pr-2">Card Number:</label>
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
                <input type="submit" value="Add" class="btn btn-success" />
              </div>
            </div>
            <pre>{{ cardInfo }}</pre>
          </div>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {

  name: "AddCard",
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

  props: {
      addCard: Function,
  },

  methods: {
    onAdd: function () {
      this.addCard({
        name: this.cardInfo.name,
        number: this.cardInfo.number,
        expiry: this.cardInfo.expiry,
        passNumber: this.cardInfo.passNumber
      });
    },
  },
};
</script>

<style>
</style>