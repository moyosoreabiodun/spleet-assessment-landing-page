<template>

<div class="max-w-screen-xl overflow-hidden">
  <header class="flex items-center justify-between container mt-4 text-sm"> 
  <div class="flex items-center space-x-2">
    <img src="/public/Logomark.png" alt="Logo Image" class="h-7 w-7">
    <span class="font-bold text-[#181D27] font-body" >Capsule</span>
  </div>
  <nav class="flex space-x-4 text-[#616C74] font-body">
    <a href="#about">About Us</a>
    <a href="#pricing">Pricing</a>
    <a href="#product">Product</a>
    <a href="#support">Support</a>
  </nav>
  <button class="px-4 py-2 text-[#1570EF] text-sm border-2 border-[#1570EF] rounded-sm font-body">Get Capsule</button>
</header>

<section class="flex flex-row mx-auto mt-10 p-5">
  <div class="w-1/2">
    <h1 class="font-heading text-3xl text-[#212121] font-merriweather font-bold">You do the work, <br> 
      We'll do the talk
    </h1>
    <p class="mt-3 text-[#35383F] font-body">Move your customers’ <span class="text-[#1570EF]">enquiry</span> to our <br> team of experts</p>
    <p class="mt-3 text-[#616C74] text-sm font-body">Let us manage your customer relationship from their first call till <br> they become your raving fans</p>
    <button class="mt-6 bg-[#1570EF] text-white px-12 py-1 font-body">Get Started</button>
  </div>
  <div class="relative w-48 h-48 ml-7 mt-4">
    <!-- <img src="" alt="Highlight 1"> -->
    <img src="/public/Frame 11259.png" alt="" class="absolute top-[-8px] left-[-8px] w-40 h-40 object-cover" >
    <img src="/public/Frame 11258.png" alt="" class="absolute top-10 left-20 w-40 h-40 object-cover">
    <!-- <img src="" alt="Highlight 2"> -->
  </div>
</section>

<section class="bg-[#1570EF] mt-16 px-10 py-10">
   <!-- Show 4 random comments with body -->
   <CommentList :limit="4" :fields="['body']" title="" :comments="fourComments" :columns="4" charLimit="50" class="bg-white h-30 width-40 px-2 text-[#474B50] flex text-center justify-center font-body"/>
</section>

<section>
  <div class="flex flex-row mt-16">
   <!-- Show 2 random comments with only name & body -->
   <CommentList :limit="2" :fields="['name', 'body']" title="What you get" :comments="twoComments" :columns="2" charLimit=150 class="text-center px-8 py-4 font-body"/>
  </div>
</section>

<section class="mt-16 mx-auto w-full overflow-hidden">
  <h1 class="text-center mb-8 font-bold font-heading text-2xl">Choose a plan that works for you</h1>
  <div class="font-body">
      <div class="flex flex-row justify-between mx-auto px-2">
        <img src="/public/Logomark.png" alt="" class="mt-12 w-32 h-32">
        <PricingCard 
        plan="Starter Plan" 
        price="N25, 000/month" 
        description="For businesses with few customers" 
        buttonText="Subscribe Here"
      />
      <PricingCard 
        plan="Growth Plan" 
        price="N50, 000/month" 
        description="For growing businesses" 
        buttonText="Subscribe Here"
      />
      <PricingCard 
        plan="All Access" 
        price="Custom" 
        description="For e-commerce and retail businesses" 
        buttonText="Calculate Your Cost"
      />
    </div>
    <CommentTable title="" class="text-sm py-0 px-0 font-body" />
  </div>
</section>

<section class="container mx-auto bg-blue-600 text-center mt-16 text-white py-6 rounded-lg font-body">
  <h1>Join thousands of entrepreneurs using Capsule <br>
    to improve their business communications.
  </h1>
  <p class="mt-2">Ready to make your customers love your business?</p>
  <button class="bg-white text-blue-600 px-12 py-2 mt-3">Join Now</button>
</section>

<footer class="w-full bg-[#FEF8E7] mt-12 px-4 py-8 font-body">
  <div class="flex flex-row justify-between">
    <div>
      <div class="flex items-center space-x-2 mb-3">
      <img src="/public/Logomark.png" alt="Logo Image" class="h-7 w-7">
      <span class="font-bold text-[#181D27] font-body" >Capsule</span>
    </div>
      <div class="text-sm">
        <p>hello@capsule.africa</p>
        <p>+234 1 343 8692</p>
      </div>
      <div class="flex flex-row justify-between mt-3">
        <img src="/public/facebook.png" alt="Facebook Icon" class="h-5 w-5">
        <img src="/public/twitter.png" alt="Twitter Icon" class="h-5 w-5">
        <img src="/public/instagram.png" alt="Instagram Icon" class="h-5 w-5">
        <img src="/public/linkedin.png" alt="LinedIn Icon" class="h-5 w-5">
      </div>
    </div>
    <div class="text-left text-sm">
      <h4 class="font-bold mb-3">Company</h4>
      <p> Help & Support</p>
      <p>About Us</p>
      <p>Product</p>
      <p>Media</p>
      <p>FAQs</p>
    </div>
    <div class="text-right text-sm">
      <h4 class="font-bold mb-3">Address</h4>
      <p>The London Mall, 3 Standard Way,<br>Phase I, Abuja</p>
    </div>
  </div>
  <div class="flex flex-row justify-between mt-4">
    <div class="text-sm">
      <span class="mr-4">© 2025 Capsule Africa</span>
      <span>All rights reserved</span>
    </div>
   <div class="text-sm">
    <span class="mr-4">Terms & Agreement</span>
    <span>Privacy Policy</span>
   </div>
  </div>
</footer>
</div>


</template>


<script setup>
import CommentList from '@/components/CommentList.vue';
import PricingCard from '@/components/PricingCard.vue';
import CommentTable from '@/components/CommentTable.vue';
</script>


<style></style>
