<template>
  <app-navigation></app-navigation>
</template>

<script>
import { StackNavigator } from "vue-native-router";
import { DrawerNavigator } from "vue-native-router";
import MainScreen from "./Vue/Main";
import LoginScreen from "./Vue/Login";
import SignupScreen from "./Vue/Signup";
import GuestSUScreen from "./Vue/GuestSU";
import BTSignUpScreen from "./Vue/BTSignUp";
import GuestLoginScreen from "./Vue/GuestLogin";
import BTLoginScreen from "./Vue/BTLogin";
import YourGuestsScreen from "./Vue/YourGuests";
import YourBartendersScreen from "./Vue/YourBartenders";
import UserScreen from "./Vue/User";
import AccountScreen from "./Vue/Account";

const Drawer = DrawerNavigator(
  {
    Main: MainScreen,
    User: UserScreen,
    Account: AccountScreen,
    Signout: MainScreen
  },
  {
    initialRouteName: "Main",
  }
);
const AppNavigation = StackNavigator(
  {
    Drawer: Drawer,
    Main: MainScreen,
    Login: LoginScreen,
    Signup: SignupScreen,
    GuestSU: GuestSUScreen,
    BTSignUp: BTSignUpScreen,
    GuestLogin: GuestLoginScreen,
    BTLogin: BTLoginScreen,
    YourGuests: YourGuestsScreen,
    YourBartenders: YourBartendersScreen
  },
  {
    initialRouteName: 'Drawer',
  }
);
export default {
    components: { AppNavigation }
}
</script>