<template>
  <!-- <register></register> -->
  <login></login>
</template>

<script>

import login from './components/login'
// import register from './components/register'
export default {
  name: 'App',

  components: {
    login:login
    // register:register
  },

  data: () => ({
    //
  }),
};
</script>
