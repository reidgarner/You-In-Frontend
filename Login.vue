<template>
    <view class="container">
        <text class="text-color-primary">You In?</text>
        <text class="As-a">Login as a</text>
        <touchable-opacity class="button-1" :on-press="handleButton">
            <text class="button-text">Guest</text>
        </touchable-opacity>
        <text class="Or">Or a</text>
        <touchable-opacity class="button-2" :on-press="handleButton">
            <text class="button-text">Service</text>
            <text class="button-text">Provider</text>
        </touchable-opacity>
        </view>
</template>

<script>
import { Font } from 'expo';

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            isLoaded: false
    }
    },

    async mounted() {
        await Expo.Font.loadAsync({
            'Reenie Beanie': require('./assets/fonts/ReenieBeanie.ttf')
        })
    this.isLoaded = true;
    },

    methods: {
        handleButton() {
            this.navigation.navigate("Login");
        }
    }
}
</script>

<style>
.container {
    background-color: white;
    align-items: center;
    justify-content: center;
    flex: 1;
}
.text-color-primary {
    color: black;
    font-size: 50;
    position: relative; bottom: 150;
    font-family: Courier;
}

.button-1 {
    background-color: rgb(67, 67, 67);
    width: 250;
    height: 50;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 50;
}

.button-2 {
    background-color: rgb(67, 67, 67);
    width: 250;
    height: 100;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 10;
    position: relative; top: 80;
}

.button-text {
    color: rgb(159, 159, 159);
    font-size: 40;
    font-family: Courier;
}

.As-a {
    color: black;
    font-size: 40;
    position: relative; top: 30;
    font-family: Courier;
}

.Or {
    color: black;
    font-size: 40;
    position: relative; top: 60;
    font-family: Courier;
}
</style>