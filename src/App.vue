<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated class="bg-primary text-white" height-hint="98">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer" />
        <q-toolbar-title>
          <q-avatar>
            <img src="https://i.pinimg.com/564x/27/a7/43/27a743d54b2dd5a52df2e0addbfd433f.jpg">
          </q-avatar>
          Title
        </q-toolbar-title>
        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
      </q-toolbar>
      <q-tabs align="left">
        <q-route-tab to="/page1" label="Page One" />
        <q-route-tab to="/page2" label="Page Two" />
        <q-route-tab to="/page3" label="Page Three" />
      </q-tabs>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" bordered>
      <!-- drawer content -->
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" bordered>
      <div class="q-pa-md row items-start q-gutter-md">
        <q-card class="my-card">
          <img src="https://i.pinimg.com/564x/4e/a3/2b/4ea32bde3d6d10178cfab2186713402c.jpg" />
          <q-card-section>
            <div class="text-h6">Rp 1.000.000</div>
            <div class="text-subtitle2">Sepatu Jordan</div>
          </q-card-section>
          <q-card-section class="q-pt-none">
            {{ lorem }}
          </q-card-section>
        </q-card>
        <q-card class="my-card">
          <q-img src="https://i.pinimg.com/564x/78/a2/a6/78a2a6348ca885c34c04465c49502d2e.jpg">
            <div class="absolute-bottom text-subtitle2 text-center">
             
            </div>
          </q-img>
        </q-card>
        <q-card class="my-card">
          <q-img src="https://i.pinimg.com/564x/c5/34/86/c53486dbc4e80bfd1aa08bbb9cadf85b.jpg">
            <div class="absolute-bottom text-h6">
              
            </div>
          </q-img>
          <q-card-section>
            {{ lorem }}
          </q-card-section>
        </q-card>
        <q-card class="my-card">
          <q-img src="https://i.pinimg.com/564x/71/25/52/7125523de81a5a3462f408648c1ba9d5.jpg">
            <div class="text-subtitle2 absolute-top text-center">
              
            </div>
          </q-img>
        </q-card>
        <q-card class="my-card">
          <q-img src="https://i.pinimg.com/564x/01/c6/59/01c65952e079c97d91e6d07f8d37ea7f.jpg">
            <div class="text-h5 absolute-bottom text-right">
              
            </div>
          </q-img>
        </q-card>
        <q-card class="my-card">
          <q-item>
            <q-item-section avatar>
              <q-avatar>
                <img src="https://i.pinimg.com/564x/97/85/2a/97852a65eac68c429c7577b0a66b2411.jpg">
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label></q-item-label>
              <q-item-label caption></q-item-label>
            </q-item-section>
          </q-item>
          <img src="https://i.pinimg.com/564x/51/d5/c2/51d5c29b5adb7cc2d3e8298209aaa254.jpg" />
        </q-card>
        <q-card class="my-card">
          <q-img src="https://i.pinimg.com/564x/32/85/4b/32854b302bbe622478bdcd8fe4c504ee.jpg">
            <div class="absolute-bottom">
              <div class="text-h6"></div>
              <div class="text-subtitle2"></div>
            </div>
          </q-img>
          <q-card-actions>
            <q-btn flat></q-btn>
            <q-btn flat></q-btn>
          </q-card-actions>
        </q-card>
      </div>
    </q-drawer>

    <q-page-container>
      <div class="q-pa-md">
        <q-carousel
          animated
          v-model="slide"
          arrows
          navigation
          infinite
        >
          <q-carousel-slide :name="1" img-src="https://i.pinimg.com/564x/2a/0f/fa/2a0ffa934ad1d452e6f547ef0f8443df.jpg" />
          <q-carousel-slide :name="2" img-src="https://i.pinimg.com/564x/14/ed/35/14ed35c83abd0a84bf6cf16ce064a6fd.jpg" />
          <q-carousel-slide :name="3" img-src="https://i.pinimg.com/564x/41/cd/ce/41cdce65ae2598b1452e22870e242ffa.jpg" />
          <q-carousel-slide :name="4" img-src="https://i.pinimg.com/564x/d3/3d/7b/d33d7b576aa9433fb3b9feba7d815961.jpg" />
        </q-carousel>
      </div>
      <router-view />
    </q-page-container>

    <q-footer elevated class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          <div></div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)
    const slide = ref(1)
    const lorem = ref()

    const toggleLeftDrawer = () => {
      leftDrawerOpen.value = !leftDrawerOpen.value
    }

    const toggleRightDrawer = () => {
      rightDrawerOpen.value = !rightDrawerOpen.value
    }

    return {
      leftDrawerOpen,
      rightDrawerOpen,
      slide,
      lorem,
      toggleLeftDrawer,
      toggleRightDrawer
    }
  }
}
</script>

<style>
.my-card {
  width: 300px;
}
</style>
