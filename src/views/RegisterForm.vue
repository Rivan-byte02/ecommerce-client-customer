<template>
  <div>
    <div class="navbar navbar-light bg-info">
      <div>
        <router-link to="/"
        class="btn btn-outline-secondary ml-3"><i class="fas fa-home mr-2"></i>Home</router-link>
        <router-link
        to="/login"
        class="btn btn-outline-secondary ml-3"
        ><i class="fas fa-sign-in-alt mr-2"></i>Login</router-link>
      </div>
    </div>
    <div class="register">
      <h1>Register to CMS</h1>
      <form class="p-4" @submit.prevent="register">
        <div class="row mb-3">
          <label for="inputEmail3" class="col-sm-3 col-form-label">Email</label>
          <div class="col-sm-8">
            <input v-model="user.email" type="email" class="form-control" id="inputEmail3">
          </div>
        </div>
        <div class="row mb-3">
          <label for="inputPassword3" class="col-sm-3 col-form-label">Password</label>
          <div class="col-sm-8">
            <input v-model="user.password" type="password" class="form-control" id="inputPassword3">
          </div>
        </div>
        <div class="row mb-3">
          <a
          class="col-sm-12"
          @click.prevent="login">Have an account</a>
        </div>
        <button type="submit" class="btn btn-primary">Sign in</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'RegisterForm',
  data () {
    return {
      user: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    login () {
      this.$router.push('/login')
    },
    register () {
      this.$store.dispatch('registerUser', this.user)
    }
  }
}
</script>

<style>

form {
  width: 500px;
  align-self: center;
  border: 1px lightblue solid;
  border-radius: 20px;
}

.register {
  height: 500px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}

#roleHelper {
  text-align: center;
  color: gray;
  margin-left: 8em;
}

</style>
