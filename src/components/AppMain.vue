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
                        <img :src="imagePath(image)" :alt="getAltText(image)">
                    </figure>
                    <a :href="getImageURL(image)">{{ getLinkText(image) }}</a>
                </li>
            </ul>
        </section>
        <!-- Section Links -->
        <section id="links">
            <div class="col">
                <!-- Links DC Comics -->
                <ul>
                    <h2>DC COMICS</h2>
                    <li>Characters</li>
                    <li>Comics</li>
                    <li>Movies</li>
                    <li>TV</li>
                    <li>Games</li>
                    <li>Videos</li>
                    <li>News</li>
                </ul>

                <!-- Links Shop -->
                <ul>
                    <h2>SHOP</h2>
                    <li>Shop DC</li>
                    <li>Shop DC Collection</li>
                </ul>
            </div>
            <div class="col">
                <!-- Links DC -->
                <ul>
                    <h2>DC</h2>
                    <li>Terms Of Use</li>
                    <li>Privacy Policy (New)</li>
                    <li>Ad Choiches</li>
                    <li>Advertasing</li>
                    <li>Jobs</li>
                    <li>Subscriptions</li>
                    <li>Talent Workshops</li>
                    <li>CPSC Certificates</li>
                    <li>Ratings</li>
                    <li>Shop Help</li>
                    <li>Contact Us</li>
                </ul>
            </div>
            <div class="col">
                <!-- Links DC Sites -->
                <ul>
                    <h2>SITES</h2>
                    <li>DC</li>
                    <li>MAD Magazine</li>
                    <li>DC Kids</li>
                    <li>DC Universe</li>
                    <li>DC Power Visa</li>
                </ul>
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
    justify-content: center;
    align-items: center;
}

#info-shop a {
    color: white;
}

#info-shop li {
    display: flex;
    align-items: center;
    margin-left: 20px;
}

#info-shop img {
    max-width: 70px;
    padding: 30px 10px;
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
}


#links ul {
    display: flex;
    flex-direction: column;
    margin-left: 200px;
    margin-top: 20px;
    color: white;
}
</style>