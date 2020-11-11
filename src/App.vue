<template>
  <v-app>
    <v-app-bar app color="white" dark>
      <div class="d-flex align-center">
        <v-img
          eager
          class="mr-2"
          contain
          src="../src/assets/Through The Glass Creatives Logo Revamp (no BG_Favicon).png"
          transition="scale-transition"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>
      <div class="d-flex mr-10" v-if="!isMobile">
        <div
          class="mx-5 h6 link"
          v-for="(nav, i) in navs"
          :key="i"
          @click="selectedNav = i"
          :class="selectedNav == i ? 'text-main-active' : 'text-main'"
        >
          {{ nav }}
        </div>
      </div>
      <div v-else>
        <v-menu
          v-if="screenWidth <= 960"
          close-on-click
          min-width="100%"
          nudge-bottom="12"
          offset-y
          bottom
          class="mt-10 ml-auto"
          transition="slide-y-transition"
          tile
        >
          <template v-slot:activator="{ on: menu }">
            <v-icon v-on="menu" x-large color="#0a1c2f">menu</v-icon>
          </template>
          <v-card
            style="color:#a3a3a3"
            minz-width="100%"
            color="#fafafa"
            tile
            flat
          >
            <v-list>
              <v-list-item
                v-for="(nav, i) in navs"
                :key="i"
                @click="
                  $router.push(`/${nav.toLowerCase()}`), (selectedNav = i)
                "
                :class="selectedNav == i ? 'text-main-active' : 'text-main'"
                >{{ nav }}</v-list-item
              >
            </v-list>
          </v-card>
        </v-menu>
      </div>
    </v-app-bar>

    <v-main v-if="selectedNav == 1">
      <v-app>
        <v-img eager src="../src/assets/banner-bg.png">
          <v-container>
            <v-row>
              <v-col
                cols="12"
                md="6"
                class="d-flex align-center justify-center"
                order="2"
                order-md="1"
              >
                <div>
                  <div
                    class="white--text text-center font-weight-bold"
                    :class="isMobile ? 'h4' : 'h2'"
                  >
                    THROUGH THE GLASS CREATIVES
                  </div>
                  <div class="h5 white--text font-weight-thin text-center">
                    BLOG SECTION
                  </div>
                </div>
              </v-col>
              <v-col cols="12" md="6" order="1" order-md="2">
                <v-img
                  eager
                  contain
                  :max-height="isMobile ? '300' : ''"
                  src="../src/assets/Through The Glass Home Page Art (no BG).png"
                ></v-img>
              </v-col>
            </v-row>
          </v-container>
        </v-img>
      </v-app>
      <v-container>
        <v-tabs grow centered slider-color="purple" color="purple">
          <v-tab>
            <span :class="isMobile ? 'h5' : 'h4'">FOOD</span>
          </v-tab>
          <v-tab>
            <span :class="isMobile ? 'h5' : 'h4'">TRAVEL</span>
          </v-tab>
          <v-tab-item class="pa-5">
            <v-img
              eager
              src="../src/assets/blog_01.jpg"
              :max-height="isMobile ? '115' : '300'"
            >
            </v-img>
            <div class="mt-5 class h3 ">Healthy Foods</div>
            <v-container>
              <v-row>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img eager src="../src/assets/food1.jpg" max-height="300">
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">Healthy foods you can serve</div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img eager src="../src/assets/food2.jpg" max-height="300">
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      Breakfast: Start your day with an egg
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img eager src="../src/assets/food3.jpg" max-height="300">
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      How to prepare mushrooms for your meals?
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img eager src="../src/assets/food4.jpg" max-height="300">
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      The benefits of vegetables in your body
                    </div>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>

            <div class="mt-5  h3 ">Breads</div>

            <v-container>
              <v-row>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/bread1.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      All you need to know in baking
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/bread2.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      How to prepare your dough
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/bread3.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      The steps in making a delicious bread
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/bread1.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      Breads across the world - 10 best breads
                    </div>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-tab-item>
          <v-tab-item class="pa-5">
            <v-img eager src="../src/assets/blog_03.jpg" max-height="300">
            </v-img>
            <div class="mt-5 h3">Travel and Leisure</div>
            <v-container>
              <v-row>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/travel1.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      Foods to cook to enjoy outdoor activities
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/travel2.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      Best places to visit around the world
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/travel3.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      10 Travel guide and tips for you
                    </div>
                  </v-card>
                </v-col>
                <v-col cols="12" md="6">
                  <v-card>
                    <v-img
                      eager
                      src="../src/assets/travel4.jpg"
                      max-height="300"
                    >
                      <v-container
                        class="d-flex fill-height justify-end align-end"
                      >
                        <v-card
                          color="yellow darken-2"
                          class="pa-2 rounded-pill"
                        >
                          <div class="font-weight-bold">Read More</div>
                        </v-card>
                      </v-container>
                    </v-img>
                    <div class="h5 ma-3">
                      Find peace in the places you go
                    </div>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-tab-item>
        </v-tabs>
      </v-container>
    </v-main>
    <v-main v-else>
      <v-container class="d-flex align-center justify-center fill-height">
        <div class="h5 font-weight-thin">
          <v-icon color="yellow" large>warning</v-icon>
          Under maintenance
        </div>
      </v-container>
    </v-main>
  </v-app>
</template>

<style scoped>
.h1 {
  font-weight: 300;
  font-size: 6rem;
  letter-spacing: -0.09375rem;
}

.h2 {
  font-weight: 300;
  font-size: 3.75rem;
  letter-spacing: -0.03125rem;
}

.h3 {
  font-weight: 400;
  font-size: 3rem;
  letter-spacing: normal;
}

.h4 {
  font-weight: 400;
  font-size: 2.125rem;
  letter-spacing: -0.015625remm;
}

.h5 {
  font-weight: 400;
  font-size: 1.5rem;
  letter-spacing: normal;
  line-break: strict;
  word-break: keep-all;
}

.h6 {
  font-weight: 500;
  font-size: 1.25rem;
  letter-spacing: 0.009375rem;
}

.subtitle-text-1 {
  font-weight: 400;
  font-size: 1rem;
  letter-spacing: 0.009375rem;
}

.text-main {
  color: #0a1c2f;
}

.text-main-active {
  color: #4b5b9e;
}

.link {
  cursor: pointer;
}
</style>

<script>
export default {
  data: () => ({
    screenWidth: "",
    isMobile: false,
    navs: ["HOME", "BLOG", "ABOUT US", "SERVICES", "CONTACT US"],
    selectedNav: 1
  }),

  created() {
    window.addEventListener("resize", this.onWindowResize);
  },
  destroyed() {
    window.removeEventListener("resize", this.onWindowResize);
  },

  mounted() {
    this.screenWidth = screen.width;
    this.isMobile = this.screenWidth <= 960 ? true : false;
  },

  methods: {
    onWindowResize() {
      this.screenWidth = screen.width;
      this.isMobile = this.screenWidth <= 960 ? true : false;
    }
  }
};
</script>
