<template>
  <App v-if="isAppReady" />
</template>

<script>
import App from "./src";

import React from "react";
import { AppLoading } from "expo";
import { Container, Text } from "native-base";
import * as Font from "expo-font";
import { Ionicons } from "@expo/vector-icons";

export default {
  components: {
    App
  },
  data() {
    return {
      isAppReady: false
    };
  },
  async created() {
    await Font.loadAsync({
      Roboto: require("native-base/Fonts/Roboto.ttf"),
      Roboto_medium: require("native-base/Fonts/Roboto_medium.ttf"),
      ...Ionicons.font
    });
    this.isAppReady = true;
  }
};
</script>
