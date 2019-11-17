<template>
	<div class="page-content">
		<section class="banner">
			<div class="row no-margin">
				<div id="banner-carousel" class="carousel slide" data-ride="carousel">
					<div class="carousel-inner" role="listbox">
						<div class="item banner3">
							<a href="/" class="img beyaz">
								<div class="ucan-yazi turuncu">
									<span class="baslangic"></span>
									<span class="yazi turuncu">HIZLI KARGO</span>
									<span class='bitis'></span>
								</div>
								<div class="top1 voffset2">AYNI GÜN KARGO</div>
								<p class="top3 roboto light voffset2">Haftaiçi 16.00'a kadar gelen siparişleri aynı gün
									içinde kargoya teslim ediyoruz.</p>
							</a>
						</div>
						<div class="item banner1">
							<a href="/caffe-fresco-all-day-blend-kahveler" class="img beyaz">
								<div class="ucan-yazi turuncu">
									<span class="baslangic"></span>
									<span class="yazi turuncu">HAFTANIN ÜRÜNÜ</span>
									<span class='bitis'></span>
								</div>
								<div class="top1 voffset2">ALL DAY BLEND</div>
								<div class="top2 roboto light turuncu">CAFFE FRESCO</div>
								<p class="top3 roboto light voffset2">Sadece Kolombiya çekirdeklerini içerir, yumuşak ve
									pürüzsüz aromaya sahiptir. Günün her saati keyifle içebilirsiniz.</p>
							</a>
						</div>
						<div class="item banner2 active">
							<a href="/urban-grind" class="img beyaz">
								<div class="ucan-yazi turuncu">
									<span class="baslangic"></span>
									<span class="yazi turuncu">HAFTANIN ÜRÜNÜ</span>
									<span class='bitis'></span>
								</div>
								<div class="top1 voffset2">KİLOLUK KAHVE</div>
								<div class="top2 roboto light turuncu">URBAN GRIND</div>
								<p class="top3 roboto light voffset2">Kahvenizi keyifle içebilmeniz için özel tasarlanan
									porselen kupalarımız kısa bir süre için Urban Grind kiloluk kahvelerle hediye.</p>
							</a>
						</div>
					</div>
					<a class="left carousel-control" href="#banner-carousel" data-slide="prev">
						<span class="glyphicon glyphicon-chevron-left"></span>
					</a>
					<a class="right carousel-control" href="#banner-carousel" data-slide="next">
						<span class="glyphicon glyphicon-chevron-right"></span>
					</a>
				</div>
			</div>
		</section>

		<section class="urunserit tanisma container">
			<div class="row">
				<h2 class="text-center turuncu">POPÜLER TANIŞMA SETLERİ</h2>

				<div class="col-md-3 col-xs-6" :key="index" v-for="(item, index) in setler">
					<div class="urun">
						<a class="resim">
							<!-- TODO: bug düzelt-->
							<i class="icon icon-sepet back-turuncu beyaz katalog-sepete-ekle"
								v-on:click="sepeteEkle(index)"></i>
							<img class="beklemede" :src="item.image">
						</a>
						<a :href="item.url">
							<div class="title text-center">
								<span class="inner-title">{{ item.title }}</span>
							</div>
						</a>
						<a :href="item.markaurl">
							<div class="text-center marka roboto">{{ item.marka }}</div>
						</a>
						<div class="text-center fiyat">
							<p>{{ item.fiyat }} TL</p>
						</div>
					</div>
				</div>
			</div>
			<a href="kahve-tanisma-setleri.html" class="btn text-center back-turuncu">TÜMÜNÜ GÖR</a>
		</section>

		<div class="back-gray">
			<section class="markalarimiz container">
				<div class="row">
					<h2 class="text-center kahve" style="font-size: 36px; font-weight: 700;">POPÜLER MARKALAR</h2>
					<a href="/chemex" class="col-xs-4 col-sm-2"><img src="https://kahhve.com/img/markalar/png/chemex.png"></a>
					<a href="/bialetti" class="col-xs-4 col-sm-2"><img src="https://kahhve.com/img/markalar/png/bialetti.png"></a>
					<a href="/hario" class="col-xs-4 col-sm-2"><img src="https://kahhve.com/img/markalar/png/hario.png"></a>
					<a href="/bodum" class="col-xs-4 col-sm-2"><img src="https://kahhve.com/img/markalar/png/bodum.png"></a> 
					<a href="/aeropress" class="col-xs-4 col-sm-2"><img src="https://kahhve.com/img/markalar/png/aeropress.png"></a>
					<a href="/cool-beans" class="col-xs-4 col-sm-2"><img src="https://kahhve.com/img/markalar/png/coolbeans.png"></a>
				</div> <a href="/markalarimiz" class="btn text-center">BÜTÜN MARKALARIMIZ</a>
			</section>
		</div>

		<section class="information beyaz">
			<div class="col-md-8 img">
				<div class="pull-right inner">
					<h2 class="text-center turuncu">“KAHVEYE DAİR HER ŞEY”</h2>
					<div class="text-center roboto voffset2">Kahhve.com olarak evinizde ve ofisinizde iyi bir kahve
						yapabilmek için gerekli olan her şeyi sizin için bir araya getirdik!</div>
					<p class="text-center roboto light voffset2">Taze kavrulmuş ve hemen kargoya verilen size özel
						kahveniz, kahvenizi hazırlayabilmeniz için gerekli küçük büyük her türlü ekipman, filtreler,
						değirmenler, kahvenizi mükemmelleştirmek için tarifler tüyolar ve daha niceleri Kahhve.com’da.
					</p>
				</div>
			</div>
			<div class="col-md-4 sag-bolum">
				<h2 class="text-center turuncu">OFİS KAHHVE ABONELİĞİ</h2>
				<div class="text-center voffset2">Ofisiniz beş kişi de olsa yüz kişi de olsa dilediğiniz kadar taze
					kahve dilediğiniz zaman kapınızda.</div>
				<p class="text-center roboto light voffset2">Ofisinizde hangi makinayı, hangi kahveyi kullanmanız
					gerektiğine karar veremiyor, ofisinizin kahve tedariğini kaliteli ve düzenli bir şekilde organize
					etmek istiyorsanız size yardımcı olmaktan memnuniyet duyarız.</p>
				<p class="text-center roboto light voffset2"><a href="mailto:ofis@kahhve.com"
						class="turuncu">ofis@kahhve.com</a> adresine yazın veya 0533 392 5679 telefonundan bize ulaşın
					ve hemen sizinle kahve çözümünüzü hayata geçirelim.</p>
			</div>
		</section>

		<section class="urunserit kahveler container">
			<div class="row">
				<h2 class="text-center turuncu">POPÜLER KAHHVELER</h2>
				<div class="col-md-3 col-xs-6" :key="index" v-for="(item, index) in popKahveler">
					<div class="urun">
						<a class="resim">
							<i class="icon icon-sepet back-turuncu beyaz katalog-sepete-ekle"
								v-on:click="sepeteEkle(index)"></i>
							<img class="beklemede" :src="item.image">
						</a>
						<a :href="item.url">
							<div class="title text-center">
								<span class="inner-title">{{ item.title }}</span>
							</div>
						</a>
						<a :href="item.markaurl">
							<div class="text-center marka roboto">{{ item.marka }}</div>
						</a>
						<div class="text-center fiyat">
							<p>{{ item.fiyat }} TL</p>
						</div>
					</div>
				</div>
			</div>
			<a href="kahveler.html" class="btn text-center back-turuncu">TÜMÜNÜ GÖR</a>
		</section>

		<div class="back-gray">
			<section class="urunserit container">
				<div class="row">
					<h2 class="text-center">POPÜLER EKİPMAN & AKSESUARLAR</h2>
					<div class="col-md-3 col-xs-6" :key="index" v-for="(item, index) in popEkipmanlar">
						<div class="urun">
							<a class="resim">
								<i class="icon icon-sepet back-turuncu beyaz katalog-sepete-ekle"
									v-on:click="sepeteEkle(index)"></i>
								<img class="beklemede" :src="item.image">
							</a>
							<a :href="item.url">
								<div class="title text-center">
									<span class="inner-title">{{ item.title }}</span>
								</div>
							</a>
							<a href="/hario">
								<div class="text-center marka roboto">{{ item.marka }}</div>
							</a>
							<div class="text-center fiyat">
								<p>{{ item.fiyat }} TL</p>
							</div>
						</div>
					</div>
				</div>
				<a href="kahve-demleme-ekipmanlari.html" class="btn text-center">TÜMÜNÜ GÖR</a>
			</section>
		</div>

		<div>
			<section class="urunserit container">
				<div class="row">
					<h2 class="text-center turuncu">GÜNCEL BLOG YAZILARI</h2>
					<div class="col-md-4 col-xs-12">
						<div class="urun">
							<a href="/blog/genel-bilgi/hamilelik-ve-kahve-tuketimi/">
								<img class="beklemede" src="https://kahhve.com/blog/wp-content/uploads/2019/04/85B4EC45-26AC-4691-829C-184752FA2D4A-300x300.jpg">
							</a>
							<a href="/blog/genel-bilgi/hamilelik-ve-kahve-tuketimi/">
								<div class="title text-center">
									<span class="inner-title buyuk1">HAMİLELİK VE KAHVE TÜKETİMİ</span>
								</div>
							</a>
						</div>
					</div>
					<div class="col-md-4 col-xs-12">
						<div class="urun">
							<a href="/blog/kahve/filtre-kahve-ve-kalori/">
								<img class="beklemede" src="https://kahhve.com/blog/wp-content/uploads/2019/03/BC605DE3-FEFB-45BC-89FB-A50B2FAA3713-300x300.jpg"
									alt="Filtre Kahve ve Kalori">
							</a>
							<a href="/blog/kahve/filtre-kahve-ve-kalori/">
								<div class="title text-center">
									<span class="inner-title buyuk1">FİLTRE KAHVE VE KALORİ</span>
								</div>
							</a>
						</div>
					</div>
					<div class="col-md-4 col-xs-12">
						<div class="urun">
							<a href="/blog/kahve/kahve-kavurma/">
								<img class="beklemede" src="https://kahhve.com/blog/wp-content/uploads/2019/02/147E3CA6-3A3A-411D-A26F-9F7F9005220C-300x300.jpg"
									alt="Kahve Kavurma">
							</a>
							<a href="/blog/kahve/kahve-kavurma/">
								<div class="title text-center">
									<span class="inner-title buyuk1">KAHVE KAVURMA</span>
								</div>
							</a>
						</div>
					</div>
				</div>
				<a href="/blog" class="btn text-center back-turuncu">TÜMÜNÜ GÖR</a>
			</section>
		</div>
	</div>
</template>

<script>
	export default {
		data() {
			return {
				active: false,
				cart: [],
				toplam: 0.00,
				popKahveler: [
					{
						markaurl: '/caffe-fresco',
						sepette: 'Caffe Fresco All Day Blend',
						image: 'https://kahhvecom.imgix.net/urunler/796_1550056308_k43.jpg',
						url: '/caffe-fresco-all-day-blend-kahveler',
						title: 'ALL DAY BLEND',
						marka: 'CAFFE FRESCO',
						fiyat: 21.99
					},
					{
						markaurl: '/coffee-sapiens',
						sepette: 'Coffee Sapiens Evolution Blend',
						image: 'https://kahhvecom.imgix.net/urunler/55_1521108632_Txj.jpg',
						url: '/coffee-sapiens-evolution-blend-kahveler',
						title: 'EVOLUTION BLEND',
						marka: 'COFFEE SAPIENS',
						fiyat: 39.99
					},
					{
						markaurl: '/cool-beans',
						sepette: 'Cool Beans Costa Rica',
						image: 'https://kahhvecom.imgix.net/urunler/67_1444945568_pN1.jpg',
						url: '/cool-beans-costa-rica-kahveler',
						title: 'COSTA RICA',
						marka: 'COOL BEANS',
						fiyat: 44.99
					},
					{
						markaurl: '/urban-grind',
						sepette: 'Urban Grind Guatemala Santa Barbara',
						image: 'https://kahhvecom.imgix.net/urunler/668_1550484839_u9J.jpg',
						url: '/urban-grind-guatemala-santa-barbara-kahveler',
						title: 'GUATEMALA SANTA BARBARA',
						marka: 'URBAN GRIND',
						fiyat: 49.99
					},
				],

				popEkipmanlar: [{
						markaurl: '/hario',
						sepette: 'Hario Kettle Buono 1.0 LT',
						image: 'https://kahhvecom.imgix.net/urunler/361_1469013202_cZg.jpg',
						url: '/hario-kettle-buono-10-lt-kahve-demleme-ekipmanlari',
						title: 'KETTLE BUONO 1.0 LT',
						marka: 'HARIO',
						fiyat: 279.99
					},
					{
						markaurl: '/hario',
						sepette: 'Hario Mizudashi Soğuk Demleme',
						image: 'https://kahhvecom.imgix.net/urunler/198_1444597118_LnY.jpg',
						url: '/hario-mizudashi-soguk-demleme-kahve-demleme-ekipmanlari',
						title: 'MIZUDASHI SOĞUK DEMLEME',
						marka: 'HARIO',
						fiyat: 139.99
					},
					{
						markaurl: '/hario',
						sepette: 'Hario Mini Mill Plus Skerton Öğütücü',
						image: 'https://kahhvecom.imgix.net/urunler/751_1561111234_Gug.jpg',
						url: '/hario-mini-mill-plus-skerton-ogutucu-kahve-degirmenleri',
						title: 'MINI MILL PLUS SKERTON ÖĞÜTÜCÜ',
						marka: 'HARIO',
						fiyat: 229.99
					},
					{
						markaurl: '/bialetti',
						sepette: 'Bialetti Moka Pot Kirmizi 1 Cup',
						image: 'https://kahhvecom.imgix.net/urunler/757_1543556047_ZS1.jpg',
						url: '/bialetti-moka-pot-express-kirmizi-1-cup-moka-pot',
						title: 'MOKA POT EXPRESS KIRMIZI 1 CUP',
						marka: 'BIALETTI',
						fiyat: 149.99
					},
				],

				setler: [{
						markaurl: '/aeropress',
						sepette: 'Aeropress Tanışma Seti',
						image: 'https://kahhvecom.imgix.net/urunler/789_1569671404_ASZ.jpg',
						url: '/aeropress-aeropress-tanisma-seti-kahve-tanisma-setleri',
						title: 'AEROPRESS TANIŞMA SETI',
						marka: 'AEROPRESS',
						fiyat: 329.99
					},
					{
						markaurl: '/kahhvecom',
						sepette: 'Kahhve Tanışma Seti',
						image: 'https://kahhvecom.imgix.net/urunler/92_1569671134_BG8.jpg',
						url: '/kahhvecom-tanisma-seti-kahveler',
						title: 'KAHHVE TANIŞMA SETI',
						marka: 'KAHHVECOM',
						fiyat: 49.99
					},
					{
						markaurl: '/hario',
						sepette: 'Hario V60 Tanışma Seti',
						image: 'https://kahhvecom.imgix.net/urunler/112_1569671179_VwG.jpg',
						url: '/hario-set-kahve-demleme-ekipmanlari',
						title: 'V60 TANIŞMA SETI',
						marka: 'HARIO',
						fiyat: 229.99
					},
					{
						markaurl: '/bialetti',
						sepette: 'Bialetti Moka Pot Tanışma Seti',
						image: 'https://kahhvecom.imgix.net/urunler/135_1569671319_5Up.jpg',
						url: '/bialetti-moka-pot-baslangic-seti-kahve-demleme-ekipmanlari',
						title: 'MOKA POT TANIŞMA SETI 3 CUP',
						marka: 'BIALETTI',
						fiyat: 219.99
					},
				]
			}
		},

		created() {
			this.cart = JSON.parse(localStorage.getItem('sepettekiler' || []));
			this.toplam = JSON.parse(localStorage.getItem('toplam' || []));
		},

		methods: {
			sepeteEkle(index) {
				this.cart.push(this.setler[index]);
				this.toplam += this.setler[index].fiyat;
				localStorage.setItem('sepettekiler', JSON.stringify(this.cart));
				localStorage.setItem('toplam', JSON.stringify(this.toplam));
			}
		}
	}
</script>