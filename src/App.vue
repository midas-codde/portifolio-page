<script setup lang="ts">
import svgBg from './components/svg/svgBg.vue'
//  import svgAbout from './components/vue-design/svgAbout.vue'
import svgHome from './components/vue-design/svgHome.vue'
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
        <p>Sou desenvolvedor web, atualmente focado em Front-end.
          Tenho experiência com Freelancer e projetos pessoais.
          Estudo um pouco de Back-end com a finalidade de um dia
          me tornar um Programador FullStack.</p>
        <div class="btn-left">Saiba mais</div>
        <div class="btn-right">Fale comigo!</div>
        <svgHome class="svg-home" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
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
        position: absolute;
        bottom: 0;
        transition: all 0.2s;

        &:hover {
          box-shadow: inset 0px 0px 15px 1px $main-vue;
        }
      }

      .btn-right {
        position: absolute;
        bottom: 0;
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
</style>
