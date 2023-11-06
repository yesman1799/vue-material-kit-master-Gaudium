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
              title="FORMAMNON"
              description="Formmanmnom je jedinečný produkt starých mistrů upravený do současné podoby dermatologem s více jak 40ti letou praxí."
            />

            <RotatingCardBack
              image="https://images.unsplash.com/photo-1498889444388-e67ea62c464b?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1365&q=80"
              title="Popis Formamnonu"
              description="Formamnon je odzkoušený na mnoha pacientech se statisticky významným účinkem, zejména pokud jde o mykózy nejen na prstech nohou. Genialita Formanonu je v jednoduchosti, Xylopie spolu s tea tree olejem vykazují silnou antimikrobiální a antimykotickou účinnost. Taktéž šalvěj má rovněž příznivé účinky na pleť a snižuje nadměrné pocení. Účinek je navíc posílen konzervačním přípravkem s obsahem stříbra určeným pro kosmetické produkty tohoto typu a hlavně s neurodipeptidem alaptidem, jehož obecné regenerační účinky jsou dostatečně známy díky jeho fenomenálnímu mechanismu účinku jeho působení."
            />
          </RotatingCard>
        </div>
        <div class="col-lg-6 ms-auto">
          <div class="row justify-content-start">
            <DefaultInfoCard
              icon="content_copy"
              title="Přírodní léčiva"
              description="Produkt je vytvořen 100% z přírodních látek."
            />
            <DefaultInfoCard
              icon="flip_to_front"
              title="Intenzivní obnova kůže"
              description="Výborné na kožní rány, kousance, štípance od obtížného hmyzu, mykózy, pupínky, škrábance, přírodní výroba produktu."
            />
          </div>
          <div class="row justify-content-start mt-5">
            <DefaultInfoCard
              class="mt-3"
              icon="price_change"
              title="Genialita Formamnonu je v jednoduchosti"
              description="Jelikož obsahuje pouze 7 látek, je jednoduchý a tedy jedinečný."
            />
            <DefaultInfoCard
              class="mt-3"
              icon="devices"
              title="Bezkonkurenční na trhu"
              description=" Přípravek lze použít nejen na mykotické postižení prstů u nohou, ale opravdu na mnoho dalších kožních postižení po celém těle. "
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
