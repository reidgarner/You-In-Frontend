<template>
  <app-navigation></app-navigation>
</template>

<script>
import { StackNavigator } from "vue-native-router";
import { DrawerNavigator } from "vue-native-router";
import MainScreen from "./Main";
import LoginScreen from "./Login";
import SignupScreen from "./Signup";
import GuestSUScreen from "./GuestSU";
import SPSignUpScreen from "./SPSignUp";
import GuestLoginScreen from "./GuestLogin";
import SPLoginScreen from "./SPLogin";
import SubscribersScreen from "./Subscribers";
import YourPeopleScreen from "./YourPeople";
import UserScreen from "./User";
import AccountScreen from "./Account";

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
    SPSignUp: SPSignUpScreen,
    GuestLogin: GuestLoginScreen,
    SPLogin: SPLoginScreen,
    Subscribers: SubscribersScreen,
    YourPeople: YourPeopleScreen
  },
  {
    initialRouteName: 'Main',
  }
);
export default {
    components: { AppNavigation }
}
</script>