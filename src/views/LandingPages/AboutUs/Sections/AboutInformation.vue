<script setup>
</script>
<template>
  <section class="py-7">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6 my-4">
          <iframe
            src="https://storage.googleapis.com/maps-solutions-1w6ugz8fn2/locator-plus/aac7/locator-plus.html"
            class="w-100" height="400" allowfullscreen="" loading="lazy"></iframe>
        </div>
        <div class="col-lg-4 ms-auto mt-lg-0 mt-6" style="text-align: center">
          <h2>{{ $t('aboutus.mapTitle') }}</h2>
          <h4>Guadium 2022 s.r.o.</h4>
          <h4>Moskevská 14</h4>
          <h4>Most 1 434 01</h4>
          <h4>{{ $t('aboutus.mapCountry') }}</h4>
        </div>
      </div>
    </div>
  </section>
</template>
