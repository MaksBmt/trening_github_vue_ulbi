<template>
  <form>
    <p>Если хотите доставку - нажмите кнопку "ДА"</p>
    <button
      :disabled="isDisable"
      type="button"
      @click.stop="showInput"
      :class="{ disable: transport }"
      class="btn dialog"
    >
      Да
    </button>
    <!-- <div class="adress" v-if="transport" :class="{ hidden: isAdress }">
      <label for="adress">Ввидите адрес доставки:</label>
      <textarea
        name="adress"
        id="adress"
        cols="30"
        rows="10"
        required
        v-model="text"
      ></textarea> 
    </div>-->

    <div class="adress" v-if="transport" :class="{ hidden: isAdress }">
      <label for="adress">Ввидите адрес доставки:</label>
      <textarea
        name="adress"
        id="adress"
        cols="30"
        rows="10"
        required
        v-model="text"
      ></textarea>
    </div>

    <button
      class="btn"
      @click.prevent="showAdress"
      v-if="transport"
      :class="{ hidden: isAdress }"
    >
      Оформить
    </button>
  </form>
</template>


<script>
export default {
  data() {
    return {
      transport: "",
      text: "",
      isDisable: false,
      isAdress: false,
    };
  },
  methods: {
    showInput() {
      this.transport = true;
      this.isDisable = true;
    },
    showAdress() {
      // this.$emit("adress", this.text);
      this.$emit("adress", { text: this.text, testring: "testing" });
      // this.text;
      // console.log(this.text);
      this.isAdress = true;
      // $emit("showAdress", this.isAdress);
    },
  },
};
</script>

<!-- <style scoped>
form {
  display: flex;
  flex-direction: column;
  width: 600px;
} 

.btn {
  width: 100px;
  margin-top: 15px;
  margin-left: auto;
  margin-right: auto;
  align-self: flex-end;
  padding: 10px 15px;
  border: 1px solid teal;
  background: none;
  cursor: pointer;
}

.dialog {
  color: black;
}

.btn:hover {
  color: #fff;
  background: #f00;
}
</style> -->