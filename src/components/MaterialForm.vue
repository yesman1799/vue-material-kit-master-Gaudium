<template>
  <div class="container">
    <form>
      <label>{{ $t('form.nameLabel') }}</label>
      <input type="text" v-model="name" name="name" :placeholder="$t('form.nameLabel')" />
      <label>{{ $t('form.emailLabel') }}</label>
      <input type="email" v-model="email" name="email" :placeholder="$t('form.emailLabel')" />
      <label>{{ $t('form.messageLabel') }}</label>
      <textarea
        name="message"
        v-model="message"
        cols="30"
        rows="5"
        :placeholder="$t('form.messageLabel')"
      >
      </textarea>

      <input type="submit" :value="$t('form.send')" />
    </form>
  </div>
</template>

<script>
import emailjs from "emailjs-com";
export default {
  name: "ContactUs",
  data() {
    return {
      name: "",
      email: "",
      message: "",
    };
  },
  methods: {
    sendEmail(e) {
      try {
        emailjs.sendForm(
          "service_6uetk0k",
          "template_sd27c4g",
          e.target,
          "Din7bCPCNolUPSp1u",
          {
            name: this.name,
            email: this.email,
            message: this.message,
          }
        );
      } catch (error) {
        console.log({ error });
      }
      // Reset form field
      this.name = "";
      this.email = "";
      this.message = "";
    },
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
}

.container {
  display: block;
  margin: auto;
  text-align: center;
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
  width: 50%;
}

label {
  float: left;
}

input[type="text"],
[type="email"],
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

input[type="submit"] {
  background-color: #4caf50;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #45a049;
}
</style>
