<template>
  <v-app
    :class="
      $vuetify.breakpoint.mdAndDown
        ? 'primary lighten-5 layout-auth-mobile'
        : 'layout-auth primary lighten-5'
    "
    :style="
      $vuetify.breakpoint.mdAndUp
        ? { background: 'url(' + require('@/assets/loginbg.jpg') + ')' }
        : ''
    "
  >
    <v-container class="border my-6">
      <v-row align="center" justify="center" class="my-12">
        <v-col cols="12" sm="10">
          <v-card class="elevation-6 mt-16">
            <v-window v-model="step">
              <!-- <v-window-item :value="1">
                <v-row>
                  <v-col cols="12" md="6">
                    <v-card-text class="mt-3 mb-6">
                      <v-flex
                        id="logo"
                        class="text-center ma-4 my-2 mb-13 mx-4"
                      >
                        <img
                          src="@/assets/Logo.jpeg"
                          alt="Amaar"
                          width="150px"
                          height="100px "
                        />
                      </v-flex>
                      <h1 class="text-center  my-6 my-6 mb-0">
                        Login in to Your Account
                      </h1>
                      <v-row align="center" justify="center" class="">
                        <v-col cols="12" sm="8" class="my-0">
                          <v-text-field
                            label="Email"
                            outlined
                            dense
                            color="blue"
                            autocomplete="false"
                            class="mt-16"
                          />
                          <v-text-field
                            label="Password"
                            outlined
                            dense
                            color="blue"
                            autocomplete="false"
                            type="password"
                          >
                            <template slot="append">
                              <v-icon
                                v-if="isViewPassword"
                                @click="isViewPassword = true"
                                >mdi-eye</v-icon
                              >
                              <v-icon
                                v-if="!isViewPassword"
                                @click="isViewPassword = true"
                                >mdi-eye-off</v-icon
                              >
                            </template>
                          </v-text-field>
                          <v-row>
                            <v-col cols="12" sm="7">
                              <a
                                href="javascript:void(0)"
                                class="text_decoration_none success--text pl-3"
                                @click="reachUs()"
                                >Reach Us</a
                              >
                            </v-col>
                            <v-col cols="12" sm="5" xs12 class="my-0">
                              <v-flex xs12>
                                <a
                                  href="javascript:void(0)"
                                  class="
                                    text_decoration_none
                                    caption
                                    black--text
                                    mt-6
                                  "
                                  @click="step++"
                                  >Forgot Password?</a
                                >
                              </v-flex>
                            </v-col>
                          </v-row>
                          <v-btn
                            color="dark voilet"
                            class="mb-0 mt-6"
                            dark
                            block
                            tile
                            >Log in</v-btn
                          >
                        </v-col>
                      </v-row>
                    </v-card-text>
                  </v-col>
                  <v-col cols="12" md="6" class="teal lighten-2 rounded-bl-xl">
                    <div style="text-align: center; padding: 180px 0">
                      <v-card-text class="white--text">
                        <h3 class="text-center">Don't Have an Account Yet?</h3>
                        <h6 class="text-center">
                          Let's get you all set up so you can start with AMAAR
                          REAL ESTATE<br />
                          onboarding experience
                        </h6>
                      </v-card-text>
                    </div>
                  </v-col>
                </v-row>
              </v-window-item> -->
              <v-window-item :value="2">
                <v-row>
                  <v-col cols="12" md="6" class="teal lighten-2 rounded-br-xl">
                    <div style="text-align: center; padding: 180px 0">
                      <v-card-text class="white--text">
                        <h3 class="text-center">Alredy Signed up?</h3>
                        <h6 class="text-center">
                          Log in to your account so you can continue building
                          and<br />
                          editing your onboarding flows
                        </h6>
                      </v-card-text>
                      <div class="text-center">
                        <v-btn tile outlined dark @click="step--"
                          >Go Back</v-btn
                        >
                      </div>
                    </div>
                  </v-col>

                  <v-col cols="12" md="6">
                    <v-card-title class="text-center">
                      <v-flex xs12 class="text-center ma-2 mt-10">
                        <img
                          src="@/assets/Logo.jpeg"
                          alt="Amaar"
                          width="150"
                          height="100px "
                        />
                      </v-flex>
                    </v-card-title>
                    <v-flex>
                      <v-card-text>
                        <h2 class="text-center ma-2 my-6 mt-1">
                          Forgot Password
                        </h2>

                        <v-text-field
                          autocomplete="off"
                          name="login"
                          label="Email"
                          class="mt-1 my-2 mx-18"
                          type="text"
                          dense
                          color="blue"
                          outlined
                          required
                        >
                        </v-text-field>
                        <v-flex>
                          <v-btn
                            color="dark voilet"
                            class="my-2 mt-2 justify-lg-space-around"
                            dark
                            block
                            tile
                            >SEND</v-btn
                          >
                        </v-flex>
                      </v-card-text>
                    </v-flex>
                  </v-col>
                </v-row>
              </v-window-item>
            </v-window>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    step: 1,
  }),
  props: {
    source: String,
  },
};
</script>
<style scoped>
.v-application .rounded-bl-xl {
  border-bottom-left-radius: 300px !important;
}
.v-application .rounded-br-xl {
  border-bottom-right-radius: 300px !important;
}
.layout-auth {
  background-repeat: no-repeat !important;
  background-size: 100% !important;
}

.layout-auth-mobile {
  background: url(https://portal.findabait.com/assets/media/bg/bg.jpg) no-repeat
    center center fixed !important;
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
#logo {
  border-radius: 10px 100px / 120px;
}
.border {
  border-radius: 4px;
}
</style>








<!-- <template>
  <v-container class="mt-6" fluid fill-height>
    <v-form ref="form" class="my-3" lazy-validation v-model="formValid">
      <v-card>
        <v-window>
          <v-window-item :value="2">
            <v-row>
              <v-col cols="12" md="6" class="teal lighten-2 rounded-br-xl">
                <div style="text-align: center; padding: 180px 0">
                  <v-card-text class="white--text">
                    <h3 class="text-center">Alredy Signed up?</h3>
                    <h6 class="text-center">
                      Log in to your account so you can continue building and<br />
                      editing your onboarding flows
                    </h6>
                  </v-card-text>
                  <div class="text-center">
                    <v-btn tile outlined dark @click="closeForm()"
                      >Go Back</v-btn
                    >
                  </div>
                </div>
              </v-col>

              <v-col cols="12" md="6">
                <v-card-title class="text-center">
                  <v-flex xs12 class="text-center ma-2 mt-10">
                    <img
                      src="@/assets/Logo.jpeg"
                      alt="Amaar"
                      width="100"
                      height="80px "
                    />
                  </v-flex>
                </v-card-title>
                <v-flex>
                  <v-card-text>
                    <h2
                      class="text-center pt-0 pb-6 ma-2 my-6 mt-1"
                      v-if="!isForgetSuccess"
                    >
                      Forgot Password
                    </h2>
                    <v-text-field
                      autocomplete="off"
                      name="login"
                      label="Email"
                      color="blue"
                      v-if="!isForgetSuccess"
                      @keydown.enter="sendForgotPasswordLink()"
                      type="text"
                      required
                      :class="formModel.email ? 'successfield' : 'errorfield'"
                      :rules="emailRules"
                      v-model="formModel.email"
                      outlined
                    >
                      <template slot="append">
                        <v-icon color="white">mdi-email</v-icon>
                      </template>
                    </v-text-field>
                    <h4 v-if="isForgetSuccess">
                      Forget password link send on your email successfully.
                    </h4>
                  </v-card-text>

                  <v-card-actions>
                    <v-flex>
                      <v-btn
                        color="dark voilet"
                        class="my-2 mt-2 justify-lg-space-around"
                        :disabled="!formValid"
                        outlined
                        v-if="!isForgetSuccess"
                        @click="sendForgotPasswordLink()"
                        :loading="loading"
                        dark
                        block
                        tile
                        >SEND</v-btn
                      >
                    </v-flex>
                  </v-card-actions>
                </v-flex>
              </v-col>
            </v-row>
          </v-window-item>
        </v-window>
      </v-card>
    </v-form>
  </v-container>
</template>
<script>
export default {
  data() {
    return {
      formModel: {},
      formValid: false,
      loading: false,
      emailRules: [
        (v) => !!v || 'Email is required',
        (v) =>
          /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(\.\w{2,3})+$/.test(v) ||
          'E-mail must be valid',
      ],
      isForgetSuccess: false,
    }
  },
  methods: {
    sendForgotPasswordLink() {
      this.loading = true
      this.$axios
        .post(
          ` ${process.env.VUE_APP_BASE_API}/api/v1/auth/forgot-password?userName=${this.formModel.email}`
        )
        .then(() => {
          this.isForgetSuccess = true
          this.loading = false
        })
    },
    closeForm() {
      this.$emit('closeForm')
    },
  },
}
</script>

<style scoped>
.border_radius_5 {
  border-radius: 15px !important;
}
</style> -->