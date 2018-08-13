<template>
  <v-container mt-5 pt-5 text-xs-center>

    <v-layout row wrap>
      <v-flex xs12 sm6 offset-sm3>
        <h1>Welcome Back!</h1>
      </v-flex>
    </v-layout>

    <!-- Signin Form -->
    <v-layout row wrap>
      <v-flex xs12 sm6 offset-sm3>
        <v-card color="secondary" dark>
          <v-card-text>
            <v-container>
              <v-form>
                <v-layout row>
                  <v-flex xs12>
                    <v-text-field v-model="username" prepend-icon="face" label="Username" type="text" required></v-text-field>
                  </v-flex>
                </v-layout>

                <v-layout row>
                  <v-flex xs12>
                    <v-text-field v-model="password" prepend-icon="extension" label="Password" type="password" required></v-text-field>
                  </v-flex>
                </v-layout>

                <v-layout row>
                  <v-flex xs12>
                    <v-btn type="submit" color="accent">Signin</v-btn>
                  </v-flex>
                </v-layout>
              </v-form>
            </v-container>
          </v-card-text>
        </v-card>
      </v-flex>
    </v-layout>

  </v-container>
</template>

<script>
export default {
  name: "Signin",
  data() {
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    handleSignin() {
      this.$store.dispatch("signinUser", {
        username: this.username,
        password: this.password
      });
    }
  }
};
</script>
