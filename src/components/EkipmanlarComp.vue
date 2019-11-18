<template>
    <div class="page-content">

        <div class="katalog">
            <section class="baslik ekipmanlar">
                <div class="col-md-offset-1 col-md-8">
                    <h1 class="beyaz">KAHVE DEMLEME<br>EKİPMAN &amp; AKSESUARLAR</h1>
                    <h2 class="turuncu roboto">Taze kahve keyfiniz için ihtiyacınız olan her şey!</h2>
                    <div class="back-ekipman"></div>
                    <p class="beyaz roboto">Kahvenizin aromasını ve lezzettini en iyi şekilde bardağınıza getirecek
                        birbirinden özel ve nitelikli kahve demleme ekipmanlarını sizler için bir araya getirdik.
                        Chemex, Hario, Bialetti, Moka Pot, Aeropress, French Press ve kahve keyfinizi evinizde ve
                        ofisinizde yaşamanızı sağlayacak tüm ekipmanlara buradan ulaşabilirsiniz.</p>
                </div>
            </section>

            <section class="katalog" id="kahhveEkipmanlar">
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
                            <h3 class="turuncu">EKİPMAN</h3>
                            <ul class="ekipman-icons kategori-filtreleri">
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-french-press"></i>
                                        <div>French Press</div>
                                    </a>
                                </li>
                                <li>
                                    <a v-on:click="bialettiSec" class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-moka-pot"></i>
                                        <div>Moka Pot</div>
                                    </a>
                                </li>
                                <li>
                                    <a v-on:click="chemexSec" class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-chemex"></i>
                                        <div>Chemex</div>
                                    </a>
                                </li>
                                <li>
                                    <a v-on:click="harioSec" class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-dripper"></i>
                                        <div>Hario</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-filtre"></i>
                                        <div>Filtre</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-tarti"></i>
                                        <div>Aksesuarlar</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-cold-drip"></i>
                                        <div>Soğuk Kahve</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-kettle"></i>
                                        <div>Kettle</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-mug"></i>
                                        <div>Mug</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-aeropress"></i>
                                        <div>Aeropress</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-kahve-makinesi"></i>
                                        <div>Kahve Makineleri</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-tamper"></i>
                                        <div>Barista Ekipmanlari</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-degirmen"></i>
                                        <div>Öğütücü</div>
                                    </a>
                                </li>
                                <li>
                                    <a class="text-center inner kategori-filtresi ">
                                        <i class="icon icon-yedek-parcalar"></i>
                                        <div>Yedek Parça</div>
                                    </a>
                                </li>
                            </ul>

                            <h3 class="turuncu">MARKA</h3>
                            <ul class="marka-filtreleri">
                                <li><a v-on:click="hepsiniSec" class="kahve hepsini-gor pointer">Hepsini Gör</a></li>
                                <li><a v-on:click="bialettiSec" class="kahve marka-filtresi pointer">Bialetti(<span
                                            class="adet">3</span>)</a></li>
                                <li><a v-on:click="chemexSec" class="kahve marka-filtresi pointer">Chemex(<span
                                            class="adet">3</span>)</a></li>
                                <li><a v-on:click="harioSec" class="kahve marka-filtresi pointer">Hario(<span
                                            class="adet">5</span>)</a></li>
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
                sayfa:[],
                itemPerPage: 6,
                a: 0,
                b: 6,
                adet: 1,
                chemexUrunler: [
                    {
                        isAvailable: true,
                        markaurl: '/chemex',
                        sepette: 'Chemex Beyaz Filtre 6-8 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/50_1440881161_NU3.jpg',
                        url: '/chemex-beyaz-filtre-filtreler',
                        title: 'BEYAZ FILTRE 6-8 CUP',
                        marka: 'CHEMEX',
                        fiyat: 74.99 },
                    {
                        isAvailable: true,
                        markaurl: '/chemex',
                        sepette: 'Chemex Ahşap Tutacaklı 6 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/47_1439898391_u6Z.jpg',
                        url: '/chemex-ahsap-tutacakli-6-cup-kahve-demleme-ekipmanlari',
                        title: 'AHŞAP TUTACAKLI 6 CUP',
                        marka: 'CHEMEX',
                        fiyat: 379.99 },
                    {
                        isAvailable: true,
                        markaurl: '/chemex',
                        sepette: 'Chemex Ahşap Tutacaklı 8 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/133_1468588393_zow.jpg',
                        url: '/chemex-ahsap-tutacakli-8-cup-kahve-demleme-ekipmanlari',
                        title: 'AHŞAP TUTACAKLI 8 CUP',
                        marka: 'CHEMEX',
                        fiyat: 399.99 },

                    ],

                    bialettiUrunler: [
                    {
                        isAvailable: true,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Moka Pot Express Kırmızı 1 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/751_1561111234_Gug.jpg',
                        url: '/bialetti-moka-pot-express-kirmizi-1-cup-moka-pot',
                        title: 'MOKA POT EXPRESS KIRMIZI 1 CUP',
                        marka: 'BIALETTI',
                        fiyat: 149.99 },
                    {
                        isAvailable: true,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Orzo Express',
                        image: 'https://kahhvecom.imgix.net/urunler/456_1492581342_zGf.jpg',
                        url: '/bialetti-orzo-express-kahve-demleme-ekipmanlari',
                        title: 'ORZO EXPRESS',
                        marka: 'BIALETTI',
                        fiyat: 129.99 },
                    {
                        isAvailable: false,
                        markaurl: '/bialetti',
                        sepette: 'Bialetti Moka Pot Alpina 3 Cup',
                        image: 'https://kahhvecom.imgix.net/urunler/76_1444578738_YZI.jpg',
                        url: '/bialetti-moka-pot-alpini-3-cup-kahve-demleme-ekipmanlari',
                        title: 'MOKA POT ALPINA 3 CUP',
                        marka: 'BIALETTI',
                        fiyat: 219.99 },
                    ],

                    harioUrunler: [
                    {
                        isAvailable: true,
                        markaurl: '/hario',
                        sepette: 'Hario V60 Tanışma Seti',
                        image: 'https://kahhvecom.imgix.net/urunler/112_1569671179_VwG.jpg',
                        url: '/hario-set-kahve-demleme-ekipmanlari',
                        title: 'V60 TANIŞMA SETI',
                        marka: 'HARIO',
                        fiyat: 229.99 },
                    {
                        isAvailable: false,
                        markaurl: '/hario',
                        sepette: 'Hario Mill Skerton Tanışma Seti',
                        image: 'https://kahhvecom.imgix.net/urunler/857_1569938448_bEm.jpg',
                        url: '/hario-mini-mill-skerton-tanisma-seti-kahve-degirmenleri',
                        title: 'MINI MILL SKERTON TANIŞMA SETI',
                        marka: 'HARIO',
                        fiyat: 269.99 },
                    {
                        isAvailable: false,
                        markaurl: '/hario',
                        sepette: 'Hario V60 Tanışma Seti Barista',
                        image: 'https://kahhvecom.imgix.net/urunler/852_1569673649_CUv.jpg',
                        url: '/hario-v60-tanisma-seti-barista-kahve-demleme-ekipmanlari',
                        title: 'V60 TANIŞMA SETI BARİSTA',
                        marka: 'HARIO',
                        fiyat: 874.99 },
                    {
                        isAvailable: false,
                        markaurl: '/hario',
                        sepette: 'Hario Tanışma Seti Pro',
                        image: 'https://kahhvecom.imgix.net/urunler/851_1569673369_TX7.jpg',
                        url: '/hario-v60-tanisma-seti-pro-kahve-demleme-ekipmanlari',
                        title: 'V60 TANIŞMA SETI PRO',
                        marka: 'HARIO',
                        fiyat: 479.99 },
                    {
                        isAvailable: true,
                        markaurl: '/hario',
                        sepette: 'Hario V60 02 Seramik Dripper Beyaz',
                        image: 'https://kahhvecom.imgix.net/urunler/94_1453646682_GML.jpg',
                        url: '/hario-v60-02-dripper-beyaz-seramik-kahve-demleme-ekipmanlari',
                        title: 'V60 02 SERAMIK DRIPPER BEYAZ',
                        marka: 'HARIO',
                        fiyat: 149.99 },
                    ]
            }
        },

        created(){
            setTimeout(() => this.isLoading = false, 1000)
            this.hepsi = this.chemexUrunler.concat(this.harioUrunler, this.bialettiUrunler);
            this.sayfa = this.hepsi.slice(this.a,this.b);
            this.hepsi = this.sayfa;
        },

        methods: {
            kahhveSepeteEkle(index){
                this.isLoading = true;
				setTimeout(() => this.isLoading = false, 500);
                this.cart = JSON.parse(localStorage.getItem('sepettekiler' || [] ));
                this.toplam += JSON.parse(localStorage.getItem('toplam' || [] ));
                this.cart.push(this.hepsi[index]);
                this.toplam += this.hepsi[index].fiyat;
                localStorage.setItem('sepettekiler', JSON.stringify(this.cart));
                localStorage.setItem('toplam', JSON.stringify(this.toplam));
            },

            hepsiniSec(){
                this.hepsi = this.chemexUrunler.concat(this.harioUrunler, this.bialettiUrunler);
            },

            chemexSec(){
                this.hepsi = this.chemexUrunler;
            },

            harioSec(){
                this.hepsi = this.harioUrunler;
            },

            bialettiSec(){
                this.hepsi = this.bialettiUrunler;
            },

            artanFiyat(){
                this.hepsi.sort((a, b) => (a.fiyat > b.fiyat) ? 1 : -1);
            },

            azalanFiyat(){
                this.hepsi.sort((a, b) => (a.fiyat > b.fiyat) ? 1 : -1).reverse();
            },

            nextPage(){
                if (this.b < 12) {
                    this.hepsi = this.chemexUrunler.concat(this.harioUrunler, this.bialettiUrunler);
                    this.a += this.itemPerPage;
                    this.b += this.itemPerPage;
                    this.sayfa = this.hepsi.slice(this.a, this.b);
                    this.hepsi = this.sayfa;
                }
            },

            prevPage(){
                if (this.a > 0) {
                    this.hepsi = this.chemexUrunler.concat(this.harioUrunler, this.bialettiUrunler);
                    this.a -= this.itemPerPage;
                    this.b -= this.itemPerPage;
                    this.sayfa = this.hepsi.slice(this.a, this.b);
                    this.hepsi = this.sayfa;
                }
            },

            adetUp(){
                this.adet++
            },

            adetDown(){
                if (this.adet > 1) {
                    this.adet--
            }
        },
    }
}
</script>