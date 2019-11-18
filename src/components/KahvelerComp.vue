<template>
    <div class="page-content">

        <div class="katalog">
            <section class="baslik kahveler">
                <div class="col-md-offset-1 col-md-6">
                    <h1 class="beyaz">KAHVE ÇEŞİTLERİ</h1>
                    <h2 class="kahve roboto">Kahveler</h2>
                    <div class="back-ekipman"></div>
                    <p class="beyaz roboto">Büyük bir hassasiyetle seçilip özenle kavrulmuş kahve çekirdeklerini kolayca
                        temin edebilmeniz için sitemizde bir araya getirdik. Sipariş ettiğiniz kahvenizi dilerseniz
                        çekirdek, dilerseniz de kullandığınız kahve demleme ekipmanınıza uygun olarak kargolamadan hemen
                        önce öğütüp sizlere ulaştırıyoruz. <span>Hem de aynı gün kargoda!</span></p>
                </div>
            </section>

            <section class="katalog">
                <div class="dropdown siralama">
                    <a href="#" class="dropdown-toggle buyuk1" data-toggle="dropdown" role="button" aria-haspopup="true"
                        aria-expanded="false">Sıralama<span class="caret"></span></a>
                    <ul class="dropdown-menu buyuk1">
                        <li><a v-on:click="azalanFiyat" href="#">Fiyat Azalan</a></li>
                        <li><a v-on:click="artanFiyat" href="#">Fiyat Artan</a></li>
                        <li><a href="#">Akıllı Sıralama</a></li>
                        <!-- Sayfada olduğundan dolayı eklendi. Herhangi bir fonksiyonu yoktur. -->
                        <li><a href="#">Benzer Ürünler</a></li>
                        <!-- Sayfada olduğundan dolayı eklendi. Herhangi bir fonksiyonu yoktur. -->
                    </ul>
                </div>

                <div class="row no-padding">
                    <div class="col-md-3 filtreler hidden-xs">
                        <div class="sabit">
                            <h3 class="turuncu">MARKA</h3>
                            <ul class="marka-filtreleri">
                                <li><a v-on:click="bialettiSec" class="kahve marka-filtresi pointer">Bialetti(<span
                                            class="adet">2</span>)</a></li>
                                <li><a v-on:click="caffeFrescoSec" class="kahve marka-filtresi pointer">Caffe
                                        Fresco(<span class="adet">3</span>)</a></li>
                                <li><a v-on:click="caffeVergnanoSec" class="kahve marka-filtresi pointer">Caffe
                                        Vergnano(<span class="adet">4</span>)</a></li>
                                <li v-on:click="kategoriUzat" v-if="noktalar" class="devamini-gor">.......</li>
                                <li><a v-if="kategoriAcma" v-on:click="coffeeSapiensSec"
                                        class="kahve marka-filtresi pointer">Coffee Sapiens(<span
                                            class="adet">2</span>)</a></li>
                                <li><a v-if="kategoriAcma" v-on:click="kronotropSec"
                                        class="kahve marka-filtresi pointer">Kronotrop(<span class="adet">1</span>)</a>
                                </li>
                            </ul>

                            <h3 class="turuncu">ORIGIN</h3>
                            <ul class="marka-filtreleri">
                                <li><a class="kahve marka-filtresi pointer">Antigua(<span class="adet">3</span>)</a>
                                </li>
                                <li><a class="kahve marka-filtresi pointer">Blend(<span class="adet">3</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Brazil(<span class="adet">5</span>)</a></li>
                                <li class="devamini-gor">.......</li>
                            </ul>

                            <h3 class="turuncu">TAT</h3>
                            <ul class="marka-filtreleri">
                                <li><a class="kahve marka-filtresi pointer">Aromalı Kahve(<span
                                            class="adet">3</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Meyvemsi / Az Kavrulmuş(<span
                                            class="adet">3</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Orta Yumuşak / Dengeli(<span
                                            class="adet">5</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Yoğun / Sert(<span
                                            class="adet">5</span>)</a></li>
                            </ul>
                            <h3 class="turuncu">EKİPMAN</h3>
                            <ul class="marka-filtreleri">
                                <li><a class="kahve marka-filtresi pointer">Decaf Kahve(<span class="adet">3</span>)</a>
                                </li>
                                <li><a class="kahve marka-filtresi pointer">Esspresso Kahve(<span
                                            class="adet">3</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Filtre Kahve(<span
                                            class="adet">5</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Kapsül Kahve(<span
                                            class="adet">5</span>)</a></li>
                                <li><a class="kahve marka-filtresi pointer">Soğuk Kahve(<span class="adet">5</span>)</a>
                                </li>
                            </ul>
                        </div>
                    </div>
                    <div class="col-md-9 urunler">
                        <div class="row urun-listesi">
                            <div class="col-md-4 col-xs-6" v-for="(item, index) in hepsi" :key="index">
                                <div v-if="item.isAvailable === true" class="urun">
                                    <a class="resim">
                                        <i class="icon icon-sepet back-turuncu beyaz katalog-sepete-ekle"
                                            v-on:click="kahhveSepeteEkle(index)"></i>
                                        <img class="" :src="item.image">
                                    </a>
                                    <router-link :to="item.url" class="a">
                                        <div class="title text-center">
                                            <span class="inner-title">{{ item.title }}</span>
                                        </div>
                                    </router-link>
                                    <router-link :to="item.markaurl" class="a">
                                        <div class="text-center marka roboto">{{ item.marka }}</div>
                                    </router-link>
                                    <div class="text-center fiyat">
                                        <p>{{ item.fiyat }} TL</p>
                                    </div>
                                </div>
                                <div v-else class="urun">
                                    <a class="resim">
                                        <span class="stokta-yok back-turuncu beyaz">STOKTA YOK</span>
                                        <img class="" :src="item.image">
                                    </a>
                                    <router-link :to="item.url" class="a">
                                        <div class="title text-center">
                                            <span class="inner-title">{{ item.title }}</span>
                                        </div>
                                    </router-link>
                                    <router-link :to="item.markaurl" class="a">
                                        <div class="text-center marka roboto">{{ item.marka }}</div>
                                    </router-link>
                                    <div class="text-center fiyat">
                                        <p>{{ item.fiyat }} TL</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                        <div class="row">
                            <nav aria-label="Page navigation" class="navigation">
                                <ul class="pagination">
                                    <li class="kahve">
                                        <a v-on:click="prevPage" aria-label="Previous">
                                            <span aria-hidden="true">«</span>
                                        </a>
                                    </li>
                                    <li class="kahve"><a>1</a></li>
                                    <li class="kahve"><a>2</a></li>
                                    <li class="kahve">
                                        <a v-on:click="nextPage" aria-label="Next">
                                            <span aria-hidden="true">»</span>
                                        </a>
                                    </li>
                                </ul>
                            </nav>
                        </div>
                        <div class="roboto light kahve">
                            <h1>Kahve</h1> <!-- Doğrudan siteden kopyalanmıştır -->
                            <p>Dünyada sudan sonra en çok tüketilen içecek olan kahve, günlük dünya çapında 2.25 milyar
                                kupaya ulaştı. Kahve ağacının tohumu olan yeşil <strong>kahve çekirdekleri</strong>
                                tropikal iklimde yüksek bölgelerde yetişmektedir. Birçok çeşidi olmasına rağmen iki
                                çeşit kahve türü yaygındır. <strong>Arabica</strong> kahve çekirdekleri dünya kahve
                                üretiminin %80'ini oluşturmaktadır, %20'si ise <strong>robusta</strong> kahve
                                çekirdekleridir.</p>
                            <div>
                                <h3>Kahve Üretimi</h3>
                                <p>En çok kahve dünya üretiminin %25'lik kısmıyla <strong>Brezilya</strong>da
                                    gerçekleşmektedir. Onu sırasıyla; <strong>Vietnam</strong>,
                                    <strong>Kolombiya</strong>, <strong>Endonezya</strong> ve <strong>Etiyopya</strong>
                                    takip etmektedir. Neredeyse bütün ülkelerde senede bir kere hasat alınsa da
                                    kolombiya gibi bazı ülkelerde 2 defa hasat alınmaktadır. Kahve çekirdekleri
                                    yetiştikleri hava koşullarına, toprak bileşenlerine göre tat, aroma, acidite ve
                                    gövde özelliklerini almaktadır. Bu yüzden kahveler yetiştirildikleri bölgeye göre
                                    sınıflandırılırlar. Sadece bir yörede yetişmiş kahvelere <strong>single
                                        origin</strong>, birçok farklı bölgeden gelen kahvelerin karıştırılması ile elde
                                    edilen kahvelere harman(blend) denmektedir.</p>
                            </div>
                            <div>
                                <h3>Kahve Kavurma</h3>
                                <p>Kahveler yeşil çekirdek olarak yıllarca bir değişiklik görmeden saklanabilirler. Bu
                                    yüzden kahveler yetiştirildikleri bölgelerden Türkiye'ye yeşil çekirdek olarak sevk
                                    edilmektedirler. <strong>Petra, Coffee Sapiens, Kronotrop, Cool Beans, Urban Grind,
                                        Caffe Fresco, Coffeerem, Coffeemamma, Overdose, Punctum, Shorts Coffee</strong>
                                    gibi markaların tecrübeli baristaları tarafından, kahvenin tadını en güzel ortaya
                                    çıkaracağını düşündükleri profilde kavrulurlar. <strong>Illy, Bialetti, Caffe
                                        Vergnano</strong> gibi klasik italya kahve kültürünü sürdüren markalar
                                    kahvelerini İtalya'da kavurup bütün dünyaya dağıtım yapmaktadır.</p>
                            </div>
                            <div>
                                <h3>Kahve Çeşitleri</h3>
                                <p>Kahve, içecek olarak tüketebilmek için öğütülmeli ve demlenmelidir. İstenilen kahve
                                    tadına ve sahip olunan ekipmana göre demleme yöntemi seçilir.
                                    <strong>Espresso</strong>, yüksek basınçtaki sıcak suyun ince öğütülmüş kahve içinde
                                    geçirilerek demlenir. Az miktarda, yoğun ve kremamsı bir kahve elde edilir.
                                    <strong>Filtre kahve</strong>de sıcak su kahve üzerine dökülür, suyun kahvenin özünü
                                    alması beklenir ve filtrelenerek bir kupa veya karafa aktarılır.</p>
                            </div>
                            <div>
                                <h3>Kahve Demleme Ekipmanları</h3>
                                <p>Kavrulmuş kahve çekirdeklerinin kullanılacak ekipmana uygun boyutta öğütülmesi
                                    gerekmektedir. Türk Kahvesi için çok ince; espresso için ince; hario, moka pot,
                                    aeropress için ince-orta; filtre kahve makinesi için orta; chemex için orta-kalın;
                                    french press için kalın; soğuk demleme için çok kalın öğütülmüş kahve kullanılması
                                    uygun olacaktır.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
        </div>
        <div v-if="isLoading" class="yukleniyor" style="display: block;">
              <div class="zeplin"></div>
        </div>

        <div v-else class="yukleniyor" style="display: none;">
              <div class="zeplin"></div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                isLoading: true,
                cart: [],
                toplam: 0,
                hepsi: [],
                sayfa: [],
                itemPerPage: 6,
                a: 0,
                b: 6,
                kategoriAcma: false,
                noktalar: true,

                bialettiKahveler: [{
                        isAvailable: true,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Gusto Dolce Öğütülmüş Kahve 250 gram',
                        image: 'https://kahhvecom.imgix.net/urunler/737_1537871362_3NA.png',
                        url: '/bialetti-gusto-dolce-ogutulmus-kahve-250-gram-kahveler',
                        title: 'Bialetti Gusto Dolce Öğütülmüş Kahve 250 gram',
                        marka: 'Bialetti',
                        fiyat: 79.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Gusto Intenso Öğütülmüş Kahve 250 gram',
                        image: 'https://kahhvecom.imgix.net/urunler/739_1542778084_QDU.jpg',
                        url: '/bialetti-caffe-macinato--kahveler',
                        title: 'Bialetti Gusto Intenso Öğütülmüş Kahve 250 gram',
                        marka: 'Bialetti',
                        fiyat: 79.99
                    },
                ],

                caffeVergnanoKahveler: [{
                        isAvailable: true,
                        markaurl: '/caffe-vergnano',
                        sepette: 'Caffe Vergnano Espresso 1882',
                        image: 'https://kahhvecom.imgix.net/urunler/119_1441352400_zn1.jpg',
                        url: '/vergnano-espresso-1882-kahveler',
                        title: 'Espresso 1882',
                        marka: 'Caffe Vergnano',
                        fiyat: 62.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/caffe-vergnano',
                        sepette: 'Caffe Fresco Arabica Çekirdek Kahvesi',
                        image: 'https://kahhvecom.imgix.net/urunler/122_1563525190_Pfu.png',
                        url: '/vergnano-arabica-cekirdek-kahvesi-kahveler',
                        title: 'Arabica Çekirdek Kahvesi',
                        marka: 'Caffe Fresco',
                        fiyat: 51.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/caffe-vergnano',
                        sepette: 'Caffe Fresco Arabica Moka',
                        image: 'https://kahhvecom.imgix.net/urunler/120_1441352749_Tvd.jpg',
                        url: '/vergnano-arabica-moka-kahveler',
                        title: 'Arabica Moka',
                        marka: 'Caffe Fresco',
                        fiyat: 51.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/caffe-vergnano',
                        sepette: 'Caffe Fresco Arabica Espresso',
                        image: 'https://kahhvecom.imgix.net/urunler/121_1443548403_g5G.jpg',
                        url: '/vergnano-arabica-espresso',
                        title: 'Arabica Espresso',
                        marka: 'Caffe Fresco',
                        fiyat: 51.99
                    },
                ],

                caffeFrescoKahveler: [{
                        isAvailable: true,
                        markaurl: '/caffe-fresco',
                        sepette: 'Caffe Fresco All Day Blend',
                        image: 'https://kahhvecom.imgix.net/urunler/796_1550056308_k43.jpg',
                        url: '/caffe-fresco-all-day-blend-kahveler',
                        title: 'All Day Blend',
                        marka: 'Caffe Fresco',
                        fiyat: 21.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/caffe-fresco',
                        sepette: 'Caffe Fresco Espresso Blend 1 KG',
                        image: 'https://kahhvecom.imgix.net/urunler/811_1565851189_uQt.jpg',
                        url: '/caffe-fresco-espresso-blend-1-kg-kahveler',
                        title: 'Caffe Fresco Espresso Blend 1 KG',
                        marka: 'Caffe Fresco',
                        fiyat: 84.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/caffe-fresco',
                        sepette: 'Caffe Fresco All Day Blend 1 KG',
                        image: 'https://kahhvecom.imgix.net/urunler/812_1565087080_BHZ.jpg',
                        url: '/caffe-fresco-all-day-blend-1-kg-kahveler',
                        title: 'All Day Blend 1 KG',
                        marka: 'Caffe Fresco',
                        fiyat: 84.99
                    },
                ],

                coffeeSapiensKahveler: [{
                        isAvailable: true,
                        markaurl: '/coffee-sapiens',
                        sepette: 'Coffee Sapiens Evolution Blend',
                        image: 'https://kahhvecom.imgix.net/urunler/55_1521108632_Txj.jpg',
                        url: '/coffee-sapiens-evolution-blend-kahveler',
                        title: 'Evolution Blend',
                        marka: 'Coffee Sapiens',
                        fiyat: 39.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/coffee-sapiens',
                        sepette: 'Coffee Sapiens Mutation Blend',
                        image: 'https://kahhvecom.imgix.net/urunler/54_1521108565_3mn.jpg',
                        url: '/coffee-sapiens-mutation-blend-kahveler',
                        title: 'Mutation Blend',
                        marka: 'Coffee Sapiens',
                        fiyat: 49.99
                    },
                ],

                kronotropKahveler: [
                    {
                    isAvailable: true,
                    markaurl: '/kronotrop',
                    sepette: 'Kronotrop Endonezya Frinsa Collective',
                    image: 'https://kahhvecom.imgix.net/urunler/843_1567000093_yE5.jpg',
                    url: '/kronotrop-endonezya-frinsa-collective-kahveler',
                    title: 'Endonezya Frinsa Collective',
                    marka: 'Kronotrop',
                    fiyat: 59.99
                    }, 
                ]
            }
        },

        created() {
            setTimeout(() => this.isLoading = false, 1000)
            this.hepsi = this.bialettiKahveler.concat(this.caffeFrescoKahveler, this.caffeVergnanoKahveler, this
                .coffeeSapiensKahveler, this.kronotropKahveler);
            this.sayfa = this.hepsi.slice(this.a, this.b);
            this.hepsi = this.sayfa;
        },

        methods: {
            kahhveSepeteEkle(index) {
                this.isLoading = true;
				setTimeout(() => this.isLoading = false, 500);
                this.cart = JSON.parse(localStorage.getItem('sepettekiler' || [] ));
                this.toplam += JSON.parse(localStorage.getItem('toplam' || [] ));
                this.cart.push(this.hepsi[index]);
                this.toplam += this.hepsi[index].fiyat;
                localStorage.setItem('sepettekiler', JSON.stringify(this.cart));
                localStorage.setItem('toplam', JSON.stringify(this.toplam));
            },

            bialettiSec() {
                this.hepsi = this.bialettiKahveler;
            },

            kronotropSec() {
                this.hepsi = this.kronotropKahveler;
            },

            caffeFrescoSec() {
                this.hepsi = this.caffeFrescoKahveler;
            },

            caffeVergnanoSec() {
                this.hepsi = this.caffeVergnanoKahveler;
            },

            coffeeSapiensSec() {
                this.hepsi = this.coffeeSapiensKahveler;
            },

            artanFiyat() {
                this.hepsi.sort((a, b) => (a.fiyat > b.fiyat) ? 1 : -1);
            },

            azalanFiyat() {
                this.hepsi.sort((a, b) => (a.fiyat > b.fiyat) ? 1 : -1).reverse();
            },

            nextPage() {
                if (this.b < 12) {
                    this.hepsi = this.bialettiKahveler.concat(this.caffeFrescoKahveler, this.caffeVergnanoKahveler, this
                        .coffeeSapiensKahveler, this.kronotropKahveler);
                    this.a += this.itemPerPage;
                    this.b += this.itemPerPage;
                    this.sayfa = this.hepsi.slice(this.a, this.b);
                    this.hepsi = this.sayfa;
                }
            },

            prevPage() {
                if (this.a > 0) {
                    this.hepsi = this.bialettiKahveler.concat(this.caffeFrescoKahveler, this.caffeVergnanoKahveler, this
                        .coffeeSapiensKahveler, this.kronotropKahveler);
                    this.a -= this.itemPerPage;
                    this.b -= this.itemPerPage;
                    this.sayfa = this.hepsi.slice(this.a, this.b);
                    this.hepsi = this.sayfa;
                }
            },

            kategoriUzat() {
                this.kategoriAcma = true;
                this.noktalar = false;
            }
        }
    }
</script>