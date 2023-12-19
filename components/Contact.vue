<template>
  <div class="w-full py-20 px-4 bg-white">

    <div class="max-w-6xl mx-auto flex flex-col">

      <h1 class="text-2xl  sm:text-6xl text-green-600 font-bold text-center py-8">
        Contact Us
      </h1>

      <div class="w-full flex flex-col-reverse py-20 px-4 my-4 mx-auto text-green-400  bg-gray-400">

      <div class="w-full py-20 px-4 mx-auto text-green-400 my-4 bg-black">
        <form
          class="flex flex-col gap-3 sm:flex items-center justify-between w-full"
        >
            <label for="name"> Name:</label>
          <input
            class="p-3 flex w-full rounded-md text-black"
            type="text"
            placeholder="enter your name"
            name="name"
          />

          <label for="email"> Email:</label>
          <input
            class="p-3 flex w-full rounded-md text-black"
            type="email"
            placeholder="enter your email address"
            name="email"
          />

          <label for="message"> Your message:</label>
          <input
            class="p-3 flex w-full rounded-md text-black"
            type="message"
            placeholder="message"
            name="message"
          />
          <button
            class="bg-[#00df9a] text-black rounded-md font-medium w-48 ml-4 my-6 px-6 py-3"
          >
            submit
          </button>
        </form>
      </div>
      <div class="text-2xl  sm:text-3xl text-green-600 font-bold text-center py-8">
        <h1>Than you for your message</h1>
      </div>

    </div>

    </div>
  </div>
</template>
