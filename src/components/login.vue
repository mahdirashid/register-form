<template>
    <div class="col-4 back-register" dir="rtl">
        <div class="logo">
        </div>
        <form class="form-login" style="padding:30px"   @submit.prevent="login">
        <v-text-field
            color="purple darken-2"
            v-model="username"
            label="نام کاربری"
            solo
            rounded
        ></v-text-field>
        <v-text-field 
            
            style="border:red"
            v-model="password"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show1 ? 'text' : 'password'"
            label="گذرواژه"
            solo
            rounded
            @click:append="show1 = !show1"
        ></v-text-field>
        <v-btn style="float=right" rounded="" >ورود</v-btn>
        </form>
    </div>

</template>
<script>

export default {
    name:"login",
    data(){
        return{
            username:"",
            password: "",
            phone:null,
            show1: false,
            rules: {
                min: v => v.length >= 8 || 'حداقل 8 کاراکتر',
        },
        }
    }
}
</script>
<style>
    .back-register{
        
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        height: 400px;
        position: absolute;
        left: 50%;
        top: 50%;
        background-color: gainsboro;
        transform: translate(-50%, -50%);
        border-radius:10px ;
        
    }
    .back-register:before{
        content: "";
        width:408.78px ;
        height: 400px;
        border-radius: 10px;
        position: absolute;
        transform: translate(-50%, -50%);
        left: 50%;
        top: 50%;
        background-color:white;
        opacity: 0.2;
        -webkit-filter: blur(1px);
        -moz-filter: blur(1px);
        -o-filter: blur(1px);
        -ms-filter: blur(1px);
        filter: blur(1px);
    }
    .logo{
        height: 100px;
    }
</style>    