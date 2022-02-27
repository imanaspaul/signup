<template>
  <div class="hello">
    <GoogleLogin
      :params="params"
      :logoutButton="false"
      :onFailure="onFailure"
      :onSuccess="onSuccess"
      >Logout</GoogleLogin
    >
  </div>
</template>

<script>
  import GoogleLogin from 'vue-google-login';
  export default {
    name: 'HelloWorld',
    data() {
      return {
        // client_id is the only required property but you can add several more params, full list down bellow on the Auth api section
        params: {
          client_id:
            '913916646115-0kgs4iftssh35tq09mtg60ge7prsrfn3.apps.googleusercontent.com',
        },
        // only needed if you want to render the button with the google ui
        renderParams: {
          width: 250,
          height: 50,
          longtitle: true,
        },
      };
    },
    components: {
      GoogleLogin,
    },
    methods: {
      onSuccess(googleUser) {
        console.log(googleUser);

        // This only gets the user information: id, name, imageUrl and email
        // console.log(googleUser.getBasicProfile());
      },
      onFailure(googleUser) {
        console.log(googleUser);

        // This only gets the user information: id, name, imageUrl and email
        // console.log(googleUser.getBasicProfile());
      },
    },
  };
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h3 {
    margin: 40px 0 0;
  }
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: inline-block;
    margin: 0 10px;
  }
  a {
    color: #42b983;
  }
</style>
