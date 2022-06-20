<template>
  <q-page class="row items-center justify-center" :padding="true">
    <div class="col-12 width-960 text-center">
      <q-img :src="
        $q.dark.isActive ? '/images/frog-night.png' : '/images/frog-day.png'
      " fit="scale-down" alt="Frog app" />
    </div>
    <div class="col-12 text-center" id="getfrog">
      <a href="https://flathub.org/apps/details/com.github.tenderowl.frog">
        <img width="240" alt="Download on Flathub" src="https://flathub.org/assets/badges/flathub-badge-en.png" />
      </a>
    </div>

    <div class="col-12 width-960">
      <h2 class="text-center">Extract Text From Anywhere</h2>
      <p class="text-body1">
        Quickly extract text from any source such as images, websites, even
        video - everywhere you can grab an image shot. Even if it is encoded in
        a QR code!
      </p>

      <q-separator class="q-mt-xl" />
      <h3 class="text-center" id="features">Features</h3>

      <div class="row">
        <div class="col-12 col-sm-8 q-pa-md">
          <h5>Extract QR Code and barcode</h5>
          <p>Capture, extract and convert any QR codes or barcodes in a second.</p>
        </div>
        <div class="col-12 col-sm-4 q-pa-md">
          <q-img src="/images/qrcode.jpg" fit="scale-down" width="280px" class="rounded-borders" />
        </div>
      </div>

      <div class="row">
        <div class="col-12 col-sm-4 q-pa-md">
          <q-img src="/images/drag-n-drop.jpg" fit="scale-down" width="280px" class="rounded-borders" />
        </div>
        <div class="col-12 col-sm-8 q-pa-md">
          <h5>Drag-n-drop</h5>
          <p>You do not need to make a screenshot of the image. Drag and drop it straight into the Frog window to
            extract the text.</p>
        </div>
      </div>

      <div class="row">
        <div class="col-12 col-sm-8 q-pa-md">
          <h5>Tons of supported languages</h5>
          <p>Frog support a lot of languages, even those which didn't used for today.</p>
        </div>
        <div class="col-12 col-sm-4 q-pa-md">
          <q-img src="/images/languages.jpg" fit="scale-down" width="280px" class="rounded-borders" />
        </div>
      </div>

      <q-separator class="q-mt-xl" />
      <h3 class="text-center" id="privacy">Privacy</h3>
      <div class="row">
        <div class="col-12 col-sm-4 q-pa-md">
          <q-img src="/images/privacy.jpg" fit="scale-down" width="280px" class="rounded-borders" />
        </div>
        <div class="col-12 col-sm-8 q-pa-md">
          <h5>Frog use Portals to respect your privacy</h5>
          <p>We respect your privacy and don't ask you to give to Frog extra permissions.</p>
        </div>
      </div>

      <q-separator class="q-mt-xl" />
      <h3 class="text-center" id="license">Support</h3>
      <div class="row">
        <div class="col-12 text-center">
          <p>
            Frog is made by <a class="text-primary" href="https://tenderowl.com/">TenderOwl</a> and distributed for free. If you like it, please consider to buy me a coffee.
          </p>
          <p>
            <a href="https://www.buymeacoffee.com/tenderowl" target="_blank"><img
                src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee"
                style="height: 60px !important;width: 217px !important;"></a>
          </p>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script lang="ts" setup>
import { useQuasar } from 'quasar';

const $q = useQuasar();
</script>


<style lang="scss" scoped>
.width-960 {
  max-width: 960px;
}
</style>
