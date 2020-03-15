<template>
    <div class="back-register red col-4" dir="rtl">
        <div outlined class="logo"></div>
        <form class="form-register"   @submit.prevent="login">
        <v-text-field
        label="نام و نام خانوادگی"
        v-model="name"
        required
        solo
        rounded
        >
        </v-text-field>
        <v-text-field
        v-model="email"
        label="ایمیل"
        :rules="[rules.required, rules.email]"
        required
        solo
        rounded
        >
        </v-text-field>
        <v-text-field
        label="شماره تلفن همراه"
        v-model="phoneNumber"
        type="phone-number"
        required
        solo
        rounded
        >
        
        </v-text-field>
        <v-text-field 
            style="border:red"
            v-model="password"
            :append-icon="show2 ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.min]"
            :type="show2 ? 'text' : 'password'"
            label="گذرواژه"
            solo
            rounded
            @click:append="show2 = !show2"
        ></v-text-field>
        
        </form>
        <v-btn 
        
        rounded
        >
            ثبت نام
        </v-btn>
    </div>
</template>
<script>
export default {
    name:"register",
    data(){
        return{
            name:"",
            email:"",
            phone:null,
            phoneNumber:"",
            password:"",
            show2: false,
            rules: {
                min: v => v.length >= 8 || 'حداقل 8 کاراکتر',
                email: value => {
                const emailpattern = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
                return emailpattern.test(value) || 'ایمیل شما بی اعتبار است'
        }}}
    }
    
}
</script>
<style scoped>
    .back-register{
        padding: 50px;
        background-color: gainsboro;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        height: 550px;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%)
    }
    .logo{
        height: 100px;
    }
</style>