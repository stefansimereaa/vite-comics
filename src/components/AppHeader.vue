<script>
export default {
    data() {
        return {
            data: [
                {
                    text: 'Characters',
                    url: '#',
                    current: false,
                },
                {
                    text: 'Comics',
                    url: '#',
                    current: true,
                },
                {
                    text: 'Movies',
                    url: '#',
                    current: false,
                },
                {
                    text: 'TV',
                    url: '#',
                    current: false,
                },
                {
                    text: 'Games',
                    url: '#',
                    current: false,
                },
                {
                    text: 'Collectibles',
                    url: '#',
                    current: false,
                },
                {
                    text: 'Videos',
                    url: '#',
                    current: false,
                },
                {
                    text: 'Fans',
                    url: '#',
                    current: false,
                },
                {
                    text: 'News',
                    url: '#',
                    current: false,
                },
                {
                    text: 'Shop',
                    url: '#',
                    current: false,
                },
            ],

        }

    },
    methods: {
        handleLinkClick(item) {
            //Modifica nella navbar le a se cliccate
            item.current = true;
            this.data.forEach((i) => {
                if (i !== item) {
                    i.current = false;
                }
            });
        },
    },
}
</script>

<template>
    <header>
        <nav>
            <figure>
                <img src="../assets/img/dc-logo.png" alt="DC Logo">
            </figure>
            <ul>
                <li v-for="(item, index) in data" :key="index">
                    <a :href="item.url" :class="{ 'current': item.current }" @click="handleLinkClick(item)">{{ item.text
                    }}</a>
                </li>
            </ul>
        </nav>
    </header>
</template>

<style lang="scss">
@import '../assets/scss/style.scss';

@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&family=Open+Sans+Condensed:wght@700&display=swap');

/* Header */
header {
    height: 150px;
}

nav {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin-top: 10px
}

a {
    text-decoration: none;
    color: black;
    position: relative;
}

a.current {
    color: blue;
}

a.current::after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -2px;
    width: 100%;
    height: 2px;
    background-color: blue;
}
</style>