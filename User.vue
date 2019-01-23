<template>
    <view class="container">
        <text class="title">User</text>
        <view class="username-container" v-for="(servicer, index) in servicers" :key="index">
            <text class="username" >{{ servicer.name }}</text>
            <text class="workplace" >{{ servicer.workplace }}</text>
            <image 
            :style="{width: 300, height: 300, borderRadius: 20}"
            :source="{uri: servicer.image}"
            />
        </view>
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
            text: '',
            servicers: [
                { name: "Reid Garner", workplace: "@Five Bar", image: "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In/assets/QR_Code.png"}
            ]
    }
    },

    async mounted() {
        await Expo.Font.loadAsync({
            'Reenie Beanie': require('./assets/fonts/ReenieBeanie.ttf')
        })
    this.isLoaded = true;
    }
}
</script>

<style>
.container {
    background-color: white;
    align-items: center;
    flex: 1;
}

.title {
    font-size: 50;
    /* position: relative; bottom: 375; */
    font-family: Courier;
}

.username {
    font-size: 30;
}

.workplace {
    font-size: 20;
}

.username-container {
    align-items: center;
}

</style>