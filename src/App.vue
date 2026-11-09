
<script setup>
import { ref } from 'vue'

import {
  Github,
  Linkedin,
  Facebook,
  Mail,
  MapPin
} from 'lucide-vue-next'

const nome = ref('Delcínio Chirindza')

const menu = [
  { titulo: 'Início', destino: '#inicio' },
  { titulo: 'Quem sou eu?', destino: '#sobre' },
  { titulo: 'O que faço?', destino: '#experiencia' },
  { titulo: 'Hobbies', destino: '#hobbies' },
  { titulo: 'Contactos', destino: '#contactos' }
]

const profissao = 'Software Developer | Systems Analyst'
const descricao = 'Sou programador, analista de sistemas e docente. Desenvolvo aplicações e soluções de informação.'
const fotoPerfil = '/images/perfil.jpeg'

const perfil = {
  titulo: 'Quem sou eu?',
  apresentacao:
    'Sou licenciado em Engenharia de Tecnologias e Sistemas de Informação, com especialização em Engenharia de Software. Trabalho no desenvolvimento e análise de sistemas de informação e também exerço actividades de docência universitária.',
  localizacao: 'Maputo, Moçambique',
  formacao: 'Licenciatura em Engenharia de Tecnologias e Sistemas de Informação',
  especializacao: 'Engenharia de Software'
}

const competencias = [
  'Java',
  'Spring Boot',
  'JavaScript',
  'Vue.js',
  'React',
  'PostgreSQL',
  'Oracle',
  'REST APIs',
  'Git'
]


const experiencias = [
  {
    id: 1,
    icone: '💻',
    titulo: 'Desenvolvimento de Software',
    descricao:
      'Desenvolvo e mantenho aplicações Web e serviços de integração, utilizando tecnologias como Java, Spring Boot e bases de dados relacionais.',
    tecnologias: ['Java', 'Spring Boot', 'REST APIs']
  },
  {
    id: 2,
    icone: '📊',
    titulo: 'Análise de Sistemas',
    descricao:
      'Participo no levantamento de requisitos, análise de processos e definição de soluções para responder às necessidades dos utilizadores.',
    tecnologias: ['UML', 'BPMN', 'Requisitos']
  },
  {
    id: 3,
    icone: '🎓',
    titulo: 'Docência Universitária',
    descricao:
      'Apoio a formação de estudantes em programação, combinando fundamentos teóricos com exercícios e projectos práticos.',
    tecnologias: ['Java', 'Python', 'Programação']
  },
  {
    id: 4,
    icone: '🧩',
    titulo: 'Arquitectura e Integração',
    descricao:
      'Colaboro na organização de aplicações e integração de componentes, procurando soluções sustentáveis e de fácil manutenção.',
    tecnologias: ['APIs', 'Git', 'Docker']
  }
]


const hobbies = [
  {
    id: 1,
    icone: '📚',
    titulo: 'Leitura',
    descricao:
      'Gosto de ler sobre tecnologia, desenvolvimento pessoal e outros assuntos que me permitem aprender.'
  },
  {
    id: 2,
    icone: '🎵',
    titulo: 'Música',
    descricao:
      'A música faz parte dos meus momentos de descanso e ajuda-me a desligar da rotina.'
  },
  {
    id: 3,
    icone: '✈️',
    titulo: 'Viagens',
    descricao:
      'Gosto de conhecer novos lugares, descobrir outras realidades e aprender com diferentes culturas.'
  },
  {
    id: 4,
    icone: '🤝',
    titulo: 'Actividades comunitárias',
    descricao:
      'Valorizo o convívio, a partilha de conhecimentos e a participação em iniciativas comunitárias.'
  }
]


const contactos = {
  localizacao: 'Maputo, Moçambique',

  // Preencher com o seu endereço de email
  email: 'chirindzadelcinio@gmail.com'
}

const redesSociais = [
  {
    id: 1,
    nome: 'GitHub',
    icone: Github,
    url: 'https://github.com/djchirindza'
  },
  {
    id: 2,
    nome: 'LinkedIn',
    icone: Linkedin,
    url: 'https://www.linkedin.com/in/delciniochirindza/'
  },
  {
    id: 3,
    nome: 'Facebook',
    icone: Facebook,
    url: 'https://www.facebook.com/share/1Cgsp8kRy6/'
  }
]

const menuAberto = ref(false)

function fecharMenu() {
  menuAberto.value = false
}


</script>

<template>
  <div class="portfolio">

    
<header class="cabecalho">
  <div class="logo">
    <span class="simbolo">&lt;/&gt;</span>
    {{ nome }}
  </div>

  <button
    class="menu-toggle"
    type="button"
    :aria-expanded="menuAberto"
    aria-controls="menu-principal"
    :aria-label="menuAberto ? 'Fechar menu' : 'Abrir menu'"
    @click="menuAberto = !menuAberto"
  >
    {{ menuAberto ? '✕' : '☰' }}
  </button>

  <nav
    id="menu-principal"
    class="navegacao"
    :class="{ 'menu-aberto': menuAberto }"
    aria-label="Navegação principal"
  >
    <a
      v-for="item in menu"
      :key="item.destino"
      :href="item.destino"
      @click="fecharMenu"
    >
      {{ item.titulo }}
    </a>
  </nav>
</header>


    <main>
      <section id="inicio" class="hero">
        <div class="secao">
          <p class="saudacao">Olá, seja bem-vindo!</p>

          <h1>{{ nome }}</h1>

          <h2>{{ profissao }}</h2>

          <p class="descricao">
            {{ descricao }}
          </p>

          <div class="hero-botoes">
            <a href="#experiencia" class="btn btn-principal">
              Ver o meu percurso
            </a>
            <a href="#contactos" class="btn btn-secundario">
              Contactar-me
            </a>
          </div>
        </div>  

        <div class="hero-imagem">
          <div class="moldura">
            <img :src="fotoPerfil" alt="Fotografia de Delcínio Chirindza">
          </div>
        </div>

      </section>

      
<section id="sobre" class="secao sobre">
  <div class="secao-cabecalho">
    <span class="secao-etiqueta">APRESENTAÇÃO</span>
    <h2>{{ perfil.titulo }}</h2>
    <p>Um pouco sobre o meu percurso e formação.</p>
  </div>

  <div class="sobre-conteudo">
    <div class="sobre-texto">
      <h3>Desenvolvimento de Software e Sistemas de Informação</h3>

      <p>{{ perfil.apresentacao }}</p>

      <div class="sobre-detalhes">
        <p><strong>Localização:</strong> {{ perfil.localizacao }}</p>
        <p><strong>Formação:</strong> {{ perfil.formacao }}</p>
        <p><strong>Especialização:</strong> {{ perfil.especializacao }}</p>
      </div>
    </div>

    <div class="sobre-competencias">
      <h3>Competências técnicas</h3>

      <div class="competencias-lista">
        <span
          v-for="competencia in competencias"
          :key="competencia"
          class="competencia"
        >
          {{ competencia }}
        </span>
      </div>
    </div>
  </div>
</section>
      
<section id="experiencia" class="secao experiencia">

  <div class="secao-cabecalho">
    <span class="secao-etiqueta">EXPERIÊNCIA PROFISSIONAL</span>
    <h2>O que faço?</h2>
    <p>
      As principais áreas em que desenvolvo a minha
      actividade profissional.
    </p>
  </div>

  <div class="experiencias-grid">

    <article
      v-for="experiencia in experiencias"
      :key="experiencia.id"
      class="experiencia-card"
    >
      <div class="experiencia-icone">
        {{ experiencia.icone }}
      </div>

      <h3>{{ experiencia.titulo }}</h3>

      <p>{{ experiencia.descricao }}</p>

      <div class="experiencia-tecnologias">
        <span
          v-for="tecnologia in experiencia.tecnologias"
          :key="tecnologia"
          class="tecnologia-tag"
        >
          {{ tecnologia }}
        </span>
      </div>
    </article>

  </div>
</section>


      
<section id="hobbies" class="secao hobbies">

  <div class="secao-cabecalho">
    <span class="secao-etiqueta">ALÉM DA PROFISSÃO</span>
    <h2>Os meus Hobbies</h2>
    <p>
      Algumas actividades que fazem parte
      dos meus interesses pessoais.
    </p>
  </div>

  <div class="hobbies-grid">

    <article
      v-for="hobby in hobbies"
      :key="hobby.id"
      class="hobby-card"
    >
      <div class="hobby-icone">
        {{ hobby.icone }}
      </div>

      <h3>{{ hobby.titulo }}</h3>

      <p>{{ hobby.descricao }}</p>
    </article>

  </div>

</section>


      
<section id="contactos" class="secao contactos">
  <div class="secao-cabecalho">
    <span class="secao-etiqueta">CONTACTOS</span>
    <h2>Vamos conversar?</h2>
    <p>
      Estou disponível para trocar ideias sobre
      desenvolvimento de software, sistemas de informação
      e novas oportunidades de colaboração.
    </p>
  </div>

  <div class="contactos-conteudo">
    <div class="contacto-localizacao">
      <MapPin :size="24" />
      <span>{{ contactos.localizacao }}</span>

<a
  :href="`mailto:${contactos.email}`"
  class="contacto-email"
>
  {{ contactos.email }}
</a>

    </div>

    <a
      v-if="contactos.email"
      :href="`mailto:${contactos.email}`"
      class="btn btn-principal"
    >
      <Mail :size="19" />
      Enviar mensagem
    </a>

    <p v-else class="contacto-aviso">
      Pode encontrar-me nas redes profissionais
      indicadas no rodapé.
    </p>
  </div>
</section>

    </main>

<footer class="rodape">
  <div class="rodape-conteudo">
    <div class="rodape-identidade">
      <h3>&lt;/&gt; {{ nome }}</h3>
      <p>Software Developer | Systems Analyst</p>
    </div>

    <div class="redes-sociais">
      <template
        v-for="rede in redesSociais"
        :key="rede.id"
      >
        <a
          v-if="rede.url"
          :href="rede.url"
          :aria-label="rede.nome"
          :title="rede.nome"
          target="_blank"
          rel="noopener noreferrer"
          class="rede-link"
        >
          <component :is="rede.icone" :size="22" />
        </a>

        <span
          v-else
          :title="`${rede.nome} - por configurar`"
          class="rede-link rede-inactiva"
        >
          <component :is="rede.icone" :size="22" />
        </span>
      </template>
    </div>
  </div>

  <div class="rodape-inferior">
    <p>© 2026 {{ nome }}. Todos os direitos reservados.</p>
    <a href="#inicio">Voltar ao início ↑</a>
  </div>
</footer>
  

  </div>
</template>

<style scoped>
.portfolio {
  min-height: 100vh;
  background-color: #101827;
  color: white;
  font-family: Arial, sans-serif;
}

.cabecalho {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 25px 5%;
  background-color: #0b1120;
  border-bottom: 1px solid #263244;
}

.logo {
  font-size: 20px;
  font-weight: bold;
  color: #ffffff;
}

.simbolo {
  color: #00e08a;
  margin-right: 10px;
}

.navegacao {
  display: flex;
  gap: 25px;
}

.navegacao a {
  color: #ffffff;
  text-decoration: none;
  font-size: 15px;
  transition: color 0.3s;
}

.navegacao a:hover {
  color: #00e08a;
}

.secao {
  min-height: 70vh;
  padding: 100px 8%;
  border-bottom: 1px solid #263244;
  scroll-margin-top: 20px;
}

.secao h1 {
  font-size: 48px;
  color: #00e08a;
}

.secao h2 {
  font-size: 28px;
}

.secao p {
  color: #cbd5e1;
  line-height: 1.8;
}

html {
  scroll-behavior: smooth;
}

@media (max-width: 768px) {
  .cabecalho {
    flex-direction: column;
    gap: 20px;
  }

  .navegacao {
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px;
  }

  .secao {
    padding: 70px 6%;
  }

  .secao h1 {
    font-size: 34px;
  }
}


/* SECÇÃO PRINCIPAL */

.hero {
  min-height: 85vh;
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  align-items: center;
  gap: 60px;
  padding: 80px 8%;
}

.saudacao {
  color: #00e08a;
  font-size: 18px;
}

.hero h1 {
  font-size: clamp(36px, 5vw, 64px);
  margin: 15px 0;
  color: #ffffff;
}

.hero h2 {
  font-size: 26px;
  font-weight: 500;
  color: #00e08a;
}

.descricao {
  margin-top: 25px;
  max-width: 600px;
  line-height: 1.8;
  color: #cbd5e1;
}

.hero-botoes {
  display: flex;
  gap: 20px;
  margin-top: 35px;
}

.btn {
  display: inline-block;
  padding: 14px 26px;
  border-radius: 30px;
  font-weight: bold;
  text-decoration: none;
  transition: 0.3s;
}

.btn-principal {
  background-color: #00c878;
  color: #08131c;
}

.btn-principal:hover {
  background-color: #00e08a;
  transform: translateY(-3px);
}

.btn-secundario {
  color: #00e08a;
  border: 2px solid #00c878;
}

.btn-secundario:hover {
  background-color: #00c878;
  color: #08131c;
}

.hero-imagem {
  display: flex;
  justify-content: center;
  align-items: center;
}

.moldura {
  width: min(350px, 100%);
  aspect-ratio: 1;
  border-radius: 50%;
  border: 3px solid #00c878;
  padding: 15px;
  box-shadow: 0 0 35px rgba(0, 200, 120, 0.25);
}

.moldura img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 50%;
}

/* RESPONSIVIDADE */

@media (max-width: 768px) {
  .hero {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 40px;
    padding: 70px 6%;
  }

  .descricao {
    margin-inline: auto;
  }

  .hero-botoes {
    justify-content: center;
    flex-wrap: wrap;
  }

  .moldura {
    width: min(280px, 100%);
  }
}


/* QUEM SOU EU */

.sobre {
  background-color: #0b1120;
}

.secao-cabecalho {
  text-align: center;
  margin-bottom: 55px;
}

.secao-etiqueta {
  color: #00c878;
  font-size: 13px;
  font-weight: bold;
  letter-spacing: 3px;
}

.secao-cabecalho h2 {
  font-size: 38px;
  margin: 15px 0;
}

.sobre-conteudo {
  display: grid;
  grid-template-columns: 1.3fr 1fr;
  gap: 50px;
  align-items: start;
}

.sobre-texto h3,
.sobre-competencias h3 {
  font-size: 23px;
  margin-bottom: 20px;
}

.sobre-texto p {
  line-height: 1.9;
}

.sobre-detalhes {
  margin-top: 30px;
}

.sobre-detalhes strong {
  color: #00e08a;
}

.sobre-competencias {
  padding: 30px;
  background-color: #141e30;
  border: 1px solid #263244;
  border-radius: 16px;
}

.competencias-lista {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
}

.competencia {
  padding: 10px 16px;
  background-color: #0b1120;
  border: 1px solid #00c878;
  border-radius: 25px;
  color: #00e08a;
  font-size: 14px;
}

@media (max-width: 768px) {
  .sobre-conteudo {
    grid-template-columns: 1fr;
    gap: 30px;
  }

  .secao-cabecalho h2 {
    font-size: 30px;
  }
}


/* ETAPA 7 - EXPERIÊNCIA PROFISSIONAL */

.experiencia {
  background-color: #101827;
}

.experiencias-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 25px;
  max-width: 1200px;
  margin: 0 auto;
}

.experiencia-card {
  display: flex;
  flex-direction: column;
  padding: 30px;
  background-color: #141e30;
  border: 1px solid #263244;
  border-radius: 16px;
  transition: transform 0.3s, border-color 0.3s;
}

.experiencia-card:hover {
  transform: translateY(-6px);
  border-color: #00c878;
}

.experiencia-icone {
  font-size: 32px;
  margin-bottom: 20px;
}

.experiencia-card h3 {
  color: #ffffff;
  font-size: 22px;
  margin: 0 0 15px;
}

.experiencia-card p {
  color: #cbd5e1;
  line-height: 1.8;
  margin-bottom: 25px;
}

.experiencia-tecnologias {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: auto;
}

.tecnologia-tag {
  padding: 7px 12px;
  border-radius: 20px;
  background-color: #0b1120;
  color: #00e08a;
  font-size: 12px;
}

/* ADAPTAÇÃO PARA TELEMÓVEIS */

@media (max-width: 768px) {
  .experiencias-grid {
    grid-template-columns: 1fr;
  }

  .experiencia-card {
    padding: 24px;
  }
}

/* ETAPA 8 - HOBBIES */

.hobbies {
  background-color: #0b1120;
}

.hobbies-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 25px;
  max-width: 1100px;
  margin: 0 auto;
}

.hobby-card {
  padding: 35px;
  background-color: #141e30;
  border: 1px solid #263244;
  border-radius: 16px;
  transition: transform 0.3s, border-color 0.3s;
}

.hobby-card:hover {
  transform: translateY(-6px);
  border-color: #00c878;
}

.hobby-icone {
  font-size: 38px;
  margin-bottom: 20px;
}

.hobby-card h3 {
  color: #ffffff;
  font-size: 22px;
  margin-bottom: 15px;
}

.hobby-card p {
  color: #cbd5e1;
  line-height: 1.8;
  font-size: 15px;
}

/* RESPONSIVIDADE */

@media (max-width: 768px) {
  .hobbies-grid {
    grid-template-columns: 1fr;
  }

  .hobby-card {
    padding: 25px;
  }
}


/* ETAPA 9 - CONTACTOS */

.contactos {
  background-color: #101827;
  text-align: center;
  min-height: auto;
  padding-top: 100px;
  padding-bottom: 100px;
}

.contactos .secao-cabecalho p {
  max-width: 650px;
  margin: 0 auto;
}

.contactos-conteudo {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 25px;
}

.contacto-localizacao {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #cbd5e1;
}

.contacto-localizacao svg {
  color: #00c878;
}

.contactos .btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
}

.contacto-aviso {
  color: #94a3b8;
}

/* RODAPÉ */

.rodape {
  padding: 45px 8% 20px;
  background-color: #0b1120;
  border-top: 1px solid #263244;
}

.rodape-conteudo {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 30px;
}

.rodape-identidade h3 {
  margin: 0;
  color: #00e08a;
  font-size: 20px;
}

.rodape-identidade p {
  color: #94a3b8;
  font-size: 14px;
}

.redes-sociais {
  display: flex;
  align-items: center;
  gap: 15px;
}

.rede-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 45px;
  height: 45px;
  background-color: #141e30;
  color: #00e08a;
  border: 1px solid #263244;
  border-radius: 12px;
  text-decoration: none;
  transition: 0.3s;
}

a.rede-link:hover {
  background-color: #00c878;
  color: #0b1120;
  transform: translateY(-4px);
}

.rede-inactiva {
  opacity: 0.4;
  cursor: not-allowed;
}

.rodape-inferior {
  display: flex;
  justify-content: space-between;
  gap: 20px;
  margin-top: 35px;
  padding-top: 20px;
  border-top: 1px solid #263244;
}

.rodape-inferior p,
.rodape-inferior a {
  color: #94a3b8;
  font-size: 13px;
  text-decoration: none;
}

.rodape-inferior a:hover {
  color: #00e08a;
}

@media (max-width: 768px) {
  .rodape-conteudo,
  .rodape-inferior {
    flex-direction: column;
    text-align: center;
  }

  .contactos {
    padding: 70px 6%;
  }
}
.contacto-email {
  color: #00e08a;
  text-decoration: none;
  overflow-wrap: anywhere;
}

.contacto-email:hover {
  text-decoration: underline;
}


/* MENU RESPONSIVO */

.menu-toggle {
  display: none;
  background: transparent;
  color: #00e08a;
  border: 1px solid #263244;
  border-radius: 8px;
  padding: 8px 12px;
  font-size: 24px;
  cursor: pointer;
}

@media (max-width: 768px) {
  .cabecalho {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
  }

  .menu-toggle {
    display: block;
  }

  .navegacao {
    display: none;
    flex-direction: column;
    width: 100%;
    gap: 0;
  }

  .navegacao.menu-aberto {
    display: flex;
  }

  .navegacao a {
    padding: 14px 0;
    border-bottom: 1px solid #263244;
  }
}


</style>