<script setup lang="ts">
import svgBg from './components/svg/svgBg.vue'
import svgCode from './components/vue-design/svgCode.vue';
//  import svgAbout from './components/vue-design/svgAbout.vue'
import svgHome from './components/vue-design/svgHome.vue'
import svgPc from './components/vue-design/svgPc.vue';
//  import svgPc from './components/vue-design/svgPc.vue'
//  import svgProjects from './vue-design/components/svgProjects.vue'
</script>

<template>
  <div class="home-container">
    <svgBg class="background" />
    <div class="home-center">
      <div class="nav-bar">
        <img class="logo" src="./assets/icons/midas-logoBG-white.png" alt="">
        <a class="btn-nav" href="#">Home</a>
        <a class="btn-nav" href="#">About me</a>
        <a class="btn-nav" href="#">Skills</a>
        <a class="btn-nav" href="#">Projects</a>
        <a href="http://" target="_blank" rel="noopener noreferrer"><img src="./assets/icons/linkedin.png" alt=""
            class="i-linkedin"></a>
        <a href="http://" target="_blank" rel="noopener noreferrer"><img class="i-gmail" src="./assets/icons/gmail.png"
            alt=""></a>
        <a href="http://" target="_blank" rel="noopener noreferrer"><img src="./assets/icons/github.png" alt=""
            class="i-github"></a>
      </div>
      <div class="home-content">
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
          <div class="btn-left">Saiba mais</div>
          <div class="btn-right">Fale comigo!</div>
        </div>
        <svgHome class="svg-home" />
      </div>
    </div>
  </div>
  <div class="about-container">
    <div class="about-center">
      <svgCode class="svg-code" />
      <div class="about-line"></div>
      <h1>Sobre mim</h1>
      <div class="about-left">
        <svgPc class="svg-pc" />
      </div>
      <div class="about-right">
        <div class="about-column">
          <h2>Oi, <br> Me chamo <span>Richard</span>.</h2>
          <p>Tenho 20 anos e atualmente moro no Rio de Janeiro. Sempre gostei de games e tecnologia e foi através dos
            jogos que tive interesse na área de programação. Hoje sigo minha carreira dominando as tecnologias ReactJs e
            VueJs. Estudo um pouco de PHP para ter conhecimentos sólidos em back-end pra um dia me tornar um Dev
            FullStack. ☕</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
// VAR
$color-primary: #212428;
$color-secondary: #2B3037;
$main-vue: #00FF7F;

.home-container {
  width: 100vw;
  height: 100vh;
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;

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
        border-right: 3px solid $main-vue;
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
        color: $main-vue;
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
      }

      .btn-left {
        width: 167px;
        height: 45px;
        border: 1px solid $main-vue;
        background-color: $color-primary;
        color: $main-vue;
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
          box-shadow: inset 0px 0px 15px 1px $main-vue;
        }
      }

      .btn-right {
        left: 230px;
        width: 167px;
        height: 45px;
        flex-shrink: 0;
        background-color: $main-vue;
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
          box-shadow: 0px 0px 15px 1px $main-vue;
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


      .logo {
        position: absolute;
        left: -20px;
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
          background-color: $main-vue;
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
  height: 100vh;
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
      background-color: $main-vue;
      right: 600px;
      top: 195px;
    }

    .about-left {
      width: 50%;
      height: 100%;
      position: relative;

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
        color: $main-vue;
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
      width: 800px !important;
      left: 40% !important;
      transform: translateX(-50%) !important;
    }


    .about-left {
      width: 100% !important;
      display: flex !important;
      justify-content: center !important;
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
      transform: translateX(-50%);
      width: 300px;
      display: flex;
      justify-content: center;
    }
  }

  .about-line {
    top: 630px !important;
    left: 50%;
    transform: translateX(-50%);
  }

  .svg-code {
    display: none !important;
  }
}

@media screen and (max-width: 600px) {

  .about-center {
    h1 {
      top: 320px !important;
      font-size: 2rem !important;
    }

    .about-line {
      top: 430px !important;
      width: 400px !important;
    }

    .svg-pc {
      width: 600px !important;
      bottom: -100px !important;
    }
  }

  .about-right {
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

//===== ABOUT END =====
</style>
