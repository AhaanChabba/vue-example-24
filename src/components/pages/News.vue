<script>
import NewsItem from "../widgets/NewsItem.vue";
import NewsItemFooter from "../widgets/NewsItemFooter.vue";
import TimeStamp from "../widgets/TimeStamp.vue";
import axios from "axios"
export default {
    data() {
        return {
            featuredArticle: {
                imageUrl: "https://images.performgroup.com/di/library/omnisport/79/d8/6c9b4b26f64a40ea89b7f69ccd088d40.jpg?t=-955230179&w=640",
                title: "Inter boss Simone Inzaghi reveals admiration for Diego Simeone ahead of clash",
                gmtTime: "2024-02-19T20:04:27.000Z",
                source: "FotMob",
                lead: "Simone Inzaghi and Diego Simeone, now boss of Atletico Madrid, helped Lazio win Serie A as players in 2000.",
                sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                pageURL: "https://www.fotmob.com/news/138lzxhk8mmsi1nflku3xemdte-inter-boss-simone-inzaghi-reveals-admiration-diego-simeone-ahead-clash"
            },
            articles: [
                {
                    imageUrl: "https://images.performgroup.com/di/library/omnisport/d0/77/2_75334763.jpg?t=52676590&w=1200&h=630",
                    title: "Cardiff boss Erol Bulut praises influence of Liverpool loanee Nat Phillips",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "FotMob",
                    lead: "Perry Ng's second-half header sealed victory over Bristol City.",
                    sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                    pageURL: "https://www.fotmob.com/news/vcqqwhrji9ft1i2r6scvxgjfy-cardiff-boss-erol-bulut-praises-influence-liverpool-loanee-nat-phillips"
                },
                {
                    imageUrl: "https://images.performgroup.com/di/library/omnisport/ce/85/2_75334546.jpg?t=59876078&w=1200&h=630",
                    title: "Josh Sargent bags late winner as Norwich overcome Sunderland",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "FotMob",
                    lead: "The American has now scored in seven home games in a row.",
                    sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                    pageURL: "https://www.fotmob.com/news/1wjki11r710yw1fgri1q7uyou8-josh-sargent-bags-late-winner-norwich-overcome-sunderland"
                },
                {
                    imageUrl: "https://images.performgroup.com/di/library/omnisport/f2/a3/2_75503404.jpg?t=43674590&w=1200&h=630",
                    title: "Leeds' winning run halted with draw at Huddersfield",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "FotMob",
                    lead: "United had to come back from a goal down.",
                    sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                    pageURL: "https://www.fotmob.com/news/1ki8x2assz6f91coq0frtwf4gy-leeds-winning-run-halted-draw-at-huddersfield"
                },
                {
                    imageUrl: "https://images.performgroup.com/di/library/omnisport/f8/c9/c4cfaba576ab4ec98fb86f1eeffccf8a.jpg?t=56876334&w=1200&h=630",
                    title: "Massimiliano Allegri not underestimating Napoli as Juve look to end barren run",
                    gmtTime: "2024-02-19T20:04:27.000Z",
                    source: "FotMob",
                    lead: "The reigning champions are only ninth, with visitors Juve 17 points better off.",
                    sourceIconUrl: "https://images.fotmob.com/image_resources/news/fotmob.png",
                    pageURL: "https://www.fotmob.com/news/um781xuc7vzl18oi2kp3h6jdi-massimiliano-allegri-not-underestimating-napoli-juve-look-end-barren-run"
                },
            ],
        }
    },
    components: {
        NewsItem,
        TimeStamp, 
        NewsItemFooter
    }
    ,
    methods: {
        fetchData(){
        axios.get("https://fotmob-backend.onrender.com/articles").then(response => {
               this.articles = response.data;
           });
        }
        
        
  
    
   
    }
}
</script>

<template>
    
    <button @click="fetchData">Fetch Data</button>

    <header class="WorldNewsHeader">
        <h1>World News</h1>
    </header>
    <div class="layout">
        <div class="featuredArticle">
            <div class="featuredImage">
                <img :src="featuredArticle.imageUrl" alt="featured article image" />
            </div>
            <div class="featuredArticleText">
                <h3>{{ featuredArticle.title }}</h3>
                <NewsItemFooter :article="featuredArticle" />
            </div>
        </div>
        <div class="articleGrid">
            <NewsItem v-for="article in articles" :newsItem="article" :key="article.title" />
        </div>
    </div>
</template>

<style scoped>
.WorldNewsHeader {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    margin: 0px 30px;
}
.featuredArticle {
    cursor: pointer;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: 1fr;
    padding: 0px 30px;
    position: relative;
}
.featuredImage {
    width: 100%;
    height: 100%;
    max-width: 640px;
}
.featuredImage>img {
    /* needs to also specify child to resize */
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.featuredArticleText {
    display: flex;
    -webkit-box-align: center;
    align-items: center;
    -webkit-box-pack: center;
    justify-content: center;
    background: var(--GlobalColorScheme-Background-background2);
    height: 100%;
    width: 100%;
    flex-direction: column;
    gap: 24px;
    padding: 20px;
}
.articleGrid {
    margin-top: 48px;
    padding: 0px 30px;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 40px 24px;
    -webkit-box-align: start;
    align-items: start;
}
</style>