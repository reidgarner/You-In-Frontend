<template>
    <view class="container">
        <image-background :source="beerBackdrop" class="imageContainer">
            <view class="your-guests-container">
                <image :source="YourGuest1" class="YourGuest1"></image>
                <image :source="YourGuest2" class="YourGuest2"></image>
            </view>
            <scroll-view :style="{width: '100%'}">
                <view class="guest-list" v-for="(guest, index) in guests" :key="index">
                    <touchable-opacity class="flex-container" :on-press="() => handleListTap(guest)">
                        <image 
                        :style="{width: 50, height: 50, borderRadius: 25, marginRight: 8}"
                        :source="{uri: guest.image}"
                        />
                        <text class="guest-name">{{ guest.name }}</text>
                    </touchable-opacity>
                </view>
            </scroll-view>
        </image-background>
    </view>
</template>

<script>
import beerBackdrop from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/beer_3_background.png";
import YourGuest1 from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/YourGuests_Black.png";
import YourGuest2 from "/Users/reidgarner/Galv-Projects/CAPSTONE/You-In-Frontend/assets/YourGuests_Tan.png";

export default {
    props: {
        navigation: {
            type: Object
        }
    },

    data() {
        return {
            guests: [
                { name: "Andrew Pedersen", image: "https://media.licdn.com/dms/image/C4E03AQEpxR0WN9GdcQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=oiOQvx3RNjfSSIDt8WZPY2KxHzdU5mZt77ru6btBE0o"},
                { name: "Josh Scala", image: "https://media.licdn.com/dms/image/C4E03AQGYJwFr3fgYMQ/profile-displayphoto-shrink_800_800/0?e=1554336000&v=beta&t=zC5L3DcvS8M_75yAe4e2yRZytRzIosb_8ClErWOMWWc"},
                { name: "Meredith Fontana", image: "https://media.licdn.com/dms/image/C4E03AQFa0C4W1juD4Q/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=qodE-DNhf-5dJF_gLPC-fWtRbQdM0cL8wkhPR3cHCNs"},
                { name: "Jimmy Liang", image: "https://media.licdn.com/dms/image/C5103AQFEZJ2HnuAdGA/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=5A-oN3LrBEVnCYQ44Kv1bvm5wUlhZLNeS6IlBYPOpBw"},
                { name: "DeBronis Warren", image: "https://media.licdn.com/dms/image/C5603AQHN3WwoEuuaRQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=LYpJXaNVP5TN__Ii0uX74mMqHn5Rjb0vF74OXleSA04"},
                { name: "Gary Anderson", image: "https://media.licdn.com/dms/image/C5603AQE3krKwFpFC8w/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=EJvYlUM86hPbnjffQMyeH3bfCYuZjsH3_XNOTBsd_9g"},
                { name: "Sonja Chacon", image: "https://media.licdn.com/dms/image/C4E03AQGEg5ZaDPyHCQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=ppVLrLBhrOIXl-rF80pw_p3M0ln5h3joNoffQfjcUpo"},
                { name: "Ben Rumsey", image: "https://media.licdn.com/dms/image/C4E03AQHDx8tdiYUO8w/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=bt7H5j4xLR08-wj1wov8y0-VVyUh1friEZ4iRyrHbKo"}
            ],
            beerBackdrop: beerBackdrop,
            YourGuest1: YourGuest1,
            YourGuest2: YourGuest2
        }
    },

    methods: {
        handleListTap(guest) {
            console.log(guest.name) 
        }
    }
}
</script>

<style>
.container {
    background-color: rgb(99, 99, 99);
    align-items: center;
    flex: 1;
}

.imageContainer {
    flex: 1;
    align-items: center;
    justify-content: center;
    width: 100%;
}

.your-guests-container {
    height: 80;
    width: 300;
    display: flex;
    justify-content: center;
    align-items: center;
}

.YourGuest1 {
    height: 143%;
    width: 143%;
    position: relative; top: 85;
}

.YourGuest2 {
    height: 148%;
    width: 145%;
    position: relative; bottom: 30;
}

.guest-list {
    padding: 15;
    position: relative; bottom: 5;
}

.flex-container {
    flex-direction: row;
    align-items: center;
}

.guest-name {
    color: whitesmoke;
    font-size: 30;
}
</style>