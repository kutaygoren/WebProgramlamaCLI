<template>
    <div class="page-content">

        <div class="katalog">
            <section class="baslik ekipmanlar">
                <div class="col-md-offset-1 col-md-8">
                    <h1 class="beyaz">KAHVE TANIŞMA SETLERI</h1>
                    <h2 class="turuncu roboto">Kahve Ekipmanları Tanışma Setleri</h2>
                    <div class="back-ekipman"></div>
                    <p class="beyaz roboto">Kahve Demleme Ekipmanlarını kullanmak için ihtiyacınız olan ekipman ve
                        aksesuarları yanında 5 çeşit 50gr kahve ile bir arada alabileceğiniz setler oluşturduk. </p>
                </div>
            </section>

            <section class="katalog" id="kahhveTanisma">
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
                        <h3 class="turuncu">MARKA</h3>
                        <ul>
                            <li><a v-on:click="aeropressSec" class="kahve marka-filtresi pointer">Aeropress(<span
                                        class="adet">2</span>)</a></li>
                            <li><a v-on:click="bialettiSec" class="kahve marka-filtresi pointer">Bialetti(<span
                                        class="adet">3</span>)</a></li>
                            <li><a v-on:click="harioSec" class="kahve marka-filtresi pointer">Hario(<span
                                        class="adet">4</span>)</a></li>
                            <li><a v-on:click="kahhveSec" class="kahve marka-filtresi pointer">KahhveCom(<span
                                        class="adet">1</span>)</a></li>
                        </ul>
                    </div>

                    <div class="col-md-9 urun-listesi">
                        <div class="row">
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
                                    <li class="turuncu"><a>1</a></li>
                                </ul>
                            </nav>
                        </div>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                cart: [],
                toplam: 0,
                hepsi: [],

                kahhvesetler: [{
                    isAvailable: true,
                    markaurl: '/kahhvecom',
                    sepette: 'Kahhve Tanışma Seti',
                    image: 'https://kahhvecom.imgix.net/urunler/92_1569671134_BG8.jpg',
                    url: '/kahhvecom-tanisma-seti-kahveler',
                    title: 'KAHHVE TANIŞMA SETI',
                    marka: 'KAHHVECOM',
                    fiyat: 49.99
                }, ],

                bialettiSetler: [{
                        isAvailable: true,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Moka Pot Tanışma Seti 3 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/135_1569671319_5Up.jpg',
                        url: '/bialetti-moka-pot-baslangic-seti-kahve-demleme-ekipmanlari',
                        title: 'MOKA POT TANIŞMA SETI 3 CUP',
                        marka: 'BIALETTI',
                        fiyat: 219.99
                    },
                    {
                        isAvailable: true,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Moka Pot Tanışma Seti 2 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/778_1569671374_THD.jpg',
                        url: '/bialetti-moka-pot-tanisma-seti-2-cup-kahve-demleme-ekipmanlari',
                        title: 'MOKA POT TANIŞMA SETI 2 CUP',
                        marka: 'BIALETTI',
                        fiyat: 199.99
                    },
                    {
                        isAvailable: false,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Moka Pot Tanışma Seti 3 Cup Pro',
                        image: 'https://kahhvecom.imgix.net/urunler/850_1569672595_xp6.jpg',
                        url: '/bialetti-moka-pot-tanisma-seti-3-cup--pro-moka-pot',
                        title: 'MOKA POT TANIŞMA SETI 3 CUP PRO',
                        marka: 'BIALETTI',
                        fiyat: 474.99
                    },
                ],

                aeropressSetler: [{
                        isAvailable: true,
                        markaurl: '/aeropress',
                        sepette: 'Aeropress Tanışma Seti',
                        image: 'https://kahhvecom.imgix.net/urunler/789_1569671404_ASZ.jpg',
                        url: '/aeropress-aeropress-tanisma-seti-kahve-tanisma-setleri',
                        title: 'AEROPRESS TANIŞMA SETI',
                        marka: 'AEROPRESS',
                        fiyat: 329.99
                    },
                    {
                        isAvailable: false,
                        markaurl: '/aeropress',
                        sepette: 'Aeropress Tanışma Seti Pro',
                        image: 'https://kahhvecom.imgix.net/urunler/855_1569674802_kdG.jpg',
                        url: '/aeropress-aeropress-tanisma-seti-pro-kahve-demleme-ekipmanlari',
                        title: 'AEROPRESS TANIŞMA SETI PRO',
                        marka: 'AEROPRESS',
                        fiyat: 579.99
                    },
                ],

                harioSetler: [{
                        isAvailable: true,
                        markaurl: '/hario',
                        sepette: 'Hario V60 Tanışma Seti',
                        image: 'https://kahhvecom.imgix.net/urunler/112_1569671179_VwG.jpg',
                        url: '/hario-set-kahve-demleme-ekipmanlari',
                        title: 'V60 TANIŞMA SETI',
                        marka: 'HARIO',
                        fiyat: 229.99
                    },
                    {
                        isAvailable: false,
                        markaurl: '/hario',
                        sepette: 'Hario Mill Skerton Tanışma Seti',
                        image: 'https://kahhvecom.imgix.net/urunler/857_1569938448_bEm.jpg',
                        url: '/hario-mini-mill-skerton-tanisma-seti-kahve-degirmenleri',
                        title: 'MINI MILL SKERTON TANIŞMA SETI',
                        marka: 'HARIO',
                        fiyat: 269.99
                    },
                    {
                        isAvailable: false,
                        markaurl: '/hario',
                        sepette: 'Hario V60 Tanışma Seti Barista',
                        image: 'https://kahhvecom.imgix.net/urunler/852_1569673649_CUv.jpg',
                        url: '/hario-v60-tanisma-seti-barista-kahve-demleme-ekipmanlari',
                        title: 'V60 TANIŞMA SETI BARİSTA',
                        marka: 'HARIO',
                        fiyat: 874.99
                    },
                    {
                        isAvailable: false,
                        markaurl: '/hario',
                        sepette: 'Hario Tanışma Seti Pro',
                        image: 'https://kahhvecom.imgix.net/urunler/851_1569673369_TX7.jpg',
                        url: '/hario-v60-tanisma-seti-pro-kahve-demleme-ekipmanlari',
                        title: 'V60 TANIŞMA SETI PRO',
                        marka: 'HARIO',
                        fiyat: 479.99
                    },
                ]
            }
        },

        created() {
            this.hepsi = this.kahhvesetler.concat(this.bialettiSetler, this.harioSetler, this.aeropressSetler);
        },

        methods: {
            kahhveSepeteEkle(index) {
                this.cart = JSON.parse(localStorage.getItem('sepettekiler' || []));
                this.toplam += JSON.parse(localStorage.getItem('toplam' || []));
                this.cart.push(this.hepsi[index]);
                this.toplam += this.hepsi[index].fiyat;
                localStorage.setItem('sepettekiler', JSON.stringify(this.cart));
                localStorage.setItem('toplam', JSON.stringify(this.toplam));
            },

            aeropressSec() {
                this.hepsi = this.aeropressSetler;
            },

            harioSec() {
                this.hepsi = this.harioSetler;
            },

            bialettiSec() {
                this.hepsi = this.bialettiSetler;
            },

            kahhveSec() {
                this.hepsi = this.kahhvesetler;
            },

            artanFiyat() {
                this.hepsi.sort((a, b) => (a.fiyat > b.fiyat) ? 1 : -1);
            },

            azalanFiyat() {
                this.hepsi.sort((a, b) => (a.fiyat > b.fiyat) ? 1 : -1).reverse();
            }
        }
    }
</script>