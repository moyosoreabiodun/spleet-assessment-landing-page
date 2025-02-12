<template>

<header class="flex justify-between items-center container mx-auto mt-4"> 
  <div class="flex items-center space-x-2">
    <img src="/public/Logomark.png" alt="Logo Image" class="h-7 w-7">
    <span class="font-bold text-[#181D27] font-body" >Capsule</span>
  </div>
  <nav class="space-x-4 text-[#616C74] font-body">
    <a href="#about">About Us</a>
    <a href="#pricing">Pricing</a>
    <a href="#product">Product</a>
    <a href="#support">Support</a>
  </nav>
  <button class=" px-4 py-1 text-[#1570EF] border-2 border-[#1570EF] rounded-sm">Get Capsule</button>
</header>

<section class="flex flex-row mx-auto mt-10 p-5">
  <div class="w-1/2">
    <h1 class="font-heading text-3xl text-[#212121] font-merriweather font-bold">You do the work, <br> 
      We'll do the talk
    </h1>
    <p class="mt-3 text-[#35383F]">Move your customers’ <span class="text-[#1570EF]">enquiry</span> to our <br> team of experts</p>
    <p class="mt-3 text-[#616C74] text-sm">Let us manage your customer relationship from their first call till <br> they become your raving fans</p>
    <button class="mt-6 bg-[#1570EF] text-white px-12 py-1 ">Get Started</button>
  </div>
  <div class="relative w-48 h-48 ml-7 mt-4">
    <!-- <img src="" alt="Highlight 1"> -->
    <img src="/public/Frame 11259.png" alt="" class="absolute top-[-8px] left-[-8px] w-40 h-40 object-cover" >
    <img src="/public/Frame 11258.png" alt="" class="absolute top-10 left-20 w-40 h-40 object-cover">
    <!-- <img src="" alt="Highlight 2"> -->
  </div>
</section>

<section class="bg-[#1570EF] mt-10 px-10 py-7">
   <!-- Show 4 random comments with name & body -->
   <CommentList :limit="4" :fields="['body']" title="" :comments="fourComments" :columns="4" charLimit="50" class="bg-white h-40 width-40 text-[#474B50] text-center"/>
</section>

<section>
  <div class="flex flex-row">
   <!-- Show 2 random comments with only name & email -->
   <CommentList :limit="2" :fields="['name', 'body']" title="What you get" :comments="twoComments" :columns="2" charLimit="150" class="text-center"/>
  </div>
</section>

<section>
  <h1>Choose a plan that works for you</h1>
  <div>
      <div class="flex flex-row gap-2 mx-auto px-2">
        <img src="/public/Logomark.png" alt="">
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
    <CommentTable title="" />
  </div>
</section>

<section class="container mx-auto bg-blue-600 text-center">
  <h1>Join thousands of entrepreneurs using Capsule <br>
    to improve their business communications.
  </h1>
  <p>Ready to make your customers love your business?</p>
  <button>Join Now</button>
</section>

<footer>
  <div class="flex flex-row justify-between">
    <div>
      <div>
        <img src="/public/Logomark.png" alt="">
        <h1>Capsule</h1>
      </div>
      <div>
        <p>hello@capsule.africa</p>
        <p>+234 1 343 8692</p>
      </div>
      <div class="flex flex-row justify-between">
        <img src="/public/facebook.png" alt="">
        <img src="/public/twitter.png" alt="">
        <img src="/public/instagram.png" alt="">
        <img src="/public/linkedin.png" alt="">
      </div>
    </div>
    <div class="text-left">
      <h1>Company</h1>
      <p> Help & Support</p>
      <p>About Us</p>
      <p>Product</p>
      <p>Media</p>
      <p>FAQs</p>
    </div>
    <div class="text-right">
      <h1>Address</h1>
      <p>The London Mall, 3 Standard Way,<br>Phase I, Abuja</p>
    </div>
  </div>
  <div class="flex flex-row justify-between">
    <div>
      <p>© 2025 Capsule Africa</p>
      <p>All rights reserved</p>
    </div>
   <div>
    <p>Terms & Agreement</p>
    <p>Privacy Policy</p>
   </div>
  </div>
</footer>



</template>




<script setup>
import CommentList from '@/components/CommentList.vue'; // Import the component
import PricingCard from '@/components/PricingCard.vue';
import CommentTable from '@/components/CommentTable.vue';
</script>


<style></style>
