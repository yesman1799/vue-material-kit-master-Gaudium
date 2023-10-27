<script setup>
import RotatingCard from "../../../examples/cards/rotatingCards/RotatingCard.vue";
import RotatingCardFront from "../../../examples/cards/rotatingCards/RotatingCardFront.vue";
import RotatingCardBack from "../../../examples/cards/rotatingCards/RotatingCardBack.vue";
import DefaultInfoCard from "../../../examples/cards/infoCards/DefaultInfoCard.vue";
</script>
<template>
  <section class="my-5 py-5">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-4 ms-auto me-auto p-lg-4 mt-lg-0 mt-4">
          <RotatingCard>
            <RotatingCardFront
              image="https://images.unsplash.com/photo-1569683795645-b62e50fbf103?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=987&q=80"
              icon="touch_app"
              title="Naše Nejlepší <br /> Produkty"
              description="Máme tu pro vás všechno, co vaše tělo potřebuje"
            />

            <RotatingCardBack
              image="https://images.unsplash.com/photo-1498889444388-e67ea62c464b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1365&q=80"
              title="Již Brzy"
              description="You will save a lot of time going from prototyping to full-functional
                code because all elements are implemented."
              :action="[
                {
                  route: './/sections/page-sections/hero-sections.html',
                  label: 'Start with Headers',
                },
              ]"
            />
          </RotatingCard>
        </div>
        <div class="col-lg-6 ms-auto">
          <div class="row justify-content-start">
            <DefaultInfoCard
              icon="content_copy"
              title="Přírodní léčiva"
              description="justo nec ultrices dui sapien eget mi proin sed libero enim sed faucibus turpis in
              "
            />
            <DefaultInfoCard
              icon="flip_to_front"
              title="Obnova kůže"
              description="bibendum enim facilisis gravida neque convallis a cras semper auctor neque vitae tempus quam pellentesque"
            />
          </div>
          <div class="row justify-content-start mt-5">
            <DefaultInfoCard
              class="mt-3"
              icon="price_change"
              title="Ušetři peníze a uzdrav tělo"
              description="Už nekupujte chemické masky a krémy! S námi jsou 100% přírodní"
            />
            <DefaultInfoCard
              class="mt-3"
              icon="devices"
              title="support 24/7"
              description="chatbot Emily si s vámi rád promluví"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
