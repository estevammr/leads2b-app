<template>
    <div class="row">
        <form class="col s12" @submit.prevent="login">
            <h4>Sign in</h4>
            <div class="row">
                <div class="input-field col s6">
                    <input required v-model="email" type="email" placeholder="Name"/>
                    <label>Email</label>
                </div>
                <div class="input-field col s6">
                    <label>Password</label>
                    <input required v-model="password" type="password" placeholder="Password"/>
                </div>
            </div>             
            <button class="btn waves-effect waves-light" type="submit">Login</button>
        </form>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                email : "",
                password : ""
            }
        },
        methods: {
            login: function () {
                let email = this.email 
                let password = this.password
                this.$store.dispatch('login', { email, password })
                .then(() => this.$router.push('/employee'))
                .catch(err => console.log(err))
            }
        }
    }
</script>

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