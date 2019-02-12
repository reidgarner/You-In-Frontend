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
                { name: "Ryan St Germain", image: "https://media.licdn.com/dms/image/C4E03AQGYPPXg1PWXUw/profile-displayphoto-shrink_800_800/0?e=1554336000&v=beta&t=KkQPanB7PD7IGF10_e6lYHhIWOeMNg9PsMA6Y8frmGs"},
                { name: "Josh Scala", image: "https://media.licdn.com/dms/image/C4E03AQGYJwFr3fgYMQ/profile-displayphoto-shrink_800_800/0?e=1554336000&v=beta&t=zC5L3DcvS8M_75yAe4e2yRZytRzIosb_8ClErWOMWWc"},
                { name: "Meredith Fontana", image: "https://media.licdn.com/dms/image/C4E03AQFa0C4W1juD4Q/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=qodE-DNhf-5dJF_gLPC-fWtRbQdM0cL8wkhPR3cHCNs"},
                { name: "Jimmy Liang", image: "https://media.licdn.com/dms/image/C5103AQFEZJ2HnuAdGA/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=5A-oN3LrBEVnCYQ44Kv1bvm5wUlhZLNeS6IlBYPOpBw"},
                { name: "Sonja Chacon", image: "https://scontent-sea1-1.xx.fbcdn.net/v/t1.0-9/19060205_10105214983118923_3700574548883142484_n.jpg?_nc_cat=110&_nc_ht=scontent-sea1-1.xx&oh=fc427d44c7cae92db0ad55dea8b853a6&oe=5CFD4770"},
                { name: "DeBronis Warren", image: "https://media.licdn.com/dms/image/C5603AQHN3WwoEuuaRQ/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=LYpJXaNVP5TN__Ii0uX74mMqHn5Rjb0vF74OXleSA04"},
                { name: "Gary Anderson", image: "https://media.licdn.com/dms/image/C5603AQE3krKwFpFC8w/profile-displayphoto-shrink_800_800/0?e=1553731200&v=beta&t=EJvYlUM86hPbnjffQMyeH3bfCYuZjsH3_XNOTBsd_9g"},
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