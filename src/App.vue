  <template>
  <!-- <div class="app" @create="showInput"> -->
  <div class="app">
    <dialog-form @adress="inAdress" />
    <text-adress :text="text" />
  </div>
</template>


<script>
import dialogForm from "@/components/dialogForm.vue";
import textAdress from "@/components/textAdress.vue";
export default {
  components: { dialogForm, textAdress },
  data() {
    return {
      text: "",
    };
  },
  methods: {
    inAdress(dates) {
      this.text = dates.text;
      console.log("parent", this.text, dates.testring);
    },
  },
};
</script>

<style>
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

.hidden {
  display: none;
}

.disable {
  cursor: auto;
  opacity: 0.4;
}

.disable.btn:hover {
  color: black;
  background: #fff;
}

.btn:hover {
  color: #fff;
  background: #f00;
}

.label-text {
  padding-right: 20px;
}

.adress {
  margin-top: 20px;
  padding: 15px;
}

label {
  display: block;
}
</style>