<template>
  <b-modal
    id="modal-error"
    class="modal modal-error"
    title="Error"
    header-bg-variant="dark"
    header-text-variant="light"
    v-model="isShown"
  >
    <p class="modal__desc">
      Много запросов, пожалуйста перезагрузите страницу. 
    </p>
    <template #modal-footer>
      <div class="modal__footer">
        <b-row>
          <b-col>
            <b-button class="modal__btn" variant="success" @click="reload()">
              Перезагрузить
            </b-button>
          </b-col>
          <b-col>
            <b-button
              class="modal__btn"
              variant="secondary"
              @click="goToMain()"
            >
              На главную страницу
            </b-button>
          </b-col>
        </b-row>
      </div>
    </template>
  </b-modal>
</template>

<script>

export default {
  computed: {
    showErrorModal() {
      return this.$store.state.showErrorModal;
    },
  },
  data() {
    return {
      isShown: false,
    };
  },
  methods: {
    reload() {
      this.$router.go();
    },
    goToMain() {
      this.$store.dispatch("toggleError");
      this.$router.push("/");
    },
  },
  watch: {
    showErrorModal: function (val) {
      this.isShown = val;
    },
  },
};
</script>

<style></style>
