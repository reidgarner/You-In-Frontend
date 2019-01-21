<template>
  <app-navigation></app-navigation>
</template>

<script>
import { StackNavigator } from "vue-native-router";
import MainScreen from "./Main";
import LoginScreen from "./Login";
import SignupScreen from "./Signup";
import GuestSUScreen from "./GuestSU";

const AppNavigation = StackNavigator(
  {
    Main: MainScreen,
    Login: LoginScreen,
    Signup: SignupScreen,
    GuestSU: GuestSUScreen
  },
  {
    initialRouteName: 'Main',
  }
);
export default {
    components: { AppNavigation }
}
</script>