<template>
    <app-navigation></app-navigation>
</template>
<script>
import Second from "./Second";
import Other from "./Other";
import { StackNavigator } from "vue-native-router";

const AppNavigation = StackNavigator(
  {
    Second: Second,
    Other: Other
  },
  {
    initialRouteName: "Second",
    headerMode: "none"
  }
);

export default {
  components: { AppNavigation }
};
</script>