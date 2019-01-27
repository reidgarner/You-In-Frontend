<template>
    <view class="container">
        <text class="title">User</text>
        <view class="username-container" v-for="(bartender, index) in bartenders" :key="index">
            <text class="username" >{{ bartender.name }}</text>
            <text class="workplace" >{{ bartender.workplace }}</text>
            <image 
            :style="{width: 300, height: 300, borderRadius: 20}"
            :source="{uri: bartender.qr}"
            />
        </view>
    </view>
</template>

<script>
export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            bartenders: [
                { name: "Reid Garner", workplace: "@Five Bar", qr: "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/QR_Code.png"}
            ]
        }
    },
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
    font-family: Helvetica;
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