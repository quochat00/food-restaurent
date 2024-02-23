<template>
  <div id="app">
      <div v-if="admin">
          <router-view></router-view>
      </div>
      <div v-else>
          <TheHeader />

          <div class="auth-wrapper">
              <div class="auth-inner">
                  <router-view></router-view>
              </div>
          </div>
          <TheFooter />
      </div>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';
import { mapActions } from 'vuex';
import { mapState } from 'vuex';
export default {
  name: 'App',
  components: {
      TheHeader,
      TheFooter,
  },

  created() {
      this.getFoodsData()
  },

  computed: {
      ...mapState(["admin"])
  },

  methods: {
      ...mapActions(["getFoodsData"])
  }
}
</script>

<style>
@import "./assets/css/global_style.css";
</style>

