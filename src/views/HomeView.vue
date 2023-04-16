<template>
  <div class="container">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <section>
      <div class="text-center text-light my-3">
        <h1 class="fw-bold">RTP SLOT MPO08</h1>
        <p class="fs-3">
          RTP Slot MPO08 | Membawa Keberuntungan Serta Kemenangan
        </p>
        <img class="mb-3" alt="" src="../assets/images/bannermpo08.jpg" />
        <a class="btn btn-danger fw-bold fs-3"  href="https://www.kayabets.com/index" target="_blank">
          POLA SLOT KLIK DISINI!!!
        </a>
      </div>
    </section>
    <section>
      <div class="gameBox px-2">
        <div class=" col-12">
          <div class="row row-cols-lg-5 row-cols-sm-4 row-cols-2">
            <div v-for="item in gameIcon" :key="item" class="cal mb-3 py-2">
              <a href="https://www.kayabets.com/electron" target="_blank">
                <img
                  :src="item.url"
                  class="card-img-top"
                  :alt="item.alt"
                />
              </a>
              <div class="progress rounded-pill mt-2 position-relative" style="height: 24px;">
                <p class="position-absolute top-50 start-50 translate-middle text-dark fs-6 fw-bolder">
                  {{item.percentage}}%
                </p>
                <div v-if="over80(item.percentage)"
                  class="progress-bar bg-warning progress-bar-striped progress-bar-animated"
                  role="progressbar"
                  :aria-valuenow="item.percentage"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  :style="`width: ${item.percentage}%`"
                >
                </div>
                <div v-else
                  class="progress-bar bg-success progress-bar-striped progress-bar-animated"
                  role="progressbar"
                  :aria-valuenow="item.percentage"
                  aria-valuemin="0"
                  aria-valuemax="100"
                  :style="`width: ${item.percentage}%`"
                >
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import gameData from '../assets/data.json'
export default {
  data() {
    return {
      banner: gameData.banner,
      gameIcon: gameData.gameIcon
    }
  },
  methods: {
    over80 (num) {
      return num >= 80
    }
  },
  mounted () {
    console.log(gameData.banner)
  }
}
</script>
