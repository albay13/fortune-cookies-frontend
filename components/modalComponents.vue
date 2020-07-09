<template>
  <div>
    <b-modal v-model="modalShow" id="modal-scoped" centered>
      <template v-slot:modal-header>
        <h5>ADD YOUR OWN-MADE UP FORTUNE?</h5>
        <p class="btn-exit" @click="close()">x</p>
      </template>

      <template v-slot:default>
        <input
          v-model="message"
          type="text"
          class="form-control"
          maxlength="30"
          placeholder="Enter your own-made up fortune"
        />
      </template>

      <template v-slot:modal-footer>
        <b-button size="sm" variant="success" @click="addFortune()">
          Add Fortune
        </b-button>
        <b-button size="sm" variant="danger" @click="cancel()">
          Cancel
        </b-button>
      </template>
    </b-modal>
  </div>
</template>
<script>
export default {
  data() {
    return {
      modalShow: true,
      message: ""
    };
  },
  methods: {
    addFortune() {
      this.$emit("addFortune", this.message);
    },
    cancel() {
      this.modalShow = false;
      this.$emit("cancel");
    },
    close() {
      this.modalShow = false;
      this.$emit("close");
    }
  }
};
</script>
<style scoped>
.btn-exit {
  cursor: pointer;
}
.modal-mask {
  position: fixed;
  z-index: 9998;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: table;
  transition: opacity 0.3s ease;
}

.modal-wrapper {
  display: table-cell;
  vertical-align: middle;
}

.modal-container {
  width: 300px;
  margin: 0px auto;
  padding: 20px 30px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.33);
  transition: all 0.3s ease;
  font-family: Helvetica, Arial, sans-serif;
}

.modal-header h3 {
  margin-top: 0;
  color: #42b983;
}

.modal-body {
  margin: 20px 0;
}

.modal-default-button {
  float: right;
}

.modal-enter {
  opacity: 0;
}

.modal-leave-active {
  opacity: 0;
}

.modal-enter .modal-container,
.modal-leave-active .modal-container {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
