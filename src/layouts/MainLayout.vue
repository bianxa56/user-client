<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated class="bg-lime-1">
      <q-toolbar>
<!--        <q-btn-->
<!--          flat-->
<!--          dense-->
<!--          round-->
<!--          style="color: black"-->
<!--          icon="menu"-->
<!--          aria-label="Menu"-->
<!--          @click="toggleLeftDrawer"-->
<!--        />-->

        <q-toolbar-title class="text-center" style="color: black">
          <q-avatar>
            <img src="~assets/chateau/logo.jpg">
          </q-avatar>
          Chateau D Alta
        </q-toolbar-title>

        <!--        <div>Quasar v{{ $q.version }}</div>-->
      </q-toolbar>
    </q-header>

<!--    <q-drawer class="bg-lime-1"-->
<!--              v-model="leftDrawerOpen"-->
<!--              show-if-above-->
<!--              bordered-->
<!--    >-->
<!--      <q-list>-->

<!--        <q-item-label header>-->
<!--          Essential Links-->
<!--        </q-item-label>-->

<!--        <EssentialLink-->
<!--          v-for="link in essentialLinks"-->
<!--          :key="link.title"-->
<!--          v-bind="link"-->
<!--        />-->
<!--      </q-list>-->

<!--    </q-drawer>-->

    <q-page-container>
      <q-card>

      </q-card>
      <router-view />
    </q-page-container>
  </q-layout>

</template>

<script>
import { defineComponent, ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

const linksList = [
  {
    title: 'Dashboard',
    caption: '',
    icon: 'dashboard',
    link: '/dashboardPage'
  },
  {
    title: 'About Us',
    caption: '',
    icon: 'info',
    link: '/aboutUs'
  },
]

export default defineComponent({
  name: 'MainLayout',

  components: {
    // EssentialLink
  },

  setup () {
    const leftDrawerOpen = ref(false)

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer () {
        leftDrawerOpen.value = !leftDrawerOpen.value
      }
    }
  }
})
</script>
