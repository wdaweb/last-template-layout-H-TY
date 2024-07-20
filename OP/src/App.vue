<template>
  <v-app class="bg-white">
    <!-- 導覽列 -->
    <!-- 取消 box-shadow 的效果，在標籤添加 flat -->
    <v-app-bar class="flex-fixed bg-transparent mt-3" flat>
      <v-app-bar-title>
          <v-row class="flex-nowrap text-center align-center">
            <!-- Logo圖片 -->
            <v-col class="" isLg="2">
              <v-img src="./assets/image/logo.png" height="45px" fill></v-img>
            </v-col>
            <!-- 導覽列項目 -->
            <v-col class="text-subtitle-1" isLg="6" :class="{ 'xs-screen-class': isXs, 'sm-screen-class': isSm, 'md-screen-class': isMd}">
              <!-- 取消按鈕的波紋效果，在標籤添加 :ripple="false" -->
              <!-- 選單 hover 效果 -->
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn class="omNo" 
                :ripple="false" 
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >Home</v-btn>
              </v-hover>
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn class="omNo" 
                :ripple="false" 
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >Services</v-btn>
              </v-hover>
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn class="omNo" 
                :ripple="false" 
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >Portfolio</v-btn>
              </v-hover>
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn class="omNo" 
                :ripple="false" 
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >Testimonials</v-btn>
              </v-hover>
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn class="omNo" 
                :ripple="false" 
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >Team</v-btn>
              </v-hover>
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn id="menuList" class="omNo" 
                :ripple="false" 
                append-icon="mdi-chevron-down"
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >Menu</v-btn>
              </v-hover>
              <v-hover v-slot:default="{ isHovering, props }">
                <v-btn class="omNo" 
                :ripple="false" 
                v-bind="props" 
                :color="isHovering ? 'primary' : undefined"
                >News</v-btn>
              </v-hover>
            </v-col>
            <!-- Get Quotes 按鈕 -->
            <v-col isLg="2" :class="{ 'xs-screen-class': isXs, 'sm-screen-class': isSm}">
              <v-btn class="bg-blue-darken-1 rounded-pill px-3" height="48px">Get Quotes</v-btn>
            </v-col>
            <!-- 光暗色切換按鈕 -->
            <v-col isLg="2">
              <v-btn icon="mdi-moon-waning-crescent" size="40px"class="rounded-circle bg-white rotate-30"></v-btn>
            </v-col>
          </v-row>
      </v-app-bar-title>
      <!-- Menu 的下拉選單的選項 -->
      <v-menu activator="#menuList" open-on-hover open-delay="0" close-delay="0">
          <v-list class="bg-white">
            <v-list-item v-for="(el, index) in items" :key="index">
              <v-list-item-title>{{ el.name }}</v-list-item-title>
            </v-list-item>
          </v-list>
      </v-menu>
    </v-app-bar>

    <v-main class="pa-0">
      <!-- 機器人背景圖片 -->
      <v-img class="position-absolute top-0" src="./assets/image/hero-bg.png" width="100vw"
      height="800px" cover></v-img>

      <!-- 右側文字欄位 -->
      <v-container class="pa-0 ma-0" fluid>
        <v-card class="bg-transparent d-flex align-center" height="800px" flat>
          <v-row class="ma-0 justify-end">
            <v-col cols="6" :class="{ 'text-center': isXs || isSm}">
              <v-card-title :class="{ 'text-h4': isXs || isSm || isMd, 'text-h3': isLg}" style="white-space: wrap; line-height: 1;">Delivering Superior Services <span class="text-blue-darken-1">IT Solutions.</span></v-card-title>
              <v-card-text class="text-subtitle-1 my-4">
                You can easily change any design to your own. It is also highly customizable SEO        friendly template.
              </v-card-text>
              <div class="pa-4">
                <v-icon class="text-subtitle-1 me-5" color="blue-darken-1" icon="mdi-twitter"></v-icon>
                <v-icon class="text-subtitle-1 me-5" color="blue-darken-1" icon="mdi-facebook"></     v-icon>
                <v-icon class="text-subtitle-1 me-5" color="blue-darken-1" icon="mdi-linkedin"></     v-icon>
                <v-icon class="text-subtitle-1 me-5" color="blue-darken-1" icon="mdi-instagram"></      v-icon>
              </div>
              <v-card-actions class="pa-4">
                <v-btn class="bg-blue-darken-1 rounded-pill d-flex align-center pa-4 me-5" height="40px">Get Quotes</v-btn>
                <v-btn class="bg-blue-darken-1 rounded-pill d-flex align-center pa-4" height="40px">Get Started</v-btn>
              </v-card-actions>
            </v-col>
          </v-row>
        </v-card>
      </v-container>

      <!-- 提供服務_卡片 -->
      <v-container>
        <!-- <v-card>
          <v-img></v-img>
          <v-card-title></v-card-title>
          <v-card-text></v-card-text>
        </v-card> -->
        <v-row class="flex-wrap justify-center">
          <v-col class="d-flex pa-0 " isXs="12" isSm="12" isMd="4" isLg="4">
            <v-card class="d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-design.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Application Design</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0 " isXs="12" isSm="12" isMd="4" isLg="4">
            <v-card class="d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-hosting.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Web Hosting</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0 " isXs="12" isSm="12" isMd="4" isLg="4">
            <v-card class="d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-social.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Social Media</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <v-row class="flex-wrap justify-center">
          <v-col class="d-flex pa-0 " isXs="12" isSm="12" isMd="4" isLg="4">
            <v-card class="d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-seo.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">SEO Optimization</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0 " isXs="12" isSm="12" isMd="4" isLg="4">
            <v-card class="d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-cloud.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Cloud Server</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0 " isXs="12" isSm="12" isMd="4" isLg="4">
            <v-card class="d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-secure.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Data Secuity</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <!-- Testimonials_卡片 -->
      <v-container class="d-flex flex-column align-center mt-15 mb-8">
        <h1 class="text-blue-darken-1">Testimonials</h1>
        <p class="text-body-1 text-orange-darken-2">Lorem ipsum dolor sit amet</p>

        <v-card class="bg-white mt-15 pa-5 w-75">
          <v-row class="align-center">
            <v-col cols="3">
              <v-img class="rounded-circle" src="@/assets/image/testimonial-1.jpg" cover></v-img>
            </v-col>
            <v-col cols="9">
              <v-card-title class="pa-0">Jhone Doe</v-card-title>
              <v-card-subtitle class="pa-0">CFO</v-card-subtitle>
              <div>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
              </div>
            </v-col>
          </v-row>
          <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttitora entum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibh et. Maecen aliquam. </v-card-text>
        </v-card>

        <v-card class="bg-white mt-15 pa-5 w-75">
          <v-row class="align-center">
            <v-col cols="3">
              <v-img class="rounded-circle" src="@/assets/image/testimonial-2.jpg" cover></v-img>
            </v-col>
            <v-col cols="9">
              <v-card-title class="pa-0">Afa Rose</v-card-title>
              <v-card-subtitle class="pa-0">Web Designer</v-card-subtitle>
              <div>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
              </div>
            </v-col>
          </v-row>
          <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttitora entum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibh et. Maecen aliquam. </v-card-text>
        </v-card>

        <v-card class="bg-white mt-15 pa-5 w-75">
          <v-row class="align-center">
            <v-col cols="3">
              <v-img class="rounded-circle" src="@/assets/image/testimonial-3.jpg" cover></v-img>
            </v-col>
            <v-col cols="9">
              <v-card-title class="pa-0">Keena Lara</v-card-title>
              <v-card-subtitle class="pa-0">Store Owner</v-card-subtitle>
              <div>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
                <v-icon color="yellow" icon="mdi-star"></v-icon>
              </div>
            </v-col>
          </v-row>
          <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttitora entum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibh et. Maecen aliquam. </v-card-text>
        </v-card>

      </v-container>


    </v-main>
  </v-app>
</template>



<script setup>
import { ref } from 'vue'
import { useDisplay } from 'vuetify'

const { width, xs, sm, md, mdAndUp, lg, lgAndUp } = useDisplay()

const isXs = xs
const isSm = sm
const isMd = md
const isLg = lgAndUp

onMounted(() => {
    console.log('width',width.value)
    console.log('md',md.value)
})

// onMounted(() => {
//   console.log('sm',sm.value)
//   console.log('md',md.value)
//   console.log('lg',lg.value)
//   console.log('xl',xl.value)
//   console.log('mobile' ,mobile.value)
//   console.log(useDisplay())
// })

const items = ref([
  { name: 'About' },
  { name: 'Pricing' },
  { name: 'FAQs' },
  { name: 'Terms & Conditions' },
  { name: 'Privacy Policy' },
  { name: 'Blogs' },
  { name: 'Blog Detail Page' }
])

</script>




<style scoped lang="scss">
@import './styles/main.scss';

.rotate-30 {
  transform: rotate(-30deg);
}

.omNo{
  --v-theme-overlay-multiplier: 0;
}

.xs-screen-class{
  display: none;
}

.sm-screen-class{
  display: none;
}

.md-screen-class{
  display: none;
}

.lg-screen-class{
  
}

.v-btn--size-default {
    --v-btn-size: 1rem;
    --v-btn-height: 36px;
    font-size: var(--v-btn-size);
    min-width: 64px;
    padding: 0 6px;
}

</style>