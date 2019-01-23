<template>
    <view class="container">
        <text class="title">Your People</text>
        <!-- <view :style="{borderTopWidth: 1, borderTopColor: 'gray', width: '100%'}"></view> -->
        <scroll-view :style="{width: '100%'}">
            <view class="border" v-for="(subscriber, index) in subscribers" :key="index">
                <touchable-opacity class="flex-container" :on-press="() => handleListTap(subscriber)">
                    <image 
                    :style="{width: 40, height: 40, borderRadius: 20, marginRight: 8}"
                    :source="{uri: subscriber.image}"
                    />
                    <text>{{ subscriber.name }}</text>
                    <text class="IO">{{ subscriber.IO }}</text>
                </touchable-opacity>
            </view>
        </scroll-view>
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
            subscribers: [
                { name: "Andrew Pederson", IO: "OUT", image: "https://media.licdn.com/dms/image/C4E03AQEpxR0WN9GdcQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=oiOQvx3RNjfSSIDt8WZPY2KxHzdU5mZt77ru6btBE0o"},
                { name: "Josh Scala", IO: "OUT", image: "https://media.licdn.com/dms/image/C4E03AQF3bGM_mVBJ7A/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=_Ok9fTOd6ItBeimZIOIMxa4Hn75xrkiwgQkOnX4-Rqo"},
                { name: "Meredith Fontana", IO: "OUT", image: "https://media.licdn.com/dms/image/C4E03AQFa0C4W1juD4Q/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=qodE-DNhf-5dJF_gLPC-fWtRbQdM0cL8wkhPR3cHCNs"},
                { name: "Jimmy Liang", IO: "OUT", image: "https://media.licdn.com/dms/image/C5103AQFEZJ2HnuAdGA/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=5A-oN3LrBEVnCYQ44Kv1bvm5wUlhZLNeS6IlBYPOpBw"},
                { name: "DeBronis Warren", IO: "OUT", image: "https://media.licdn.com/dms/image/C5603AQHN3WwoEuuaRQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=LYpJXaNVP5TN__Ii0uX74mMqHn5Rjb0vF74OXleSA04"},
                { name: "Gary Anderson", IO: "OUT", image: "https://media.licdn.com/dms/image/C5603AQE3krKwFpFC8w/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=EJvYlUM86hPbnjffQMyeH3bfCYuZjsH3_XNOTBsd_9g"},
                { name: "Sonja Chacon", IO: "OUT", image: "https://media.licdn.com/dms/image/C4E03AQGEg5ZaDPyHCQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=ppVLrLBhrOIXl-rF80pw_p3M0ln5h3joNoffQfjcUpo"},
                { name: "Ben Rumsey", IO: "OUT", image: "https://media.licdn.com/dms/image/C4E03AQHDx8tdiYUO8w/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=bt7H5j4xLR08-wj1wov8y0-VVyUh1friEZ4iRyrHbKo"}
            ]
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
        },
        handleListTap(subscriber) {
            console.log(subscriber.name) 
        }
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
    color: black;
    font-size: 50;
    /* position: relative; bottom: 375; */
    font-family: Courier;
}

.border {
    /* border-bottom-width: 1;
    border-color: gray;
    width: 100%; */
    padding: 15;
}

.flex-container {
    flex-direction: row;
    align-items: center;
}

.IO {
    margin-left: auto;
}

</style>