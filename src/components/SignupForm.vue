<template>






  <div class="flex flex-col w-full h-full min-h-screen">
            <!-- Add Grid -->
            <div class="flex-1 grid grid-cols-6 md:grid-cols-12 px-2 py-4">
                <!-- add main area -->
                <div
                    class="col-span-6 col-start-1 md:col-span-10 md:col-start-2 xl:col-span-8 xl:col-start-3 flex flex-col">
                    <span class="block overflow-hidden flex flex-col items-center text-center pb-6">
                        <span
                            class="relative block">
                            <h1 class="text-3xl font-bold py-8">Contact usss</h1>
                            <p class="py-8">If you have an enquiry regarding the online shop or a general
                                enquiry for our Customer
                                Services department, please contact us either by completing the form below or by using
                                Live Chat.</p>
                        </span>
                    </span>
                    <div class="">





                        <form class="grid flex-row w-full grid-cols-1 lg:grid-cols-2 md:gap-8" action="">
                            <div class="flex-grow pb-6">
                                <!-- FIRST NAME AREA -->
                                <div class="relative flex w-full">
                                    <div
                                        class="flex border-0 border-b border-solid border-error text-base text-black font-medium w-full py-1 px-0">

                                        <input class="outline-none w-full bg-transparent" type="text">
                                        <span
                                            class="absolute left-0 duration-300 pointer-events-none placeholder opacity-60 transition-bottom ease-1 bottom-1 text-black text-base">First
                                            Name</span>
                                    </div>
                                </div>
                            </div>
                            <div class="flex-grow pb-6">
                                <!-- LAST NAME AREA -->
                                <div class="relative flex w-full">
                                    <div
                                        class="flex border-0 border-b border-solid border-error py-1 bg-transparent text-base text-black font-medium w-full py-1 px-0">
                                        <input class="outline-none w-full bg-transparent" type="text">
                                        <span
                                            class="absolute left-0 duration-300 pointer-events-none placeholder opacity-60 transition-bottom ease-1 bottom-1 text-black text-base">Last
                                            Name</span>
                                    </div>
                                </div>
                            </div>
                            <div class="flex-grow pb-6">
                                <!-- EMAIL AREA -->
                                <div class="relative flex w-full">
                                    <div
                                        class="flex border-0 border-b border-solid border-error py-1 text-base text-black font-medium w-full py-1 px-0">
                                        <input class="outline-none w-full bg-transparent" type="email" name="" id="">
                                    </div>
                                    <span
                                        class="absolute left-0 duration-300 pointer-events-none placeholder opacity-60 transition-bottom ease-1 bottom-1 text-black text-base">Email
                                        Address*</span>
                                </div>
                            </div>
                            <div class="relative flex-grow pb-6">
                                <!-- ENQUIRY TYPE -->
                                <div class="relative flex-grow pb-6">
                                    <div class="flex items-center w-full">
                                        <div class="relative select-input w-full cursor-pointer">
                                            <label
                                                class="absolute text-base bottom-1 left-0 opacity-60 transform duration-400 ease-ease-1"
                                                for="">Enquiry Type*</label>
                                            <div
                                                class="transform absolute w-2 h-2 -translate-y-1/2 right-0.5 top-1/2 transform transform-all ease-ease-1 duration-300">
                                            </div>
                                            <input
                                                class=" bg-transparent pointer-events-none text-base text-black font-medium w-full py-1 px-0 outline-none"
                                                type="select" name="" id="">
                                            <div class="w-full bg-black h-divider"></div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="flex-grow lg:col-span-2 pb-6">
                                MAIN MESSAGE
                            </div>
                            <div class="flex-grow pb-6 lg:col-start-2">
                                Button
                            </div>
                        </form>
                    </div>
                </div>

            </div>



        </div>

















  <form @submit.prevent="handleSumbit">

<label>First Name*</label>
<input type="text" required v-model="firstName">

<label>Last Name*</label>
<input type="text" required v-model="lastName">

<label>Email Address*</label>
<input type="email" required v-model="email">


<label>Enquiry type*</label>
<select v-model="enquiry">
  <option value="deliveries">Deliveries</option>
  <option value="orders">Orders</option>
  <option value="payments">Payments</option>
  <option value="stock">Products/Stock</option>
  <option value="return">Returns</option>
  <option value="shipping">Shipping</option>
  <option value="promotion">Promotion</option>
  <option value="technical">Website/Technical</option>
</select>


<label>Message*</label>

<textarea v-model="message" rows="10" required></textarea>



<button id="submit">
  Submit
</button>




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
  
  </form>




</template>

<script>



export default {
  data() {
    // this tracks the input and stores them
    return {
      firstName: '',
      lastName: '',
      email: '', 
      enquiry: '',
      message: ''
    }
  },
methods: {
  handleSumbit() {
    console.log('form submitted')
    console.log('First Name: ', this.firstName)
    console.log('Last Name: ', this.lastName)
    console.log('Email Address: ', this.email)
    console.log('Enquiry: ', this.enquiry)
    console.log('Message: ', this.message)
    alert('Thank you. We will get back to you as soon as possible')
  }
} 

}

 


</script>




<style>
form {
/* max-width: 420px;
margin: 30px auto;
background: transparent;
text-align: center;
padding: 40px;
border-radius: 10px; */
}

/* label {
    color: #000;
    display: inline block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}

input, select, textarea {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid ddd;
    color: #555;
     resize: none;
}

#submit  {
  background: black;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
} */



</style>