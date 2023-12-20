<template>
  <div class=" bg-white px-6 py-24 sm:py-32 lg:px-8">

  <div class="mx-auto max-w-2xl text-center">
    <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Contact Us</h2>
    <p class="mt-2 text-lg font-sans leading-8 text-black">We really Appreciate your contribution </p>
  </div>

  <form  @submit.prevent="submitForm"  class="mx-auto mt-16 max-w-xl sm:mt-20">
    <div class="grid grid-cols-1 gap-x-8 gap-y-6 sm:grid-cols-2">

      <div>
        <label for="first-name" class="block text-sm font-semibold leading-6 text-gray-900">First name</label>
        <div class="mt-2.5">
          <input type="text" v-model="firstName" required name="first-name" id="first-name" autocomplete="given-name" class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6">
        </div>
      </div>

      <div>
        <label for="last-name" class="block text-sm font-semibold leading-6 text-gray-900">Last name</label>
        <div class="mt-2.5">
          <input type="text" v-model="lastName" required name="last-name" id="last-name" autocomplete="family-name" class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6">
        </div>
      </div>

      

      <div class="sm:col-span-2">
        <label for="email" class="block text-sm font-semibold leading-6 text-gray-900">Email</label>
        <div class="mt-2.5">
          <input type="email"  v-model="email" required name="email" id="email" autocomplete="email" class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6">
        </div>
      </div>
      

      <div class="sm:col-span-2">
        <label for="message" class="block text-sm font-semibold leading-6 text-gray-900">Message</label>
        <div class="mt-2.5">
          <textarea name="message" v-model="message" required id="message" rows="4" class="block w-full rounded-md border-0 px-3.5 py-2 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"></textarea>
        </div>
      </div>

    </div>
    <div class="mt-10">
      <button type="submit" id="btn" class="block w-full rounded-md bg-green-600 px-3.5 py-2.5 text-center text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600">Let's talk</button>
    </div>
  </form>


</div>
</template>

<script>

export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      message: '',
    };
  },

  methods: {
    submitForm() {
      if (this.validateForm()) {
       
        console.log('message is submitted successfully');
       
      }
    },
    validateForm() {

      if (!this.firstName || !this.lastName || !this.email || !this.message) {
        alert('Please fill in all fields');
        return false;
      }


      return true;
    },
  },
};


</script>