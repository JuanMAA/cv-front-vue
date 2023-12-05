<script setup lang="ts">
import { ref } from 'vue';

const domain = ref('gabbo.cl');
const name = ref('Juan Gabriel Mansilla');
const profession = ref('Full Stack Developer');
const resume = ref(
  'Soy un apasionado desarrollador Full Stack especializado en Vue.js, JavaScript, Node.js y Express.js.'
);

const contact = ref([
  {
    type: 'Email',
    value: 'juan@example.com',
  },
  {
    type: 'Teléfono',
    value: '+123456789',
  },
]);

const socialMedia = ref([
  {
    platform: 'LinkedIn',
    link: 'https://www.linkedin.com/in/jmansilla/',
    iconClass: 'fab fa-linkedin', // Clase del icono de Font Awesome para LinkedIn
  },
  {
    platform: 'Twitter',
    link: 'https://twitter.com/jmansilla_dev',
    iconClass: 'fab fa-twitter', // Clase del icono de Font Awesome para Twitter
  },
  // Agrega más redes sociales según sea necesario
]);
const education = ref([
  {
    institution: 'Platzi',
    degree: 'Front-End con Vue',
    year: '2023',
  },
]);

const experience = ref([
  {
    company: 'Company A',
    position: 'Software Engineer',
    year: '2020-2022',
  },
  {
    company: 'Company B',
    position: 'Web Developer',
    year: '2018-2020',
  },
  // Agrega más experiencias según sea necesario
]);

const courses = ref([
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  {
    name: 'Curso de Desarrollo Web',
    institution: 'Platzi',
    year: '2022',
  },
  // Agrega más cursos según sea necesario
]);

const portfolio = ref([
  {
    project: 'Curriculum con Vue.js 3',
    description:
      'Experienced Full Stack Developer with a passion for creating efficient and scalable web applications. Proven track record in delivering high-quality software solutions from concept to deployment.',
    year: '2024',
    link: 'https://ejemplo.com/proyecto1',
  },
  {
    project: 'Curriculum con Nuxt.js 3',
    description:
      'Experienced Full Stack Developer with a passion for creating efficient and scalable web applications. Proven track record in delivering high-quality software solutions from concept to deployment.',
    year: '2024',
    link: 'https://ejemplo.com/proyecto2',
  },
  // Agrega más proyectos según sea necesario
]);
</script>

<template>
  <div class="container">
    <div class="left-section">
      <div class="text-center banner-container" >
        <img  src="/gabbo.svg" class="logo-image" alt="Vite logo" />
    <div class="logo-description">
        <p class="title-text">{{ name }}</p>
        <p class="description-text">{{ resume }}</p>
        <p class="social-text">
          <span v-for="(social, index) in socialMedia" :key="index">
            <i :class="social.iconClass" alt="Vite logo" />
          </span>
        </p>
    </div>

      </div>

      <div class="icons">
        <a href="https://vitejs.dev" target="_blank">
          <img src="/pt.svg" class="logo" alt="Vite logo" />
        </a>
        <a href="https://vuejs.org/" target="_blank">
          <img src="/es.svg" class="logo vue" alt="Vue logo" />
        </a>
        <a href="https://less.org/" target="_blank">
          <img src="/us.svg" class="logo vue" alt="Less logo" />
        </a>
      </div>
    </div>

    <div class="right-section">
      <div class="education-container">
        <h3>Educación</h3>
        <div class="divider"></div>
        <ul class="no-bullets">
          <li v-for="(edu, index) in education" :key="index">
            <img
              src="https://yt3.googleusercontent.com/rwU607PYF9jK9QL2I85SdfCLVZJGGsxWukuF_LxD0PepnqEIrFVg3W85FOVPDmWdMN1SxyJ7Xi8=s900-c-k-c0x00ffffff-no-rj"
              alt="Icon"
              class="list-icon"
            />
            <strong> {{ edu.degree }}</strong>
            - {{ edu.institution }} ({{ edu.year }})
          </li>
          <p>
            Experienced Full Stack Developer with a passion for creating
            efficient and scalable web applications. Proven track record in
            delivering high-quality software solutions from concept to
            deployment.
          </p>
          <a class="art-deco-link pb-nn" :href="edu?.link" target="_blank"
            >Ver certificado</a
          >
        </ul>
      </div>

      <div class="education-container">
        <h3>Cursos</h3>
        <div class="divider"></div>
        <ul class="no-bullets">
          <li v-for="(course, index) in courses" :key="index">
            <img
              src="https://yt3.googleusercontent.com/rwU607PYF9jK9QL2I85SdfCLVZJGGsxWukuF_LxD0PepnqEIrFVg3W85FOVPDmWdMN1SxyJ7Xi8=s900-c-k-c0x00ffffff-no-rj"
              alt="Icon"
              class="list-icon"
            />
            <strong>{{ course.name }}</strong> - {{ course.institution }} ({{
              course.year
            }})<br />
            <p>
              Experienced Full Stack Developer with a passion for creating
              efficient and scalable web applications. Proven track record in
              delivering high-quality software solutions from concept to
              deployment.
            </p>
            <a class="art-deco-link pb-nn" :href="courses?.link" target="_blank"
              >Ver certificado</a
            >
          </li>
        </ul>
      </div>

      <div class="education-container">
        <h3>Portafolio</h3>
        <div class="divider"></div>
        <ul>
          <li v-for="(project, index) in portfolio" :key="index">
            <strong>{{ project.project }}</strong>
            <p>{{ project.description }} ({{ project.year }})</p>
            <p>
              <a class="art-deco-link" :href="project.link" target="_blank"
                >Ver proyecto</a
              >
            </p>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped lang="less">
.pb-nn {
  margin-bottom: 90px;
}
.icon-a {
  font-size: 25px;
  padding: 5px;
}
.text-center {
  text-align: center;
}
.education-container {
  background-color: white;
  padding: 5px 25px;
  border: 1px solid #f4f2ee;
  margin: 5px;
  border-radius: 8px;
}
.profile-container {
  padding: 10px;
}
.no-bullets {
  list-style: none; /* Quita los puntos de la lista */
}

/* Agrega un poco de margen inferior para separar los elementos de la lista */
.no-bullets li {
  margin-bottom: 8px;
}
.list-icon {
  width: 30px; /* Ajusta el tamaño del icono según sea necesario */
  height: 30px; /* Ajusta el tamaño del icono según sea necesario */
  margin-right: 8px; /* Ajusta el espacio entre el icono y el texto según sea necesario */
  vertical-align: middle; /* Alinea verticalmente la imagen con el texto */
}
.logo {
  height: 2em;
  padding: 0.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.icons {
  text-align: center;
}

.container {
  display: flex;
  flex-wrap: wrap;
}

.banner-container{
  background-color: #00BB7F;
}

.profile-image {
  width: 100%;
  height: 100%;
  border-radius: 50%;
}

.logo-image {
  width: 100%;
  height: 100%;
}

.left-section {
  flex: 0.5;
  min-width: 200px; /* Ajusta según sea necesario */
  text-align: left;
  position: sticky;
  top: 0;
  height: fit-content; /* Ajusta según sea necesario */
}

.logo-description{
  padding: 25px;
  font-size: 18px;
  color: white;
    font-weight: bold;
    text-align: left;
      background-color: #2f4a60; /* Cambia el color de fondo según tus preferencias */

}

.description-text{
  font-size: 14px;
  //text-transform: uppercase;
    font-family:'MontBlanc-Trial-Bold';
        text-align: left;
}

.title-text{
  font-size: 17px;
  text-transform: uppercase;
  font-weight: 900;
  font-family:'MontBlanc-Trial-Bold';
  
}

.profession-text{
  font-size: 15px;
  text-transform: uppercase;
  font-family:'MontBlanc-Trial-Bold';
}

.social-text{
    font-size: 30px;
}


.social-text span{
  padding-left: 2px;
}

.right-section {
  flex: 2;
  min-width: 400px; /* Ajusta según sea necesario */
  text-align: left;
}

.divider {
  border-bottom: 1px solid #ccc; /* Ajusta según sea necesario, color del divisor */
  margin: 16px 0; /* Ajusta según sea necesario para agregar espacio entre las secciones */
}

@media screen and (max-width: 768px) {
  .left-section,
  .right-section {
    flex: 1;
    min-width: 100%;
  }

  .divider {
    display: none; /* Oculta los divisores en pantallas más pequeñas */
  }
}

@media screen and (max-width: 480px) {
  .right-section {
    order: -1;
  }

  .social-media-list {
    display: flex;
    flex-wrap: wrap;

    li {
      flex: 1;
      min-width: 100%;
    }
  }
}

.art-deco-link {
  text-decoration: none;
  color: #404040; /* Color del texto y del borde */
  border-radius: 10%;
  padding: 5px 10px; /* Ajusta el relleno según sea necesario */
  border: 1px solid #404040; /* Añade el borde al botón */
  border-radius: 14px; /* Añade esquinas redondeadas al botón */
  transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
}

.art-deco-link:hover {
  background-color: #404040; /* Cambia el color de fondo en el hover */
  color: #ffffff; /* Cambia el color del texto en el hover */
}
</style>
