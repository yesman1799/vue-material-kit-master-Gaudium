<script setup>
// example components
import TransparentBlogCard from "../../../../examples/cards/blogCards/TransparentBlogCard.vue";
import BackgroundBlogCard from "../../../../examples/cards/blogCards/BackgroundBlogCard.vue";

//Vue Material Kit 2 components
import post1 from "@/assets/img/examples/testimonial-6-2.jpg";
import post2 from "@/assets/img/examples/testimonial-6-3.jpg";
import post3 from "@/assets/img/examples/blog-9-4.jpg";
import post4 from "@/assets/img/examples/blog2.jpg";
</script>
<template>
  <section class="py-3">
    <div class="container">
      <div class="row">
        <div class="col-lg-6">
          <h3 class="mb-5">Zkuste naše novinky</h3>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-3 col-sm-6">
          <TransparentBlogCard
            :image="post1"
            title="FORMAMNON"
            description="nisl nisi scelerisque eu ultrices vitae auctor eu augue ut lectus arcu bibendum at varius"
          />
        </div>
        <div class="col-lg-3 col-sm-6">
          <TransparentBlogCard
            :image="post2"
            title="Produkt 2"
            description="vel elit scelerisque mauris pellentesque pulvinar pellentesque habitant morbi tristique senectus et netus et malesuada"
          />
        </div>
        <div class="col-lg-3 col-sm-6">
          <TransparentBlogCard
            :image="post3"
            title="Produkt 3"
            description="duis tristique sollicitudin nibh sit amet commodo nulla facilisi nullam vehicula ipsum a arcu cursus"
          />
        </div>
        <div class="col-lg-3 col-md-12 col-12">
          <BackgroundBlogCard
            :image="post4"
            title="Zobrazit seznam produktů"
            description="luctus accumsan tortor posuere ac ut consequat semper viverra nam libero justo laoreet sit amet"
          />
        </div>
      </div>
    </div>
  </section>
</template>
