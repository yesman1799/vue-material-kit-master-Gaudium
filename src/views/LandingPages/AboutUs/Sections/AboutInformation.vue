<script setup>
// example components
import DefaultInfoCard from "../../../../examples/cards/infoCards/DefaultInfoCard.vue";
</script>
<template>
  <section class="py-7">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6">
          <div class="row justify-content-start">
            <DefaultInfoCard
              color="info"
              icon="public"
              title="Fully integrated"
              description="We get insulted by others, lose trust for those We get back
                  freezes"
            />
            <DefaultInfoCard
              color="info"
              icon="payments"
              title="financni hodnota"
              description="lorem ipsum"
            />
          </div>
          <div class="row justify-content-start mt-4">
            <DefaultInfoCard
              color="info"
              icon="apps"
              title="100 % naše výroba"
              description="Naše produkty si sami výrábíme z znovuvyužitelných zdrojů"
            />
            <DefaultInfoCard
              color="info"
              icon="3p"
              title="Pečlivost"
              description="Staráme se o naše produkty a zákazníky"
            />
          </div>
        </div>
        <div class="col-lg-4 ms-auto mt-lg-0 mt-6" style="text-align: center">
          <h2>Kde se nacházíme?</h2>
          <h4>Guadium 2022 s.r.o.</h4>
          <h4>tř. Budovatelů 2327/106</h4>
          <h4>Most 434 01</h4>
          <h4>Česká republika</h4>
        </div>
      </div>
    </div>
  </section>
</template>
