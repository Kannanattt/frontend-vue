<template>
<div
    style="height: 100%; width: 100%;  display: flex; justify-content: center; align-items: center;"
  >
 <v-form
   style="height: 50%; width: 50%; "
    ref="form"
    v-model="valid"
    lazy-validation
  >
<v-card width="100%" height="100%" style=" display: flex; flex-direction:column; align-items: center;">
  <h1> เข้าสู่ระบบ</h1>
    <v-text-field
      v-model="name"
      :counter="10"
      :rules="nameRules"
      label="ชิ่อ"
      required
    ></v-text-field>

    <v-text-field
      v-model="email"
      :rules="emailRules"
      label="รหัสผ่าน"
      required
    ></v-text-field>

    

    <v-btn
      :disabled="!valid"
      color="success"
      class="mr-4"
      @click="validate"
    >
        เข้าสู่ระบบ
    </v-btn>

    
</v-card>
  </v-form>
</div>
  </template>

<<script>
  export default {
    data: () => ({
      valid: true,
      name: '',
      nameRules: [
        v => !!v || 'Name is required',
        v => (v && v.length <= 10) || 'Name must be less than 10 characters',
      ],
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+\..+/.test(v) || 'E-mail must be valid',
      ],
      select: null,
      items: [
        'Item 1',
        'Item 2',
        'Item 3',
        'Item 4',
      ],
      checkbox: false,
    }),

   methods: {
    login() {
      if (this.$refs.form.validate(true)) {
        localStorage.setItem("username", this.username);
        this.$EventBus.$emit("getUsername");
        this.$EventBus.$emit("checklogin");
        this.$router.push({ path: "/" }).catch(() => {});
       
      }
    },
   },};
</script>
<style>

</style>