<template>
  <v-footer :absolute="!fixed" app :color="cor">
      <div class="somos">
        <p>nos somos</p>
        <h1>{{ somos }}</h1>
      </div>
      <div class="conte">
        <h1>
          conte qualquer <br />
          coisa pra gente.
        </h1>
      </div>
      <div class="journal">fique atualizado sobre nossos produtos.</div>
      <form action="">
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
        <v-btn text class="enviar"
          >enviar
          <svg
            width="80"
            height="16"
            viewBox="0 0 106 16"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M0.999948 7.7169L104 8.01758"
              stroke="white"
              stroke-width="3"
            />
            <path
              d="M104 8.01758L98.0171 2.00009"
              stroke="white"
              stroke-width="3"
            />
            <path
              d="M104 8.01736L97.9822 13.9998"
              stroke="white"
              stroke-width="3"
            />
          </svg>
        </v-btn>
      </form>
      <div class="policies">
        <div class="copy">
          © {{ somos }} 2021. Todos os Direitos <br />
          Reservados
        </div>
        <div class="copyright">
          <nuxt-link to="/servicos">
            <v-btn text class="copyright">serviços</v-btn>
          </nuxt-link>
          <nuxt-link to="/institucional">
            <v-btn text class="copyright">institucional</v-btn>
          </nuxt-link>
          <nuxt-link to="/cookies">
            <v-btn text class="copyright">cookies</v-btn>
          </nuxt-link>
        </div>
      </div>
    </v-footer>
</template>

<script>
export default {
    name: 'FooterBottom',
    props: {
      somos: {
        type: String,
        default: ''
      },
      cor: {
        type: String,
        default: '#ffffff'
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

$font-stack-primary: 'Nexa', 'Roboto';
$font-stack-secondary: 'Qaligo';

$font-size-header-logo: 28px;
$font-size-line: 24px;
$font-size-footer-big: 32px;
$font-size-footer-small: 16px;
$font-size-footer-cta-header: 20px;
$font-size-footer-cta-subheader: 28px;
$font-size-copyright: 18px;



.v-footer {
  height: 600px;
  position: relative;
  padding: 0 100px;
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
    font-weight: thin;
    font-size: $font-size-footer-small;
    line-height: 20px;
  }
  h1 {
    font-weight: bold;
    font-size: $font-size-footer-big;
    line-height: 32px;
  }
}

%base-footer-cta {
  display: flex;
  align-items: flex-end;
  color: $font-color-primary;
}

.conte {
  @extend %base-footer-cta;
  font-family: $font-stack-secondary;
  font-weight: normal;
  font-size: $font-size-footer-cta-header;
  line-height: 80px;
}
.journal {
  @extend %base-footer-cta;
  font-family: $font-stack-primary;
  font-weight: bold;
  font-size: $font-size-footer-cta-subheader;
  line-height: 36px;
}
form {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}
input {
  margin-right: 30px;
  font-weight: bold;
  font-size: $font-size-footer-big;
  line-height: 48px;
  color: $font-color-primary;
  outline: none;
  opacity: 0.5;
  border-bottom: 1px solid $font-color-primary;
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
  font-weight: bold;
  font-size: $font-size-footer-big;
  line-height: 48px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-transform: lowercase;
  width: 250px !important;
  color: $font-color-primary;

  :hover svg {
    animation: 0.7s enviar infinite;
  }
}

%base-footer-policies {
  align-items: flex-end;
  color: $font-color-primary;
  display: flex;
  font-family: $font-stack-primary;
  font-weight: thin;
  font-size: $font-size-copyright;
  line-height: 22px;
  text-transform: uppercase;
}

.policies {
  @extend %base-footer-policies;
  width: 100%;
  justify-content: space-between;
  align-items: center;
}
.copyright {
  @extend %base-footer-policies;
}

</style>