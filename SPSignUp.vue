<template>
    <view class="container">
        <text class="title">You In?</text>
        <text class="As-a">Service Provider</text>
        <view class="input-container">
            <text-input class="input" v-model="text" placeholder="Full Name"/>
            <text-input class="input" v-model="text" placeholder="Email"/>
            <text-input class="input" v-model="text" placeholder="Password"/>
        </view>
        <touchable-opacity class="button-2" :on-press="handleSubscribers">
            <text class="button-text">Signup</text>
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
            isLoaded: false,
            text: ''
    }
    },

    async mounted() {
        await Expo.Font.loadAsync({
            'Reenie Beanie': require('./assets/fonts/ReenieBeanie.ttf')
        })
    this.isLoaded = true;
    },

    methods: {
        handleSubscribers() {
            this.navigation.navigate("Subscribers");
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
.title {
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
    font-family: Courier;
}

.Or {
    color: black;
    font-size: 40;
    position: relative; top: 60;
    font-family: Courier;
}

.input-container {
    display: flex;
    justify-content: space-evenly;
    height: 200;
    width: 300;

}

.input {
    height: 50; 
    width: 300; 
    border-radius: 10; 
    border-color: gray; 
    border-width: 1;
}

</style>