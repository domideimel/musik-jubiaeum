<template>
  <div class="text-white text-center" id="home">
    <div class="row hero bg-red-8">
      <div class="col flex-center flex column items-center">
        <div class="q-py-xl">
          <h1>50 Jahre</h1>
          <h3>Negertalmusikanten</h3>
          <p class="text-body1">
            Uns gibt es schon 50 Jahre.. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Autem, consectetur
            eos
            in neque quam quis?
          </p>
          <q-btn class="q-mt-lg" flat round icon="keyboard_arrow_down" color="white" size="lg" />
        </div>
      </div>
    </div>
    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 280">
      <path fill="#d32f2f" fill-opacity="1"
            d="M0,128L80,149.3C160,171,320,213,480,202.7C640,192,800,128,960,122.7C1120,117,1280,171,1360,197.3L1440,224L1440,0L1360,0C1280,0,1120,0,960,0C800,0,640,0,480,0C320,0,160,0,80,0L0,0Z"></path>
    </svg>
  </div>
</template>

<script>
export default {
  name: 'Hero'
}
</script>

<style scoped lang="sass">
  #home
    margin: -24px -24px 0 -24px
    .hero
      width: 100vw

    svg
      margin: 0 -24px
      max-width: 100%

</style>
