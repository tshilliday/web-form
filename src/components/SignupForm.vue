<!-- ***********
      ITEMS TO COMPLETE
     *********** 
      
1). All placeholder animations and get the placeholder to stay above the text (3/4 COMPLETE)
2). Font and sizing installed (COMPLETE)
3). Get correct thank you message displaying !important (COMPLETED)
4). Get all other minor animations on (INCOMPLETE)
5). Error message displaying on incorrect/invalid form options (INCOMPLETE) 
6). Test responsiveness (COMPLETE)
7) Get Git commit pushed and ready
8). Email to explain things done and things missed
9). Dropdown to displace correct styling (INCOMPLETE)
10). Show hidden field when order number is selected on the drodown (INCOMPLETE)
       -->

<template>
  <div class="success" v-if="savingSuccessful">
    <span
      class="block overflow-hidden flex flex-col items-center text-center pb-6"
    >
      <span class="relative block">
        <h1 class="text-6xl font-black py-6 pt-16">Thank You!</h1>
        <p class="text-xl pb-16 font-medium">
          Our Customer Services department will be in touch.
        </p>
      </span>
    </span>
  </div>

  <form class="" @submit.prevent="handleSumbit" v-if="!savingSuccessful">
    <div class="flex flex-col w-full h-full min-h-screen">
      <!-- Add Grid -->
      <div class="flex-1 grid grid-cols-6 md:grid-cols-12 px-2 py-4">
        <!-- add main area -->
        <div
          class="col-span-6 col-start-1 md:col-span-10 md:col-start-2 xl:col-span-8 xl:col-start-3 flex flex-col"
        >
          <span
            class="block overflow-hidden flex flex-col items-center text-center pb-6"
          >
            <span class="relative block">
              <h1 class="text-6xl font-black py-6 pt-16">Contact Us</h1>
              <p class="text-xl pb-16 font-medium">
                If you have an enquiry regarding the online shop or a general
                enquiry for our Customer Services department, please contact us
                either by completing the form below or by using Live Chat.
              </p>
            </span>
          </span>
          <div
            class="grid flex-row w-full grid-cols-1 lg:grid-cols-2 md:gap-10"
          >
            <div class="flex-grow pb-12">
              <!-- FIRST NAME AREA -->
              <div class="relative flex w-full">
                <div
                  class="border-0 border-b border-solid border-black border-error text-base text-black font-medium w-full px-0"
                >
                  <input
                    class="form-control w-full bg-transparent"
                    placeholder="First Name*"
                    type="text"
                    required
                    v-model="firstName"
                  />
                  <label class="form-label">First Name*</label>
                </div>
              </div>
            </div>
            <div class="flex-grow pb-12">
              <!-- LAST NAME AREA -->
              <div class="relative flex w-full">
                <div
                  class="border-0 border-b border-solid border-black border-error text-base text-black font-medium w-full px-0"
                >
                  <input
                    class="form-control w-full bg-transparent"
                    placeholder="Last Name*"
                    type="text"
                    required
                    v-model="lastName"
                  />
                  <label class="form-label">Last Name*</label>
                </div>
              </div>
            </div>

            <div class="flex-grow pb-12">
              <!-- EMAIL AREA -->
              <div class="relative flex w-full">
                <div
                  class="border-0 border-b border-solid border-black border-error text-base text-black font-medium w-full px-0"
                >
                  <input
                    class="form-control w-full bg-transparent"
                    placeholder="Email Address*"
                    type="email"
                    required
                    v-model="email"
                  />
                  <label class="form-label">Email Address*</label>
                </div>
              </div>
            </div>

            <div class="relative flex-grow pb-12">
              <!-- ENQUIRY TYPE -->
              <div class="relative flex-grow pb-6">
                <div class="flex items-center w-full">
                  <div
                    class="border-0 border-b border-solid border-black border-error text-base text-black font-medium w-full px-0 pb-0.5"
                  >
                    <select
                      class="form-control w-full bg-transparent"
                      placeholder="Enquiry Type*"
                      v-model="enquiry"
                    >
                      <option value="deliveries">Deliveries</option>
                      <option value="orders">Orders</option>
                      <option value="payments">Payments</option>
                      <option value="stock">Products/Stock</option>
                      <option value="return">Returns</option>
                      <option value="shipping">Shipping</option>
                      <option value="promotion">Promotion</option>
                      <option value="technical">Website/Technical</option>
                    </select>
                    <label class="form-label">Enquiry type*</label>
                  </div>
                </div>
              </div>
            </div>

            <div class="flex-grow lg:col-span-2 pb-6">
              <textarea
                v-model="message"
                rows="10"
                placeholder="Write your message here*"
                required
              ></textarea>
            </div>
            <div class="flex-grow pb-6 lg:col-start-2">
              <button class="text-left" id="submit">Submit</button>
            </div>

            <!-- v-model binds the data in both directions -->

            <!-- Testing output on page -->
            <!-- <p>
First Name: {{ firstName }}
  </p>
  
    <p>
Last Name: {{ lastName }}
  </p>
    <p>
Email: {{ email }}
  </p>

    <p>
Enquiry: {{ enquiry }}
  </p>

  <p>
Message: {{ message }}
  </p> -->
          </div>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    // this tracks the input and stores them
    return {
      firstName: "",
      lastName: "",
      email: "",
      enquiry: "",
      message: "",
      savingSuccessful: false,
    };
  },
  methods: {
    handleSumbit() {
      console.log("form submitted");
      console.log("First Name: ", this.firstName);
      console.log("Last Name: ", this.lastName);
      console.log("Email Address: ", this.email);
      console.log("Enquiry: ", this.enquiry);
      console.log("Message: ", this.message);
      // alert("Thank You! Our Customer Services department will be in touch.");
      this.savingSuccessful = true;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;500;700&display=swap");

html,
body {
  font-family: "Space Grotesk", sans-serif;
  letter-spacing: 0.01em;
}

#app {
  font-family: "Space Grotesk", sans-serif;
  letter-spacing: 0.01em;
}

input,
select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid ddd;
  /* color: #555; */
  resize: none;
  background: transparent;
}

textarea {
  width: 100%;
  box-sizing: border-box;
  border: 1px solid black;
  resize: none;
  background: transparent;
  padding: 15px !important;
  outline: none !important;
}

#submit {
  width: 100%;
  background: rgb(44, 44, 44);
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
}

#submit:hover {
  background: black;
}

.form-label {
  font-size: 1em;
  display: block;
  opacity: 1;
  transform: translateY(-1em);
  transform-origin: 0 0;
  transition: all 0.3s;
  pointer-events: none;
  line-height: 8px;
  font-weight: 300;
}

.form-control {
  box-shadow: none;
  border-radius: 0px;
  border-color: #ccc;
  width: 100%;
  transition: all 0.5s;
}

.form-control::placeholder {
  color: transparent;
}

textarea::placeholder {
  color: black !important;
  font-weight: 300;
}

.form-control:focus {
  box-shadow: none;
  outline: none;
}

.form-control:focus + .form-label {
  transform: translateY(-2.5em);
}

.form-control:focus + .form-label,
.form-control:not(:placeholder-shown) + .form-label {
  transform: translateY(-2.5em);
}
</style>
