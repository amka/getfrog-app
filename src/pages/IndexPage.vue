<template>
  <q-page class="column items-center justify-evenly" :padding="true">
    <div class="screenshot">
      <img
        :src="
          $q.dark.isActive
            ? '/src/assets/frog-night.png'
            : '/src/assets/frog-day.png'
        "
        alt="Frog app window"
      />
    </div>
    <div class="flathub download-btn">
      <a href="https://flathub.org/apps/details/com.github.tenderowl.frog">
        <img
          width="240"
          alt="Download on Flathub"
          src="https://flathub.org/assets/badges/flathub-badge-en.png"
        />
      </a>
    </div>

    <div class="width-960">
      <h2 class="text-center">Extract Text From Anywhere</h2>
      <p class="text-body1">
        Quickly extract text from any source such as images, websites, even
        video - everywhere you can grab an image shot. Even if it is encoded in
        a QR code!
      </p>

      <h3 class="text-center">Features</h3>
      <div class="row">
        <img src="~/" alt="" />
        <h5>Extract text with screenshot tool</h5>
      </div>

      <div class="row">
        <img src="~/" alt="" />
        <h5>Extract QR Code and barcode</h5>
      </div>

      <div class="row">
        <h5>Have an image? Use drag-n-drop to process it.</h5>
      </div>

      <div class="row">
        <h5>Extract text from CLI.</h5>
      </div>

      <h3 class="text-center">Privacy</h3>
      <div class="row">
        <h5>Extract text with screenshot tool</h5>
      </div>
    </div>
  </q-page>
</template>

<script lang="ts" setup>
import { useQuasar } from 'quasar';

const $q = useQuasar();
</script>
