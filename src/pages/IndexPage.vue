<template>
  <q-page style="margin-top: -60px">
    <section class="heroSection bg-primary">
      <div class="heroSection__content container q-mb-xl">
        <img
              style="max-width: fit-content; width: 100%; max-width: 100%;"
              class="responsive" src="src/assets/FinVideoHorizontal.jpg">
      </div>

    </section>
    <section class="features q-py-xl">
      <div class="container">
        <div class="row q-col-gutter-lg q-py-xl">
          <div class="col-12 col-md-12">
            <hover v-slot="{hoverIsActive}">
              <q-card :class="{ 'shadow-6 cursor-pointer': hoverIsActive }">
                <q-card-section class="text-center">
                  <q-avatar size="70px" class="bg-primary text-white" icon="description"></q-avatar>
                  <h5 class="text-h4 q-my-md">Programa de Gobierno</h5>
                  <p class="text-gray text-subtitle1 text-justify">Con el programa de gobierno que pongo a su consideración y que fue construido con la comunidad a través de 20 talleres y la participación de 573 personas, continuaremos con el progreso de estos últimos años y consolidaremos a Girardota como el mejor municipio del norte del Valle de Aburrá, sin perder la idiosincrasia, alegría y cordialidad
que nos caracteriza.</p>
                  <q-btn
                    class="text-white"
                    elevated
                    rounded
                    color="blue"
                    label="Dercargar"
                    icon="attach_file"
                    type="a"
                    href="https://www.juanignacioalcalde.com/PG Territorio de Vida - Juan Ignacio Torres.pdf"
                  />
                </q-card-section>
              </q-card>
            </hover>
          </div>
        </div>
      </div>
    </section>
    <section class="about q-mb-xl q-py-xl">
      <div class="container">
        <div class="row">
          <div class="col-0 col-md-6">
            <img
              :style="($q.screen.md || $q.screen.lg || $q.screen.xl) ? 'width: 500px; max-width: fit-content;' : 'width: 100%; max-width: 100%;'"
              class="responsive q-pa-xl" src="src/assets/Juancho.png">
          </div>
          <div class="col-12 col-md-6 self-center text-right">
            <h2 class="text-h3 text-weight-thin fredoka">Candidato</h2>
            <p class="text-subtitle1 text-justify">
              Soy Juan Ignacio Torres Gómez, un girardotano educado en un hogar amoroso, familiar y religioso, convencido del respeto por el ser humano, el trabajo con honestidad y la
importancia de los lazos familiares como soporte de la sociedad.<br/>
Hoy, como candidato a la alcaldía de nuestro querido municipio, los invito a trabajar por Girardota, para reducir la inequidad y generar oportunidades económicas y sociales sostenibles en el tiempo; me comprometo a enfocar las políticas de gasto social en la mitigación de la desigualdad del ingreso y a romper el ciclo perverso de la pobreza y falta de oportunidades. Necesitamos educar a nuestros niños, niñas y jóvenes para que cuando crezcan contribuyen activamente a la construcción de una sociedad más justa y equitativa. Necesitamos acceder a los servicios de salud no solo para salvar vidas sino para mejorar la calidad de ella. Necesitamos que nuestros adultos mayores cuenten con los recursos necesarios para preservar la dignidad en la
ancianidad.</p>
          </div>
        </div>
      </div>
    </section>
  </q-page>
</template>

<script setup>
import {goToSection} from "src/support/helpers/scroll";
import Hover from "src/modules/common/components/HoverComponent.vue";

const features = [
  {
    icon: "fas fa-check",
    label: "Feature 1"
  },
  {
    icon: "fas fa-check",
    label: "Feature 2"
  },
  {
    icon: "fas fa-check",
    label: "Feature 3"
  }
];
</script>

<style scoped>
.heroSection {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 90vh;
  position: relative;
  overflow: hidden;
}

.waves {
  position: absolute;
  bottom: -8px;
  left: 0;
  right: 0;
}

.heroSection__content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100%;
  z-index: 1;
}

.heroSection__title {
  color: #fff;
  font-weight: bold;
  text-align: center;
}
</style>
