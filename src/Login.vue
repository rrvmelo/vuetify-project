<template>
  <v-container>
    <v-row allign="center" justify="center">
      <v-col cols="12" sm="10">
        <v-card class="elevation-6 mt-10">
          <v-window v-model="step">
            <v-window-item :value="1">
              <v-row>
                <v-col cols="12" sm="6">
                  <v-cart-text class="mt-12">
                    <h4 class="text-center">Login in to Your Account</h4>
                    <h6 class="text-center grey--text">Login in to your account so you can continue building <br>and editing your onbordarding flows</h6>
                    <v-row allign="center" justify="center">
                      <v-col cols="12" sm="8">

                        <v-text-field 
                        label="Email" 
                        outlined 
                        dense 
                        color="blue" 
                        autocomplete="false" 
                        class="mt-16">
                        </v-text-field>
                        <v-text-field 
                        label="Password" 
                        outlined 
                        dense 
                        color="blue" 
                        autocomplete="false" 
                        type="password">
                        </v-text-field>

                        <v-row>
                          <v-col cols="12" sm="7">
                            <v-checkbox 
                            label="Remember Me" 
                            class="mt-n1" 
                            color="blue">
                          </v-checkbox>
                          </v-col>
                          <v-col cols="12" sm="5">
                            <span class="caption blue--text" to="#">Forgot Password</span>
                          </v-col>
                        </v-row>
                        <v-btn color="blue" dark block title>Log in</v-btn>

                        <h5 
                        class=" text-center grey--text mt-4 mb-3"
                        >Or Log in using </h5>
                        <div class="d-flex justify-space-between align-center mx-10 mb-16">
                        <v-btn depressed outlined color="grey">
                          <v-icon color="red">fab fa-google</v-icon>
                        </v-btn>
                        <v-btn depressed outlined color="grey">
                          <v-icon color="blue">fab fa-facebook</v-icon>
                        </v-btn>
                        <v-btn depressed outlined color="grey">
                          <v-icon color="light-blue lighten">fab fa-google</v-icon>
                        </v-btn>
                      </div>
                      </v-col>
                    </v-row>
                  </v-cart-text>
                </v-col>
                <v-col cols="12" sm="6" class="blue rounded-bl-xl"></v-col>
              </v-row>
            </v-window-item>
          </v-window>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>

export default {
  data: () => ({
    step: 1
  }),
  propos: {
    source: String
  }
}
</script>

<style scoped>
.v-aplication .rounded-bl-xl {
  border-bottom-left-radius: 300px !important;
}

.v-aplication .rounded-br-xl {
  border-bottom-right-radius: 300px !important;
}
</style>
