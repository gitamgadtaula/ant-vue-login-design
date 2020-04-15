<template>
  <div class="home">
    <a-row class="form">
      <a-col :span="14" class="form-left">
        <!-- <h1>Welcome to Rasello ! </h1> -->
        <h2> Sign in </h2>

        <a-form-model 
          :rules="rules" 
          :model="form" 
          ref="ruleForm"
          layout="horizontal">
        <a-form-model-item label="Enter your username" prop="username" ref="username">
        <a-input placeholder="Username" v-model="form.username" class="form-input" size="large">
        <a-icon slot="prefix" type="user" />
        </a-input>
        </a-form-model-item>

        <a-form-model-item label="Enter your password" prop="username" ref="username">
        <a-input-password placeholder="input password" v-model="form.password" class="form-input" size="large">
        <a-icon slot="prefix" type="key" />
        </a-input-password>
        </a-form-model-item>

         <a-form-item>
          <a-checkbox v-decorator="[
          'remember',
          {
            valuePropName: 'checked',
            initialValue: true,
          },
          ]
          ">Remember me</a-checkbox>
        <a class="login-form-forgot" href="">
        Forgot password
        </a>
        </a-form-item>

        <a-button class="my-btn" size="large" @click="onSubmit()"> Login </a-button>
        </a-form-model>
      </a-col>

      <a-col :span="10" class="form-right">
        <div class="form-right-div">
          <img slot="cover" 
          src="https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Apple_logo_black.svg/647px-Apple_logo_black.svg.png" 
          width="100px" height="120px"/>
          <br />
          
        <h1>Welcome to Rasello ! </h1>
          We live for the relentless pursuit to advance Enterprises who quest to
          pioneer their industries by catalyzing their performance through the
          Rasello platforms.
          <hr>
        <h3>At Rasello, we live for the relentless pursuit to advance Enterprises who quest to pioneer and 
            sustain market leadership by catalyzing their performance through the Rasello platforms.
            That pursuit has lead Rasello to operate for over 8 years across 4 countries with a team of 
            40+ people worldwide.
        </h3>

        </div>
      </a-col>
    </a-row>
    <br>

    
  </div>
</template>

<script>

export default {
  data(){
    return {
      form:{
        username:'',
        password:''
      },
      rules: {
        username: [
          { required: true, message: 'Please input Username'},
          { min: 3, max: 5, message: 'Length should be 3 to 10'},
        ],
        password:[
          {required: true, message: "please input your password"},
          {min :5, message: "minimum password length is 5"}
        ]}
    }
  },
   methods: {
    onSubmit() {
      this.$refs.ruleForm.validate(valid => {
        if (valid) {
          alert('submit!');
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    }
   }
}
</script>
<style scoped>
.home{
  margin-top:100px;
  margin-left:160px;
  margin-right:160px;

}
.form{
  border-radius: 12px 12px 12px 12px;
  border: 2px solid rgb(0, 181, 136);
  box-shadow:-5px 2px 7px -3px rgb(20, 90, 165);
  
}
.form-left{
   padding:40px 20px 40px 20px;  
}
.form-right{
  /* background-color:rgb(130, 187,247); */
  /* background-color: #5ae6fd */
  background: linear-gradient(90deg, rgb(47, 199, 181) 0%, rgba(255,255,255,1) 100%, rgba(0,255,241,1) 100%);
  height:100%;
  border-radius: 0px 12px 12px 0px;
}
.form-right-div{
 padding:40px 20px 40px 20px; 
}

.form-input{
  width:50%;
  display:block;
  margin-left: auto;
  margin-right: auto;
  margin-top:10px;
  margin-bottom:10px;
}
.my-btn{
  background-color: rgb(0, 181, 136);
  font-size: 20px;
  /* background: linear-gradient(90deg, rgb(3, 43, 38) 0%, rgba(255,255,255,1) 100%, rgb(8, 125, 179) 100%); */
}
</style>