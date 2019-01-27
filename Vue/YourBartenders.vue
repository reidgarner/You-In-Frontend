<template>
    <view class="container">
        <text class="title">Your Bartenders</text>
        <scroll-view :style="{width: '100%'}">
            <view class="border" v-for="(bartender, index) in bartenders" :key="index">
                <touchable-opacity class="flex-container" :on-press="() => handleListTap(bartender)">
                    <image 
                    :style="{width: 40, height: 40, borderRadius: 20, marginRight: 8}"
                    :source="{uri: bartender.image}"
                    />
                    <text>{{ bartender.name }}</text>
                    <text class="IO">{{ bartender.IO }}</text>
                </touchable-opacity>
            </view>
        </scroll-view>
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

    methods: {
        handleButton() {
            this.navigation.navigate("Login");
        },
        handleListTap(bartender) {
            console.log(bartender.name) 
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
    font-family: Helvetica;
}

.border {
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