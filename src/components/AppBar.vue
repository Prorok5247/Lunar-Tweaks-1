<template>
    <v-app-bar dark color="primary" class="flex-grow-0">
      <v-app-bar-title id="title">Lunar Tweaks</v-app-bar-title>
      <v-spacer></v-spacer>
      <v-btn class="mr-5" @click="openLink('https://discord.gg/XDzgdRSWfn')">
        <v-icon left>mdi-discord</v-icon>
        Discord
      </v-btn>
      <v-btn @click="showCredits = true">
        <v-icon left>mdi-copyright</v-icon>
        Credits
      </v-btn>
      <v-dialog v-model="showCredits" width="500">
        <v-card>
        <v-card-title class="text-h5 primary">
          About
        </v-card-title>
        <v-card-text class="mt-5">
          Lunar Tweaks
          <br>
          Official software of LunarTweaks (LT) Team
          <br><br>
          Designed and coded by 
          <strong>Cy0ze</strong><br><br>
          A big thanks to
          <ul>
            <li><strong>Prorok</strong> for saving me a lot of time for the Hypixel Mods patch</li>
            <li>
              <strong>Aetopia</strong> for coding and maintaining <a @click="openLink('https://github.com/Aetopia/Lunar-Client-Lite-Launcher')">Lunar Client Lite</a>
              <v-icon color="blue" size="20" class="ml-1">mdi-open-in-new</v-icon>
              <br><span class="italic">(We are not affiliated with Lunar Client Lite or Aetopia!)</span>
            </li>
            <li>
              <strong>Specially</strong> for being a super cool person, promoting and trusting me.
              <a @click="openLink('https://www.youtube.com/c/SpeciallyMC')">His YouTube channel</a>
              <v-icon color="blue" size="20" class="ml-1">mdi-open-in-new</v-icon>
            </li>
            <li>
              <strong>Jordan</strong> for canceling us over and over again.
            </li>
          </ul>
          <br>
          <span class="version">LunarTweaks <strong>v{{ softwareVersion }}</strong></span>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn color="primary" text @click="openLink('https://github.com/RichardDorian/Lunar-Tweaks')">
            <v-icon left>mdi-github</v-icon>
            <span>GitHub</span>
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn color="error" text @click="showCredits = false">Close</v-btn>
        </v-card-actions>
      </v-card>
      </v-dialog>
    </v-app-bar>
</template>

<script>
import electron from 'electron';

export default {
  name: 'AppBar',

  data: () => ({
    showCredits: false,
    softwareVersion: electron.remote.app.getVersion()
  }),

  methods: {
    openLink(link) {
      require('electron').shell.openExternal(link);
    }
  },

  mounted () {
    
  } 
};
</script>

<style>
.italic {
  font-style: italic;
}

.v-app-bar-title__content {
  width: 200px !important;
}
</style>