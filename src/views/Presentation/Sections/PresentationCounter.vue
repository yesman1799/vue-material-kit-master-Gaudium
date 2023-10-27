<script setup>
import DefaultCounterCard from "../../../examples/cards/counterCards/DefaultCounterCard.vue";
</script>

<template>
  <section class="pt-3 pb-4" id="count-stats">
    <div class="container">
      <div class="row">
        <div class="col-lg-9 z-index-2 border-radius-xl mx-auto py-3">
          <div class="row">
            <div class="col-md-4 position-relative">
              <DefaultCounterCard
                color="success"
                title="Podpora Ukrajiny"
                description="Слава Україні! Героям слава!"
                :count="70"
                suffix="+"
                :duration="3000"
                divider="vertical"
              />
            </div>
            <div class="col-md-4 position-relative year">
              <DefaultCounterCard
                color="success"
                title="Tuzemská firma"
                description="Česká firma založena roku 2022"
                :count="2022"
                suffix=""
                :duration="3000"
                divider="vertical"
              />
            </div>
            <div class="col-md-4">
              <DefaultCounterCard
                color="success"
                title="support"
                description="Máme 24/7 podporu prostřednictvím chatbota"
                :count="24"
                suffix=" / 7"
                :duration="3000"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
