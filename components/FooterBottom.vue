<template>
  <v-footer :absolute="!fixed" app :color="cor">
      <div class="somos">
        <p>nos somos</p>
        <h1>{{ somos }}</h1>
      </div>
      <div class="conte">
        <h1 v-html="footerCta">
          conte qualquer <br />
          coisa pra gente.
        </h1>
      </div>
      <div class="journal">fique atualizado com nossos melhores produtos.</div>
      <form action="">
        <div class="input-container">
          <input
          id="nome"
          v-model="name"
          type="text"
          name="nome"
          placeholder="nome"
          :class="isEmpty(name)"
        />
        <input
          id="email"
          v-model="email"
          type="email"
          name="email"
          placeholder="email"
          :class="isEmpty(email)"
        />
        </div>
        <div class="cta-footer">
          <v-btn text class="enviar"
            >enviar
            <img src="@/assets/img/seta.svg" alt="enviar">
          </v-btn>
          <WppCTA :phone="5521912345678"/>
        </div>
      </form>
      <div class="policies">
        <div class="copy">
          © {{ somos }} 2021. Todos os Direitos Reservados
        </div>
        <div class="copyright">
          <nuxt-link to="/servicos">
            <v-btn text class="copyright">serviços</v-btn>
          </nuxt-link>
          <nuxt-link to="/cookies">
            <v-btn text class="copyright">cookies</v-btn>
          </nuxt-link> 
          <nuxt-link to="/institucional">
            <v-btn text class="copyright">institucional</v-btn>
          </nuxt-link>
        </div>
      </div>
    </v-footer>
</template>

<script>
import WppCTA from '@/components/WppCTA.vue'

export default {
    name: 'FooterBottom',
    components: [
      WppCTA
    ],
    props: {
      somos: {
        type: String,
        default: ''
      },
      cor: {
        type: String,
        default: '#ffffff'
      },
      footerCta: {
        type: String,
        default: 'conte qualquer <br/> coisa pra gente.'
      }
    },
    data() {
        return {
            name: '',
            email: '',
            fixed: false,
        }
    },
    methods: {
        isEmpty(object) {
        if (String(object).length > 0 && String(object) !== undefined) {
            return 'active'
        }
        return ''
        }
    }
}
</script>

<style lang="scss" scoped>

$font-color-primary: white !important;
$font-color-secondary: black !important;

$bg-color-primary: #F2994A !important;
$bg-color-secondary: #219653 !important;

$font-stack-primary: 'Axiforma', sans-serif;
$font-stack-secondary: 'Nexa';

$font-size-line: 24px;
$font-size-footer-big: 36px;
$font-size-footer-small: 14px;
$font-size-footer-cta-header: 20px;
$font-size-footer-cta-subheader: 28px;
$font-size-copyright: 14px;



.v-footer {
  height: 670px;
  position: relative;
  padding: 0 42px;
  justify-content: space-evenly;
  align-items: flex-start;
  flex-direction: column;
}

.somos {
  > * {
    font-family: $font-stack-primary;
    margin-top: 0;
    margin-bottom: 0;
    display: flex;
    align-items: center;
    color: $font-color-primary;
  }
  p {
    font-weight: 300;
    font-size: 18px;
    line-height: 20px;
  }
  h1 {
    font-weight: bold;
    font-size: 18px;
    line-height: 20px;
  }
}

%base-footer-cta {
  display: flex;
  align-items: flex-end;
  color: $font-color-primary;
}

.conte h1{
  @extend %base-footer-cta;
  font-family: $font-stack-primary;
  font-weight: bold;
  font-size: 36px;
  line-height: 46px;
}
.journal {
  @extend %base-footer-cta;
  font-family: $font-stack-primary;
  font-weight: 300;
  font-size: 24px;
  line-height: 25px;
}
form {
  display: flex;
  align-items: left;
  justify-content: space-evenly;
  flex-direction: column;
  width: 100%;
  .input-container {
    max-width: 753px;
  }
}
input {
  width: 100%;
  font-weight: bold;
  font-size: 24px;
  height: 50px;
  color: $font-color-primary;
  outline: none;
  opacity: 0.5;
  border-bottom: 1px solid $font-color-primary;
  font-family: Nexa;
  margin-bottom: 10px;
  & + input {
    margin-bottom: 0px;
  }
}

input::placeholder{
  color: $font-color-primary;
  opacity: 0.5;

  :hover{
    opacity: 1;
    transition: 0.3;
  }
}

input:hover {
  opacity: 1;
  transition: 0.3s;
}

input.active {
  opacity: 1;
  transition: 0.3s;
}

@keyframes enviar {
  0% {
    transform: translateX(0);
  }
  50% {
    transform: translateX(10px);
  }
  100% {
    transform: translateX(0);
  }
}

.enviar {
  font-family: Nexa;
  font-weight: bold;
  margin-top: 16px;
  font-size: 48px;
  line-height: 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-transform: lowercase;
  width: 280px !important;
  color: $font-color-primary;
  letter-spacing: 0px;
  padding: 0px;

  :hover img {
    animation: 0.7s enviar infinite;
  }
}

%base-footer-policies {
  color: $font-color-primary;
  display: flex;
  font-family: $font-stack-primary;
  font-weight: 300;
  font-size: $font-size-copyright;
  line-height: 22px;
  text-transform: uppercase;
}

.policies {
  @extend %base-footer-policies;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  flex-direction: row;
}
.copyright {
  @extend %base-footer-policies;
  flex-direction: column;
  a {
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
    cursor: pointer;
  }
}

button.copyright {
  display: flex;
  align-items: center;
}

.cta-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;

  
}

@media (max-width: 720px) {
  .cta-footer {
    flex-direction: column;
    button {
      margin-top: 25px;

      & + button {
        margin-top: 15px;
      }
    }
  }
  
    
  }
</style>