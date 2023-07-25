<script setup lang="ts">
import { ref, onMounted, onBeforeMount } from 'vue';
import svgBgFooter from './components/svg/svgBgFooter.vue'
import svgBg from './components/svg/svgBg.vue'
import svgCode from './components/vue-design/svgCode.vue'
import svgCodeReact from './components/react-design/svgCodeReact.vue'
import svgHome from './components/vue-design/svgHome.vue'
import svgHomeReact from './components/react-design/svgHomeReact.vue'
import svgPc from './components/vue-design/svgPc.vue'
import svgPcReact from './components/react-design/svgPcReact.vue'
import svgProjects from './components/vue-design/svgProjects.vue'
import svgProjectsReact from './components/react-design/svgProjectsReact.vue'
import svgContact from './components/vue-design/svgContact.vue'
import svgContactReact from './components/react-design/svgContactReact.vue'
import AOS from 'aos'

AOS.init();

const showButton = ref(false)

const checkScroll = () => {
   if (window.scrollY > 300) {
      showButton.value = true
   } else {
      showButton.value = false
   }
}

onMounted(() => {
   window.addEventListener("scroll", checkScroll)
})

onBeforeMount(() => {
   window.removeEventListener("scroll", checkScroll)
})

const btnTop = () => {
   window.scrollTo(0, 0)
}

const nameDesign = ref('Vue')
const mainColor = ref('#00FF7F')
const reactMode = ref(false)

const toggle = (el: HTMLInputElement) => {
   if (el.checked == true) {
      reactMode.value = true
      nameDesign.value = "React"
      mainColor.value = "#25BEEF"
   } else {
      reactMode.value = false
      nameDesign.value = "Vue"
      mainColor.value = "#00FF7F"
   }
}
</script>
<template>
   <div v-if="showButton" v-on:click="btnTop" class="btn-top"><img src="../src/imgs/up-arrow.png" alt=""></div>
   <div id="home" class="home-container">
      <svgBg class="background" />
      <div class="home-center">
         <div data-aos="fade-down" data-aos-duration="1000" class="nav-bar">
            <div class="input-design">
               <p class="text-mode">Design</p>
               <div class="switch-check">
                  <input @input="(toggle($event.target as HTMLInputElement))" type="checkbox" name="" id="toggleBtn">
                  <label for="toggleBtn" class="toggle"></label>
               </div>
               <p class="text-design">{{ nameDesign }}</p>
            </div>
            <img class="logo" src="./assets/icons/midas-logoBG-white.png" alt="">
            <a class="btn-nav" href="#home">Home</a>
            <a class="btn-nav" href="#about">About me</a>
            <a class="btn-nav" href="#skills">Skills</a>
            <a class="btn-nav" href="#projects">Projects</a>
            <a href="https://www.linkedin.com/in/richard-israel-667462246/" target="_blank" rel="noopener noreferrer"><img
                  v-show="!reactMode" src="./assets/icons/linkedin.png" alt="" class="i-linkedin"></a>
            <a href="https://www.linkedin.com/in/richard-israel-667462246/" target="_blank" rel="noopener noreferrer"><img
                  v-show="reactMode" src="./assets/icons/linkedinReact.png" alt="" class="i-linkedin"></a>
            <a href="mailto:richardisraelmagalhaes@gmail.com" target="_blank" rel="noopener noreferrer"><img
                  v-show="!reactMode" class="i-gmail" src="./assets/icons/gmail.png" alt=""></a>
            <a href="mailto:richardisraelmagalhaes@gmail.com" target="_blank" rel="noopener noreferrer"><img
                  v-show="reactMode" class="i-gmail" src="./assets/icons/gmailReact.png" alt=""></a>
            <a href="https://github.com/RichardMidas" target="_blank" rel="noopener noreferrer"><img v-show="!reactMode"
                  src="./assets/icons/github.png" alt="" class="i-github"></a>
            <a href="https://github.com/RichardMidas" target="_blank" rel="noopener noreferrer"><img v-show="reactMode"
                  src="./assets/icons/githubReact.png" alt="" class="i-github"></a>
         </div>
         <div data-aos="fade-up" data-aos-duration="1000" class="home-content">
            <div class="container-typed">
               <p class="text-typed">Hellow world!</p>
            </div>
            <h1>Olá, eu sou <span>Midas</span>!</h1>
            <h2>Desenvolvedor Front end</h2>
            <p class="text-content">Sou desenvolvedor web, atualmente focado em Front-end.
               Tenho experiência com Freelancer e projetos pessoais.
               Estudo um pouco de Back-end com a finalidade de um dia
               me tornar um Programador FullStack.</p>
            <div class="btns-row">
               <a href="https://github.com/RichardMidas" target="_blank">
                  <div class="btn-left">Saiba mais</div>
               </a>
               <a href="#contact">
                  <div class="btn-right">Fale comigo!</div>
               </a>
            </div>
            <svgHome v-if="!reactMode" class="svg-home" />
            <svgHomeReact v-else class="svg-home" />
         </div>
      </div>
   </div>
   <div id="about" class="about-container">
      <div class="about-center">
         <svgCode v-if="!reactMode" data-aos="fade-left" data-aos-duration="1000" class="svg-code" />
         <svgCodeReact v-else data-aos="fade-left" data-aos-duration="1000" class="svg-code" />
         <div data-aos="fade-right" data-aos-duration="1000" class="about-line"></div>
         <h1 data-aos="fade-right" data-aos-duration="1000">Sobre mim</h1>
         <div class="about-left" data-aos="fade-right" data-aos-duration="1000">
            <img class="about-profile" src="../src/imgs/profile.png" alt="">
            <svgPc v-if="!reactMode" class="svg-pc" />
            <svgPcReact v-else data-aos="fade-right" data-aos-duration="1000" class="svg-pc" />
         </div>
         <div data-aos="fade-left" data-aos-duration="1000" class="about-right">
            <div data-aos="fade-left" data-aos-duration="1000" class="about-column">
               <h2>Oi, <br> Me chamo <span>Richard</span>.</h2>
               <p>Tenho 20 anos e atualmente moro no Rio de Janeiro. Sempre gostei de games e tecnologia e foi através dos
                  jogos que tive interesse na área de programação. Hoje sigo minha carreira dominando as tecnologias
                  ReactJs e
                  VueJs. Estudo um pouco de PHP para ter conhecimentos sólidos em back-end pra um dia me tornar um
                  Desenvolvedor
                  FullStack. ☕</p>
            </div>
         </div>
      </div>
   </div>
   <div id="skills" class="skills-container">
      <div class="skills-center">
         <div class="skills-text">
            <div data-aos="fade-right" data-aos-duration="1000" class="skills-line"></div>
            <h1 data-aos="fade-down" data-aos-duration="1000">Conhecimentos</h1>
            <h2 data-aos="fade-up" data-aos-duration="1000">Tecnologias que uso no meu dia a dia</h2>
            <div data-aos="fade-left" data-aos-duration="1000" class="skills-line"></div>
         </div>
         <div data-aos="fade-up" data-aos-duration="1000" class="skills-content">
            <div class="skills-flex">
               <div class="skills-itens">
                  <div class="itens-icon">
                     <div class="itens-bg"></div>
                     <img src="./assets/icons/html-icon.png" alt="">
                     <h2>HTML5</h2>
                     <p>HTML5 é uma linguagem de marcação para a World Wide Web e é uma tecnologia chave da Internet,
                        originalmente
                        proposto por Opera Software.</p>
                  </div>
               </div>
               <div class="skills-itens">
                  <div class="itens-icon">
                     <div class="itens-bg"></div>
                     <img src="./assets/icons/css-icon.png" alt="">
                     <h2>CSS3</h2>
                     <p>Cascading Style Sheets é um mecanismo para adicionar estilos a uma página web.</p>
                  </div>
               </div>
            </div>
            <div class="skills-flex">
               <div class="skills-itens">
                  <div class="itens-icon">
                     <div class="itens-bg"></div>
                     <img src="./assets/icons/js-icon.png" alt="">
                     <h2 style="width: 125px;">Java Script</h2>
                     <p>JavaScript é uma linguagem de programação interpretada estruturada, de script em alto nível com
                        tipagem
                        dinâmica fraca e multiparadigma, juntamente com HTML e CSS.</p>
                  </div>
               </div>
               <div class="skills-itens">
                  <div class="itens-icon">
                     <div class="itens-bg"></div>
                     <img src="./assets/icons/vue-icon.png" alt="">
                     <h2>Vue Js</h2>
                     <p>Vue.js é um framework JavaScript de código-aberto, focado no desenvolvimento de interfaces de
                        usuário e
                        aplicativos de página única.</p>
                  </div>
               </div>
            </div>
            <div class="skills-flex">
               <div class="skills-itens">
                  <div class="itens-icon">
                     <div class="itens-bg"></div>
                     <img src="./assets/icons/react-icon.png" alt="">
                     <h2>React Js</h2>
                     <p>O React é uma biblioteca front-end JavaScript de código aberto com foco em criar interfaces de
                        usuário em
                        páginas web.</p>
                  </div>
               </div>
               <div class="skills-itens">
                  <div class="itens-icon">
                     <div class="itens-bg"></div>
                     <img src="./assets/icons/php-icon.png" alt="">
                     <h2>PHP</h2>
                     <h3>(básico)</h3>
                     <p>PHP é uma linguagem interpretada livre, usada originalmente apenas para o desenvolvimento de
                        aplicações
                        presentes e atuantes no lado do servidor.</p>
                  </div>
               </div>
            </div>
         </div>
      </div>
   </div>
   <div id="projects" class="projects-container">
      <div class="projects-center">
         <h1 data-aos="fade-right" data-aos-duration="600">Projetos</h1>
         <div data-aos="fade-right" data-aos-duration="800" class="projects-line"></div>
         <div data-aos="fade-right" data-aos-duration="1000" class="projects-left">
            <svgProjects v-if="!reactMode" class="svg-projects" />
            <svgProjectsReact v-else class="svg-projects" />
         </div>
         <div class="projects-right">
            <div data-aos="fade-left" data-aos-duration="500" class="projects-row">
               <a href="https://github.com/RichardMidas/Jogo-da-forca" target="_blank">
                  <div class="projects-content-rl">
                     <img class="project-img p" src="../src/imgs/project1.png" alt="">
                     <h2>Jogo da Forca</h2>
                     <p>Jogo da forca desenvolvido em Java Script com interação de cores definidas.</p>
                  </div>
               </a>
               <a href="https://github.com/RichardMidas/company-plataform" target="_blank">
                  <div class="projects-content-rl">
                     <img class="project-img p" src="../src/imgs/project2.png" alt="">
                     <h2>Company Plataform</h2>
                     <p>Interface feita em VueJs que simula um sistema gerencial de uma empresa. <br> (Em desenvolvimento)
                     </p>
                  </div>
               </a>
            </div>
            <div data-aos="fade-right" data-aos-duration="1000" class="projects-row">
               <div class="projects-content">
                  <h3>Em breve</h3>
               </div>
               <div class="projects-content">
                  <h3>Em breve</h3>
               </div>
            </div>
            <div data-aos="fade-left" data-aos-duration="1500" class="projects-row">
               <div class="projects-content">
                  <h3>Em breve</h3>
               </div>
               <div class="projects-content">
                  <h3>Em breve</h3>
               </div>
            </div>
         </div>
      </div>
   </div>
   <div id="contact" class="contact-container">
      <svgBgFooter v-if="!reactMode" class="svgBgFooter" />
      <svgBgFooter v-else class="svgBgFooter" />
      <div class="contact-center">
         <div data-aos="zoom-out-right" data-aos-duration="1500" class="contact-left">
            <h2>Tem interesse no meu trabalho?</h2>
            <h3>Entre em contato comigo :&#41</h3>
            <div class="contact-row">
               <a href="http://wa.me/5521973972811" target="_blank" rel="noopener noreferrer"><img v-if="!reactMode"
                     class="contact-icon" src="../src/assets/icons/wppFooter.png" alt="" srcset=""></a>
               <a href="http://wa.me/5521973972811" target="_blank" rel="noopener noreferrer"><img v-if="reactMode"
                     class="contact-icon" src="../src/assets/icons/wppReact.png" alt="" srcset=""></a>
               <a href="http://mailto:richardisraelmagalhaes@gmail.com" target="_blank" rel="noopener noreferrer"><img
                     v-if="!reactMode" class="contact-icon" src="../src/assets/icons/gmailFooter.png" alt="" srcset=""></a>
               <a href="http://mailto:richardisraelmagalhaes@gmail.com" target="_blank" rel="noopener noreferrer"><img
                     v-if="reactMode" class="contact-icon" src="../src/assets/icons/gmailReact.png" alt="" srcset=""></a>
               <a href="http://www.linkedin.com/in/richard-israel-667462246/" target="_blank"
                  rel="noopener noreferrer"><img v-if="!reactMode" class="contact-icon"
                     src="../src/assets/icons/linkedinFooter.png" alt="" srcset=""></a>
               <a href="http://www.linkedin.com/in/richard-israel-667462246/" target="_blank"
                  rel="noopener noreferrer"><img v-if="reactMode" class="contact-icon"
                     src="../src/assets/icons/linkedinReact.png" alt="" srcset=""></a>
            </div>
            <a class="contact-btn" href="https://github.com/RichardMidas" target="_blank">
               <img v-if="!reactMode" class="contact-git" src="../src/assets/icons/github.png" alt="">
               <img v-if="reactMode" class="contact-git" src="../src/assets/icons/githubReact.png" alt="">
            </a>
         </div>
         <div data-aos="zoom-out-left" data-aos-duration="1500" class="contact-right">
            <svgContact v-if="!reactMode" class="svgContact" />
            <svgContactReact v-else class="svgContact" />
         </div>
         <p>Site desenvolvido por <a href="https://github.com/RichardMidas" target="_blank">Midas</a></p>
      </div>
   </div>
</template>
<style lang="scss" scoped>
// VAR
$color-primary: #212428;
$color-secondary: #2B3037;
$main-vue: #00FF7F;
$main-react: #25BEEF;

.btn-top {
   width: 50px;
   height: 50px;
   border-radius: 50%;
   background-color: v-bind(mainColor);
   cursor: pointer;
   position: fixed;
   opacity: 50%;
   z-index: 5;
   right: 50px;
   bottom: 50px;
   display: flex;
   align-items: center;
   justify-content: center;
   transition: all .3s;

   &:hover {
      opacity: 100%;
   }

   img {
      width: 20px;
   }

}

.home-container {
   width: 100vw;
   height: 1000px;
   display: flex;
   align-items: center;
   justify-content: center;
   position: relative;

   .background {
      position: absolute;
      z-index: -1;
      top: 0;
   }

   .home-center {
      width: 1200px;
      height: 100%;
      padding: 0px 30px;
      color: #ffff;

      .home-content {
         height: 500px;
         width: 100%;
         display: flex;
         justify-content: center;
         flex-direction: column;
         position: relative;

         .container-typed {
            // background-color: red;
            width: 165px;
            display: inline-block;
         }

         .text-typed {
            // background-color: red;
            width: 100%;
            font-family: Fira Code;
            font-weight: 300;
            border-right: 3px solid v-bind(mainColor);
            white-space: nowrap;
            overflow: hidden;
            animation: typing 2s steps(18), cursor .4s step-end infinite alternate;
         }

         @keyframes cursor {
            50% {
               border-color: transparent;
            }
         }

         @keyframes typing {
            from {
               width: 0;
            }
         }

         span {
            color: v-bind(mainColor);
         }

         h1 {
            font-size: 3.5rem;
            font-family: Open sans;
            font-weight: 600;
         }

         h2 {
            font-size: 2.7rem;
            font-family: Open sans;
            font-weight: 600;
            margin-bottom: 10px;
         }

         p {
            font-size: 1.2rem;
            font-family: Open sans;
            letter-spacing: 0.8px;
            width: 570px;
         }

         .btns-row {
            display: flex;
            flex-direction: row;
            position: absolute;
            bottom: 0;

            a {
               text-decoration: none;
            }

         }

         .btn-left {
            width: 167px;
            height: 45px;
            border: 1px solid v-bind(mainColor);
            background-color: $color-primary;
            color: v-bind(mainColor);
            font-family: Open Sans;
            font-size: 20px;
            font-weight: 300;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.2s;
            margin-right: 40px;


            &:hover {
               box-shadow: inset 0px 0px 15px 1px v-bind(mainColor);
            }
         }

         .btn-right {
            left: 230px;
            width: 167px;
            height: 45px;
            flex-shrink: 0;
            background-color: v-bind(mainColor);
            color: #FFF;
            font-family: Open Sans;
            font-size: 20px;
            font-style: normal;
            font-weight: 700;
            line-height: normal;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.2s;

            &:hover {
               box-shadow: 0px 0px 15px 1px v-bind(mainColor);
            }
         }

      }

      .svg-home {
         width: 650px;
         position: absolute;
         right: 0;
         bottom: 0px;
      }

      .nav-bar {
         width: 100%;
         height: 150px;
         display: flex;
         align-items: center;
         justify-content: center;
         position: relative;

         .input-design {
            display: flex;
            flex-direction: column;
            position: absolute;
            left: 200px;
            align-items: center;
            width: 50px;
            height: 60px;
         }

         .text-mode {
            font-family: Open sans;
            font-size: .8rem;
            position: absolute;
            top: 0;
         }

         .text-design {
            font-family: Open sans;
            font-size: .8rem;
            position: absolute;
            bottom: 0;
            font-weight: 700;
            color: v-bind(mainColor);
         }

         .switch-check {
            z-index: 1;
            width: 35px;
            height: 15px;
            border-radius: 30px;
            cursor: pointer;
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            background-color: v-bind(mainColor);

            input {
               z-index: 1;
               width: 100%;
               height: 100%;
               position: absolute;
               appearance: none;
               border-radius: 30px;
               transition: all .5s;
               cursor: pointer;

               &:checked {
                  background-color: $main-react;
               }

               &:checked+.toggle {
                  left: 20px;

               }
            }

            .toggle {
               width: 15px;
               height: 15px;
               position: absolute;
               border-radius: 50%;
               z-index: 2;
               left: 0;
               top: 0;
               background-color: #fff;
               transition: cubic-bezier(0.895, 0.07, 0.685, 0.68);
               transition: .5s;
               cursor: pointer;
            }
         }

         .logo {
            position: absolute;
            left: -20px;
            pointer-events: none;
         }

         .btn-nav {
            color: #ffff;
            font-family: Open Sans;
            margin: 0px 40px;
            text-decoration: none;
            position: relative;

            &::after {
               position: absolute;
               content: " ";
               width: 0px;
               height: 3px;
               background-color: v-bind(mainColor);
               bottom: -8px;
               left: 0;
               transition: all .2s;
            }

            &:hover {
               &::after {
                  width: 100%;
               }
            }


         }


         .i-linkedin {
            width: 40px;
            margin-right: 160px;
            position: absolute;
            right: 0;
            top: 50px;
         }

         .i-gmail {
            width: 40px;
            margin-right: 80px;
            position: absolute;
            right: 0;
            top: 50px;
         }

         .i-github {
            width: 40px;
            position: absolute;
            right: 0;
            top: 50px;
         }
      }
   }
}

@media screen and (max-width: 1110px) {

   .home-container {
      margin-bottom: 150px !important;
   }

   .home-content {
      display: flex;
      align-items: center;
      justify-content: center;
   }

   .svg-home {
      scale: .8;
      left: 43%;
      transform: translate(-50%);
      top: 550px;
   }

   p {
      text-align: center;
   }
}

@media screen and (max-width: 940px) {

   .nav-bar {
      display: none !important;
   }
}

@media screen and (max-width: 600px) {
   .home-content {
      h1 {
         font-size: 2rem !important;
      }

      h2 {
         font-size: 2rem !important;
      }

      .text-content {
         width: 400px !important;
         font-size: .7rem !important;
      }

      .btn-left,
      .btn-right {
         bottom: 30px !important;
         width: 150px !important;
      }

      .btns-row {
         bottom: 50px !important;
      }

      .svg-home {
         width: 500px !important;
         top: 450px !important;
      }
   }

}

//===== HOME END =====
.about-container {

   width: 100vw;
   height: 1000px;
   display: flex;
   align-items: center;
   justify-content: center;

   .about-center {
      width: 1500px;
      height: 100%;
      display: flex;
      flex-direction: row;
      position: relative;

      .svg-code {
         width: 2000px;
         position: absolute;
         right: -650px;
         display: flex;
      }

      h1 {
         position: absolute;
         font-family: Open sans;
         color: #ffff;
         font-size: 3rem;
         font-weight: 500;
         right: 300px;
         top: 160px;
      }

      .about-line {
         position: absolute;
         width: 600px;
         height: 5px;
         border-radius: 5px 0 0 5px;
         background-color: v-bind(mainColor);
         right: 600px;
         top: 195px;
      }

      .about-left {
         width: 50%;
         height: 100%;
         position: relative;

         .about-profile {
            top: 370px;
            right: 91px;
            width: 490px;
            position: absolute;
            z-index: 2;
            transition: .3s all;

            &:not(:hover) {
               filter: grayscale(1);
            }
         }

         .svg-pc {
            width: 1000px;
            position: absolute;
            right: -100px;
         }

      }

      .about-right {
         width: 50%;
         height: 100%;
         display: flex;
         align-items: center;
         justify-content: start;

         h2 {
            color: #ffff;
            font-size: 3rem;
            font-family: Open sans;
            font-weight: 400;
         }

         span {
            color: v-bind(mainColor);
         }

         p {
            color: #ffff;
            font-size: 1rem;
            font-family: Open sans;
            font-weight: 400;
            width: 500px;
         }

         .about-row {
            display: flex;
            flex-direction: column;
         }

      }

   }
}

@media screen and (max-width: 1110px) {



   .about-center {
      padding-top: 350px !important;
      display: flex !important;
      flex-direction: column !important;
      align-items: center !important;
      justify-content: center !important;
      height: 1500px !important;

      .svg-pc {
         // width: 800px !important;
         // left: 40% !important;
         // transform: translateX(-50%) !important;
         display: none;
      }


      .about-left {
         width: 100% !important;
         display: flex !important;
         justify-content: center !important;

         .about-profile {
            width: 700px !important;
            left: 50% !important;
            transform: translateX(-50%) !important;
         }
      }

      .about-right {
         width: 100% !important;
         display: flex !important;
         justify-content: center !important;
      }

      h2 {
         text-align: center;
      }

      h1 {
         top: 520px !important;
         left: 50%;
         transform: translateX(-50%) !important;
         width: 300px;
         display: flex;
         justify-content: center;
      }
   }

   .about-line {
      top: 630px !important;
      left: 50%;
      transform: translateX(-50%) !important;
   }

   .svg-code {
      display: none !important;
   }
}

@media screen and (max-width: 600px) {

   .about-center {
      h1 {
         // top: 320px !important;
         font-size: 2rem !important;
      }

      .about-line {
         top: 600px !important;
         width: 400px !important;
      }

      .about-left {
         height: 400px !important;

         .about-profile {
            top: 150px !important;
            width: 400px !important;
            left: 50% !important;
            transform: translateX(-50%) !important;
         }
      }

      .about-right {
         height: 400px !important;
         align-items: start !important;

         h2 {
            font-size: 2rem !important;
         }

         p {
            font-size: .8rem !important;
            width: 350px !important;
         }
      }
   }


}

//===== ABOUT END =====
.skills-container {
   width: 100vw;
   height: 1000px;
   background-color: $color-primary;
   display: flex;
   justify-content: center;

   .skills-center {
      width: 1600px;
      height: 100%;

      .skills-text {
         display: flex;
         width: 100%;
         height: 200px;
         justify-content: center;
         align-items: center;
         position: relative;

         h1 {
            margin: 0 50px;
            color: #ffff;
            font-family: Open sans;
            font-weight: 400;
         }

         h2 {
            position: absolute;
            bottom: 30px;
            color: #ffff;
            font-family: Fira code;
            font-weight: 300;
         }

         .skills-line {
            width: 500px;
            height: 5px;
            background-color: v-bind(mainColor);
            border-radius: 5px;
         }
      }

      .skills-content {
         width: 100%;
         height: 750px;
         display: flex;
         flex-direction: row;

         .skills-flex {
            display: flex;
            width: 100%;
            height: 100%;
         }

         .skills-itens {
            width: 100%;
            height: 80%;
            border: 1px solid v-bind(mainColor);
            transition: .5s all;
            overflow-x: hidden;

            .itens-icon {
               width: 100%;
               height: 100%;
               position: relative;
               overflow-y: hidden;
               overflow-x: hidden;
               // background-color: red;
               transition: .5s all;

               &:not(:hover) {
                  filter: grayscale(1);
               }

               &:hover .itens-bg {
                  bottom: 0px;
               }

               &:hover img {
                  width: 150px;
                  top: 80px;
               }

               &:hover h2 {
                  top: 270px;
               }

               &:hover h3 {
                  top: 300px;
               }

               .itens-bg {
                  background: v-bind(mainColor);
                  background: linear-gradient(0deg, v-bind(mainColor) 0%, rgba(22, 22, 22, 0) 20%);
                  position: absolute;
                  width: 100%;
                  height: 100%;
                  bottom: -150px;
                  transition: all .5s;
               }

               img {
                  position: absolute;
                  left: 50%;
                  transform: translateX(-50%);
                  top: 150px;
                  transition: .4s all;
                  width: 100px;
               }

               h2 {
                  position: absolute;
                  color: #FFF;
                  font-family: Open sans;
                  font-weight: 600;
                  top: 290px;
                  left: 50%;
                  transition: .4s all;
                  transform: translateX(-50%);
               }

               h3 {
                  position: absolute;
                  color: #FFF;
                  font-family: Open sans;
                  font-weight: 600;
                  top: 320px;
                  left: 50%;
                  transition: .4s all;
                  transform: translateX(-50%);
               }

               &:not(:hover) p {
                  opacity: 0;
                  bottom: 120px;
               }

               p {
                  position: absolute;
                  left: 50%;
                  transform: translateX(-50%);
                  width: 250px;
                  bottom: 180px;
                  font-size: .9rem;
                  transition: .5s all;
                  color: #fff;
                  font-family: Open sans;
                  text-align: center;
               }
            }

            &:hover {
               width: 100%;
            }
         }
      }
   }


}

@media screen and (max-width: 1110px) {
   .skills-container {
      margin-top: 300px;
      height: 2300px;
   }

   .skills-content {
      flex-direction: column !important;
      height: 2500px !important;
      display: flex;
      align-items: center;
   }

   .skills-flex {
      width: 50% !important;
      height: 700px !important;
      align-items: center;
   }

   .skills-itens {
      height: 95% !important;
   }
}

@media screen and (max-width: 750px) {
   .skills-itens {
      height: 90% !important;
      width: 50% !important;
   }

   .skills-flex {
      width: 80% !important;
      height: 500px !important;
   }

   .skills-container {
      height: 1850px !important;
   }

   .skills-content {
      height: 1850px !important;
   }

   .skills-text {
      h1 {
         font-size: 1.5rem;
      }

      h2 {
         font-size: 1rem !important;
      }

      .skills-line {
         width: 150px !important;
      }
   }

   .itens-icon {
      img {
         width: 80px !important;
      }

      p {
         bottom: 0 !important;
         font-size: .8rem !important;
         width: 90% !important;
      }

      &:hover p {
         bottom: 50px !important;
         opacity: 100% !important;
      }

      &:hover h2 {
         top: 200px !important;
      }

      &:hover h3 {
         top: 230px !important;
      }
   }
}

@media screen and (max-width: 500px) {
   .skills-container {
      height: 2000px !important;
   }

   .skills-content {
      height: 2000px !important;
   }

   .skills-itens {
      height: 90% !important;
      width: 40% !important;
   }

   .skills-flex {
      display: flex !important;
      justify-content: center;
   }

   .itens-icon {
      img {
         width: 80px !important;
      }

      p {
         bottom: 0 !important;
         font-size: .8rem !important;
         width: 90% !important;
      }

      &:hover p {
         bottom: 50px !important;
         opacity: 100% !important;
      }

      &:hover h2 {
         top: 200px !important;
      }

      &:hover h3 {
         top: 230px !important;
      }
   }
}

//===== SKILLS END =====
.projects-container {
   width: 100vw;
   height: 1000px;
   display: flex;
   justify-content: center;

   .projects-center {
      width: 1700px;
      height: 100%;
      display: flex;
      position: relative;

      h1 {
         color: #FFF;
         text-shadow: -4px -3px 0px v-bind(mainColor);
         font-family: Fira Code;
         font-size: 2.5rem;
         font-weight: 600;
         left: 50px;
         top: 50px;
         position: absolute;
      }

      .projects-line {
         top: 130px;
         position: absolute;
         width: 500px;
         left: 30px;
         height: 5px;
         background-color: v-bind(mainColor);
      }

      .projects-left {
         display: flex;
         position: relative;
         align-items: center;
         width: 40%;
         height: 100%;

         .svg-projects {
            width: 130%;
         }
      }

      .projects-right {
         width: 60%;
         height: 100%;
         display: flex;
         align-items: center;
         justify-content: center;
         flex-direction: column;

         .projects-row {
            width: 100%;
            height: 33%;
            display: flex;
            align-items: center;
            justify-content: center;

            a {
               display: flex;
               margin: 0px 30px;
               width: 35%;
               height: 250px;
            }

            .projects-content-rl {
               width: 100%;
               height: 250px;
               border: 3px solid v-bind(mainColor);
               cursor: pointer;
               display: flex;
               align-items: center;
               justify-content: center;
               transition: all .3s;
               position: relative;

               h3 {
                  color: v-bind(mainColor);
                  font-family: Open Sans;
                  transition: all .5s;
               }

               &:hover h3 {
                  letter-spacing: 3px;
               }

               &:hover {
                  scale: 1.2;
               }

               &:hover h2 {
                  top: 40px;
                  opacity: 1;
               }

               &:hover p {
                  bottom: 40px;
                  opacity: 1;
               }

               h2 {
                  top: 10px;
                  left: 30px;
                  position: absolute;
                  font-family: Open sans;
                  color: v-bind(mainColor);
                  opacity: 0;
                  transition: all .5s;
                  pointer-events: none;
               }

               p {
                  position: absolute;
                  bottom: 10px;
                  left: 30px;
                  color: #fff;
                  font-family: Open sans;
                  width: 80%;
                  opacity: 0;
                  transition: all .5s;
                  pointer-events: none;
               }

               .project-img {
                  width: 100%;
                  height: 100%;
                  transition: all .4s;

                  &:hover {
                     opacity: 5%;
                  }
               }
            }

            .projects-content {
               width: 35%;
               height: 250px;
               border: 3px solid v-bind(mainColor);
               margin: 0 30px;
               cursor: pointer;
               display: flex;
               align-items: center;
               justify-content: center;
               transition: all .3s;
               position: relative;

               h3 {
                  color: v-bind(mainColor);
                  font-family: Open Sans;
                  transition: all .5s;
               }

               &:hover h3 {
                  letter-spacing: 3px;
               }

               &:hover {
                  scale: 1.2;
               }

               &:hover h2 {
                  top: 40px;
                  opacity: 1;
               }

               &:hover p {
                  bottom: 40px;
                  opacity: 1;
               }

               h2 {
                  top: 10px;
                  left: 30px;
                  position: absolute;
                  font-family: Open sans;
                  color: v-bind(mainColor);
                  opacity: 0;
                  transition: all .5s;
                  pointer-events: none;
               }

               p {
                  position: absolute;
                  bottom: 10px;
                  left: 30px;
                  color: #fff;
                  font-family: Open sans;
                  width: 80%;
                  opacity: 0;
                  transition: all .5s;
                  pointer-events: none;
               }

               .project-img {
                  width: 100%;
                  height: 100%;
                  transition: all .4s;

                  &:hover {
                     opacity: 5%;
                  }
               }
            }
         }
      }
   }
}

@media screen and (max-width: 1110px) {
   .projects-center {
      h1 {
         top: -200px !important;
         left: 50% !important;
         transform: translateX(-50%) !important;
      }
   }

   .projects-line {
      top: -130px !important;
      left: 50% !important;
      transform: translateX(-50%) !important;
   }

   .projects-container {
      margin-top: 300px;
   }

   .projects-left {
      display: none !important;
   }

   .projects-right {
      width: 100% !important;
   }
}

@media screen and (max-width: 600px) {
   .projects-row {
      flex-direction: column;
      margin: 1px;
      height: 700px !important;

      a {
         width: 300px !important;
         margin: 20px 0px !important;
      }
   }

   .projects-container {
      height: 1800px;
   }

   .projects-content {
      margin: 20px 0px !important;
      width: 300px !important;
   }

   .projects-content-rl {
      margin: 20px 0px !important;
      width: 300px !important;
   }
}

//===== PROJECTS END =====
.contact-container {
   width: 100vw;
   height: 1000px;
   position: relative;
   display: flex;
   justify-content: center;
   overflow: hidden;

   .svgBgFooter {
      position: absolute;
      bottom: -100px;
      z-index: -1;
   }

   .contact-center {
      width: 1500px;
      height: 100%;
      display: flex;

      p {
         font-family: Open sans;
         color: #FFF;
         position: absolute;
         bottom: 30px;
         left: 50%;
         transform: translate(-50%);

         a {
            color: v-bind(mainColor);
            text-decoration: none;
         }
      }

      .contact-left {
         height: 100%;
         width: 50%;
         display: flex;
         justify-content: center;
         align-items: center;
         flex-direction: column;

         h2 {
            font-family: Open sans;
            font-size: 2rem;
            color: #fff;
            font-weight: 500;
         }

         h3 {
            font-family: Open sans;
            font-size: 1.5rem;
            color: #fff;
            font-weight: 500;
         }

         .contact-btn {
            margin-top: 30px;
            width: 250px;
            height: 60px;
            border: 1px solid v-bind(mainColor);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all .5s;

            &:hover {
               box-shadow: inset 0px 0px 15px 1px v-bind(mainColor);
            }
         }

         .contact-git {
            width: 35px;

         }

         .contact-row {
            width: 500px;
            height: 80px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-top: 30px;

            .contact-icon {
               width: 50px;
               margin: 0px 20px;
               transition: all .2s;

               &:hover {
                  scale: 1.2;
               }
            }
         }
      }

      .contact-right {
         height: 100%;
         width: 50%;
         display: flex;
         align-items: center;

         .svgContact {
            width: 500px;
         }
      }
   }
}

@media screen and (max-width: 1110px) {
   .contact-center {
      flex-direction: column;
      height: 1000px !important;

      .contact-left {
         width: 100% !important;
         align-items: center !important;
         justify-content: center !important;
      }

      .contact-right {
         width: 100% !important;
         align-items: center !important;
         justify-content: center !important;
      }
   }
}

@media screen and (max-width: 600px) {
   .contact-left {
      h2 {
         font-size: 1.3rem !important;
      }

      h3 {
         font-size: 1.1rem !important;
      }
   }

   .svgBgFooter {
      bottom: -150px;
   }

   .contact-right {
      position: relative;

      .svgContact {
         width: 300px !important;
         position: absolute;
         top: -100px;
      }
   }
}

//===== CONTACT END =====</style>
