<script>
import buyComicsDigitalComics from "../assets/img/buy-comics-digital-comics.png";
import buyComicsMerchandise from "../assets/img/buy-comics-merchandise.png";
import buyComicsShopLocator from "../assets/img/buy-comics-shop-locator.png";
import buyComicsSubscriptions from "../assets/img/buy-comics-subscriptions.png";
import buyDcPowerVisa from "../assets/img/buy-dc-power-visa.svg";

export default {
    data() {
        return {
            images: [
                buyComicsDigitalComics,
                buyComicsMerchandise,
                buyComicsShopLocator,
                buyComicsSubscriptions,
                buyDcPowerVisa
            ]
        };
    },
    methods: {
        getAltText(image) {
            const imageName = image.replace('.png', '').replace('.svg', '');
            const altText = imageName.startsWith('buy-') ? imageName.substring(4) : imageName;
            return altText.toUpperCase();
        },
        getImageURL(image) {
            return '#';
        },
        getLinkText(image) {
            const imageName = image.replace('.png', '').replace('.svg', '');
            const linkText = imageName
                .split('-')
                .slice(2)
                .map(word => word.charAt(0).toUpperCase() + word.slice(1))
                .join(' ');
            return linkText;
        }

    },
    computed: {
        imagePath() {
            return (image) => {
                if (image.endsWith('.svg')) {
                    return image.replace('.svg', '.png');
                }
                return image;
            };
        }
    }
};
</script>

<template>
    <main>
        <!-- Section Content -->
        <section id="content">
            <h2><i class="fa-solid fa-arrow-right"></i> Content goes here <i class="fa-solid fa-arrow-left"></i></h2>
        </section>
        <!-- Section Info Shop -->
        <section id="info-shop">
            <ul>
                <li v-for="(image, index) in images" :key="index">
                    <figure>
                        <img :src="image" :alt="getAltText(image)">
                    </figure>
                    <a :href="getImageURL(image)">{{ getLinkText(image) }}</a>
                </li>
            </ul>
        </section>
        <!-- Section Links -->
        <section id="links">
            <div class="container-links">
                <!-- BG Logo DC -->
                <div class="logo">
                    <img src="../assets/img/dc-logo-bg.png" alt="Logo">
                </div>
                <div class="col">
                    <div class="col">
                        <!-- Links DC Comics -->
                        <h2>DC COMICS</h2>
                        <ul>
                            <li><a href="#">Characters</a></li>
                            <li><a href="#">Comics</a></li>
                            <li><a href="#">Movies</a></li>
                            <li><a href="#">TV</a></li>
                            <li><a href="#">Games</a></li>
                            <li><a href="#">Videos</a></li>
                            <li><a href="#">News</a></li>
                        </ul>
                    </div>
                    <div class="col">
                        <!-- Links Shop -->
                        <h2>SHOP</h2>
                        <ul>
                            <li><a href="#">Shop DC</a></li>
                            <li><a href="#">Shop DC Collection</a></li>
                        </ul>
                    </div>
                </div>
                <div class="col">
                    <!-- Links DC -->
                    <h2>DC</h2>
                    <ul>
                        <li><a href="#">Terms Of Use</a></li>
                        <li><a href="#">Privacy Policy (New)</a></li>
                        <li><a href="#">Ad Choices</a></li>
                        <li><a href="#">Advertising</a></li>
                        <li><a href="#">Jobs</a></li>
                        <li><a href="#">Subscriptions</a></li>
                        <li><a href="#">Talent Workshops</a></li>
                        <li><a href="#">CPSC Certificates</a></li>
                        <li><a href="#">Ratings</a></li>
                        <li><a href="#">Shop Help</a></li>
                        <li><a href="#">Contact Us</a></li>
                    </ul>
                </div>
                <div class="col">
                    <!-- Links DC Sites -->
                    <h2>SITES</h2>
                    <ul>
                        <li><a href="#">DC</a></li>
                        <li><a href="#">MAD Magazine</a></li>
                        <li><a href="#">DC Kids</a></li>
                        <li><a href="#">DC Universe</a></li>
                        <li><a href="#">DC Power Visa</a></li>
                    </ul>
                </div>
            </div>
        </section>

    </main>
</template>

<style>
/* Section Content */
#content {
    background-color: #1c1c1c;
    color: white;
}


/* Section Info Shop */
#info-shop {
    background-color: #0182f9;
    display: flex;
    justify-content: space-around;
    align-items: center;
}

#info-shop a {
    color: white;
}

#info-shop li {
    display: flex;
    align-items: center;
    margin-left: 100px;
}

#info-shop img {
    max-width: 80px;
    padding: 20px 10px;
}

h2 {
    font-size: 30px;
    padding: 50px;
    margin-left: 200px;
}

/* Section Links */
#links {
    display: flex;
    background-image: url(../assets/img/footer-bg.jpg);
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}

.container-links {
    display: flex;
    margin-left: 250px;
    margin-top: 30px;
}

#links .col {
    display: flex;
    flex-direction: column;
    margin-right: 20px;
    padding: 0 10px;
}

#links h2 {
    font-size: 20px;
    margin-bottom: 10px;
    padding: 0px;
    margin-left: 10px;
    color: white;
}

#links ul {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
    margin-bottom: 10px;
    color: white;
    font-size: 14px;
}

#links li {
    padding: 2px 10px;
}

#links a {
    color: grey;
}

.logo {
    position: absolute;
    bottom: 20px;
    right: 20px;
}

.logo img {
    width: 500px;
}
</style>