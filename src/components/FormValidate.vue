<template>
  <div class="container">
    <!-- <p v-if="error.includes('Email')">
      This email Exists
    </p> -->
    <!-- <p v-for="item in error" v-bind:key="item"> 
      <span v-if="item ">{{item}}</span>
    </p> -->
    <form action="" v-on:submit.prevent>
      <div class="form-group mt-2 text-start">
        <input type="email" v-model="form.Email" class="form-control" placeholder="Email" />
        <span class="text-danger " v-if="error.includes('Email')">This Email field is Required</span>
      </div>
      <div class="form-group mt-2 text-start">
        <input type="password" v-model="form.Password" class="form-control" placeholder="Password" />
        <span class="text-danger " v-if="error.includes('Password')">This Password field is Required</span>
      </div>
      <div class="form-group mt-2 text-start">
        <input type="checkbox" value="Java" id="java" v-model="form.profesional" />
        <label class="ms-2" for="java">Java</label>
      </div>
      <div class="form-group mt-2 text-start">
        <input type="checkbox" value="Php" id="php"  v-model="form.profesional" />
        <label class="ms-2" for="php">PHP</label>
      </div>
      <div class="form-group mt-2 text-start">
        <input type="checkbox" value="C#" id="C#"  v-model="form.profesional" />
        <label class="ms-2" for="C#">C#</label> <br>
        <span class="text-danger " v-if="error.includes('profesional')">This Profisional field is Required</span>
      </div>
      <h1 class="text-center text-info">Gender</h1>
      <div class="form-group mt-2 text-start">
        <input type="radio" value="Male" name="gender"  v-model="form.Gender" />
        <label class="ms-2">Male</label>

      </div>
      <div class="form-group mt-2 text-start">
        <input type="radio" value="Female" name="gender" v-model="form.Gender"  />
        <label class="ms-2" >Female</label> <br>
         <span class="text-danger " v-if="error.includes('Gender')">This Gender field is Required</span>
      </div>
      <div class="form-group mt-2 text-start">
        <input type="submit" class="btn btn-info"  @click="dataSubmit"/>
      </div>

    </form>
  </div>
</template>

<style scoped>
</style>

<script>
// import { defineComponent } from '@vue/composition-api'

export default {
  name: "FormValidate",
  data(){
    return{
      form :{
        Email:'',
        Password:'',
        profesional:[],
        Gender:''
      },
      error:[]
    }
  },
  methods:{
    dataSubmit(){
      this.error = []
      let lenghterror=0;
      for(let items in this.form){
        if(this.form[items] =="" || this.form[items].length===0)
        this.error.push(items)
        lenghterror =this.form[items].length;
      }
      console.log(lenghterror);
      // console.log(this.error);
      
    }
  }
};
</script>
