<template>
  <app-navigator></app-navigator>
</template>

<script>
import {
  createAppContainer,
  createMaterialTopTabNavigator,
  createStackNavigator
} from "vue-native-router";

import HomeScreen from "./screens/Home.vue";
import CameraScreen from "./screens/Camera.vue";
import WebServiceScreen from "./screens/WebService.vue";
import DatabaseScreen from "./screens/Database.vue";

const Tabs = createMaterialTopTabNavigator({
  AlmacenamientoDatos: DatabaseScreen
});

const StackNavigator = createStackNavigator(
  {
    Tabs,
    Camara: CameraScreen
  },
  {
    defaultNavigationOptions: {
      gestureEnabled: false,
      title: "EA-NR - Almacenamiento de Datos",
      headerTitleStyle: {
        textAlign: "center",
        alignSelf: "center",
        color: "white"
      },
      headerStyle: {
        backgroundColor: "#088A85"
      }
    }
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator }
};
</script>
