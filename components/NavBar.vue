<template>
    <div class="mx-auto my-0 flex flex-col bg-black w-full sm:flex sm:flex-row text-yellow-100 justify-between py-8 px-10">
        <h1 class="text-2xl sm:text-3xl  font-bold text-center text-green-400">
            <a href="/">Finace-Company</a>
         
        </h1>
        <div>
            <ul class=" text-white flex mt-3  sm:flex gap-2 sm:gap-6 mr-4 justify-between items-center">
                <li><NuxtLink to="/">Home</NuxtLink></li>
                <li><NuxtLink to="about">About Us </NuxtLink></li>
                <li><NuxtLink to="projects"> Projects</NuxtLink> </li>
                <li><NuxtLink to="contact"> Contact Us</NuxtLink></li>
            </ul>
        </div>
    </div>
</template>