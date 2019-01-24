<template>
    <view class="container">
        <text class="title">You In?</text>
        <text class="As-a">Bar Guest</text>
        <view class="input-container">
            <text-input class="input" auto-capitalize="none" v-model="first_name" placeholder="First Name"/>
            <text-input class="input" auto-capitalize="none" v-model="last_name" placeholder="Last Name"/>
            <text-input class="input" auto-capitalize="none" v-model="email" placeholder="Email"/>
            <text-input class="input" auto-capitalize="none" v-model="password" placeholder="Password"/>
        </view>
        <touchable-opacity class="button" :on-press="handleYourBartenders">
            <text class="button-text">Signup</text>
        </touchable-opacity>
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
            first_name: '',
            last_name: '',
            email: '',
            password: ''
    }
    },

    methods: {
        handleYourBartenders() {
            this.navigation.navigate("YourBartenders");
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

.button {
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