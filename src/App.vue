<template>
    <div class="px-5 relative flex justify-center items-center lg:mx-auto h-screen w-full login-bg">
      <!-- HEADER -->
      <div class="absolute inset-0 top-6 h-1/6 w-full">
        <div class="w-full lg:w-3/4 px-5 lg:px-0 mx-auto flex justify-between items-center pb-2 border-b border-[#D3D3DD]">
          <div class="flex gap-2 items-center">
            <img alt="mra logo" src="/src/assets/images/mra-logo.svg" />
            <img src="" alt="">
            <p class="text-[#5C5C7E] font-bold text-lg hidden lg:block">{{ jsonData.common.appname }}</p>
          </div>
          <p class="flex gap-4 lg:gap-8 text-[#5C5C7E]">
            <span class="hover:underline hover:cursor-pointer hover:text-[#373779]">{{ jsonData.header.privacy }}</span>
            <span class="hover:underline hover:cursor-pointer hover:text-[#373779]">{{ jsonData.header.support }}</span>
          </p>
        </div>
      </div>
      <div class="w-full lg:w-3/4 mx-5 lg:mx-auto grid lg:grid-cols-2 lg:gap-20 gap-10 z-50">
        <!-- IMAGE CONTAINER -->
        <div class="w-full hidden lg:block">
          <img class="mx-auto" alt="office image" src="/src/assets/images/office.svg" />
        </div>
        <!-- LOGIN FORM CONTAINER -->
        <div class="w-full flex justify-center items-center">
          <div class="rounded-md overflow-y-auto p-8 min-w-full sm:min-w-[400px] md:min-w-[400px] shadow-md sign-in-box bg-neutral-100">
            <form class="space-y-3" @submit.prevent="onSubmit">
              <div class="text-start">
                <h2 class="pb-1 text-3xl font-semibold text-[#169447]">
                  {{ jsonData.sign_in.text.signin }}
                </h2>
                <p class="pb-2 text-sm text-[#3D5948] dark:text-night-200">{{ jsonData.sign_in.text.welcomeback }}</p>
              </div>
  
              <div class="space-y-3 text-left">
                <div class="form__group">
                  <div class="relative">
                    <input v-model="form.user_id" id="email" class="border-solid border-2 rounded-md  peer block h-10" type="text" placeholder=" " />
                    <label class="absolute top-2 left-1 origin-[0] -translate-y-4 scale-95 transform bg-white px-2 text-sm text-gray-500 duration-300 peer-placeholder-shown:top-1/2 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:scale-100 peer-focus:top-2 peer-focus:-translate-y-4 peer-focus:scale-95 peer-focus:px-2 peer-focus:text-primary-500 dark:bg-night-700 dark:text-night-200" for="email">
                      {{ jsonData.sign_in.text.user_id }}
                    </label>
                  </div>
                 
                </div>
  
                <div class="form__group">
                  <div class="relative">
                    <input v-model="form.password" id="password" class="peer block h-10 border-solid border-2 rounded-md" placeholder=" " />
                    <label class="absolute top-2 left-1 origin-[0] -translate-y-4 scale-95 transform bg-white px-2 text-sm text-gray-500 duration-300 peer-placeholder-shown:top-1/2 peer-placeholder-shown:-translate-y-1/2 peer-placeholder-shown:scale-100 peer-focus:top-2 peer-focus:-translate-y-4 peer-focus:scale-95 peer-focus:px-2 peer-focus:text-primary-600 dark:bg-night-700 dark:text-night-200" for="password">
                      {{ jsonData.sign_in.text.password }}
                    </label>
                   
                  </div>
                  
                </div>
              </div>
  
              <div class="flex items-center justify-between space-x-3 pb-3">
                <div class="flex items-center">
                  <input id="remember-me" class="cursor-pointer" type="checkbox" name="remember-me" />
                  <label class="ml-2 block text-sm text-gray-400 dark:text-night-200" for="remember-me">
                    {{ jsonData.sign_in.text.remember_me }}
                  </label>
                </div>
  
                <div class="text-sm">
                  <a class="font-medium text-[#58597F] hover:text-[#2f3391]" href="#">
                    {{ jsonData.sign_in.text.forgot_password }}
                  </a>
                </div>
              </div>
  
              <!-- Submit Button -->
              <div class="flex justify-center">
                <button id="submit-button" class="group relative flex w-full justify-center rounded-full border border-transparent bg-[#169447] py-2 px-4 text-sm font-medium text-white focus:outline-none focus:ring-2 focus:ring-[#169447] focus:ring-offset-2 hover:bg-[#169447]" type="submit">
               <span>{{ jsonData.sign_in.text.signin }}</span> 
                </button>
              </div>
  
              <!-- POWERED BY -->
              <div class="flex justify-start pt-3">
                <div class="text-sm text-[#6D8275]">
                  {{ jsonData.sign_in.text.poweredby}}
                  <a class="text-[#3D5948] font-medium hover:text-[#169447]" href="#">
                    {{ jsonData.sign_in.text.doer }}
                  </a>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </template>


<script setup>
import jsondata from '@/assets/data/bn.json'

const jsonData = jsondata;


  let form = {
    user_id: '',
    password: ''
  };
  



</script>

<style scoped>
  .login-bg {
    background-image: url('/src/assets/images/login-bg.png');
    background-repeat: no-repeat;
    background-size: cover;
  }
</style>