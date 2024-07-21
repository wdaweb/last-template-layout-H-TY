<template>
  <v-app class="bg-white">
    <!-- 導覽列 -->
    <!-- 取消 box-shadow 的效果，在標籤添加 flat -->
    <v-app-bar class="bar flex-fixed py-3" flat>
      <v-app-bar-title>
          <v-row class="flex-nowrap text-center align-center text-white">
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
      <!-- 機器人背景圖片_parallax 效果 -->
      <v-img class="ukiyo barTrigger position-absolute top-0" src="./assets/image/hero-bg.png" width="100vw"
      height="900px" cover></v-img>

      <!-- 右側文字欄位 -->
      <v-container class="pa-0 ma-0" fluid>
        <v-card class="bg-transparent d-flex align-center text-white" height="800px" flat>
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

      <!-- 提供服務_卡片_GSAP 動畫 -->
      <v-container class="mt-15">
        <v-row class="flex-wrap justify-center">
          <v-col class="d-flex pa-0">
            <v-card class="C1 d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-design.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Application Design</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0">
            <v-card class="C2 d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-hosting.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Web Hosting</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0">
            <v-card class="C3 d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-social.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Social Media</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>
        </v-row>

        <v-row class="flex-wrap justify-center">
          <v-col class="d-flex pa-0">
            <v-card class="C6 d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-seo.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">SEO Optimization</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0">
            <v-card class="C5 d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-cloud.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Cloud Server</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>

          <v-col class="d-flex pa-0">
            <v-card class="C4 d-flex flex-column bg-white text-center ma-4 pa-4">
              <v-img src="@/assets/image/service-secure.svg" height="100px"></v-img>
              <v-card-title class="text-h5 text-blue-darken-1 mt-4">Data Secuity</v-card-title>
              <v-card-text class="text-body-1">Ronsectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>

      <!-- Testimonials_卡片_Swiper 套件 -->
      <v-container class="d-flex flex-column align-center mt-15 mb-8">
        <h1 class="text-blue-darken-1">Testimonials</h1>
        <p class="text-body-1 text-orange-darken-2">Lorem ipsum dolor sit amet</p>

        <swiper
          :loop="true"
          :effect="'coverflow'"
          :grabCursor="true"
          :centeredSlides="true"
          :slidesPerView="'auto'"
          :coverflowEffect="{
            rotate: 50,
            stretch: 0,
            depth: 100,
            modifier: 1,
            slideShadows: true,
          }"
          :pagination="true"
          :modules="modules"
          class="mySwiper"
          >
          <swiper-slide>
            <v-card class="bg-white pa-5 w-75">
              <v-row class="align-center pa-4">
                <v-col cols="3">
                  <v-img class="rounded-circle" src="@/assets/image/testimonial-1.jpg" cover></v-img>
                </v-col>
                <v-col class="pa-0 px-3" cols="9">
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
              <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttit oraentum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibhet. Maecen aliquam. 
              </v-card-text>
            </v-card>
          </swiper-slide>

          <swiper-slide>
            <v-card class="bg-white  pa-5 w-75">
              <v-row class="align-center pa-4">
                <v-col cols="3">
                  <v-img class="rounded-circle" src="@/assets/image/testimonial-2.jpg" cover></v-img>
                </v-col>
                <v-col cols="9" class="pa-0 px-3">
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
              <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttit oraentum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibhet. Maecen aliquam. 
              </v-card-text>
            </v-card>
          </swiper-slide>

          <swiper-slide>
            <v-card class="bg-white  pa-5 w-75">
              <v-row class="align-center pa-4">
                <v-col cols="3" class="pa-0 px-3">
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
              <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttit oraentum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibhet. Maecen aliquam. 
              </v-card-text>
            </v-card>
          </swiper-slide>

          <swiper-slide>
            <v-card class="bg-white  pa-5 w-75">
              <v-row class="align-center pa-4">
                <v-col cols="3" class="pa-0 px-3">
                  <v-img class="rounded-circle" src="@/assets/image/testimonial-4.jpg" cover></v-img>
                </v-col>
                <v-col cols="9">
                  <v-card-title class="pa-0">Fizzi Brandon</v-card-title>
                  <v-card-subtitle class="pa-0">Freelancer</v-card-subtitle>
                  <div>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                  </div>
                </v-col>
              </v-row>
              <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttit oraentum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibhet. Maecen aliquam. 
              </v-card-text>
            </v-card>
          </swiper-slide>

          <swiper-slide>
            <v-card class="bg-white  pa-5 w-75">
              <v-row class="align-center pa-4">
                <v-col cols="3" class="pa-0 px-3">
                  <v-img class="rounded-circle" src="@/assets/image/testimonial-5.jpg" cover></v-img>
                </v-col>
                <v-col cols="9">
                  <v-card-title class="pa-0">Jhone Bi</v-card-title>
                  <v-card-subtitle class="pa-0">Application Manager</v-card-subtitle>
                  <div>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                    <v-icon color="yellow" icon="mdi-star"></v-icon>
                  </div>
                </v-col>
              </v-row>
              <v-card-text>Proin iaculis purus consequat sem cure digni ssim donec porttit oraentum suscipit rhoncus. Accusantium quam, ultricies eget id, aliquam eget nibhet. Maecen aliquam. 
              </v-card-text>
            </v-card>
          </swiper-slide>

        </swiper>
      </v-container>
    </v-main>
  </v-app>
</template>



<script setup>
import { onMounted, onUnmounted, ref } from 'vue'
import { useDisplay } from 'vuetify'

// ● 引用 Swiper 套件
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';
// Import Swiper styles
import 'swiper/css';
import 'swiper/css/effect-coverflow';
import 'swiper/css/pagination';
import './style.css';
// import required modules
import { EffectCoverflow, Pagination } from 'swiper/modules';

// ● 引用 GSAP 套件
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

// ● 引用 Ukiyo.js 套件
import Ukiyo from "ukiyojs"


// 定义所需的 Swiper 模組
const modules = [EffectCoverflow, Pagination];

// gsap 註冊套件
gsap.registerPlugin(ScrollTrigger);

// 導覽列更換背景色
// 抓取已載入 DOM 的指定元素，設定動畫
onMounted (async () => {
  await nextTick()  // 确保 DOM 已完全渲染

    const tl = gsap.timeline({
            scrollTrigger: {
              trigger: '.barTrigger',
              start: '70% top',
              end: 'bottom 80%',
              scrub: 1,
              // markers: true,
            }
          })
        
          tl.to('.bar', {
            backgroundColor: "#0a254d",
          })
})

// 設定卡片隨滑鼠下移的飛入動畫
onMounted (async () => {
  await nextTick()  // 确保 DOM 已完全渲染

    const tl = gsap.timeline({
            scrollTrigger: {
              trigger: '.C1',
              start: 'top 80%',
              end: 'center 20%',
              scrub: 3,
              // markers: true,
            }
          })
        
          tl
          .from('.C1', {
            x: -2000,
            duration: 10,
            ease: "back.out"
          })
          .to('.C1', {
            x: 0,
            duration: 10,
            ease: "back.out"
          },'<1.5')

          .from('.C2', {
            x: -2000,
            duration: 10,
            ease: "back.out"
          },'<1.5')
          .to('.C2', {
            x: 0,
            duration: 10,
            ease: "back.out"
          },'<1.5')

          .from('.C3', {
            x: -2000,
            duration: 10,
            ease: "back.out"
          },'<1.5')
          .to('.C3', {
            x: 0,
            duration: 10,
            ease: "back.out"
          },'<1.5')

          .from('.C4', {
            x: -2000,
            duration: 10,
            ease: "back.out"
          },'<1.5')
          .to('.C4', {
            x: 0,
            duration: 10,
            ease: "back.out"
          },'<1.5')

          .from('.C5', {
            x: -2000,
            duration: 10,
            ease: "back.out"
          },'<1.5')
          .to('.C5', {
            x: 0,
            duration: 10,
            ease: "back.out"
          },'<1.5')

          .from('.C6', {
            x: -2000,
            duration: 10,
            ease: "back.out"
          },'<1.5')
          .to('.C6', {
            x: 0,
            duration: 10,
            ease: "back.out"
          },'<1.5')
})



// 視差效果 parallax
onMounted (async () => {
  await nextTick()

  const parallax = document.querySelectorAll(".ukiyo")
  new Ukiyo(parallax, {
      scale: 1.3, // 1~2 is recommended
      speed: 2.5, // 1~2 is recommended
      willChange: true,
      wrapperClass: "ukiyo-wrapper",
      externalRAF: false
  })
})


// 自訂義 斷點breakpoint
const { width, xs, sm, md, mdAndUp, lg, lgAndUp } = useDisplay()

const isXs = xs
const isSm = sm
const isMd = md
const isLg = lgAndUp

onMounted(() => {
    console.log('width',width.value)
    console.log('md',md.value)
})


// 導覽列項目的 js
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

.v-app-bar.v-toolbar {
    background: none;
    color: rgba(var(--v-theme-on-surface), var(--v-high-emphasis-opacity));
}

.v-btn--size-default {
    --v-btn-size: 1rem;
    --v-btn-height: 36px;
    font-size: var(--v-btn-size);
    min-width: 64px;
    padding: 0 6px;
}

.mySwiper{
  margin-top: 40px;
  height: 400px;
}


</style>