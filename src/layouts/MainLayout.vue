<template>
  <q-layout view="lHh Lpr lFf">
    <q-header>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          class="md-and-up-hide"
        />

        <q-toolbar-title style="font-family: 'Montserrat', sans-serif; font-weight: bold;">
          Territorio de Vida
        </q-toolbar-title>

        <div class="xs-hide sm-hide" style="font-family: 'Montserrat', sans-serif; font-weight: bold;">
          <q-btn flat dense no-caps label="Inicio" @click="goToSection('heroSection')" class="q-mx-sm"/>
          <q-btn flat dense no-caps label="Programa de gobierno" @click="goToSection('features')" class="q-mx-sm"/>
          <q-btn flat dense no-caps label="Candidato" @click="goToSection('about')" class="q-mx-sm"/>
        </div>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="leftDrawerOpen"
      bordered
    >
      <q-list>
        <q-item-label
          header
        >
          Menú
        </q-item-label>
        <q-item clickable @click="navigate('heroSection')">
          <q-item-section>
            <q-item-label>Inicio</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable @click="navigate('features')">
          <q-item-section>
            <q-item-label>Programa de Gobierno</q-item-label>
          </q-item-section>
        </q-item>
        <q-item clickable @click="navigate('about')">
          <q-item-section>
            <q-item-label>Candidato</q-item-label>
          </q-item-section>
        </q-item>
        
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view/>
      <q-toolbar class="flex flex-center text-white" style="border-top: 2px solid #0cbcbc; background-color: #263238">
        <div class="q-pa-md q-gutter-sm">
          <q-btn round type="a" href="https://www.instagram.com/elmedicojuanignacio/" class="bg-primary text-white"
                 icon="fab fa-instagram" target="_blank"/>
          <q-btn round type="a" href="https://twitter.com/elmedicojuanign" class="bg-primary text-white" icon="fab fa-twitter" target="_blank"/>
          <q-btn round type="a" href="https://www.facebook.com/juanignacio.torresgomez" class="bg-primary text-white" icon="fab fa-facebook"  target="_blank"/>
        </div>
      </q-toolbar>
    </q-page-container>
  </q-layout>
</template>

<script setup>
import {computed, ref} from 'vue'
import {useAuthStore} from "stores/all";
import {goToSection} from "src/support/helpers/scroll";

const $store = useAuthStore()

const leftDrawerOpen = ref(false)

const isAuthenticated = computed(() => $store.isAuthenticated)

const navigate = (section) => {
  leftDrawerOpen.value = false
  setTimeout(() => {
    goToSection(section)
  }, 250)
}

const toggleLeftDrawer = () => leftDrawerOpen.value = !leftDrawerOpen.value
const logout = () => {
  $store.SIGN_OUT()
}
</script>
