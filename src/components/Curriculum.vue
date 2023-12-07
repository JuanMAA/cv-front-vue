<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue';

const domain = ref('gabbo.cl');
const name = ref('Juan Gabriel Mansilla');
const profession = ref('Full Stack Developer');
const resume = ref(
  'Desarrollador Full Stack especializado en Vue.js, JavaScript, Node.js y Express.js.'
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
  {
    platform: 'Instagram',
    link: 'https://twitter.com/jmansilla_dev',
    iconClass: 'fab fa-instagram', // Clase del icono de Font Awesome para Twitter
  }
]);
const education = ref([
  {
    institution: 'Platzi',
    degree: 'Front-End con Vue',
    year: '2023',
  },
    {
    institution: 'Platzi',
    degree: 'Backend con Node.js',
    year: 'En Proceso',
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
  }
]);

const portfolio = ref([
  {
    project: 'Proyecto RESTful con Vue.js',
    description:
      'Experienced Full Stack Developer with a passion for creating efficient and scalable web applications. Proven track record in delivering high-quality software solutions from concept to deployment.',
    year: '2024',
    link: 'https://ejemplo.com/proyecto1',
  },
  {
    project: 'Proyecto RESTful con Nuxt.js',
    description:
      'Experienced Full Stack Developer with a passion for creating efficient and scalable web applications. Proven track record in delivering high-quality software solutions from concept to deployment.',
    year: '2024',
    link: 'https://ejemplo.com/proyecto2',
  },
  // Agrega más proyectos según sea necesario
]);

const activeItem = ref(null);

const handleScroll = () => {
  const scrollPosition = window.scrollY;

  for (const section of sections.value) {
    const sectionElement = document.getElementById(section.id);

    if (sectionElement) {
      const rect = sectionElement.getBoundingClientRect();
      const isInView = rect.top <= 0 && rect.bottom >= 0;

      if (isInView) {
        activeItem.value = section.id;
      }
    }
  }
};

const scrollToSection = (sectionId) => {
  const sectionElement = document.getElementById(sectionId);

  if (sectionElement) {
    sectionElement.scrollIntoView({ behavior: 'smooth' });
    activeItem.value = sectionId;
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener('scroll', handleScroll);
});

</script>

<template>
  <div class="container">
    <div class="left-section">
      <div class="text-center banner-container" >
        <img  src="/gabbo.svg" class="logo-image" alt="Vite logo" />
      </div>
      <div class="menu-container">
        <div @click="scrollToSection('educacion')" :class="{ 'active': activeItem === 'educacion' }">
          <h3>Educacion <i class="fa-solid fa-up-right-from-square"></i></h3> 
        </div>
        <div @click="scrollToSection('cursos')" :class="{ 'active': activeItem === 'cursos' }">
          <h3>Cursos <i class="fa-solid fa-up-right-from-square"></i></h3>
        </div>
        <div @click="scrollToSection('portafolio')" :class="{ 'active': activeItem === 'portafolio' }">
          <h3>Portafolio <i class="fa-solid fa-up-right-from-square"></i></h3>
        </div>
        <div>
          <h3 class="login-button">Login <i class="fa-solid fa-arrow-right-to-bracket"></i></h3>
        </div>
        <div>
          <h3 class="login-button">Sitio Web <i class="fa-solid fa-link"></i></h3>
        </div>
        <div>
          <h3 class="login-button">Descargar CV <i class="fa-solid fa-angles-down"></i></h3>
        </div>
      </div>

      <div class="iconos">
        <span class="icono" v-for="(social, index) in socialMedia" :key="index" >
        <i :class="social.iconClass" alt="Vite logo" />
        </span>
        <span >
          <i class="fa-solid fa-moon"></i>
        </span>
      </div>
    </div>
    

    <div class="right-section">
      <div class="education-container" id="educacion">
        <h3>Educación</h3>
          <div v-for="(edu, index) in education" :key="index" class="item-course">
          <div class="title">
            <img
              src="https://yt3.googleusercontent.com/rwU607PYF9jK9QL2I85SdfCLVZJGGsxWukuF_LxD0PepnqEIrFVg3W85FOVPDmWdMN1SxyJ7Xi8=s900-c-k-c0x00ffffff-no-rj"
              alt="Icon"
              class="list-icon"
            />
            <strong> {{ edu.degree }}</strong>
            - {{ edu.institution }} ({{ edu.year }})
            </div>
          <p class="bg-white">
            Experienced Full Stack Developer with a passion for creating
            efficient and scalable web applications. Proven track record in
            delivering high-quality software solutions from concept to
            deployment.
          </p>
          <a class="art-deco-link pb-nn" :href="edu?.link" target="_blank"
            >
            <i class="fa-solid fa-award"></i>
            Ver certificado</a
          >
          <a class="edit-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-regular fa-pen-to-square"></i>
            </a
          >
          <a class="delete-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-regular fa-trash-can"></i>
            </a
          >
                    </div>

      </div>

      <div class="education-container" id="cursos">
        <h3>Cursos</h3>
          <div v-for="(course, index) in courses" :key="index" class="item-course">
            <img
              src="https://yt3.googleusercontent.com/rwU607PYF9jK9QL2I85SdfCLVZJGGsxWukuF_LxD0PepnqEIrFVg3W85FOVPDmWdMN1SxyJ7Xi8=s900-c-k-c0x00ffffff-no-rj"
              alt="Icon"
              class="list-icon"
            />
            <strong>{{ course.name }}</strong> - {{ course.institution }} ({{
              course.year
            }})<br />
          <p class="bg-white">
              Experienced Full Stack Developer with a passion for creating
              efficient and scalable web applications. Proven track record in
              delivering high-quality software solutions from concept to
              deployment.
            </p>
            <a class="art-deco-link pb-nn" :href="courses?.link" target="_blank"
              >
<i class="fa-solid fa-award"></i>              Ver certificado</a
            >
                      <a class="edit-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-regular fa-pen-to-square"></i>
            </a
          >
          <a class="delete-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-regular fa-trash-can"></i>
            </a
          >
          </div>
      </div>

      <div class="education-container" id="portafolio">
        <h3>Portafolio</h3>
          <div v-for="(project, index) in portfolio" :key="index"  class="item-course">
                      <img
              src="https://yt3.googleusercontent.com/rwU607PYF9jK9QL2I85SdfCLVZJGGsxWukuF_LxD0PepnqEIrFVg3W85FOVPDmWdMN1SxyJ7Xi8=s900-c-k-c0x00ffffff-no-rj"
              alt="Icon"
              class="list-icon"
            />
            <strong>{{ project.project }}</strong>
                      <p class="bg-white">
              {{ project.description }} ({{ project.year }})</p>
                            <a class="art-deco-link" :href="project.link" target="_blank"
                >              <i class="fa-solid fa-link"></i>
 Ver proyecto</a
              >
            <a class="delete-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-brands fa-github"></i>
            </a
          >
                <a class="edit-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-regular fa-pen-to-square"></i>
            </a
          >

          <a class="delete-link pb-nn" :href="edu?.link" target="_blank"
            >
              <i class="fa-regular fa-trash-can"></i>
            </a
          >
          </div>
      </div>
    </div>
  </div>

</template>

<style scoped lang="less">

.icono {
  background-color: #2f4a60;
  padding: 5px 15px;
}

.icono i{
  width: 30px;
  height: 30px;
}

.iconos {
  display: flex;
  flex-direction: column; /* Alinea los elementos verticalmente */
  justify-content: center;
  align-items: flex-end; /* Alinea los elementos hacia la derecha */
  position: fixed;
  top: 50%;
  transform: translateY(-50%);
  right: 0;
  z-index: 9999;
  font-size: 25px;
  color: white;
}

.iconos span:hover{
  color: white;
  cursor: pointer;
}

.icono {
  /* Estilos para cada icono, si es necesario */
}

.pb-nn {
  margin-bottom: 90px;
}
.icon-edit{
  padding-left: 5px;
}
.icon-remove{
  padding-left: 5px;
}
.icon-a {
  font-size: 25px;
  padding: 5px;
}
.text-center {
  text-align: center;
}
.education-container {
  padding: 5px 25px;
  padding-bottom: 30px;
  margin: 0px 10px;
  border-radius: 8px;
  color: #2f4a60;
}
.profile-container {
  padding: 5px 25px;
  margin: 0px 10px;

}
.each-item{
    //background-color: white;
      display: inline;
}
.no-bullets {
  list-style: square; /* Puedes cambiar a 'circle' o 'square' según tu preferencia */
  list-style-size: 200px; /* Ajusta el tamaño según tus necesidades */
  list-style-position: outside;

}

li::marker 
{
    font-size: 2em;
    color: #03bb7f;
    
}

/* Agrega un poco de margen inferior para separar los elementos de la lista */
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
  margin-bottom: 10px;
}

.item-course{
  padding: 25px 0px 0px 0px;
  flex-direction: column;
    justify-content: space-between;
}

.bg-white{
  //background-color: white;
  padding: 0px 0px;
      margin-top: 10px;
}

.login-button{
  background-color: #03bb7f;
  color: white;
}

.login-button:hover{
text-shadow: -2px 2px 0px rgba(47,74,96,1);
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
  text-align: center;
    font-size: 35px;
    color: #2f4a60;
}
.social-icon{
      padding: 0px 5px;
}

.banner-item{
  padding: 5px 0px;
  //text-transform: uppercase;
  cursor: pointer;
      color: #2f4a60;
        font-weight: 900;
  text-align: left;
}

h3{
  background-color: #2f4a60; /* Cambia el color de fondo según tus preferencias */
      display: inline;
      color: white;
      padding: 6px 10px;
      cursor: pointer;
}

.menu-container div{
  margin-top: 6px;
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

    .banner-container{
    margin: 0px 30px;
    display: none;
  }
  .menu-container{
    text-align: center;
    display: none;
  }

  .divider {
    display: none; /* Oculta los divisores en pantallas más pequeñas */
  }
}

@media screen and (max-width: 480px) {
  .iconos{
    font-size: 20px;
    padding: 8px;
    color: white;
    background-color: #2f4a60;
    margin-right: 0px;
  }
  
  .education-container{
    padding: 0px;
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
  color: #2f4a60; /* Color del texto y del borde */
  padding: 5px 10px; /* Ajusta el relleno según sea necesario */
  border: 1px solid #2f4a60; /* Añade el borde al botón */
  transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
}

.art-deco-link:hover {
  background-color: #03bb7f; /* Cambia el color de fondo en el hover */
    border: 1px solid #2f4a60; /* Añade el borde al botón */
  color: #ffffff; /* Cambia el color del texto en el hover */
}

.delete-link {
  text-decoration: none;
  color: #2f4a60; /* Color del texto y del borde */
  padding: 5px 10px; /* Ajusta el relleno según sea necesario */
  border: 1px solid #2f4a60; /* Añade el borde al botón */
  transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
    margin-left: 5px;
}

.delete-link:hover {
  background-color: #03bb7f; /* Cambia el color de fondo en el hover */
    border: 1px solid #2f4a60; /* Añade el borde al botón */
  color: #ffffff; /* Cambia el color del texto en el hover */
}

.edit-link {
  text-decoration: none;
  color: #2f4a60; /* Color del texto y del borde */
  padding: 5px 10px; /* Ajusta el relleno según sea necesario */
  border: 1px solid #2f4a60; /* Añade el borde al botón */
  transition: background-color 0.3s ease-in-out, color 0.3s ease-in-out;
  margin-left: 5px;
}

.edit:hover {
  background-color: #03bb7f; /* Cambia el color de fondo en el hover */
    border: 1px solid #2f4a60; /* Añade el borde al botón */
  color: #ffffff; /* Cambia el color del texto en el hover */
}
</style>
