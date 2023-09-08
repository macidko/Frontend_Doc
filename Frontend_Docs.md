# ****Aldığım notları yazdığım, yeni öğrendiklerimi geçirdiğim ve ihtiyacım olursa dönüp bakacağım yer.****

<details>
  <summary>Gulp.js</summary>
# Gulp.js

- **Gulp Nedir ve Neden Kullanılır?**
    - [ ]  Tamam
    
    Gulp, bir JavaScript görev yöneticisi ve otomasyon aracıdır. Front-end geliştirme sürecinde tekrarlayıcı ve zaman alıcı görevleri otomatikleştirmek için kullanılır. Özellikle dosyaları işleme, dönüştürme, birleştirme, sıkıştırma ve geliştirme sunucusu gibi işlemleri hızlı ve verimli bir şekilde gerçekleştirmek için tercih edilir.
    
    **Örnek:**
    Varsayalım ki bir web projesi üzerinde çalışıyorsunuz ve proje dosyalarınızda Sass kullanıyorsunuz. Ancak her değişiklik yaptığınızda Sass dosyalarınızı CSS dosyalarına dönüştürmek ve ardından CSS dosyalarınızı minify etmek için her seferinde terminalde komutları elle çalıştırmanız gerekiyor. Bu oldukça zaman alıcı ve tekrarlayıcı bir işlem olabilir.
    
    İşte burada Gulp devreye girer. Gulp kullanarak, projenizin Gulpfile.js adlı yapılandırma dosyasında Sass dosyalarını CSS dosyalarına otomatik olarak dönüştürmeyi ve CSS dosyalarınızı minify etmeyi ayarlayabilirsiniz. Bu sayede her değişiklik yaptığınızda, Gulp otomatik olarak belirttiğiniz işlemleri yapar ve siz sadece kodunuzu yazmaya odaklanırsınız.
    
    Bu örnek, Gulp'un zaman kazandıran ve işleri otomatikleştiren özelliklerinden birini gösterir. Proje geliştirme sürecini daha verimli ve düzenli hale getirmek için Gulp'u kullanabilirsiniz.
    
- **Gulp Görevleri ve Pipe Kavramı**
    - [ ]  Tamam
    
    Gulp'u kullanmaya başlamak için öncelikle Node.js ve npm (Node Package Manager) kurulu olmalıdır. Daha sonra projenizde Gulp'u yüklemek ve Gulpfile.js adında bir yapılandırma dosyası oluşturmak gerekmektedir.
    
    ### **Örnek:**
    
    Node.js ve npm'yi bilgisayarınıza yüklediğinizden emin olduktan sonra, terminalde aşağıdaki komutla Gulp'u yükleyebilirsiniz:
    
    ### # Gulp'u global olarak yükleyin (eğer daha önce yüklemediyseniz)
    
    ```bash
    npm install -g gulp-cli
    ```
    
    ### # Projenizin klasöründe Gulp'u yükleyin
    
    ```bash
    npm install gulp --save-dev
    ```
    
    Bu komutlarla Gulp'u projenize ekledikten sonra, projenizin kök dizininde Gulpfile.js adında bir dosya oluşturmalısınız. Bu dosya, Gulp görevlerini tanımlayacağınız yapılandırma dosyasıdır.
    
    ```jsx
    // Gulpfile.js
    // Gulp modülünü yüklüyoruz
    const gulp = require('gulp');
    // Örnek bir Gulp görevi tanımlayalım
    gulp.task('message', function() {
    return console.log('Merhaba, Gulp!');
    });
    ```
    
    Yukarıdaki örnekte, Gulpfile.js dosyasında "message" adında bir Gulp görevi tanımlıyoruz. Bu görev, terminalde gulp message komutuyla çalıştırılabilir ve "Merhaba, Gulp!" mesajını verecektir.
    
    Özetle, Gulp'u projenize eklemek ve temel bir Gulp görevi tanımlamak için bu adımları takip etmeniz gerekmektedir. Gulpfile.js dosyası içinde tanımlayacağınız görevler sayesinde projenizdeki dosyaları işleyebilir, dönüştürebilir ve daha birçok otomasyon işlemini gerçekleştirebilirsiniz.
    
- **Dosyaları İşleme ve Dönüştürme (Minify, Concatenate, Uglify, vs.)**
    - [ ]  Tamam
    
    ### Dosyaları İşleme ve Dönüştürme (Minify, Concatenate, Uglify, vs.)
    
    Gulp, dosyaları işlemek ve dönüştürmek için çeşitli eklentileri destekler. Örneğin, CSS ve JavaScript dosyalarını minify (sıkıştırma), birleştirme, kodu optimize etme (uglify) gibi işlemler yapabilirsiniz.
    
    ### Örnek 1: CSS Minify ve Birleştirme
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const sass = require('gulp-sass');
    const cssnano = require('gulp-cssnano');
    const concat = require('gulp-concat');
    
    gulp.task('styles', function() {
    	return gulp.src('src/**/*.scss')
    	.pipe(sass())
    	.pipe(cssnano()) // CSS dosyalarını minify
    	.pipe(concat('all.min.css')) // Birleştirilmiş CSS dosyası
    	.pipe(gulp.dest('dist/css'));
    });
    ```
    
    Yukarıdaki örnekte, "styles" adında bir Gulp görevi tanımladık. Bu görev, "src" klasöründeki tüm .scss dosyalarını alır, Sass dönüşümü yapar, CSS dosyalarını minify eder ve birleştirir. Minify edilmiş ve birleştirilmiş CSS dosyasını "dist/css" klasörüne kaydeder.
    
    ### Örnek 2: JavaScript Uglify ve Birleştirme
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const uglify = require('gulp-uglify');
    const concat = require('gulp-concat');
    
    gulp.task('scripts', function() {
    	 return gulp.src('src/js/**/*.js')
    	.pipe(uglify()) // JavaScript dosyalarını sıkıştır (uglify)
    	.pipe(concat('all.min.js')) // Birleştirilmiş JS dosyası
    	.pipe(gulp.dest('dist/js'));
    });
    ```
    
    Yukarıdaki örnekte, "scripts" adında bir Gulp görevi tanımladık. Bu görev, "src/js" klasöründeki tüm .js dosyalarını alır, JavaScript kodunu sıkıştırır (uglify) ve birleştirir. Sıkıştırılmış ve birleştirilmiş JavaScript dosyasını "dist/js" klasörüne kaydeder.
    
    Bu örnekler, Gulp'un dosyaları işleme ve dönüştürme yeteneklerini göstermektedir. Gulp ile CSS ve JavaScript dosyalarını sıkıştırma, birleştirme ve optimize etme gibi işlemleri otomatikleştirerek projenizin performansını artırabilir ve dosyalarınızın boyutunu azaltabilirsiniz.
    
- **Gulp ile Sass ve CSS İşlemleri**
    - [ ]  Tamam
    
    ### Gulp ile Sass ve CSS İşlemleri
    
    Gulp, Sass dosyalarını CSS dosyalarına dönüştürmek ve CSS dosyalarını işlemek için çeşitli eklentileri destekler. Bu sayede CSS stil dosyalarınızı geliştirme sürecinde kolayca düzenleyebilir ve sonunda dönüştürerek projenizde kullanabilirsiniz.
    
    ### Örnek: Sass Dönüşümü ve CSS Minify
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const sass = require('gulp-sass');
    const cssnano = require('gulp-cssnano');
    
    gulp.task('styles', function() {
    	return gulp.src('src/**/*.scss')
    	.pipe(sass()) // Sass dosyalarını CSS'e dönüştürür
    	.pipe(cssnano()) // CSS dosyalarını minify eder
    	.pipe(gulp.dest('dist/css'));
    });
    ```
    
    Yukarıdaki örnekte, "styles" adında bir Gulp görevi tanımladık. Bu görev, "src" klasöründeki tüm .scss dosyalarını alır, Sass dönüşümü yapar ve sonrasında CSS dosyalarını minify eder. Dönüştürülen ve minify edilen CSS dosyalarını "dist/css" klasörüne kaydeder.
    
    Gulp ile Sass ve CSS işlemlerini bir araya getirerek stil dosyalarınızı dönüştürüp optimize edebilirsiniz. Bu sayede CSS yazım sürecinizi daha kolay ve verimli hale getirebilir, proje boyutunu küçülterek performansı artırabilirsiniz.
    
- **Gulp ile JavaScript İşlemleri**
    - [ ]  Tamam
    
    ### Gulp ile JavaScript İşlemleri
    
    Gulp, JavaScript dosyalarını birleştirme, sıkıştırma (uglify), kod kalitesini kontrol etme (linting) gibi işlemleri kolayca yapmak için çeşitli eklentileri destekler. Bu sayede JavaScript dosyalarınızı daha verimli ve optimize edilmiş hale getirebilirsiniz.
    
    ### Örnek: JavaScript Uglify ve Birleştirme
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const uglify = require('gulp-uglify');
    const concat = require('gulp-concat');
    
    gulp.task('scripts', function() {
    	 return gulp.src('src/js/**/*.js')
    	.pipe(uglify()) // JavaScript dosyalarını sıkıştırır (uglify)
    	.pipe(concat('all.min.js')) // Birleştirilmiş JS dosyası
    	.pipe(gulp.dest('dist/js'));
    });
    ```
    
    Yukarıdaki örnekte, "scripts" adında bir Gulp görevi tanımladık. Bu görev, "src/js" klasöründeki tüm .js dosyalarını alır, JavaScript kodunu sıkıştırır (uglify) ve birleştirir. Sıkıştırılmış ve birleştirilmiş JavaScript dosyasını "dist/js" klasörüne kaydeder.
    
    Gulp ile JavaScript işlemlerini kullanarak projenizdeki JavaScript dosyalarını optimize edebilir ve performansı artırabilirsiniz. Ayrıca, kod kalitesini kontrol etmek için linting araçlarını entegre ederek hataları erken aşamada tespit edebilir ve daha sağlam bir kod tabanı oluşturabilirsiniz.
    
- **Otomatik Yenileme (Live Reloading) ve Geliştirme Sunucusu**
    - [ ]  Tamam
    
    ### Otomatik Yenileme (Live Reloading) ve Geliştirme Sunucusu
    
    Gulp, tarayıcıda otomatik yenileme (live reloading) yapmak ve geliştirme sunucusu oluşturmak için çeşitli eklentileri destekler. Bu sayede projenizde yapılan değişiklikleri hızlıca görebilir ve geliştirme sürecini daha verimli hale getirebilirsiniz.
    
    ### Örnek: Tarayıcıda Otomatik Yenileme
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const browserSync = require('browser-sync').create();
    
    gulp.task('serve', function() {
    	browserSync.init({
    	server: './dist' // Geliştirme sunucusunu "dist" klasöründen başlat
    });
    
    // "dist" klasöründeki dosyalarda değişiklikleri takip eder ve tarayıcıda otomatik yenileme yapar
    gulp.watch('dist/**/*').on('change', browserSync.reload);
    });
    ```
    
    Yukarıdaki örnekte, "server" adında bir Gulp görevi tanımladık. Bu görev, "dist" klasöründeki dosyaları geliştirme sunucusu olarak başlatır ve tarayıcıda otomatik yenileme yapar. Gulp'un gulp.watch() yöntemi, "dist" klasöründeki dosyalardaki değişiklikleri izler ve herhangi bir değişiklik olduğunda tarayıcıyı otomatik olarak yeniler.
    
    Bu sayede, projenizde yapılan değişiklikleri takip edebilir ve anında tarayıcıda görüntüleyebilirsiniz. Geliştirme sürecini daha verimli hale getirir ve anlık geri bildirim almanızı sağlar.
    
    Gulp ile otomatik yenileme ve geliştirme sunucusu kullanarak, projenizi hızlı bir şekilde geliştirebilir ve önizleme yapabilirsiniz. Değişiklikleri hemen tarayıcıda görme imkanı, hataları hızlıca tespit etme ve düzeltme sürecini kolaylaştırır.
    
- **Gulp ile Resim Optimizasyonu**
    - [ ]  Tamam
    
    ### Gulp ile Resim Optimizasyonu
    
    Gulp, projenizdeki resim dosyalarını optimize etmek için çeşitli eklentileri destekler. Bu sayede resimlerin boyutunu küçülterek sayfa yüklemesini hızlandırabilir ve internet trafiğini azaltabilirsiniz.
    
    ### Örnek: Resim Optimizasyonu
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const imagemin = require('gulp-imagemin');
    
    gulp.task('images', function() {
    	 return gulp.src('src/images/**/*')
    	.pipe(imagemin()) // Resim dosyalarını optimize eder
    	.pipe(gulp.dest('dist/images'));
    });
    ```
    
    Yukarıdaki örnekte, "images" adında bir Gulp görevi tanımladık. Bu görev, "src/images" klasöründeki tüm resim dosyalarını alır ve resimleri optimize eder. Optimizasyon işlemi sonucunda elde edilen resimleri "dist/images" klasörüne kaydeder.
    
    Gulp ile resim optimizasyonu, web sitenizin hızını artırır ve kullanıcı deneyimini iyileştirir. Optimize edilmiş resimler, daha hızlı yükleme süreleri ve daha düşük veri tüketimi sağlar.
    
    Eğer başka bir Gulp konusu veya bir sonraki başlık tercihiniz varsa lütfen belirtin, size yardımcı olmaktan mutluluk duyarım.
    
- **Proje Yapılandırması ve Organizasyonu**
    - [ ]  Tamam
    
    ### Proje Yapılandırması ve Organizasyonu
    
    Gulp, projenizi daha iyi yapılandırmak ve dosyalarınızı daha düzenli tutmak için çeşitli eklentiler ve yöntemler sunar. Bu sayede, dosyalarınızın düzenini koruyabilir, işlemleri daha etkili bir şekilde yönetebilir ve projenizin bakımını kolaylaştırabilirsiniz.
    
    ### Örnek: Proje Yapılandırması ve Organizasyonu
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const sass = require('gulp-sass');
    const cssnano = require('gulp-cssnano');
    const uglify = require('gulp-uglify');
    const imagemin = require('gulp-imagemin');
    
    // Projenizin klasör yapısına uygun bir şekilde dosya yollarını tanımlayabilirsiniz
    const paths = {
    	styles: {
    	src: 'src/styles/**/*.scss',
    	dest: 'dist/css'
    	},
    	scripts: {
    	src: 'src/js/**/*.js',
    	dest: 'dist/js'
    	},
    	images: {
    	src: 'src/images/**/*',
    	dest: 'dist/images'
    	}
    };
    
    // Stil dosyalarını işleme görevi
    gulp.task('styles', function() {
    	 return gulp.src(paths.styles.src)
    	.pipe(sass())
    	.pipe(cssnano())
    	.pipe(gulp.dest(paths.styles.dest));
    });
    
    // JavaScript dosyalarını işleme görevi
    gulp.task('scripts', function() {
    	 return gulp.src(paths.scripts.src)
    	.pipe(uglify())
    	.pipe(gulp.dest(paths.scripts.dest));
    });
    
    // Resim dosyalarını optimize etme görevi
    gulp.task('images', function() {
    	 return gulp.src(paths.images.src)
    	.pipe(imagemin())
    	.pipe(gulp.dest(paths.images.dest));
    });
    
    // Tüm görevleri bir araya getirerek birleşik bir "build" görevi oluşturabilirsiniz
    gulp.task('build', gulp.parallel('styles', 'scripts', 'images'));
    
    // Geliştirme sırasında "watch" görevi ile dosyaları izleyebilirsiniz
    gulp.task('watch', function() {
    	gulp.watch(paths.styles.src, gulp.series('styles'));
    	gulp.watch(paths.scripts.src, gulp.series('scripts'));
    	gulp.watch(paths.images.src, gulp.series('images'));
    });
    ```
    
    Yukarıdaki örnekte, "paths" adında bir yapı oluşturduk ve stil, script ve resim dosyalarını tutmak için klasör yapılarını belirttik. Daha sonra bu yapıyı kullanarak "styles", "scripts" ve "images" adında üç ayrı Gulp görevi tanımladık. Her görev, belirtilen dosya yollarını kullanarak işlemleri gerçekleştirir.
    
    Ayrıca, "build" adında birleşik bir görev oluşturduk. Bu görev, gulp.parallel() ile tanımlanan diğer üç görevi aynı anda çalıştırır, böylece stil, script ve resim dosyalarınızı birleşik bir şekilde işleyebilirsiniz.
    
    Son olarak, "watch" adında bir görev oluşturduk. Bu görev, belirtilen dosya yollarındaki değişiklikleri izler ve ilgili görevleri otomatik olarak çalıştırır. Bu sayede, geliştirme sürecinde dosyalarınızdaki değişiklikleri takip edebilir ve anında işlenmiş sonuçları görebilirsiniz.
    
    Proje yapılandırması ve organizasyonu, projenizin karmaşıklığı arttıkça önemli hale gelir. Gulp ile yapılandırma ve organizasyon yöntemlerini kullanarak projenizi daha düzenli tutabilir ve iş akışınızı optimize edebilirsiniz.
    
- **Gulp ve Paket Yöneticileri ile Çalışma**
    - [ ]  Tamam
    
    Gulp, çeşitli eklentiler ve paket yöneticileri ile birlikte çalışabilir. Paket yöneticileri, Gulp ile kullanabileceğiniz hazır eklentilerin yönetimini sağlar. Bu şekilde projenizde ihtiyacınız olan eklentileri kolayca ekleyebilir ve güncelleyebilirsiniz.
    
    Gulp ile sık kullanılan paket yöneticilerinden iki tanesi npm (Node Package Manager) ve Yarn'dır.
    
    ### Örnek: Eklenti Kurulumu ve Çalıştırma
    
    ### # Eklenti kurulumu için npm
    
    ```bash
    npm install gulp-sass --save-dev
    ```
    
    ### # Eklenti kurulumu için Yarn
    
    ```bash
    yarn add gulp-sass --dev
    ```
    
    Yukarıdaki örnek, Gulp için "gulp-sass" eklentisinin kurulumunu göstermektedir. Eklentileri projenize ekledikten sonra, Gulpfile.js dosyanızda bu eklentiyi kullanabilirsiniz.
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const sass = require('gulp-sass');
    
    gulp.task('styles', function() {
    	 return gulp.src('src/styles/**/*.scss')
    	.pipe(sass())
    	.pipe(gulp.dest('dist/css'));
    });
    ```
    
    Gulpfile.js dosyanızda eklentileri yüklemek ve kullanmak için "require()" fonksiyonunu kullanarak ilgili eklentileri içe aktarabilirsiniz.
    
    Paket yöneticileri, projenizdeki bağımlılıkları yönetmek ve eklentileri hızlı bir şekilde eklemek için güçlü araçlardır. Gulp ile birlikte npm veya Yarn kullanarak ihtiyacınız olan eklentileri projenize ekleyebilir ve projenizi daha etkili bir şekilde geliştirebilirsiniz
    
- **Gulp ile Çoklu Ortam (Environment) Desteği**
    - [ ]  Tamam
    
    Projeler genellikle farklı ortamlarda (development, staging, production vb.) farklı ayarlarla çalıştırılır. Gulp, bu tür senaryolara uygun bir şekilde çoklu ortam desteği sağlar. Böylece, farklı ortamlarda farklı işlemler yapabilir veya yapılandırmaları değiştirebilirsiniz.
    
    **Örnek: Çoklu Ortam Desteği**
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const sass = require('gulp-sass');
    const cssnano = require('gulp-cssnano');
    const uglify = require('gulp-uglify');
    const imagemin = require('gulp-imagemin');
    
    // Ortama göre farklı yapılandırmalar
    const isProduction = process.env.NODE_ENV === 'production';
    // Stil dosyalarını işleme görevi
    gulp.task('styles', function() {
    	 return gulp.src('src/styles/**/*.scss')
    	.pipe(sass())
    	.pipe(isProduction ? cssnano() : gulp.dest('dist/css'));
    });
    
    // JavaScript dosyalarını işleme görevi
    gulp.task('scripts', function() {
    	 return gulp.src('src/js/**/*.js')
    	.pipe(isProduction ? uglify() : gulp.dest('dist/js'));
    });
    
    // Resim dosyalarını optimize etme görevi
    gulp.task('images', function() {
    	 return gulp.src('src/images/**/*')
    	.pipe(isProduction ? imagemin() : gulp.dest('dist/images'));
    });
    
    // Tüm görevleri birleşik bir "build" görevi oluşturabiliriz
    gulp.task('build', gulp.parallel('styles', 'scripts', 'images'));
    ```
    
    Yukarıdaki örnekte, "isProduction" adında bir değişken oluşturduk ve bu değişkeni ortama bağlı olarak atadık. Daha sonra stil, script ve resim dosyalarının işlenmesi sırasında, bu değişkeni kullanarak işlemleri belirli ortamlara göre yapmamızı sağladık.
    
    Örneğin, "isProduction" değişkeni true olduğunda, Gulp, stil dosyalarını ve JavaScript dosyalarını sıkıştırmak (minify) ve resimleri optimize etmek için ilgili eklentileri kullanır. Ancak "isProduction" değişkeni false olduğunda, Gulp, stil ve JavaScript dosyalarını optimize etmeden (minify etmeden) "dist" klasörüne kopyalar.
    
    Bu şekilde, farklı ortamlarda farklı yapılandırmalar yapabilir ve projenizin geliştirme, üretim ve diğer ortamlarda verimli bir şekilde çalışmasını sağlayabilirsiniz.
    
- **Gulp ile Paralel ve Sıralı Görevlerin Yürütülmesi**
    - [ ]  Tamam
    
    ### Gulp ile Paralel ve Sıralı Görevlerin Yürütülmesi
    
    Gulp, çeşitli görevleri paralel veya sıralı olarak yürütme yeteneğine sahiptir. Bu, projenizin ihtiyaçlarına göre iş akışını optimize etmenize yardımcı olur.
    
    ### Örnek: Paralel ve Sıralı Görevlerin Yürütülmesi
    
    ```jsx
    // Gulpfile.js
    const gulp = require('gulp');
    const sass = require('gulp-sass');
    const cssnano = require('gulp-cssnano');
    const uglify = require('gulp-uglify');
    const imagemin = require('gulp-imagemin');
    
    // Stil dosyalarını işleme görevi
    	gulp.task('styles', function() {
    	 return gulp.src('src/styles/**/*.scss')
    	.pipe(sass())
    	.pipe(cssnano())
    	.pipe(gulp.dest('dist/css'));
    });
    
    // JavaScript dosyalarını işleme görevi
    gulp.task('scripts', function() {
    	 return gulp.src('src/js/**/*.js')
    	.pipe(uglify())
    	.pipe(gulp.dest('dist/js'));
    });
    
    // Resim dosyalarını optimize etme görevi
    gulp.task('images', function() {
    	 return gulp.src('src/images/**/*')
    	.pipe(imagemin())
    	.pipe(gulp.dest('dist/images'));
    });
    
    // Paralel olarak çalışacak görevleri "build" görevine ekleyebiliriz
    gulp.task('build', gulp.parallel('styles', 'scripts', 'images'));
    
    // Sıralı olarak çalışacak görevleri "default" görevine ekleyebiliriz
    gulp.task('default', gulp.series('styles', 'scripts', 'images'));
    ```
    
    Yukarıdaki örnekte, gulp.parallel() ve gulp.series() yöntemlerini kullanarak görevleri paralel ve sıralı olarak yürütebiliriz.
    
    gulp.parallel() metodu, içine aldığı görevleri aynı anda başlatır ve paralel olarak çalışmasını sağlar. Bu sayede stil, script ve resim dosyaları aynı anda işlenir ve işlem süresi kısalır. "build" görevi örneğinde, stil, script ve resim dosyaları paralel olarak işlenir.
    
    gulp.series() metodu ise içine aldığı görevleri sırasıyla çalıştırır. Bir görevin tamamlanmasını bekler ve ardından diğer görevi başlatır. "default" görevi örneğinde, stil dosyaları işlenir, ardından script dosyaları işlenir ve en son resim dosyaları işlenir.
    
    Bu şekilde, projenizin gereksinimlerine uygun olarak görevleri paralel veya sıralı olarak düzenleyebilir ve projenizin iş akışını optimize edebilirsiniz.

</details>


<details>
  <summary>Webpack</summary>
  # Webpack

- **Webpack Nedir ve Neden Kullanılır?**
    - [ ]  Webpack'in temel amacını ve modern web geliştirme süreçlerindeki rolünü anlayın.
    - [ ]  Modüler geliştirme ve kaynak yönetimi avantajlarına göz atın.
- **Proje Ortamının Hazırlanması:**
    - [ ]  Yeni bir projede Webpack'i nasıl kullanacağınızı öğrenin.
    - [ ]  Webpack kurulumu ve temel proje yapılandırmasını gerçekleştirin.
- **Webpack Temel Kavramları:**
    - [ ]  Entry, output, loader, plugin gibi temel Webpack kavramlarını anlayın.
    - [ ]  Bir Webpack yapılandırma dosyasının (webpack.config.js) temel bileşenlerini öğrenin.
- **Modüler Geliştirme ve ES6 Modülleri:**
    - [ ]  ES6 modüllerini Webpack ile nasıl kullanacağınızı anlayın.
    - [ ]  Modüler geliştirme yaklaşımının avantajlarını öğrenin.
- **Asset Yönetimi ve Loader'lar:**
    - [ ]  Farklı türdeki dosyaları (CSS, resimler, fontlar) nasıl işleyeceğinizi öğrenin.
    - [ ]  Loader'lar aracılığıyla dosyaları nasıl dönüştüreceğinizi ve optimize edeceğinizi anlayın.
- **CSS ve Stil Yönetimi:**
    - [ ]  CSS dosyalarını Webpack üzerinden nasıl yönetebileceğinizi öğrenin.
    - [ ]  CSS loader'ı ile stil dosyalarını projenize nasıl entegre edeceğinizi öğrenin.
- **HTML ve Dinamik Sayfa Oluşturma:**
    - [ ]  HTML dosyalarını Webpack üzerinde nasıl yönetebileceğinizi anlayın.
    - [ ]  HTMLWebpackPlugin kullanarak dinamik olarak oluşturulan HTML sayfaları nasıl oluşturacağınızı öğrenin.
- **Uygulama Derleme ve Çıktı Yönetimi:**
    - [ ]  Projenizdeki kaynakları Webpack ile nasıl derleyeceğinizi ve çıktıya nasıl alacağınızı öğrenin.
    - [ ]  Derleme sonuçlarını optimize ederek hızlı ve etkili bir çıktı almayı öğrenin.
- **Plugin Kullanımı ve Özelleştirmeler:**
    - [ ]  Webpack plugin'lerini nasıl kullanacağınızı öğrenin.
    - [ ]  Popüler plugin'leri projelerinize nasıl entegre edeceğinizi öğrenin.
- **Geliştirme ve Üretim Ortamları:**
    - [ ]  Geliştirme sırasında hızlı geri bildirim ve canlı yeniden yükleme (live reloading) nasıl sağlanır öğrenin.
    - [ ]  Üretim sürümü için Webpack yapılandırmasını nasıl optimize edeceğinizi anlayın.
- **Webpack Mülkiyet Analizi ve Optimizasyonu:**
    - [ ]  Projenizdeki bağımlılıkları ve kullanılan modülleri nasıl analiz edeceğinizi öğrenin.
    - [ ]  Gereksiz veya çok büyük modülleri tespit ederek projenizin performansını nasıl artıracağınızı keşfedin.
- **Code Splitting ve Dinamik İthalat:**
    - [ ]  Webpack ile kod parçalama (code splitting) nasıl yapacağınızı anlayın.
    - [ ]  Dinamik import'lar ile uygulamanızın yük hızını nasıl optimize edeceğinizi öğrenin.
- **Advanced Loader Kullanımı ve Özelleştirmeler:**
    - [ ]  Loader'ları nasıl özelleştirebileceğinizi ve karmaşık senaryolarda nasıl kullanacağınızı öğrenin.
    - [ ]  Babel loader'ı ile karmaşık JavaScript dönüşümleri nasıl yapabileceğinizi öğrenin.
- **Webpack ve CSS Preprocessing Entegrasyonu:**
    - [ ]  SASS, LESS veya Stylus gibi CSS ön işlemcileri ile Webpack'i nasıl entegre edeceğinizi öğrenin.
    - [ ]  CSS preprocessors ile stil kodlarını nasıl yöneteceğinizi ve optimize edeceğinizi anlayın.
- **Webpack ve Modern JavaScript Özellikleri:**
    - [ ]  ES6+ ve sonraki JavaScript özelliklerini nasıl Webpack ile kullanabileceğinizi öğrenin.
    - [ ]  Babel ve Webpack'i entegre ederek modern JavaScript kodlarını desteklemeyi öğrenin.
- **Module Federation ve Mikroservis Entegrasyonu:**
    - [ ]  Module Federation konseptini öğrenerek mikroservis mimarisine nasıl uygun Webpack yapılandırmaları yapacağınızı keşfedin.
    - [ ]  Birden fazla uygulamanın bileşenlerini nasıl paylaşabileceğinizi öğrenin.
- **Webpack ve Modern Çıktı Formatları:**
    - [ ]  WebAssembly, modern JavaScript modülleri gibi farklı çıktı formatlarını nasıl kullanabileceğinizi anlayın.
    - [ ]  Webpack'in farklı platformlar için nasıl optimize edildiğini öğrenin.
- **Dynamic Import, Lazy Loading ve Prefetching:**
    - [ ]  Dinamik import'lar ile nasıl lazy loading yapacağınızı ve sayfa yükleme hızını nasıl artıracağınızı öğrenin.
    - [ ]  Prefetching ile kullanıcının ihtiyacı olmadan önce sayfaları nasıl ön yükleyeceğinizi öğrenin.
- **Webpack ve Uygulama Analizi:**
    - [ ]  Uygulamanızın performansını nasıl izleyeceğinizi ve analiz edeceğinizi öğrenin.
    - [ ]  Webpack Bundle Analyzer gibi araçlarla projenizdeki kaynakları nasıl optimize edeceğinizi öğrenin.
- **Webpack ve DevOps Entegrasyonu:**
    - [ ]  Webpack'i süreklilik akışına nasıl entegre edeceğinizi öğrenin.
    - [ ]  Üretim sürümleri, testler ve dağıtım süreçlerini nasıl optimize edeceğinizi anlayın.
</details>

<details>
  <summary>ESLint</summary>
  # ESLint

- **ESLint Nedir ve Nasıl Kurulur?**
    - ESLint'in amacı ve önemi
    - Proje kökünde ESLint kurulumu
    - Yerel ve global kurulum
- **ESLint Konfigürasyonu ve Ayar Dosyası:**
    - **`.eslintrc`** dosyasının oluşturulması
    - Kuralların ve ayarların belirlenmesi
    - Standart Ayar Kümeleri (Airbnb, Standard, vb.) kullanımı
- **Temel ESLint Kuralları ve Ayarları:**
    - İndentasyon ve girinti ayarları
    - Çift veya tek tırnak kullanımı
    - Noktalı virgül gerekliliği
    - Boşluk ve satır araları kuralları
- **Özel Kuralların Eklenmesi ve Değiştirilmesi:**
    - Kuralların değiştirilmesi veya devre dışı bırakılması
    - Projeye özgü kuralların eklenmesi
    - Özel kuralların hata seviyeleri
- **Terminal ve Editör Entegrasyonu:**
    - ESLint'i terminalden çalıştırma
    - Editör eklentileri ile kod denetimi
    - Otomatik düzeltme seçenekleri
- **Dosya ve Klasör İgnorlama:**
    - **`.eslintignore`** dosyasıyla dosya/klasörlerin atlanması
    - Test veya üretim klasörlerinin denetimi dışında bırakılması
- **ESLint ile Otomatik Kod Düzeltme:**
    - Otomatik düzeltme modunun kullanılması
    - Düzeltilebilir hataların otomatik olarak çözülmesi
- **Proje Entegrasyonu ve Süreklilik (CI/CD) Akışı:**
    - ESLint'in GitHub veya diğer CI/CD araçlarına entegrasyonu
    - Hata çıktıları ve raporların kullanımı
- **Özelleştirilmiş Kurallar ve Pluginler:**
    - Özel kuralların oluşturulması
    - Varolan kuralların özelleştirilmesi
    - Üçüncü taraf pluginlerin entegrasyonu
- **Preset Kullanımı ve Özelleştirme:**
    - Önceden belirlenmiş kurallar kümesi (preset) kullanımı
    - Preset kurallarının düzenlenmesi veya devre dışı bırakılması
- **ESLint Hooks ve Git Commit Denetimi:**
    - **`pre-commit`** ve **`pre-push`** kancalarıyla kod denetimi
    - Sadece değiştirilmiş dosyaların denetlenmesi
- **Yazılım Mimarisi ve Projeler Arası Kullanım:**
    - Modüler projelerde ESLint yapılandırması
    - Tek bir projede birden fazla ESLint kurallarının yönetimi
- **Eş Zamanlı Düzenleme Uyarıları:**
    - ESLint ile çalışırken diğer editörlerde düzenleme yaparken uyarıların görüntülenmesi
- **Uyumlu Modül Sistemi Ayarları:**
    - CommonJS, ES6 ve diğer modül sistemlerine uygun ayarlamalar
- **Özelleştirilmiş Raporlama ve Çıktılar:**
    - ESLint çıktısının raporlama formatının özelleştirilmesi
    - Kendi hatalarınıza özel mesajlar eklenmesi
- **ESLint İntegrasyonunun İleri Seviye Araçlarla Kullanımı:**
    - Linting sonuçlarının dashboardlarda görüntülenmesi (örn. SonarQube)
    - Süreklilik akışı içinde otomatik düzeltme ve test entegrasyonu
- **Takım İçi Standartların Oluşturulması ve Uygulanması:**
    - Proje ekibinde aynı kod standartlarının kullanılmasının sağlanması
    - Ortak ESLint yapılandırmalarının ve kuralların paylaşımı
- **ESLint Entegrasyonuyla Otomasyon:**
    - Örneklerle Git Hook'ları ve CI/CD araçlarıyla otomatik linting ve düzeltme akışları
</details>

<details>
  <summary>Babel</summary>
  # Babel

- **Babel Nedir ve Neden Kullanılır?**
    - Babel'in temel amacını ve modern JavaScript kodlarının tarayıcılar arasında nasıl uyumlu hale getirildiğini anlayın.
    - Eski tarayıcılarla uyumlu kod oluşturma ihtiyacını öğrenin.
- **Babel Kurulumu ve Temel Ayarlar:**
    - Bir projeye Babel'i nasıl entegre edeceğinizi ve kurulumun nasıl yapıldığını öğrenin.
    - **`.babelrc`** dosyası ile temel ayarları nasıl yapılandıracağınızı anlayın.
- **Babel ve ES6+ Dönüşümleri:**
    - ES6+ (ECMAScript 2015+) kodlarını nasıl daha eski JavaScript versiyonlarına dönüştüreceğinizi öğrenin.
    - Arrow fonksiyonlar, destructuring, let-const kullanımı gibi özelliklerin nasıl dönüştürüldüğünü anlayın.
- **Babel ve Modül Sistemi:**
    - ES6 modül formatını CommonJS veya AMD gibi farklı modül sistemlerine nasıl dönüştüreceğinizi öğrenin.
    - Module exports ve imports'un nasıl dönüştürüldüğünü anlayın.
- **Babel Preset'leri ve Plugin'leri:**
    - Babel'in standart dönüşümlerini içeren preset'leri nasıl kullanacağınızı öğrenin.
    - Özel dönüşümler için nasıl plugin'ler ekleyebileceğinizi anlayın.
- **Polyfill ve Tarayıcı Uyumluluğu:**
    - Polyfill'leri nasıl kullanarak tarayıcı uyumluluğunu artıracağınızı öğrenin.
    - Babel ile modern özellikleri eski tarayıcılarda nasıl destekleyebileceğinizi öğrenin.
- **Babel CLI ve Komut Satırı Kullanımı:**
    - Babel'i komut satırında nasıl kullanabileceğinizi öğrenin.
    - Dosyaları dönüştürmek ve çıktı almak için Babel CLI'nin temel komutlarını keşfedin.
- **Webpack ve Babel Entegrasyonu:**
    - Webpack ile Babel'i nasıl entegre edeceğinizi ve projenizde nasıl kullanacağınızı öğrenin.
    - Modern JavaScript kodları ile Babel dönüşümlerini nasıl birleştireceğinizi anlayın.
- **Geliştirme Ortamında Babel Kullanımı:**
    - Geliştirme sırasında Babel'i nasıl kullanabileceğinizi öğrenin.
    - Hot module replacement (HMR) gibi geliştirme hızını artıran özellikleri kullanmayı öğrenin.
- **Babel ve React Entegrasyonu:**
    - React projelerinde Babel'i nasıl kullanacağınızı ve JSX dönüşümlerini nasıl yapacağınızı öğrenin.
    - Babel ile React uygulamalarını nasıl optimize edeceğinizi anlayın.
- **Custom Babel Plugin Geliştirme:**
    - Kendi özel Babel plugin'lerinizi nasıl geliştirebileceğinizi öğrenin.
    - AST (Abstract Syntax Tree) yapısını anlayarak dönüşümler gerçekleştirme yöntemlerini öğrenin.
- **AST Analizi ve Manipülasyonu:**
    - Babel tarafından oluşturulan AST yapısını nasıl analiz edeceğinizi ve manipüle edeceğinizi öğrenin.
    - Programatik olarak kodları nasıl değiştirebileceğinizi anlayın.
- **Dynamic Import ve Code Splitting Dönüşümleri:**
    - Dinamik import'lar ve kod parçalama (code splitting) senaryolarını nasıl ele alabileceğinizi öğrenin.
    - Projenizde dinamik import'ları nasıl optimize edeceğinizi keşfedin.
- **Babel ve Decorator Kullanımı:**
    - Decorator'ları nasıl kullanabileceğinizi ve dönüştürebileceğinizi öğrenin.
    - Decorator'larla kodları nasıl genişletebileceğinizi anlayın.
- **Babel ve Uygulama Analizi:**
    - Babel ile oluşturulan çıktıları nasıl analiz edeceğinizi ve projenizdeki dönüşümleri nasıl izleyeceğinizi öğrenin.
    - Babel tarafından üretilen çıktının performansını ve kalitesini nasıl değerlendireceğinizi öğrenin.
- **WebPack ve Babel Optimize Edilmiş Projeler:**
    - Babel'i Webpack ile nasıl entegre edip optimize edilmiş projeler oluşturabileceğinizi öğrenin.
    - Geliştirme ve üretim sürümleri için Babel ve Webpack'i nasıl yapılandırmanız gerektiğini öğrenin.
- **Module Resolution ve Path Mapping:**
    - Babel'da modül çözümlemesini (module resolution) nasıl yöneteceğinizi öğrenin.
    - Alias ve path mapping ile modül yollarını nasıl daha kolay yönetebileceğinizi anlayın.
- **Babel ve Çevirici Araçlar Entegrasyonu:**
    - Babel'i çevirici araçlarla (transpiler tools) nasıl entegre edebileceğinizi öğrenin.
    - Projenizde Babel'i kullanarak farklı dil özelliklerini nasıl destekleyeceğinizi öğrenin.
- **Syntax Plugin'leri ve Özelleştirme:**
    - Babel syntax plugin'leri ile dil özelliklerini nasıl genişletebileceğinizi öğrenin.
    - Özelleştirilmiş dönüşümler ve dil özellikleri ekleyerek kodu nasıl geliştirebileceğinizi anlayın.
- **Polyfill ve Kod Entegrasyonu:**
    - Projenizde Babel polyfill'lerini nasıl kullanacağınızı ve tarayıcı uyumluluğunu nasıl artıracağınızı öğrenin.
    - Babel ile polyfill'leri nasıl entegre edeceğinizi anlayın.
</details>

<details>
  <summary>Cypress</summary>
  # Cypress

Cypress, web uygulamalarının otomasyon testlerini yazmak ve çalıştırmak için kullanılan popüler bir JavaScript tabanlı test otomasyon aracıdır

1. **Cypress Kurulumu:**
    - Node.js'in kurulu olduğundan emin olun.
    - Projenizin kök dizininde **`npm install cypress`** veya **`yarn add cypress`** komutunu kullanarak Cypress'ı projenize ekleyin.
    - Cypress'ı başlatmak için **`npx cypress open`** komutunu kullanın.
2. **İlk Testi Oluşturma:**
    - Cypress ile bir test dosyası oluşturun ve temel bir test senaryosu yazın.
    - Test senaryosunu **`it`** blokları içine yazarak başlayın.
    - Web tarayıcısını açın, bir URL'ye gitmeyi simüle edin ve birkaç basit eylem gerçekleştirin (tıklama, yazma vb.).
3. **Assert (Doğrulama):**
    - Cypress ile bir sayfada bulunan öğeleri seçin (örneğin, **`cy.get()`** ile).
    - Seçilen öğelerin beklenen durumlarını doğrulayın (örneğin, **`should`** komutu ile).
4. **Test Raporları:**
    - Cypress'ın kendi içinde sağladığı test raporlarını inceleyin.
    - İşlevselliği daha iyi anlamak için hata durumlarını kontrol edin.
5. **Test Konfigürasyonu:**
    - Cypress'ı özelleştirmek için **`cypress.json`** dosyasını kullanın.
    - Tarayıcı seçeneklerini, başlangıç URL'sini ve diğer yapılandırmaları burada ayarlayabilirsiniz.

**İleri Düzey Cypress JS Çalışma Başlıkları:**

1. **Custom Commands (Özel Komutlar):**
    - Kendi özel komutlarınızı tanımlayarak testlerinizi daha okunabilir ve yeniden kullanılabilir hale getirin.
2. **Fixture Data (Veri Görseli):**
    - Dışarıdan veri yüklemek için Fixture dosyalarını kullanmayı öğrenin.
3. **Page Object Model (Sayfa Nesnesi Modeli):**
    - Büyük ve karmaşık test senaryolarını daha iyi organize etmek için Page Object Model (POM) kullanmayı öğrenin.
4. **API Testleri:**
    - Cypress ile API testleri yazmayı ve uygulamanızın arka uç hizmetlerini test etmeyi öğrenin.
5. **Çoklu Tarayıcı Desteği:**
    - Cypress ile farklı tarayıcıları (Chrome, Firefox, Edge vb.) kullanarak testleri çalıştırmayı deneyin.
6. **Eşzamanlı Testler:**
    - Paralel test çalıştırmayı öğrenerek test sürelerini hızlandırın.
7. **Test Veri Yönetimi:**
    - Dinamik verileri test senaryolarınıza nasıl dahil edeceğinizi ve yöneteceğinizi öğrenin.
8. **CI/CD Entegrasyonu:**
    - CI/CD araçları ile Cypress testlerini nasıl entegre edeceğinizi öğrenin (örneğin, Jenkins, Travis CI, CircleCI vb.).
</details>

<details>
  <summary>MobX</summary>
  # MobX

MobX, JavaScript uygulamalarında durum yönetimi için kullanılan bir durum yönetimi kütüphanesidir.

**Başlangıç Düzeyi MobX Çalışma Başlıkları:**

1. **MobX Temel Kavramlar:**
    - MobX nedir ve neden kullanılır?
    - MobX ile reaktif programlamanın temel kavramlarını anlayın.
2. **MobX Kurulumu:**
    - Bir projeye MobX'i nasıl ekleyeceğinizi ve konfigüre edeceğinizi öğrenin.
    - npm veya yarn gibi paket yöneticilerini kullanarak MobX kurulumunu gerçekleştirin.
3. **Durum (State) Yönetimi:**
    - MobX ile uygulamanızın durumunu nasıl yöneteceğinizi öğrenin.
    - Gözlemlenebilir durum nesneleri (observable state objects) oluşturmayı ve değiştirmeyi inceleyin.
4. **Reaksiyonlar ve Tepkiler (Reactions):**
    - MobX ile reaksiyonlar (reactions) oluşturmayı ve durum değişikliklerine nasıl tepki vereceğinizi öğrenin.
    - **`autorun`**, **`when`**, **`reaction`** gibi reaksiyon türlerini inceleyin.
5. **Eylemler (Actions):**
    - MobX eylemleri (actions) ile durumu nasıl değiştireceğinizi öğrenin.
    - **`action`**, **`runInAction`**, **`flow`** gibi eylem türlerini kullanmayı inceleyin.

**İleri Düzey MobX Çalışma Başlıkları:**

1. **Türetilmiş Durum ve Türetilmiş Veri (Computed State and Derivations):**
    - MobX ile türetilmiş durumları ve verileri nasıl oluşturacağınızı öğrenin.
    - **`@computed`**, **`@derive`** gibi türetilmiş verileri inceleyin.
2. **Dış Verileri Entegre Etme:**
    - MobX'i API çağrıları, WebSocket bağlantıları ve dış veri kaynakları ile nasıl entegre edeceğinizi öğrenin.
    - MobX'ı Redux veya GraphQL ile nasıl birleştireceğinizi inceleyin.
3. **Seri Hata İşleme ve Hata Ayıklama:**
    - MobX ile hataları nasıl işleyebileceğinizi ve hata ayıklama süreçlerini nasıl iyileştirebileceğinizi öğrenin.
4. **MobX ve React Entegrasyonu:**
    - MobX ile React uygulamalarını nasıl entegre edeceğinizi öğrenin.
    - MobX React'i kullanarak bileşenlerinizi nasıl bağlayacağınızı inceleyin.
5. **Performans İyileştirmeleri:**
    - MobX performansını artırmak için öğeleri nasıl memoize edeceğinizi ve seçici yeniden işleme nasıl izin vereceğinizi öğrenin.
6. **MobX Proje Yapılandırması ve Mimari:**
    - Büyük ölçekli projeler için MobX mimari ve proje yapılandırmasını nasıl optimize edeceğinizi inceleyin.
</details>

<details>
  <summary>GraphQL</summary>
  # GraphQL

GraphQL, API geliştirmek ve sorgulamak için kullanılan bir veri sorgulama dilidir.

**Başlangıç Düzeyi GraphQL Çalışma Başlıkları:**

1. **GraphQL Temel Kavramlar:**
    - GraphQL'in ne olduğunu ve neden kullanıldığını anlayın.
    - GraphQL terminolojisi ve temel kavramları öğrenin (Sorgu, Mutasyon, Şema, Alanlar vb.).
2. **GraphQL Sorguları:**
    - GraphQL sorgularını nasıl oluşturacağınızı öğrenin.
    - Alanlar, parametreler ve dönen veriler hakkında temel bilgi edinin.
3. **GraphQL Şemaları ve Tip Tanımları:**
    - GraphQL şemalarını nasıl oluşturacağınızı ve tip tanımlarını nasıl kullanacağınızı öğrenin.
    - Özel tipler ve bağlantılar oluşturma yeteneklerini inceleyin.
4. **GraphQL Sunucu Kurulumu:**
    - Node.js, Express veya başka bir sunucu çerçevesi kullanarak GraphQL sunucusu nasıl kurulacağınızı öğrenin.
    - GraphQL sorgularını işlemek için GraphQL middleware veya kütüphanelerini nasıl kullanacağınızı anlayın.
5. **GraphQL İstemcileri:**
    - GraphQL sorgularını göndermek ve yanıtları işlemek için GraphQL istemcilerini (Apollo Client, Relay, vs.) nasıl kullanacağınızı öğrenin.

**İleri Düzey GraphQL Çalışma Başlıkları:**

1. **GraphQL Mutasyonları:**
    - GraphQL mutasyonlarını kullanarak veri değişikliklerini nasıl yapacağınızı öğrenin.
    - Sunucu tarafında veri güncelleme ve silme işlemleri nasıl gerçekleştirilir.
2. **Fragmentlar ve Fragmant Spread'leri:**
    - GraphQL fragmentlarını nasıl kullanacağınızı öğrenin.
    - Fragmanlarla tekrar kullanılabilir sorgular oluşturmayı anlayın.
3. **Derinlemesine Sorgular:**
    - GraphQL ile derinlemesine sorgular (nested queries) nasıl oluşturacağınızı öğrenin.
    - İlgili verileri tek bir sorguda nasıl alabileceğinizi inceleyin.
4. **GraphQL Güvenliği:**
    - GraphQL sorgularını güvence altına almak için güvenlik önlemlerini öğrenin.
    - Veri sızıntısı ve sorgu taşımalarını nasıl engelleyeceğinizi anlayın.
5. **GraphQL Performans İyileştirmeleri:**
    - GraphQL sorgularını optimize etmek için sorgu analizi ve veri önbelleği kullanmayı öğrenin.
    - Veri isteği ve gönderimini nasıl azaltacağınızı inceleyin.
6. **GraphQL ve Microservices:**
    - GraphQL'i mikroservis mimarileri ile nasıl kullanabileceğinizi öğrenin.
    - Çeşitli hizmetlerden veri birleştirme tekniklerini inceleyin.
7. **Subscription'lar (Abonelikler):**
    - GraphQL aboneliklerini kullanarak gerçek zamanlı veri akışlarını nasıl oluşturacağınızı öğrenin.
    - WebSocket ve Push tekniklerini inceleyin.
</details>
<details>
  <summary>Docker</summary>
  # Docker

Docker, konteyner teknolojisi kullanarak uygulamaların hızlı ve taşınabilir bir şekilde çalıştırılmasını sağlayan bir platformdur. 

**Başlangıç Düzeyi Docker Çalışma Başlıkları:**

1. **Docker Temel Kavramlar:**
    - Docker nedir ve neden kullanılır?
    - Konteyner kavramı, Docker imajları ve Docker konteynerleri gibi temel kavramları öğrenin.
2. **Docker Kurulumu:**
    - İşletim sisteminize uygun şekilde Docker'ı nasıl kuracağınızı öğrenin.
    - Docker Engine ve Docker Compose gibi araçları nasıl yükleyeceğinizi anlayın.
3. **Docker Konteynerleri Oluşturma:**
    - Dockerfile kullanarak kendi Docker imajlarınızı nasıl oluşturacağınızı öğrenin.
    - İmajlarınızı nasıl inşa edip, sürümleyip ve paylaşabileceğinizi inceleyin.
4. **Konteynerleri Çalıştırma ve Yönetme:**
    - Docker komutları ile konteynerleri nasıl başlatacağınızı ve yöneteceğinizi öğrenin.
    - Çalışan konteynerleri nasıl gözden geçireceğinizi ve durduracağınızı anlayın.
5. **Konteyner İçinde Uygulama Yönetimi:**
    - Konteynerler içinde uygulamaları nasıl yükleyeceğinizi ve yapılandıracağınızı öğrenin.
    - Docker içindeki uygulamaların bağlantılarını ve iletişimini nasıl sağlayacağınızı inceleyin.

**İleri Düzey Docker Çalışma Başlıkları:**

1. **Docker Compose ve Çoklu Konteyner Uygulamaları:**
    - Docker Compose kullanarak çoklu konteynerli uygulamaları nasıl tanımlayacağınızı ve yöneteceğinizi öğrenin.
    - Birden fazla servisin nasıl bir arada çalıştırılacağını inceleyin.
2. **Konteyner Ağı ve İletişim:**
    - Docker ağlarını nasıl oluşturacağınızı ve konteynerler arasında nasıl iletişim kuracağınızı öğrenin.
    - İç ağlar, dışarıdan erişim ve port yönlendirmesi gibi konuları inceleyin.
3. **Docker Güvenliği ve İzolasyon:**
    - Konteynerler arasında güvenlik ve izolasyon sağlama stratejilerini öğrenin.
    - Güvenlik en iyi uygulamaları, imza doğrulama ve saldırı tespitini inceleyin.
4. **Konteyner İzleme ve Günlükleme:**
    - Konteynerlerin performansını nasıl izleyeceğinizi ve günlüklerini nasıl yöneteceğinizi öğrenin.
    - Grafana, Prometheus ve ELK yığını gibi izleme araçlarını kullanmayı inceleyin.
5. **Docker ve Orkestrasyon Araçları:**
    - Docker Swarm ve Kubernetes gibi orkestrasyon araçlarıyla nasıl entegre çalışacağınızı öğrenin.
    - Büyük ölçekli uygulamaları nasıl yöneteceğinizi inceleyin.
6. **Docker ve CI/CD Entegrasyonu:**
    - Docker'ı sürekli entegrasyon/sürekli dağıtım (CI/CD) süreçlerinize nasıl entegre edeceğinizi öğrenin.
</details>
<details>
  <summary>Axios</summary>
  # Axios

Axios, JavaScript ve Node.js uygulamalarında HTTP istekleri yapmak için kullanılan bir HTTP istemcisidir.

**Başlangıç Düzeyi Axios Çalışma Başlıkları:**

1. **Axios Temel Kavramlar:**
    - Axios'un nedir ve neden tercih edildiğini anlayın.
    - HTTP istemcileri ve Axios arasındaki farkları öğrenin.
2. **Axios Kurulumu:**
    - Bir projeye Axios'u eklemek için npm veya yarn gibi paket yöneticilerini kullanmayı öğrenin.
    - Axios'un nasıl başlatılacağını ve temel yapılandırmalarını nasıl yapılacağını anlayın.
3. **GET İstekleri:**
    - Axios kullanarak HTTP GET istekleri nasıl gönderileceğinizi öğrenin.
    - URL parametreleri eklemeyi ve yanıtları işlemeyi inceleyin.
4. **POST ve Diğer HTTP İstekleri:**
    - POST, PUT, DELETE gibi HTTP isteklerini Axios ile nasıl göndereceğinizi öğrenin.
    - Veri gönderme, başlık ekleme ve yanıtları işleme konularını inceleyin.
5. **Hata İşleme:**
    - Axios ile istek sırasında ve yanıtları işlerken hata yönetimini nasıl yapılacağını öğrenin.

**İleri Düzey Axios Çalışma Başlıkları:**

1. **İnterseptörler (Interceptors):**
    - Axios interseptörlerini kullanarak isteklerinizi nasıl düzenleyebileceğinizi öğrenin.
    - İstek ve yanıtları ön işlemek ve son işlemek için interseptörlerin kullanımını inceleyin.
2. **Axios İş Akışı ve Paralel İstekler:**
    - Birden fazla Axios isteğini nasıl koordine edeceğinizi ve paralel isteklerin nasıl yapılacağını öğrenin.
3. **Axios ile Dosya Yükleme ve İndirme:**
    - Axios ile dosya yükleme (file upload) ve indirme (file download) işlemlerini nasıl gerçekleştireceğinizi öğrenin.
4. **Axios ile Oturum Yönetimi ve Kimlik Doğrulama:**
    - Axios ile oturum yönetimi ve kimlik doğrulama işlemlerini nasıl uygulayacağınızı inceleyin.
5. **Axios ve Axios İnterseptörleri ile Güvenlik:**
    - Axios ile güvenlik önlemleri ve oturum açma işlemleri nasıl gerçekleştirileceğini öğrenin.
6. **Axios ve Axios Mock Adapter:**
    - Axios Mock Adapter ile testlerde Axios isteklerini nasıl taklit edebileceğinizi öğrenin.
7. **Axios ile WebSockets Entegrasyonu:**
    - Axios ile WebSocket istemcileri ile nasıl entegrasyon yapabileceğinizi inceleyin.
</details>
<details>
  <summary>AJAX</summary>
  # AJAX

AJAX (Asynchronous JavaScript and XML), web sayfalarında veri alışverişi için kullanılan önemli bir tekniktir.

**Başlangıç Düzeyi AJAX Çalışma Başlıkları:**

1. **Temel AJAX Kavramları:**
    - AJAX'ın ne olduğunu ve nasıl çalıştığını anlayın.
    - Sunucu ile istemci arasında veri alışverişi yapabilen asenkron bir teknik olduğunu kavrayın.
2. **XMLHttpRequest Nesnesi:**
    - **`XMLHttpRequest`** nesnesini kullanarak AJAX istekleri göndermeyi öğrenin.
    - Veri alma, gönderme ve yanıtları işleme işlemlerini anlayın.
3. **AJAX İstekleri Gönderme:**
    - GET ve POST gibi farklı HTTP yöntemleri kullanarak AJAX istekleri göndermeyi öğrenin.
    - İstek başlıklarını ve veri gövdesini ayarlayabilme yeteneğini anlayın.
4. **AJAX Yanıtlarını İşleme:**
    - AJAX yanıtlarını işlemek için **`XMLHttpRequest`** kullanarak veriyi çıkartmayı ve ekranda görüntülemeyi öğrenin.
    - JSON yanıtlarını ayrıştırmayı ve kullanmayı anlayın.
5. **Hata Yönetimi:**
    - AJAX isteklerinde meydana gelebilecek hataları yakalayıp işlemeyi öğrenin.
    - İstek zaman aşımı ve ağ hataları gibi durumlar için uygun hata işleme stratejilerini uygulayın.

**İleri Düzey AJAX Çalışma Başlıkları:**

1. **AJAX Kütüphaneleri ve Framework'leri:**
    - jQuery, Axios, Fetch API gibi AJAX kütüphanelerini veya framework'leri kullanmayı öğrenin.
    - Bu araçların sunduğu kolaylıkları ve avantajları keşfedin.
2. **CORS (Cross-Origin Resource Sharing):**
    - CORS kavramını anlayın ve farklı alan adları arasında AJAX istekleri yaparken karşılaşılan güvenlik kısıtlamalarını ele almayı öğrenin.
3. **XML ve JSON ile Veri İşleme:**
    - XML ve JSON formatlarını kullanarak AJAX ile veri alışverişi yapmayı öğrenin.
    - İlgili verileri ayrıştırma ve kullanma tekniklerini geliştirin.
4. **AJAX ile Form Gönderme:**
    - Web formlarını AJAX ile sunucuya göndermeyi ve yanıtlarını işlemeyi öğrenin.
    - Form doğrulama ve geri bildirim işlemlerini entegre edin.
5. **AJAX Güvenliği:**
    - AJAX isteklerini güvenli hale getirmek için güvenlik önlemlerini öğrenin, özellikle veri doğrulama ve oturum yönetimi.
6. **Real-Time Uygulamalar:**
    - WebSocket ve WebRTC gibi teknolojileri kullanarak gerçek zamanlı uygulamalar oluşturmayı öğrenin.
7. **AJAX Entegrasyonu:**
    - AJAX'ı farklı platformlar, hizmetler ve API'lerle entegre etmeyi öğrenin, örneğin RESTful API'ler veya GraphQL kullanımı.
8. **Performans İyileştirmeleri:**
    - AJAX isteklerini optimize etmek için veri ön bellekleme, istek birleştirme ve gecikme yüklemesi gibi teknikleri kullanmayı öğrenin.
</details>
<details>
  <summary>Jest</summary>
  # Jest

Jest, JavaScript uygulamaları için bir test çerçevesidir ve genellikle React, Vue.js, ve Angular gibi JavaScript tabanlı uygulamaların test edilmesinde kullanılır. 

**Başlangıç Düzeyi Jest Çalışma Başlıkları:**

1. **Jest'in Temel Kavramları:**
    - Jest nedir ve neden kullanılır?
    - Test çerçevesi, asertif fonksiyonlar ve test dosyaları hakkında temel bilgileri öğrenin.
2. **Jest Kurulumu:**
    - Bir projeye Jest'i eklemek için Node.js ve npm veya yarn kullanarak nasıl kurulacağınızı öğrenin.
    - Jest'i projenize yerel olarak veya global olarak kurma seçeneklerini inceleyin.
3. **İlk Jest Testi:**
    - Basit bir Jest testi oluşturun.
    - Bir test dosyası oluşturun, temel asertiflerle (beklenen sonuçların kontrolü) bir test senaryosu yazın ve testi çalıştırın.
4. **Test Klasörleri ve Modülleri:**
    - Jest ile test dosyalarını ve test klasörlerini nasıl organize edeceğinizi öğrenin.
    - Testlerinizi ayrı modüllerde nasıl tanımlayacağınızı inceleyin.
5. **Test Çalıştırma ve Sonuçları:**
    - Jest'i kullanarak testleri nasıl çalıştıracağınızı ve sonuçları nasıl inceleyeceğinizi öğrenin.
    - Başarılı ve başarısız testleri nasıl tanımlayacağınızı anlayın.

**İleri Düzey Jest Çalışma Başlıkları:**

1. **Mock'lar ve Simülasyonlar:**
    - Jest ile mocklar ve simülasyonlar oluşturmayı ve harici bağımlılıkları testlerinizden izole etmeyi öğrenin.
2. **Asenkron Testler:**
    - Asenkron işlemleri (AJAX istekleri, zamanlayıcılar vb.) test etmeyi öğrenin.
    - Jest'in asenkron testlerle nasıl başa çıktığını anlayın.
3. **Testlerin Konfigürasyonu:**
    - Jest'i özelleştirmek için jest.config.js dosyasını nasıl kullanacağınızı öğrenin.
    - Özel ayarlar, modülleri nasıl yükleneceği ve test çerçevesi davranışı gibi konuları ele alın.
4. **Snapshot Testleri:**
    - Özellikle React veya Vue.js gibi UI kitaplıkları ile çalışırken, görüntü snapshot'ları oluşturmayı ve karşılaştırmayı öğrenin.
5. **Test Kapsamı ve Performans:**
    - Testlerinizi optimize etmek ve yavaş testleri tanımlamak için Jest'in kapsam seçeneklerini nasıl kullanacağınızı öğrenin.
6. **Test Otomasyonu:**
    - Jest'i CI/CD süreçlerine nasıl entegre edeceğinizi öğrenin.
    - Testlerin otomatik olarak nasıl çalıştırılacağını ve raporlanacağını anlayın.
7. **Özelleştirilmiş Asertifler:**
    - Jest'teki varsayılan asertiflerin ötesine geçerek özelleştirilmiş asertifler oluşturmayı öğrenin.
8. **Test Deneyimi ve İyi Uygulamalar:**
    - Jest ve testlerinizi daha etkili bir şekilde kullanmak için en iyi uygulamaları ve test deneyimini nasıl geliştirebileceğinizi öğrenin.
</details>
<details>
  <summary>Tailwind</summary>
  # Tailwind

- **Tailwind CSS Nedir ve Neden Kullanılır?**
    - [ ]  Tailwind CSS'in ne olduğunu ve geliştirme sürecini nasıl hızlandırdığını anlayın.
    - [ ]  CSS framework'ünün temel prensiplerini kavrayın.
- **Proje Ortamının Hazırlanması:**
    - [ ]  Bir projeye Tailwind CSS entegrasyonunu nasıl gerçekleştireceğinizi öğrenin.
    - [ ]  Tailwind CSS'i projenize nasıl kuracağınızı ve ayarlayacağınızı anlayın.
- **Temel Class Kullanımı:**
    - [ ]  Tailwind CSS'in temel sınıflarını (class'larını) nasıl kullanacağınızı öğrenin.
    - [ ]  Grid, renkler, tipografi gibi temel stilleri uygulama.
- **Responsive Tasarım ve Media Sorguları:**
    - [ ]  Responsive tasarımı nasıl oluşturacağınızı ve media sorgularını nasıl kullanacağınızı anlayın.
    - [ ]  Farklı cihaz boyutlarına göre stil ayarlamaları yapma.
- **Flexbox ve Grid Kullanımı:**
    - [ ]  Tailwind CSS ile nasıl kolayca flexbox ve grid yapıları oluşturabileceğinizi öğrenin.
    - [ ]  Layout oluşturma ve hızlı bir şekilde özelleştirme yapma.
- **Component Temelli Geliştirme:**
    - [ ]  Tailwind CSS ile bileşen temelli bir geliştirme yaklaşımı benimseme.
    - [ ]  Component'leri nasıl oluşturup özelleştireceğinizi öğrenin.
- **Class Gruplamaları ve Sınıfları Özelleştirme:**
    - [ ]  Sınıfları nasıl gruplayacağınızı ve özelleştireceğinizi öğrenin.
    - [ ]  Kullanmadığınız sınıfları projeden nasıl kaldıracağınızı anlayın.
- **Class Ekleme ve Çıkartma:**
    - [ ]  Tailwind CSS'in class ekleme ve çıkartma yeteneklerini nasıl kullanacağınızı öğrenin.
    - [ ]  Gereksiz sınıfları çıkartarak stil kodunuzu optimize etme.
- **Custom Utility Oluşturma:**
    - [ ]  Kendi özel utility class'larınızı nasıl oluşturacağınızı ve kullanacağınızı anlayın.
    - [ ]  Projenize özel özellikleri Tailwind CSS ile nasıl uygulayacağınızı öğrenin.
- **Dökümantasyon ve Kaynaklara Erişim:**
    - [ ]  Resmi Tailwind CSS dökümantasyonunu nasıl kullanacağınızı öğrenin.
    - [ ]  Tailwind CSS ekosistemi içindeki kaynaklardan nasıl yararlanabileceğinizi öğrenin.
- **Özelleştirilmiş Konfigürasyon ve Ayarlar:**
    - [ ]  Tailwind CSS'in varsayılan ayarlarını nasıl özelleştireceğinizi öğrenin.
    - [ ]  Kendi renk paletlerinizi, font ayarlarınızı ve diğer özellikleri nasıl tanımlayacağınızı anlayın.
- **Stil Genişletme ve Doğrusal Özelleştirmeler:**
    - [ ]  Tailwind CSS'in sunduğu stil tabanlarını nasıl genişletebileceğinizi öğrenin.
    - [ ]  Özel stilleri nasıl oluşturup projenizde kullanacağınızı keşfedin.
- **Plugin Entegrasyonu ve Eklentiler:**
    - [ ]  Tailwind CSS'e eklenti nasıl ekleyebileceğinizi öğrenin.
    - [ ]  Popüler eklentileri projelerinize nasıl entegre edeceğinizi anlayın.
- **Stil Kullanımı ve Temalar:**
    - [ ]  Farklı projelerde benzer stilleri nasıl kullanabileceğinizi öğrenin.
    - [ ]  Proje temalarını nasıl hızlı bir şekilde uygulayabileceğinizi anlayın.
- **CSS Animasyonları ve Geçişler:**
    - [ ]  Tailwind CSS ile nasıl animasyon ve geçişler oluşturacağınızı öğrenin.
    - [ ]  Hover etkileri, fade-in/fade-out gibi animasyonları nasıl tasarlayacağınızı keşfedin.
- **State ve Focus Durumları:**
    - [ ]  Tailwind CSS ile etkileşimli bileşenlerin nasıl tasarlanacağını öğrenin.
    - [ ]  Hover, focus ve active durumlarına özel stil uygulamalarını öğrenin.
- **Advanced Grid ve Layout Tasarımı:**
    - [ ]  Grid sistemini daha karmaşık düzenlerde nasıl kullanabileceğinizi öğrenin.
    - [ ]  Flexbox ve grid'i birleştirerek daha özelleştirilmiş layout'lar oluşturma.
- **Kompleks Bileşen Tasarımı:**
    - [ ]  Karmaşık bileşenleri Tailwind CSS ile nasıl tasarlayacağınızı öğrenin.
    - [ ]  Tab menüler, akordionlar, karuseller gibi bileşenleri nasıl oluşturabileceğinizi anlayın.
- **Optimizasyon ve Performans Artırma:**
    - [ ]  Tailwind CSS stil kodlarını nasıl daha küçük boyutta ve hızlı yüklenebilir hale getireceğinizi öğrenin.
    - [ ]  Critical CSS ve diğer optimizasyon tekniklerini keşfedin.
- **Accessibilite (Erişilebilirlik) ve Tailwind CSS:**
    - [ ]  Tailwind CSS kullanırken erişilebilirlik kurallarını nasıl uygulayacağınızı öğrenin.
    - [ ]  Erişilebilirlik konseptlerini uygulayarak projelerinizi daha kullanıcı dostu hale getirme yöntemlerini öğrenin.
</details>
<details>
  <summary>SASS</summary>
  # Sass

- **SASS Nedir ve Neden Kullanılır?**
    - [ ]  SASS'ın CSS geliştirmeyi nasıl kolaylaştırdığını anlayın.
    - [ ]  Nesting, Variables, Mixins gibi SASS'ın sağladığı özelliklerin avantajlarını öğrenin.
- **SASS ve SCSS Ayrımı:**
    - [ ]  SASS ve SCSS (Sassy CSS) arasındaki farkları anlayın.
    - [ ]  Hangi sözdizimini tercih edeceğinizi seçin.
- **SASS Çalışma Ortamının Hazırlanması:**
    - [ ]  SASS'ı kurun (Node.js gerekebilir).
    - [ ]  Projeye SASS entegrasyonu (örneğin, npm veya başka bir paket yöneticisi ile).
- **Değişkenler ve Kullanımı:**
    - [ ]  Değişkenleri tanımlama ve kullanma.
    - [ ]  Renkler, genişlikler gibi yaygın değerleri değişkenlerle nasıl yöneteceğinizi öğrenin.
- **Nesting (İç İçe Geçme):**
    - [ ]  Stilleri daha okunabilir hale getirmek için iç içe geçme.
    - [ ]  Sınıf seçicilerini daha hiyerarşik bir şekilde yazma.
- **Mixin'ler ve Extend'ler:**
    - [ ]  Mixin'lerle stil parçalarını yeniden kullanma.
    - [ ]  Extend'lerle birden çok sınıfa aynı stil özelliklerini eklemenin avantajlarını anlayın.
- **Operatörler ve İşlemler:**
    - [ ]  Matematiksel işlemleri ve operatörleri kullanma.
    - [ ]  Renkleri karıştırma veya genişlik hesaplamaları gibi örnekler.
- **Import ve Parçalama:**
    - [ ]  **`@import`** ile stil dosyalarını bölmek ve modülerleştirmek.
    - [ ]  Farklı parçaları birleştirirken hangi yaklaşımı benimsemeniz gerektiğini anlayın.
- **Kod Organizasyonu ve Modülerlik:**
    - [ ]  Büyük projelerde kodu nasıl düzenli ve yönetilebilir hale getireceğinizi öğrenin.
    - [ ]  Parçalama, stil dosyalarının yapısı ve modülerlik konularını kavrayın.
- **Derleme ve Üretim:**
    - [ ]  SASS kodlarını tarayıcı anlayabilecek CSS'e dönüştürme (derleme).
    - [ ]  Geliştirme aşamasında ve üretimde SASS kullanmanın farklarını anlayın.
- **Fonksiyonlar ve Mixin'ler:**
    - [ ]  Özelleştirilmiş mixin'ler ve fonksiyonlar oluşturma.
    - [ ]  Matematiksel hesaplamalar, renk işlemleri gibi fonksiyonları kullanma.
- **Extend Kullanımı ve Kısıtlamaları:**
    - [ ]  Extend ile stil paylaşımı ve stil öğelerinin tekrar kullanımı.
    - [ ]  Extend kullanırken nelere dikkat etmeniz gerektiğini anlama.
- **Yerel ve Global Değişkenler:**
    - [ ]  Değişkenleri yerel veya global olarak tanımlama ve kullanma.
- **Operatörler ve Hesaplamalar:**
    - [ ]  Renk ve genişlik değerlerini daha karmaşık hesaplamalarla yönetme.
    - [ ]  İleri matematiksel işlemleri SASS ile gerçekleştirme.
- **İç İçe Geçmiş Media Sorguları:**
    - [ ]  Media sorgularını iç içe geçirerek daha modüler ve okunabilir hale getirme.
    - [ ]  Responsive tasarım için medya sorgularını kullanma.
- **SASS'da Loops (Döngüler):**
    - [ ]  Döngülerle stil tekrarlarını yönetme.
    - [ ]  Renk paletleri, genişlik aralıkları gibi sık kullanılan yapıları döngülerle oluşturma.
- **SASS Derleme Optimizasyonu:**
    - [ ]  Minify ve sıkıştırma işlemleri ile çıktıyı optimize etme.
    - [ ]  Önbellek kullanımı ve hızlı derleme ayarları.
- **SASS ile CSS Mimari:**
    - [ ]  OOCSS, BEM, SMACSS gibi CSS mimarilerini SASS ile nasıl uygulayacağınızı öğrenin.
    - [ ]  Büyük projelerde nasıl düzenli ve ölçeklenebilir CSS kodları oluşturacağınızı anlayın.
- **SASS ile Animasyon ve Keyframes Kullanımı:**
    - [ ]  Animasyonlar ve keyframes'lerin SASS ile nasıl oluşturulacağını öğrenin.
    - [ ]  Çeşitli efektler için SASS kullanımını keşfedin.
- **Çeşitli SASS Araçları ve Kütüphaneleri:**
    - [ ]  SASS ile çalışırken işinizi kolaylaştıracak kütüphaneler ve araçlar.
    - [ ]  Autoprefixer, Susy gibi popüler SASS yardımcıları hakkında bilgi edinin.
</details>
<details>
  <summary>LESS</summary>
  # Less

- **LESS Sözdizimi ve Temel Kavramlar:**
    - LESS sözdizimini anlama ve temel yapıları öğrenme.
    - Değişkenler, nesting, mixin'ler gibi temel kavramlar.
- **Değişkenler ve Kullanımı:**
    - Değişkenleri tanımlama ve kullanma.
    - Renkler, genişlikler gibi değerleri değişkenlerle yönetme.
- **Nesting (İç İçe Geçme) ve Avantajları:**
    - Stilleri daha hiyerarşik ve okunabilir bir şekilde yazma.
    - İç içe geçme kullanarak stil düzeni oluşturma.
- **Mixin'lerin Oluşturulması ve Kullanımı:**
    - Mixin'lerin nasıl oluşturulduğunu ve kullanıldığını öğrenme.
    - Mixin parametreleri ile daha esnek ve yeniden kullanılabilir kodlar oluşturma.
- **Extend ve Inheritance (Kalıtım) Kullanımı:**
    - Extend kullanarak stil paylaşımının nasıl yapıldığını öğrenme.
    - Kalıtım ile stillerin yeniden kullanımını anlama.
- **Operatörler ve İşlemler:**
    - Matematiksel işlemleri ve operatörleri kullanma.
    - Değişkenlerde hesaplamalar yapma.
- **LESS Derleme ve Kompilasyon:**
    - LESS kodlarını CSS'e dönüştürme (derleme).
    - LESS'i tarayıcı tarafından anlaşılabilir CSS'e çevirme işlemi.
- **LESS Dosya Yapısı ve Modülerlik:**
    - Projede stil dosyalarını nasıl düzenleyeceğinizi ve organize edeceğinizi öğrenme.
    - Modüler bir yaklaşım benimseyerek kodun yönetimini geliştirme.
- **LESS ile Responsive Tasarım:**
    - Media sorgularını LESS ile nasıl kullanacağınızı öğrenme.
    - Farklı ekran boyutları için stil kodlarını nasıl ayarlayacağınızı öğrenme.
- **LESS Araçları ve İlerleme:**
    - LESS geliştirmenizi destekleyecek araçları ve yardımcı kütüphaneleri öğrenme.
    - Daha fazla pratik yaparak becerilerinizi geliştirme.
    
- **Mixin ve Parametrelerde İleri Kullanım:**
    - Dinamik mixin'ler oluşturma ve kullanma.
    - Mixin parametrelerini daha karmaşık senaryolarda kullanma.
- **LESS Fonksiyonları ve Kullanımı:**
    - LESS'in yerleşik fonksiyonlarını kullanma (örneğin, **`lighten`**, **`darken`**, **`percentage`**).
    - Kendi özel fonksiyonlarınızı oluşturma.
- **LESS ve OOP (Object-Oriented Programming):**
    - Stil kodlarını nesne odaklı bir yaklaşımla nasıl düzenleyebileceğinizi öğrenin.
    - LESS ile sınıf, nesne ve kalıtım konseptlerini kullanma.
- **Dinamik Stil Yönetimi:**
    - JavaScript ile etkileşim içinde olan dinamik stiller oluşturma.
    - Dinamik renk değişiklikleri, animasyonlar gibi örnekleri ele alma.
- **LESS ve CSS Grid Sistemleri:**
    - LESS ile CSS grid sistemleri oluşturma.
    - Grid yapılarını dinamik hale getirme ve farklı düzenlere uyarlamak.
- **LESS ile CSS Preloaders ve Animasyonlar:**
    - CSS ön yükleyiciler (preloaders) ve animasyonlar oluşturma.
    - İleri seviyede animasyon tekniklerini LESS ile uygulama.
- **LESS Modülerliği Geliştirme:**
    - Büyük projelerde kod modülerliğini nasıl optimize edeceğinizi öğrenme.
    - Mixin'ler, extend'ler ve diğer tekniklerle daha sağlam bir modüler yapı kurma.
- **Performans ve Derleme Optimizasyonu:**
    - Derleme sürelerini ve çıktı boyutlarını nasıl optimize edeceğinizi öğrenme.
    - LESS stil kodlarını hızlandırma ve daha iyi performans elde etme.
- **LESS Projelerinde Best Practices:**
    - LESS projelerinde en iyi uygulama yönergelerini ve kod kalitesi standartlarını öğrenme.
    - Stil dosyası organizasyonu, naming conventions, stil dosyası yapısı gibi konulara odaklanma.
- **LESS Entegrasyonu ve Süreklilik Akışı:**
    - LESS stil kodlarını süreklilik akışına entegre etme.
    - Derleme, test ve dağıtım süreçlerini optimize etme.
</details>
<details>
  <summary>Stylus</summary>
  # Stylus

- **Stylus Giriş ve Temel Kavramlar:**
    - Stylus'un CSS kodları daha kolay ve modüler hale getirmek için nasıl kullanıldığını öğrenin.
    - Değişkenler, mixin'ler, extend'ler gibi temel kavramları anlayın.
- **Değişkenler ve Kullanımı:**
    - Değişkenleri tanımlama ve kullanma.
    - Renkler, genişlikler gibi değerleri değişkenlerle yönetme.
- **Nesting (İç İçe Geçme) ve Hiyerarşik Yazım:**
    - Stilleri iç içe geçirerek daha düzenli ve okunabilir hale getirme.
    - Hiyerarşik yazımın avantajlarını öğrenme.
- **Mixin'lerin Kullanımı ve Parametreleri:**
    - Mixin'lerin nasıl oluşturulduğunu ve kullanıldığını anlayın.
    - Mixin parametreleri ile stil öğelerini esnek bir şekilde özelleştirme.
- **Extend Kullanımı ve Paylaşılan Stiller:**
    - Extend ile stil kodlarını paylaşma ve tekrar kullanma.
    - Extend kullanarak nasıl stil kalıtımı sağlayacağınızı öğrenin.
- **Stylus Mixin'leri ve Fonksiyonları:**
    - Mixin'lerin ve fonksiyonların daha karmaşık senaryolarda nasıl kullanılacağını öğrenin.
    - Dinamik stil oluşturma ve parametreli mixin'lerin gücünü keşfedin.
- **Stylus'da Modülerlik ve OOP (Nesne Odaklı Programlama):**
    - Stil kodlarını nesne odaklı bir yaklaşımla nasıl düzenleyeceğinizi öğrenin.
    - Kalıtım, sınıflar ve modüllerle daha düzenli bir stil yapı oluşturma.
- **Dinamik Stil Yönetimi ve Javascript Entegrasyonu:**
    - Stylus'u JavaScript ile entegre ederek dinamik stiller oluşturmayı öğrenin.
    - Stil kodlarını dinamik verilere dayalı olarak nasıl yöneteceğinizi öğrenin.
- **Stylus ile Responsive Tasarım:**
    - Media sorgularını nasıl kullanacağınızı ve responsive tasarımı nasıl uygulayacağınızı öğrenin.
    - Farklı cihazlara yönelik stil ayarlamalarını ele alın.
- **Stylus Performans ve Optimizasyon:**
    - Stil kodlarını daha hızlı derlemek ve daha optimize bir çıktı üretmek için teknikler öğrenin.
    - Derleme sürelerini iyileştirme ve performansı artırma yöntemleri.
- **Stylus Projelerinde Best Practices:**
    - Projelerde en iyi uygulama yönergelerini ve stil kodları kalite standartlarını öğrenin.
    - Kod organizasyonu, naming conventions, stil dosyası yapısı gibi konulara derinlemesine odaklanın.
- **Stylus ve Gelişmiş CSS Mimari:**
    - Farklı CSS mimarilerini (OOCSS, BEM, SMACSS) Stylus ile nasıl uygulayacağınızı öğrenin.
    - Büyük projelerde daha düzenli ve ölçeklenebilir stil kodları oluşturma yöntemleri.
- **Stylus Araçları ve Gelişmiş Kütüphaneler:**
    - Stylus geliştirme sürecinizi destekleyecek yardımcı araçları ve kütüphaneleri keşfedin.
    - Autoprefixer, stylus nib gibi popüler yardımcı kütüphaneleri öğrenin.
</details>
<details>
  <summary>Bootstrap</summary>
  # Bootstrap

Bootstrap, web geliştiricilerin hızlı ve duyarlı web siteleri ve uygulamaları oluşturmak için kullanabilecekleri popüler bir açık kaynak CSS çerçevesidir.

**Başlangıç Düzeyi Bootstrap Çalışma Başlıkları:**

1. **Bootstrap Temel Kavramlar:**
    - Bootstrap nedir ve nasıl çalışır?
    - Grid sistemleri, bileşenler ve stiller gibi temel kavramları öğrenin.
2. **Bootstrap Kurulumu:**
    - Bootstrap'ı projenize eklemek için CDN'leri veya npm/yarn gibi paket yöneticilerini kullanmayı öğrenin.
3. **Grid Sistemi:**
    - Bootstrap grid sistemi ile sayfa düzenlerini oluşturmayı ve duyarlı tasarım yapmayı öğrenin.
4. **Bootstrap Bileşenleri:**
    - Bootstrap bileşenlerini kullanarak düğmeler, form elemanları, navigasyon menüleri, modallar, kartlar ve diğer UI bileşenlerini nasıl oluşturacağınızı öğrenin.
5. **Özel Stiller ve Temalar:**
    - Bootstrap ile özel stil ve tema oluşturmayı öğrenin.
    - Less veya Sass kullanarak temaları özelleştirme yeteneklerini inceleyin.

**İleri Düzey Bootstrap Çalışma Başlıkları:**

1. **Bootstrap Sass/Less Kullanımı:**
    - Bootstrap'un Sass veya Less sürümlerini projenizde nasıl kullanacağınızı öğrenin.
    - Özel derleme ve yapılandırmaları ele alın.
2. **Özel Bileşenlerin Oluşturulması:**
    - Bootstrap bileşenlerini özelleştirip kendi özel bileşenlerinizi nasıl oluşturacağınızı öğrenin.
    - Özelleştirilmiş bileşenlerinizi projelerinizde kullanın.
3. **Bootstrap JavaScript:**
    - Bootstrap tarafından sunulan JavaScript bileşenlerini (örneğin, modal, dropdown) nasıl kullanacağınızı öğrenin.
    - Özel etkinlik dinleyicileri eklemek ve özelleştirmek için JavaScript'i kullanmayı inceleyin.
4. **Bootstrap Entegrasyonu:**
    - Bootstrap'ı farklı JavaScript çerçeveleri ve kütüphaneleriyle (örneğin, React, Angular, Vue.js) nasıl entegre edeceğinizi öğrenin.
5. **Bootstrap ve Mobil Uygulama Geliştirme:**
    - Bootstrap'u mobil uygulama geliştirme projelerinde nasıl kullanabileceğinizi öğrenin.
    - Duyarlı tasarımı ve mobil kullanılabilirliği iyileştirmek için en iyi uygulamaları keşfedin.
6. **Performans İyileştirmeleri:**
    - Bootstrap projelerinizin performansını artırmak için CDN optimizasyonları ve dosya sıkıştırma tekniklerini inceleyin.
7. **Bootstrap Eklentileri ve Temaları:**
    - Bootstrap için üçüncü taraf eklentileri ve özel temaları nasıl kullanacağınızı ve entegre edeceğinizi öğrenin.
8. **Test ve Hata Ayıklama:**
    - Bootstrap projelerinizi test etmek ve hata ayıklamak için tarayıcı geliştirici araçlarını ve test otomasyon araçlarını nasıl kullanacağınızı öğrenin.
</details>


<details>
  <summary>Click to expand</summary>
  ## Değişken (Variable):
Değerlerin depolanması için kullanılan yapıdır. JavaScript'te değişkenler var, let ve const anahtar kelimeleri ile tanımlanabilir.
```
let firstName = "John";
```
Burada let, const ve var anahtar kelimeleri ile sırasıyla değişkenler tanımlanmıştır. let ve const blok kapsamına sahipken, var ise fonksiyon veya global kapsama sahip olabilir. firstName deği

## Fonksiyon (Function):
JavaScript'te fonksiyonlar birer nesnedir. Kod bloklarını paketler ve bir işlevi gerçekleştirmek için kullanılır. Fonksiyonlar, parametreleri alabilir ve geri dönüş değeri üretebilirler.
```
function helloWorld() {
  console.log("Hello, World!");
}

helloWorld();
```
## Dizi (Array):
JavaScript'te bir dizi birden fazla değerin depolanması için kullanılır. Diziler, [] işaretleri arasına değerlerin virgülle ayrılması ile tanımlanır.
```
let numbers = [1, 2, 3, 4, 5];
console.log(numbers); // [1, 2, 3, 4, 5]
```

## Nesne (Object):
JavaScript'te bir nesne, özelliklerin (properties) ve yöntemlerin (methods) bir arada depolandığı bir yapıdır. Nesneler {} işaretleri ile tanımlanır.
```
const obje = {
  isim: 'Ahmet',
  soyisim: 'Yılmaz',
  yas: 30,
  adres: {
    sehir: 'Ankara',
    ilce: 'Çankaya',
    postaKodu: 06500
  }
};

console.log(obje);
```

## Sınıf (Class):
Sınıf, nesnelerin şablonlarını tanımlar. JavaScript'te sınıflar ES6 sürümünden itibaren kullanılmaktadır.
```
class Rectangle {
  constructor(width, height) {
    this.width = width;
    this.height = height;
  }

  getArea() {
    return this.width * this.height;
  }
}

// Rectangle sınıfından bir nesne oluşturun
const rect1 = new Rectangle(5, 10);

// getArea() yöntemini çağırın
console.log(rect1.getArea()); // 50 yazdırır

```
## Metod (Method):
Bir nesnenin özelliklerine erişmek veya işlem yapmak için kullanılan fonksiyonlara metod denir.

JavaScript'te bir yöntem (method), bir nesne tarafından desteklenen ve o nesneyle ilgili bir işlemi gerçekleştiren işlevsel bir kod parçasıdır. Bir yöntem, bir nesne örneği üzerinde çağrılabilir ve o nesne örneği için bir işlem yapar.

Bir JavaScript yöntemi, bir fonksiyonun bir özelliğinin bir parçası olarak tanımlanır ve genellikle bir nesne örneği üzerinde çağrılır. Yöntemler, nesne özellikleri gibi "this" anahtar kelimesini kullanarak nesne özelliklerine erişebilir ve bu özellikleri değiştirebilir.

Örneğin, aşağıdaki örnekte, "person" adlı bir nesne tanımlıyoruz ve "sayHello" adlı bir yöntem ekliyoruz:
```
let person = {
  name: "Ahmet",
  age: 30,
  sayHello: function() {
    console.log(`Merhaba, benim adım ${this.name} ve ben ${this.age} yaşındayım.`);
  }
};

// sayHello() yöntemini çağırın
person.sayHello(); // "Merhaba, benim adım Ahmet ve ben 30 yaşındayım." yazdırır
```
Yukarıdaki örnekte, "sayHello" yöntemi, "person" nesne örneği üzerinde çağrılır ve nesne özelliklerine erişir (this.name ve this.age) ve bir mesaj oluşturur.

## Parametre (Parameter):
JavaScript'te parametreler, fonksiyonlara aktarılan verilerdir. Fonksiyonlar, parametrelerin kullanılması yoluyla belirli bir işlevi yerine getirirler.

Parametreler, bir fonksiyonun tanımında parantez içinde belirtilir ve fonksiyonun çağrılmasında argümanlar olarak geçirilirler. Argümanlar, fonksiyonun işlevini gerçekleştirmesi için gereken verilerdir.

Aşağıdaki örnekte, bir fonksiyon iki parametre alır ve bu parametreleri kullanarak basit bir hesaplama yapar:
```
function multiply(num1, num2) {
  return num1 * num2;
}

let result = multiply(5, 10);
console.log(result); // 50 yazdırır
```
Yukarıdaki örnekte, "multiply" adlı bir fonksiyon tanımlıyoruz ve bu fonksiyon "num1" ve "num2" adlı iki parametre alıyor. Bu parametreler, fonksiyon çağrısında argümanlarla eşleştirilir. Fonksiyon, parametreler aracılığıyla verilen argümanları kullanarak bir işlem gerçekleştirir ve sonucu döndürür.

"Fonksiyonlar" adlı bir konuda daha örnekler ve detaylı açıklamalar yer almaktadır, buraya da bakabilirsiniz.

## Argüman (Argument):
JavaScript'te argümanlar, bir fonksiyonun çağrılması sırasında fonksiyona geçirilen değerlerdir. Bu değerler, fonksiyonun işlevini gerçekleştirmesi için gerekli olan verilerdir.

Argümanlar, bir fonksiyonun parantez içinde belirtilen parametrelerle eşleştirilir. Fonksiyon parametreleri ile argümanlar arasındaki eşleştirme sırasına göre belirlenir. Örneğin, bir fonksiyonun üç parametresi varsa ve fonksiyon çağrısı sırasında sadece iki argüman geçirilirse, fonksiyonun ilk iki parametresi, geçirilen argümanlarla eşleştirilir ve üçüncü parametre "undefined" olarak atanır.

Aşağıdaki örnekte, "multiply" adlı bir fonksiyon tanımlıyoruz ve bu fonksiyon iki argüman alıyor:
```
function multiply(num1, num2) {
  return num1 * num2;
}

let result = multiply(5, 10);
console.log(result); // 50 yazdırır
```
Yukarıdaki örnekte, "multiply" fonksiyonunu çağırırken iki argüman geçiriyoruz: 5 ve 10. Bu argümanlar, fonksiyonun "num1" ve "num2" parametreleri ile eşleştirilir ve fonksiyon, bu parametreler aracılığıyla çarpma işlemini gerçekleştirir ve sonucu döndürür.

"Fonksiyonlar" adlı bir konuda daha örnekler ve detaylı açıklamalar yer almaktadır, buraya da bakabilirsiniz.

## Operatör (Operator):
İki veya daha fazla değeri birleştirmek, karşılaştırmak veya işlemek için kullanılan sembollerdir.

Aritmetik operatörler:
Toplama (+): Sayıları toplar veya stringleri birleştirir.
Çıkarma (-): Sayılardan bir sayıyı diğerinden çıkarır.
Çarpma (*): Sayıları çarpar.
Bölme (/): Bir sayıyı diğerine böler.
Mod (%) : İlk sayıyı ikinci sayıya böler ve kalanı döndürür.
```
let num1 = 10;
let num2 = 3;

console.log(num1 + num2); // 13
console.log(num1 - num2); // 7
console.log(num1 * num2); // 30
console.log(num1 / num2); // 3.3333333333333335
console.log(num1 % num2); // 1
```

Karşılaştırma operatörleri:

Eşitlik (==): İki değer eşit ise true döndürür.
Katı eşitlik (===): İki değer hem tür hem de değer açısından eşit ise true döndürür.
Eşit değil (!=): İki değer farklı ise true döndürür.
Katı eşit değil (!==): İki değer hem tür hem de değer açısından farklı ise true döndürür.
Büyüktür (>): Sol taraftaki sayı sağ taraftakinden büyükse true döndürür.
Küçüktür (<): Sol taraftaki sayı sağ taraftakinden küçükse true döndürür.
Büyük eşit (>=): Sol taraftaki sayı sağ taraftakinden büyük veya eşitse true döndürür.
Küçük eşit (<=): Sol taraftaki sayı sağ taraftakinden küçük veya eşitse true döndürür.
```
let num1 = 10;
let num2 = 3;
let str1 = "10";

console.log(num1 == str1); // true
console.log(num1 === str1); // false
console.log(num1 != num2); // true
console.log(num1 !== str1); // true
console.log(num1 > num2); // true
console.log(num1 < num2); // false
console.log(num1 >= num2); // true
console.log(num1 <= num2); // false
```

Mantıksal operatörler:

Ve (&&): İki koşulun da doğru olması durumunda true döndürür.
Veya (||): En az bir koşulun doğru olması durumunda true döndürür.
Değil (!): Koşulun tersini döndürür.
```
let num1 = 10;
let num2 = 3;
let str1 = "10";

console.log(num1 > num2 && num1 == str1); // true
console.log(num1 > num2 || num1 < num2); // true
console.log(!(num1 > num2)); // false
```
Atama operatörleri:

Eşittir (=): Değer ataması yapar.
Toplama eşittir (+=): Değişkenin değerine bir sayı ekler ve sonucu tekrar değişkene atar.
Çıkarma eşittir (-=): Değişkenin değerinden bir sayı çıkarır ve sonucu tekrar değişkene atar.
Çarpma eşittir (*=): Değişkenin değerini bir sayıyla çarpar ve sonucu tekrar değişkene atar.
Bölme eşittir (/=): Değişkenin değerini bir sayıya böler ve sonucu tekrar değişkene atar.
```
let num1 = 10;

num1 += 5; // num1 = num1 + 5;
console.log(num1); // 15

num1 -= 3; // num1 = num1 - 3;
console.log(num1); // 12

num1 *= 2; // num1 = num1 * 2;
console.log(num1); // 24

num1 /= 4; // num1 = num1 / 4;
console.log(num1); // 6
```
Bitişik operatörler:

Arttır (++) : Değişkenin değerini 1 arttırır.
Azalt (--) : Değişkenin değerini 1 azaltır.
```
let num1 = 10;

console.log(num1++); // 10
console.log(num1); // 11

console.log(++num1); // 12

console.log(num1--); // 12
console.log(num1); // 11

console.log(--num1); // 10
```
Diğer operatörler:

Ternary (?:) : İf-else yapısının kısaltılmış halidir.
Virgül (,) : Birden fazla ifadeyi birleştirir ve son ifadenin değerini döndürür.
```
let num1 = 10;
let num2 = 3;

let max = (num1 > num2) ? num1 : num2;
console.log(max); // 10

let sum = (num1 += 2, num2 += 2, num1 + num2);
console.log(sum); // 17
```
Bit operatörleri:

AND (&) : İki sayının ikilik tabandaki karşılıklarındaki bitlerin her ikisinde de 1 olan bitleri 1 olarak belirler.
OR (|) : İki sayının ikilik tabandaki karşılıklarındaki bitlerin herhangi birinde 1 olan bitleri 1 olarak belirler.
XOR (^) : İki sayının ikilik tabandaki karşılıklarındaki bitlerin sadece birinde 1 olan bitleri 1 olarak belirler.
NOT (~) : Bir sayının ikilik tabandaki karşılığını alır ve her biti tersine çevirir.
Left Shift (<<) : Bir sayının ikilik tabandaki karşılığını belirtilen sayı kadar sola kaydırır ve boşlukları 0 ile doldurur.
Right Shift (>>) : Bir sayının ikilik tabandaki karşılığını belirtilen sayı kadar sağa kaydırır ve boşlukları en sol bitin değerine göre doldurur.
Zero-fill Right Shift (>>>) : Bir sayının ikilik tabandaki karşılığını belirtilen sayı kadar sağa kaydırır ve boşlukları 0 ile doldurur.
```
let num1 = 10; // 1010 (ikilik tabanda)
let num2 = 5; // 0101 (ikilik tabanda)

let and = num1 & num2; // 0000
console.log(and); // 0

let or = num1 | num2; // 1111
console.log(or); // 15

let xor = num1 ^ num2; // 1111
console.log(xor); // 15

let not = ~num1; // -11 (ikilik tabanda)
console.log(not); // -11

let leftShift = num1 << 2; // 101000 (ikilik tabanda)
console.log(leftShift); // 40

let rightShift = num1 >> 1; // 0101 (ikilik tabanda)
console.log(rightShift); // 5

let zeroFillRightShift = num1 >>> 1; // 0101 (ikilik tabanda)
console.log(zeroFillRightShift); // 5
```
Diğer operatörler:

Delete : Bir nesne özelliğini veya bir dizinin elemanını siler.
Typeof : Bir değerin veri türünü belirler.
Void : Bir ifadeyi değer döndürmeden işler.
In : Bir özelliğin bir nesne içinde var olup olmadığını belirler.
Instanceof : Bir nesnenin belirli bir sınıfın örneği olup olmadığını belirler.

```
// typeof operatörü
let num = 5;
let str = "Hello";
console.log(typeof num); // "number"
console.log(typeof str); // "string"

// delete operatörü
let obj = { name: "John", age: 30 };
delete obj.age;
console.log(obj); // { name: "John" }

let arr = [1, 2, 3];
delete arr[1];
console.log(arr); // [1, undefined, 3]

// in operatörü
console.log("name" in obj); // true
console.log(1 in arr); // true

// instanceof operatörü
class Person {
  constructor(name, age) {
    this.name = name;
    this.age = age;
  }
}

const person1 = new Person("Alice", 25);

console.log(person1 instanceof Person); // true
console.log(person1 instanceof Object); // true
```

## Koşul ifadesi (Conditional statement):
Belirli bir koşulun sağlanıp sağlanmadığını kontrol ederek, farklı kod bloklarının çalıştırılmasını sağlayan ifadelerdir. JavaScript'te if-else, switch-case gibi koşul ifadeleri bulunmaktadır.

## Döngü (Loop):
Belirli bir kod bloğunun, belirli bir koşul sağlanana kadar veya belirli bir sayıda kez çalıştırılmasını sağlayan yapılardır. JavaScript'te for, while, do-while gibi döngü yapıları bulunmaktadır.

## Callback fonksiyonu (Callback function):
Bir fonksiyonun, başka bir fonksiyona argüman olarak geçirilmesidir. Bu, fonksiyonların modülerliğini artırır.

## DOM (Document Object Model):
Web sayfalarının, HTML, XML ve XHTML gibi belge türlerinin birer nesne olarak temsil edildiği bir platformdır.

## İç içe fonksiyonlar (Nested functions):
Bir fonksiyon içinde tanımlanan ve o fonksiyon tarafından çağrılan fonksiyonlardır.

## Rekürsif fonksiyon (Recursive function):
Kendi kendini çağıran bir fonksiyondur.

## Kalıtım (Inheritance):
Bir sınıfın özelliklerinin ve metodlarının başka bir sınıf tarafından kullanılmasını sağlayan yapıdır.

## Get ve set fonksiyonları (Getters and setters):
Nesne özelliklerine değer atamak ve okumak için kullanılan özel fonksiyonlardır.

## Promise zincirleri (Promise chaining):
Birbirine bağlı promise'ların ardışık şekilde kullanılmasıdır.

## IIFE (Immediately Invoked Function Expression):
Fonksiyonu tanımladıktan sonra hemen çağırmak için kullanılan bir yapıdır.

## Strict modu (Strict mode):
JavaScript kodunun daha sıkı bir şekilde yorumlanmasını sağlayan bir yapıdır.

## Generatör fonksiyon (Generator function):
İçinde yield ifadesi bulunan fonksiyonlardır ve bu sayede asenkron işlemleri yönetmek için kullanılır.

## Async/await:
Asenkron işlemleri yönetmek için kullanılan bir yapıdır ve promise'ların daha okunaklı bir şekilde kullanılmasını sağlar.

## Fetch API:
Sunucudan veri almak için kullanılan bir arayüzdür ve XMLHttpRequest (XHR) yerine tercih edilir.

## Local Storage:
Web sayfasında veri saklamak için kullanılan bir mekanizmadır.

## Session Storage:
Oturum (session) boyunca veri saklamak için kullanılan bir mekanizmadır.

## Cookies:
Kullanıcının bilgisayarında saklanan küçük metin dosyalarıdır ve web sayfasının durumunu takip etmek için kullanılır.

## Regular Expression (Regex):
Belirli bir kalıba uygun olan metinleri seçmek için kullanılan bir dil ve yapısıdır.

## Template literals:
Bir dize içinde değişkenleri veya ifadeleri yerleştirmek için kullanılan yapıdır.

## Destructuring assignment:
Nesnelerin veya dizilerin özelliklerine veya elemanlarına tek seferde erişmek için kullanılan yapıdır.

## Asynchronous programming:
Asenkron işlemleri yönetmek için kullanılan bir yaklaşımdır ve zaman alıcı işlemlerin ana işlemi engellemeden yapılmasını sağlar.

## Event loop:
JavaScript'in asenkron işlemleri yönetmek için kullandığı bir yapıdır ve callback fonksiyonlarının sırayla işletilmesini sağlar.

## Scope:
Değişkenlerin ve fonksiyonların erişilebilirlik alanlarını tanımlar.

## Hoisting:
Değişkenlerin ve fonksiyonların tanımlarının, kodun yukarıya doğru kaldırılması yoluyla işlendiği bir yapıdır.

## Closures:
Bir fonksiyonun içinde tanımlanan fonksiyonlar, dış fonksiyondaki değişkenlere erişebilir ve bu değişkenleri koruyabilir.

## Callback hell:
Çok sayıda callback fonksiyonunun birbirine bağlı şekilde kullanıldığı, kodun okunaklılığını azaltan bir yapıdır.

## Debugging:
Kodun hatalarını bulmak ve düzeltmek için kullanılan bir süreçtir.

## Transpiling:
Yeni JavaScript özelliklerini eski tarayıcılarda da kullanabilmek için, yeni kod

## ES6 Modules:
ECMAScript 6 ile birlikte tanıtılan modül sistemi, JavaScript dosyalarını modüller halinde kullanmayı sağlar.

## Babel:
Yeni JavaScript özelliklerini eski tarayıcılarda da kullanabilmek için kullanılan bir transpiler'dır.

## Webpack:
JavaScript uygulamalarının modüler şekilde paketlenmesi için kullanılan bir araçtır.

## Virtual DOM:
React'ta kullanılan bir teknolojidir ve değişikliklerin öncelikle bir sanal DOM üzerinde yapılıp daha sonra gerçek DOM'a yansıtılmasını sağlar.

## Redux:
JavaScript uygulamalarında durum yönetimi için kullanılan bir kütüphanedir.

## JSX:
React uygulamalarında kullanılan, JavaScript ve HTML benzeri bir sözdizimi sunan bir yapıdır.

## Web Workers:
Web sayfalarında işlemlerin paralel şekilde yapılmasını sağlayan bir arayüzdür.

## Service Workers:
Web sayfalarının arka planda çalışarak çevrimdışı da çalışmasını sağlayan bir arayüzdür.

## IndexedDB:
Tarayıcının yerel veritabanıdır ve web sayfalarında veri saklamak için kullanılır.

## WebGL:
Web sayfalarında 3D grafikler oluşturmak için kullanılan bir arayüzdür.

## WebRTC:
Tarayıcılar arasında gerçek zamanlı iletişim kurmak için kullanılan bir arayüzdür.

## Accessibility:
Web sayfalarının tüm kullanıcılar için erişilebilir olmasını sağlamak için yapılan çalışmalardır.

## SEO (Search Engine Optimization):
Web sayfalarının arama motorları tarafından daha iyi indekslenebilmesi için yapılan çalışmalardır.

## Progressive Web Apps (PWA):
Web uygulamalarının, geleneksel mobil uygulamalar gibi davranmasını ve özellikler sunmasını sağlayan bir yapıdır.

## Single-page Application (SPA):
Web sayfalarının tek bir HTML sayfasında yüklenip, daha sonra JavaScript aracılığıyla içeriklerin dinamik olarak yüklenmesini sağlayan bir yapıdır.

## API (Application Programming Interface):
Bir yazılımın diğer yazılımlarla iletişim kurmasını sağlayan bir arayüzdür.

## CRUD (Create, Read, Update, Delete):
Veritabanı işlemlerinin temel işlemlerini ifade eder.

## Git:
Sürüm kontrolü için kullanılan bir yazılımdır ve kodun değişikliklerinin takibi ve geri alınması gibi işlemleri yap

## NPM (Node Package Manager):
Node.js projelerinde paket yönetimi için kullanılan bir araçtır.

## Yarn:
NPM alternatifi bir paket yöneticisidir.

## Linter:
Kod kalitesini artırmak ve hataları önceden tespit etmek için kullanılan bir araçtır.

## Unit Test:
Kodun küçük birimlerindeki işlevlerin doğruluğunu test etmek için kullanılan bir test türüdür.

## Integration Test:
Birkaç birim arasındaki etkileşimi test etmek için kullanılan bir test türüdür.

## End-to-End (E2E) Test:
Bir uygulamanın tüm fonksiyonlarının doğru çalıştığını kontrol etmek için kullanılan bir test türüdür.

## Continuous Integration (CI):
Kodun sürekli olarak test edilmesi ve birleştirilmesi için kullanılan bir süreçtir.

## Continuous Deployment (CD):
Kodun otomatik olarak üretim ortamına dağıtılması için kullanılan bir süreçtir.

## Agile:
Yazılım geliştirme sürecinde esnek bir yaklaşımı ifade eder ve müşteri geri bildirimleri doğrultusunda sık sık yeni özelliklerin eklenmesini ve geliştirilmesini sağlar.

## Scrum:
Agile yaklaşımın bir uygulama şeklidir ve bir ekip içinde çalışan üyelerin bir araya gelerek projeyi yönettiği bir süreçtir.

## Kanban:
Agile yaklaşıma dayalı bir proje yönetim yöntemidir ve projenin durumunu görsel olarak takip etmeyi sağlar.

## Waterfall:
Yazılım geliştirme sürecinde, bir adımın tamamlanmasının ardından diğer adıma geçilir ve geri dönüş yapılmaz.

## Spiral:
Yazılım geliştirme sürecinde, proje ilerledikçe yapılan analiz ve tasarım çalışmalarının tekrarlanması üzerine kurulu bir yaklaşımdır.

## MVP (Minimum Viable Product):
Bir ürünün en temel özelliklerini içeren ve müşteri geri bildirimleri doğrultusunda geliştirilen bir prototip aşamasıdır.

## Design Pattern:
Tekrar eden yazılım problemlerine karşı genel çözümler sunan yazılım tasarımı prensipleridir.

## SOLID:
Yazılım geliştirme prensiplerinin birleştirilmesiyle oluşan bir dizi ilkedir. S:
Tek Sorumluluk İlkesi (Single Responsibility Principle), O:
Açık/Kapalı İlkesi (Open/Closed Principle), L:
Liskov Yerine Geçme İlkesi (Liskov Substitution Principle), I:
Arayüz Ayrımı İlkesi (Interface Segregation Principle), D:
Bağımlılığı Tersine Çevirme İlkesi (Dependency Inversion Principle)

## REST (Representational State Transfer):
Web servislerinde kullanılan bir mimaridir ve HTTP protokolünü kullanarak kaynakların (resource) durumunu (state) yönetir.

## Template literals:
Bir dize içinde değişkenleri veya ifadeleri yerleştirmek için kullanılan yapıdır.

## Destructuring assignment:
Nesnelerin veya dizilerin özelliklerine veya elemanlarına tek seferde erişmek için kullanılan yapıdır.

## XML (Extensible Markup Language):
Veri aktarımı için kullanılan bir formattır ve metin tabanlı bir işaret dili kullanır.

## Type coercion:
JavaScript'te, bir veri türünün otomatik olarak başka bir veri türüne dönüştürülmesi anlamına gelir.

## Map:
JavaScript'te, her bir öğe ile bir değer çifti olan bir dizi veri yapısıdır.



## Primitive (İlkel) Veri Tipleri:

### String: 

Metin veya karakter dizileri için kullanılır.

```
let message = "Merhaba Dünya!";
```

### Number: 

Sayılar için kullanılır.  
```
let pi = 3.14;
```

### Boolean: 

Doğru veya yanlış değerleri için kullanılır. 
```
let isLogged = true;
```

### Null: 

Hiçbir değer veya yokluk için kullanılır. 

```
let myVariable = null;
```

### Undefined: 

Değer atanmamış değişkenler veya fonksiyonlar için kullanılır.  

```
let myVariable;
```

### Symbol: 

Özelleştirilmiş ve benzersiz tanımlayıcılar için kullanılır. 

```
const mySymbol = Symbol('mySymbol');
```

## Referans (Yönlendirme) Veri Tipleri:

### Object:

Tüm nesneler için kullanılır, fonksiyonlar da dahil olmak üzere. Nesneler, özellikler ve değerler içeren veri yapılarıdır.   

```
let user = { name: "Ahmet", age: 35 };
```

### Array: 

Diziler, benzer veri türlerinin bir listesi olarak kullanılır.  

```
let numbers = [1, 2, 3, 4, 5];
```

### Function: 

Fonksiyonlar, kod bloklarını bir işlev olarak gruplayarak kullanılır. 

```
function calculateSum(a, b) {
  return a + b;
}
```

### Date: 

Tarih ve saat değerleri için kullanılır. 

```
let today = new Date();
```

### RegExp: 

Düzenli ifadeleri temsil etmek için kullanılır. 

```
let pattern = /JavaScript/;
```

### Variables

JavaScript'te değişkenler, veri saklamak veya ileride kullanmak için değer atamak için kullanılır. 
JavaScript'te değişkenler dinamik olarak tip alır, yani bir değişkenin tipi, değişkenin değeri atanırken otomatik olarak belirlenir.

## var 
anahtar kelimesi, bir değişken tanımlamak için kullanılır. Ancak, "var" değişkenleri, blok kapsamı yerine işlev kapsamı veya global kapsam kullanır. Bu nedenle, "var" değişkenleri, aynı isimde birden fazla değişken tanımlanmasına izin verir ve bu da beklenmeyen sonuçlara yol açabilir.

```
var name = "John"; // var ile değişken tanımlama
```

## let 
anahtar kelimesi, "var" anahtar kelimesinin yerini almıştır. "let" değişkenleri blok kapsamını kullanır, bu nedenle aynı isimdeki bir değişkenin yeniden tanımlanması mümkün değildir. Ayrıca, "let" değişkenleri "undefined" olarak değer alır.

```
let age = 30; // let ile değişken tanımlama
```

## const 
anahtar kelimesi, "let" anahtar kelimesine benzerdir, ancak "let" ile farklı olarak, bir kez değer atandığında değiştirilemez. "const" değişkenleri, özellikle sabitler veya sabit değerler için kullanışlıdır.

```
const PI = 3.14159; // const ile sabit tanımlama
```

### Template Literals (şablon dizileri): 

Bir Javascript ifadesini düz bir yazı yazar gibi tek bir satırda yazmamızı sağlayan string çeşidi olarak tanımlanabilir. Template literals, back tick dediğimiz tırnak işaretleri içinde yazılmalıdır. (alt gr + , )

### Shorthand Property Names:(kısayol obje anahtarı isimleri): 

Javascript objesi, key-value (anahtar-değer) sistemiyle çalışan bir veri tipidir. Bir obje oluştururken, değer bir değişkenden geliyorsa, anahtarın açıkça belirtilmesine gerek yoktur. Değişkenin direk olarak objeye girilmesi, değişkenin ismini anahtar olarak, değerini ise değer olarak atar.

### Arrow Functions (oklu fonksiyon ifadeleri): 

Oklu fonksiyon ifadeleri, Javascript'te fonksiyon oluşturmanın yeni bir yöntemidir. En önemli ve sık kullanılan özelliklerinden bir tanesi implicit (üstü kapalı) return özelliğidir. Dikkat edilmesi gereken bir başka farklılık ise, oklu fonksiyon ifadeleri hoist edilmezler, yani bir değişkene atadığınız oklu fonksiyonları, function ifadesiyle oluşturduğunuz fonksiyonlar gibi, oluşturmadan önce çağıramazsınız.

### Object Destructuring

JavaScript'te nesne yıkımı (object destructuring), bir nesnenin özelliklerini ayrı ayrı değişkenlere atama yöntemidir. Bu özellikle, bir nesne yöntemi tarafından döndürülen bir nesnenin belirli özelliklerine erişmek için kullanışlıdır.
Nesne yıkımı, süslü parantezleri kullanarak bir nesnenin özelliklerine erişir. Bu özellikler, yeni değişken isimleriyle eşleştirilir. Aşağıdaki örnekte, bir kişi nesnesinden ad ve yaş özelliklerine erişilir:

```
const person = { name: "John", age: 30 };
const { name, age } = person;
console.log(name); // "John"
console.log(age); // 30
```

Bu örnekte, person adlı bir nesne tanımlanır ve name ve age özellikleri atanır. Ardından, name ve age değişkenleri, nesne yıkımı kullanılarak person nesnesindeki ilgili özelliklerle eşleştirilir.
Nesne yıkımı ayrıca, bir fonksiyon tarafından döndürülen nesneden özellikleri değişkenlere atamak için de kullanılabilir. Aşağıdaki örnekte, getPerson adlı bir fonksiyon, bir kişi nesnesini döndürür ve nesne yıkımı kullanılarak ad ve yaş değişkenlerine atanır:

```
function getPerson() {
  return { name: "John", age: 30 };
}
const { name, age } = getPerson();
console.log(name); // "John"
console.log(age); // 30
```

Bu örnekte, getPerson adlı bir fonksiyon, bir kişi nesnesini döndürür ve nesne yıkımı kullanılarak name ve age değişkenleri nesnenin özellikleriyle eşleştirilir.

### Array Destructuring

JavaScript'te dizi yıkımı (array destructuring), bir dizinin öğelerini ayrı ayrı değişkenlere atama yöntemidir. Bu özellikle, bir fonksiyon tarafından döndürülen bir dizinin belirli öğelerine erişmek için kullanışlıdır.
Dizi yıkımı, köşeli parantezleri kullanarak bir dizinin öğelerine erişir. Bu öğeler, yeni değişken isimleriyle eşleştirilir. Aşağıdaki örnekte, bir dizi oluşturulur ve ilk iki öğesi ayrı değişkenlere atanır:

```
const numbers = [1, 2, 3, 4, 5];
const [first, second] = numbers;
console.log(first); // 1
console.log(second); // 2
```

Bu örnekte, numbers adlı bir dizi tanımlanır ve first ve second değişkenleri, dizinin ilk iki öğesiyle eşleştirilir.
Dizi yıkımı ayrıca, bir fonksiyon tarafından döndürülen diziden öğeleri değişkenlere atamak için de kullanılabilir. Aşağıdaki örnekte, getNumbers adlı bir fonksiyon, bir sayı dizisini döndürür ve dizi yıkımı kullanılarak ilk iki öğe first ve second değişkenlerine atanır:

```
function getNumbers() {
  return [1, 2, 3, 4, 5];
}
const [first, second] = getNumbers();
console.log(first); // 1
console.log(second); // 2
```

Bu örnekte, getNumbers adlı bir fonksiyon, bir sayı dizisini döndürür ve dizi yıkımı kullanılarak first ve second değişkenleri dizinin ilk iki öğesiyle eşleştirilir.

### Ternary Conditional Operators (üç değişkenli koşul operatörleri)

Ternary operatörleri üç adet ifade alır. İlk ifade koşuldur. Koşul true yani doğru olarak hesaplanırsa soru işaretinden sonraki kısım işleme alınır, false yani yanlış olarak hesaplanırsa iki nokta işaretinden sonraki kısım işleme alınır.


### Terimler

### Producing Code:

"producing code" terimi, gerçek işlevselliği sağlayan, bir şeyler yapan ve zaman alan kodun yazılması anlamına gelir ve bir yazılım projesinin temel aşamalarından biridir.

Detay: https://javascript.info/promise-basics

### Consuming Code:

"consuming code" terimi, bir yazılım projesinde başka bir kaynaktan kod kullanmayı ifade eder. Bu, projenin hızlı ve verimli bir şekilde tamamlanmasına yardımcı olabilir ve açık kaynaklı projelerde yaygın bir uygulamadır.
Detay: https://javascript.info/promise-basics

### Implicit return: 

Fonksiyon içinde herhangi başka bir ifade olmaksızın tek bir ifade döndürülüyorsa implicit return özelliği kullanılabilir 

(const topla = (sayi1, sayi2) => sayi1 + sayi2;)(array function)

### Hoist: 

JavaScript'te "Hoisting (Kaldırma)" terimi, bir değişkenin veya fonksiyonun tanımlandığı yere göre etki alanının (scope) en üst düzeye taşınması anlamına gelir. Yani, bir değişken veya fonksiyon tanımlanmadan önce kullanılmışsa, bu tanımlama işlemi kod yürütülmeden önce otomatik olarak yukarı taşınır. Bu sayede, değişkenler ve fonksiyonlar, kodun başında tanımlanmış gibi davranırlar.
Örneğin, aşağıdaki kodda myVariable değişkeni, tanımlanmadan önce kullanılmıştır ancak hata vermez:

```
console.log(myVariable);
var myVariable = "Hello World!";
```

Detay: https://www.w3schools.com/js/js_hoisting.asp

Bu kodun yürütülmesi sırasında, JavaScript motoru değişkenin tanımını, kodun yukarı kısmına (global etki alanına) taşır ve undefined değeri ile başlar. Bu nedenle, console.log(myVariable) ifadesi undefined değerini yazdırır.
Ancak, let ve const anahtar kelimeleriyle tanımlanan değişkenlerde hoisting (kaldırma) meydana gelmez. Bu nedenle, let veya const anahtar kelimeleri kullanıldığında, değişkenin tanımlandığı yerde kullanılmadan önce tanımlanmış olması gerekir. Aksi halde, "ReferenceError: x is not defined" gibi bir hata mesajı alınır.
Thread: JavaScript, tek iş parçacıklı (single-threaded) bir programlama dilidir, bu nedenle JavaScript'te doğrudan Thread (iş parçası) kavramı bulunmaz. Bu, JavaScript'in yalnızca tek bir iş parçası (main thread) üzerinde çalıştığı anlamına gelir. Bu nedenle, JavaScript'te birden fazla işi aynı anda yapmak istediğinizde, örneğin uzun süren bir işlemi arka planda çalıştırmak istediğinizde, bu işlemi asenkron fonksiyonlar veya Web Worker API gibi alternatif yöntemler kullanarak yapabilirsiniz.
Asenkron fonksiyonlar, JavaScript'te bir işlem bitmeden diğer işlemlere devam etmek için kullanılır. Bu sayede, uzun süren bir işlemi gerçekleştirmek için beklemek yerine, işlem gerçekleştirilirken diğer işlemleri yapabilirsiniz. Örneğin, bir dosya veya bir veritabanı üzerinde işlem yaparken, işlem tamamlanana kadar kullanıcının diğer işlemlerini yapmasına izin vermek isteyebilirsiniz.
Web Worker API, JavaScript kodunu birkaç farklı iş parçasında (thread) çalıştırmanızı sağlar. Bu sayede, ana işlemle aynı anda çalışan bir iş parçası oluşturabilirsiniz. Web Worker API, tarayıcılarda kullanılabilen bir özelliktir ve genellikle kullanıcı arayüzü işlemlerini yavaşlatmadan uzun süren işlemleri gerçekleştirmek için kullanılır.
Dependency: JavaScript'te "dependency" terimi, bir JavaScript projesinde kullanılan dışarıdan alınan veya yaratılan diğer modüllere ihtiyaç duyma durumunu ifade eder. Bu modüller, başka bir yerde tanımlanmış fonksiyonlar, sınıflar, değişkenler, paketler vb. olabilir.
Bir JavaScript projesinde, bir modülün veya kütüphanenin diğer modüller tarafından kullanılabilmesi için öncelikle bu modülün projede bir bağımlılık olarak tanımlanması gerekir. Bu bağımlılık, genellikle bir paket yöneticisi aracılığıyla projeye eklenir.
Bir JavaScript projesinin bağımlılıkları, genellikle "package.json" adlı bir dosyada tanımlanır. Bu dosya, projenin bağımlılıklarını ve bağımlılıkların sürümlerini listeler. Bağımlılıklar, "npm" veya "yarn" gibi paket yöneticileri aracılığıyla projeye eklenebilir.
Bağımlılıkların yönetimi, bir projenin çalışması için kritik önem taşır. Eğer bir bağımlılık güncellenirse veya kaldırılırsa, projenin çalışması da etkilenebilir. Bu nedenle, projelerin bağımlılıklarını yönetmek ve güncellemek, geliştirme sürecinde önemli bir adımdır.
Örneğin, bir React projesi geliştiriyorsunuz ve "axios" adlı bir HTTP kütüphanesini kullanarak bir API'den veri çekmek istiyorsunuz. Bu durumda, "axios" kütüphanesi bir bağımlılık olarak projenize eklenir. Bağımlılığı "package.json" dosyasına eklemek için aşağıdaki komutu kullanabilirsiniz:

```
npm install axios --save
```

Bu komut, "axios" kütüphanesini projenize ekler ve "package.json" dosyasına ekler. "--save" parametresi, "axios" kütüphanesinin projenin bağımlılıkları listesine (dependencies) eklenmesini sağlar.
Value:

###  Rest Operator(...): 

JavaScript'de Rest Operator (...) , bir dizi parametreyi tek bir değişkene toplamak veya bir diziyi başka bir diziye eklemek gibi işlemler yapmak için kullanılır.

Rest operatorü, bir fonksiyona değişken sayıda argüman geçirirken kullanılabilir. Fonksiyon parametreleri, rest operatörü ile tanımlandığında, fonksiyona geçirilen tüm argümanlar bir dizi olarak toplanır.

Örneğin, aşağıdaki örnekte rest operatörü kullanılarak bir fonksiyona değişken sayıda parametre geçirilir:

const sebzeler = ['havuç', 'brokoli', ...meyveler];

console.log(sebzeler); // ['havuç', 'brokoli', 'elma', 'armut', 'muz']

Yukarıdaki örnekte, ...meyveler ifadesi, meyveler dizisinin elemanlarını tek tek ayırarak sebzeler dizisine ekler. Sonuç olarak, sebzeler dizisi, önce 'havuç' ve 'brokoli' olmak üzere iki sebze ve ardından meyveler dizisinin elemanları olan 'elma', 'armut' ve 'muz' şeklinde bir dizi haline gelir.

### Spread Oparator(...): 

JavaScript'de Spread Operator (...) bir dizi veya nesne ifadesinin öğelerini ayrıştırmak için kullanılır.

Dizi öğeleri için, Spread Operator, bir dizi ifadesinin tüm öğelerini ayırır ve bunları farklı bir dizi içine yerleştirir. Örneğin:

const numbers = [1, 2, 3];
const moreNumbers = [4, 5, 6];
const allNumbers = [...numbers, ...moreNumbers];

console.log(allNumbers); // [1, 2, 3, 4, 5, 6]
Burada, numbers ve moreNumbers dizileri, Spread Operator (...) kullanarak allNumbers dizisinde birleştirilir.

Nesne özellikleri için, Spread Operator, bir nesne ifadesindeki özellikleri başka bir nesneye kopyalamak için kullanılır. Örneğin:

const person = { name: "John", age: 30 };
const newPerson = { ...person, city: "Istanbul" };

console.log(newPerson); // { name: "John", age: 30, city: "Istanbul" }
Burada, person nesnesi, Spread Operator (...) kullanarak newPerson nesnesine kopyalanır ve yeni bir city özelliği eklenir.

### Mutable:
(Object, Array, Map, Set)

JavaScript'te bir değişkenin değerini değiştirebiliyorsanız, o değişken değiştirilebilirdir veya "mutable" olarak adlandırılır. Bu, örneğin bir dizi veya nesne gibi veri türleri için geçerlidir. Örneğin, bir diziye yeni bir öğe ekleyebilir veya bir nesnenin özelliklerini değiştirebilirsiniz ve bu değişiklikler doğrudan orijinal nesneyi etkiler.

Örneğin, aşağıdaki kodda bir diziyi değiştiriyoruz:

let myArray = [1, 2, 3];
myArray.push(4);
console.log(myArray); // [1, 2, 3, 4]

myArray dizisine push() yöntemi kullanarak 4 değerini ekledik. Bu, dizinin orijinal halini değiştirdi ve [1, 2, 3, 4] olarak güncellendi. Bu, dizi değiştirilebilir olduğu için mümkündür.

### Immutable: 
(String, Number, Boolean, null, undefined, Symbol)

JavaScript'te, bazı veri tipleri değiştirilemez (immutable) olarak adlandırılır, yani bir kez oluşturulduktan sonra değiştirilemezler. Bu özellik, programlama dilinin güvenli ve tutarlı kalmasını sağlar. Aşağıda, JavaScript'te değiştirilemez olan bazı veri tipleri listelenmiştir:

String: Bir kez oluşturulduktan sonra, bir dize (string) değiştirilemez. Bunun yerine, var olan bir dizenin bölümleri kopyalanarak yeni bir dize oluşturulabilir.
Örnek:
let str1 = "JavaScript";
let str2 = str1.slice(0,4) + " is fun!";
console.log(str2); // "Java is fun!"

Number: Bir sayı (number) değiştirilemezdir. Bunun yerine, var olan bir sayının matematiksel işlemler sonucunda elde edilen yeni bir sayı oluşturulabilir.
Örnek:

let num1 = 10;
let num2 = num1 + 5;
console.log(num2); // 15

Boolean: Bir boolean değiştirilemezdir. Bunun yerine, var olan bir boolean'ın değeri, mantıksal işlemler sonucunda elde edilen yeni bir boolean ile değiştirilebilir.
Örnek:
let bool1 = true;
let bool2 = !bool1;
console.log(bool2); // false
Symbol: Bir sembol (symbol) değiştirilemezdir. Her sembol benzersizdir ve bir kez oluşturulduktan sonra değiştirilemez.
Örnek:

let sym1 = Symbol("foo");
let sym2 = Symbol("foo");
console.log(sym1 === sym2); // false
Bu değiştirilemez veri tipleri, genellikle bir nesne içinde saklanarak kullanılır. Nesneler, özelliklerin ve değerlerin bir koleksiyonudur ve nesnelerin kendileri değiştirilebilir olsa da, nesne içindeki özellikler değiştirilemez olabilir.

### Mutate 

JavaScript'te "mutate" kelimesi, bir değişkenin değerinin değiştirilmesi anlamına gelir. Yani, bir değişkenin içeriği değiştirildiğinde, bu değişken "mutate" edilir. Bu, özellikle mutable veri tipleri (örneğin, dizi veya nesne) ile ilgili bir kavramdır, çünkü bu tür veri tiplerinin içeriği doğrudan değiştirilebilir. Immutable veri tipleri (örneğin, string veya number) ise değiştirilemezdir, bu nedenle değerleri değiştirilemez ve "mutate" edilemez.

### Render 

JavaScript'te "render", bir web sayfası veya uygulamanın görsel arayüzünün oluşturulması veya güncellenmesi sürecidir. Genellikle React, Vue veya Angular gibi JavaScript çerçevelerinde kullanılır.

Render işlemi, belirli bir duruma (state) ve/veya belirli bir veri kaynağına (props) dayanarak, bir bileşenin veya bir sayfanın HTML, CSS ve JavaScript kodunu oluşturur. Bu kod daha sonra web tarayıcısı tarafından yorumlanarak, kullanıcıların görüntüleyebileceği bir web sayfası olarak sunulur.

Render işlemi, kullanıcının etkileşimleriyle birlikte, sayfa veya uygulama içindeki bileşenlerin durumlarının değişmesiyle de tetiklenebilir. Bu durumda, render işlemi otomatik olarak yenilenir ve sayfa veya uygulama görüntüsü güncellenir.

### Re-render

React.js gibi bir kütüphane veya framework kullanılarak geliştirilen web uygulamalarında, bir bileşen (component) belirli bir durumda (state) olabilir. Bu durum, kullanıcının etkileşimi veya başka bir olay tarafından tetiklenebilir ve bileşenin yeniden render edilmesi gerekebilir. Bu yeniden render işlemi, bileşenin arayüzünün güncellenmesini sağlar ve yeni duruma göre yeniden oluşturulur. Bu sürece re-rendering denir.

Örneğin, bir sayfadaki bir bileşen, bir butona tıklama gibi bir kullanıcı etkileşimi sonrasında yeniden render edilebilir ve belirli bir duruma geçebilir. Bu durumda, bileşenin state'indeki değişikliklere göre, React bileşenleri arayüzünü yeniden oluşturur ve günceller.

### Immediate Re-Export

JavaScript'te "Immediate Re-Export", modüllerin yeniden kullanılabilirliğini artırmak için kullanılan bir modüller sistemidir.

Bu sistemde, bir modülün içeriği başka bir modül tarafından yeniden kullanılabilecek şekilde hızlıca yeniden ihraç edilebilir. Bu yöntem, gerekli fonksiyonları ve verileri içeren ayrı bir dosya oluşturmak yerine, daha küçük, yeniden kullanılabilir parçalar halinde kod yazmanızı sağlar.

Örneğin, bir "helperFunctions.js" dosyası oluşturabilirsiniz ve bu dosyadaki işlevleri başka bir modülde yeniden kullanmak isteyebilirsiniz. Bunun yerine, "helperFunctions.js" dosyasını yeniden ihraç edebilirsiniz ve diğer modülde doğrudan kullanabilirsiniz. Bu, kodunuzu daha modüler hale getirir ve tekrar kullanılabilirliğini artırır.


### Ternary Conditional Operators

Ternary conditional operators, bir koşulun doğru veya yanlış olduğunu kontrol eden bir ifade tipidir. Bu ifade, bir koşul ifadesi, bir doğru ifadesi ve bir yanlış ifadesi içerir.

Kısaca şu şekilde yazılabilir:

koşul ? doğru ifade : yanlış ifade;

Burada koşul ifadesi, kontrol edilecek koşulu ifade eder. Eğer bu koşul doğru ise, doğru ifade çalıştırılır, aksi takdirde yanlış ifade çalıştırılır.

Örneğin:
let sayi = 10;
let sonuc = sayi > 0 ? "Sayı pozitif" : "Sayı negatif veya sıfır";
console.log(sonuc); // Sayı pozitif
Bu örnekte, sayi > 0 koşulu kontrol edilir. Bu koşul doğru olduğu için, sonuc değişkenine "Sayı pozitif" atanır ve console.log ifadesi ile sonuç ekrana yazdırılır.

### Statement

JavaScript'te statement (ifade) bir işlemi tanımlayan ve uygulayan bir kod satırıdır. JavaScript programları birçok farklı statement kullanır.

Örneğin, atama işlemi yapan statement (ifade) şu şekildedir:

let x = 5;

Fonksiyon çağırma statement'i (ifade) ise şu şekildedir:

console.log("Hello, World!");

Bir döngü (loop) oluşturma statement'i (ifade) şu şekildedir:

for (let i = 0; i < 10; i++) {
  console.log(i);
}
Bu örneklerde gördüğümüz gibi, statement'ler farklı amaçlar için kullanılabilir ve JavaScript programlarında çok sık kullanılırlar.

### Expression

JavaScript'te expression (ifade), bir değerin üretildiği ve bir işlemi gerçekleştirdiği kod bloğudur. Bir expression, bir değişkene atanabilir, bir fonksiyonun argümanı olarak kullanılabilir veya bir kontrol yapısının içinde kullanılabilir.

Örnek olarak, aşağıdaki expressionlar mevcuttur:

3 + 4
"Hello " + "world"
true && false
(function() { return "Merhaba dünya"; })()
Bu ifadelerin her biri, bir değer döndüren bir işlemi gerçekleştirir. Örneğin, ilk ifade "3 + 4" toplama işlemi gerçekleştirir ve sonucu "7" döndürür. İkinci ifade, iki string ifadeyi birleştirir ve sonucu "Hello world" string'ini döndürür.

Bir değişkenin değerini tanımlamak, bir fonksiyonun geri dönüş değerini belirlemek, bir dizi veya nesne öğesinin değerini almak veya bir işlemi gerçekleştirmek gibi birçok durumda expressionlar kullanılabilir.

### Declaration

JavaScript'te bir deklarasyon, değişken, sabit veya fonksiyonun tanımlanmasıdır. Bu, ilgili değişkenin veya fonksiyonun kullanılabilmesi için bir isim ataması yapar.

Örneğin, bir değişkenin deklarasyonu aşağıdaki gibi olabilir:
let x;
Bu deklarasyon, x adında bir değişkenin tanımlandığını ve kullanılabileceğini belirtir. Ancak bu deklarasyon, değişkenin bir değer atanması veya başlatılması anlamına gelmez.

Bir fonksiyonun deklarasyonu ise aşağıdaki gibi olabilir:

function myFunction() {
  // fonksiyon kodları
}

Bu deklarasyon, myFunction adında bir fonksiyonun tanımlandığını ve kullanılabileceğini belirtir. Bu fonksiyon, çağrıldığında fonksiyon kodlarını çalıştıracaktır.

Kısacası, bir deklarasyon, bir değişkenin veya fonksiyonun tanımlandığını belirtir ve ilgili adın kullanılabilmesi için bir atama yapar.

### Component(React)
Component (Bileşen), React'ta kullanıcı arayüzünü oluşturan ve kendine özgü işlevselliği olan bağımsız bir yapıdır. Bir bileşen, çıktı olarak JSX (JavaScript XML) adı verilen özel bir sözdizimini kullanarak render edilir ve kullanıcı arayüzünde görsel öğeleri temsil eder. Bileşenler, içerisinde bulunduğu diğer bileşenlerle birleştirilerek karmaşık bir yapı oluşturur.
````
import React from 'react';

// Basit fonksiyonel bileşen tanımı
const SimpleComponent = () => {
  return (
    <div>
      <h1>Merhaba, Dünya!</h1>
      <p>Bu en basit React bileşenidir.</p>
    </div>
  );
};

export default SimpleComponent;

````
### Props(React)

### State(React)

### Hooks(React)

### Cleanup Function(useEffect vs. için)

### Component Lifecycle (React)

### Array Destructuring(React):

### Object Destructuring(React):

### Key(React)

JavaScript'te "key" terimi, genellikle React gibi arayüz kitaplıklarında kullanılan bir özelliktir. "key" özelliği, bir listede veya başka bir grup elemanlar arasında benzersiz bir tanımlayıcı olarak kullanılır.
Örneğin, bir React uygulamasında bir liste görüntülemek istediğinizde, her öğe için benzersiz bir "key" özelliği belirlemelisiniz. Bu özellik, React'in liste elemanlarının etkili bir şekilde yeniden oluşturulmasına yardımcı olur.
React, bir öğenin anahtarını değiştirirseniz, öğenin tamamen yeniden oluşturulacağını ve bu nedenle performans sorunlarına neden olabileceğini bilir. Bu nedenle, öğeler arasında benzersiz bir "key" özelliği kullanmak önemlidir.
Örneğin, aşağıdaki kodda "key" özelliği "person.id" olarak belirlenmiştir:

```
{persons.map(person => (
  <div key={person.id}>
    <span>{person.name}</span>
    <span>{person.age}</span>
  </div>
))}
```

Bu örnekte, "persons" adlı bir dizi veri kullanılarak bir liste oluşturulmuştur. Her bir öğe için benzersiz bir "key" özelliği olarak "person.id" kullanılmıştır. Bu özellik, her öğenin benzersiz olarak tanımlanmasını sağlar ve liste elemanlarının yeniden oluşturulmasını etkili bir şekilde yönetir.

### Mount

JavaScript'te "Mount" terimi, genellikle React ve diğer arayüz kitaplıklarında kullanılan bir kavramdır. "Mount" işlemi, bir bileşenin ilk kez arayüze eklenmesi anlamına gelir.
Örneğin, bir React bileşeni, sayfa yüklendiğinde ilk kez "mount" edilir. Bu aşamada, bileşenin hayat döngüsü yöntemleri (lifecycle methods) çağrılır ve bileşen hazırlanır.
React bileşenlerinin hayat döngüsünde, "componentDidMount()" adlı bir yöntem, bileşenin ilk kez "mount" edildiğinde çağrılır. Bu yöntem, bileşenin hazırlık işlemlerinin tamamlandığı anlamına gelir.
Örneğin, aşağıdaki kodda bir React bileşeni "MyComponent" tanımlanmıştır. "componentDidMount()" yöntemi, bileşen "mount" edildiğinde "console.log()" fonksiyonu çağrılarak bir mesaj yazdırır:

```
import React, { Component } from 'react';
class MyComponent extends Component {
  componentDidMount() {
    console.log('MyComponent is mounted!');
  }
  render() {
    return (
      <div>
        <h1>Hello World!</h1>
      </div>
    );
  }
}
export default MyComponent;
```

Tabii, bu örnekte "MyComponent" adlı bir React sınıf bileşeni tanımlanmıştır. Bu bileşen, "Component" adlı üst sınıfı genişletir ve bu sayede React'in özelliklerinden yararlanabilir.
Bileşenin "componentDidMount()" yöntemi, bileşenin "mount" edildiğinde otomatik olarak çağrılır. Bu örnekte, "componentDidMount()" yöntemi, konsola "MyComponent is mounted!" mesajını yazdırır.
Bileşenin "render()" yöntemi, bileşenin arayüzünü tanımlar. Bu örnekte, "render()" yöntemi, bir "div" bileşeni içinde bir "h1" başlığı içeren "Hello World!" metnini döndürür.
Son olarak, "MyComponent" bileşeni, dışa aktarılır ve başka bir dosyada kullanılabilir hale gelir.
Bu örnekte, "Mount" işlemi, React sınıf bileşenlerinin hayat döngüsünde önemli bir yer tutar ve bileşenin arayüze ilk kez eklenmesini ifade eder. "componentDidMount()" yöntemi, bileşen "mount" edildiğinde çağrıldığı için, "Mount" işlemi tamamlanmış demektir ve işlemlere devam edilebilir.

### Unmount: 
"Unmount" işlemi, bir React bileşeninin arayüzden kaldırılmasıdır ve bu işlem sırasında "componentWillUnmount()" yöntemi otomatik olarak çağrılır. Bu yöntem, bileşenin "unmount" işlemi sırasında yapılması gereken temizleme veya sonlandırma işlemlerinin yapılması için kullanılabilir.
Örneğin, bir bileşen "mount" edildiğinde, bir zamanlayıcı başlatılabilir. Bileşen "unmount" edildiğinde, bu zamanlayıcı durdurulmalıdır. Bunun için "componentWillUnmount()" yöntemi kullanılabilir.
İşte, bir React sınıf bileşeninde "Unmount" işleminin nasıl kullanılabileceğiyle ilgili basit bir örnek:

```
import React, { Component } from 'react';
class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.timer = null;
  }
  componentDidMount() {
    this.timer = setInterval(() => {
      console.log('Tick');
    }, 1000);
  }
  componentWillUnmount() {
    clearInterval(this.timer);
  }
  render() {
    return (
      <div>
        <h1>Hello World!</h1>
      </div>
    );
  }
}
export default MyComponent;
```

Bu örnekte, "MyComponent" adlı bir React sınıf bileşeni tanımlanmıştır. Bileşen, "constructor()" yöntemiyle bir "timer" adlı değişkeni "null" olarak başlatır.
Bileşen "mount" edildiğinde, "componentDidMount()" yöntemi çağrılır. Bu yöntem, "setInterval()" fonksiyonunu kullanarak bir zamanlayıcı oluşturur ve her saniye "Tick" mesajını konsola yazdırır. Zamanlayıcı, "this.timer" değişkenine atanan referans ile kaydedilir.
Bileşen "unmount" edildiğinde, "componentWillUnmount()" yöntemi çağrılır. Bu yöntem, "this.timer" değişkeninin var olup olmadığını kontrol eder. Eğer değişken varsa, "clearInterval()" fonksiyonunu kullanarak zamanlayıcıyı durdurur ve "this.timer" değişkenini "null" olarak ayarlar.
Böylece, "Unmount" işlemi sırasında bileşenin "componentWillUnmount()" yöntemi sayesinde, oluşturulan zamanlayıcının durdurulması sağlanmış olur. Bu da bellek sızıntısı ve performans sorunlarının önlenmesine yardımcı olur.

### Initializations: 

```
constructor()
```

```
super()
```
## Matematik Fonksiyonları

JavaScript'te matematik işlemlerini yapmak için kullanabileceğiniz birçok farklı fonksiyon bulunur. Aşağıda, JavaScript'te bulunan tüm matematik fonksiyonları ve örnekleri yer almaktadır:

### Math.abs(x): 

Bir sayının mutlak değerini döndürür.
```
console.log(Math.abs(-5)); // 5
```

### Math.ceil(x): 

Bir sayıyı yukarı yuvarlar.
```
console.log(Math.ceil(3.14)); // 4
```

### Math.floor(x): 

Bir sayıyı aşağı yuvarlar.
```
console.log(Math.floor(3.99)); // 3
```

### Math.round(x):

Bir sayıyı en yakın tam sayıya yuvarlar.
```
console.log(Math.round(3.5)); // 4
```

### Math.min(x, y, z, ...): 

Verilen sayıların en küçüğünü döndürür.
```
console.log(Math.min(1, 2, 3)); // 1
```

### Math.max(x, y, z, ...): 

Verilen sayıların en büyüğünü döndürür.
```
console.log(Math.max(1, 2, 3)); // 3
```

### Math.pow(x, y):

Bir sayının üssünü hesaplar.
```
console.log(Math.pow(2, 3)); // 8
```

### Math.sqrt(x): 

Bir sayının karekökünü hesaplar.
```
console.log(Math.sqrt(16)); // 4
```

### Math.random():

0 ile 1 arasında rastgele bir ondalıklı sayı döndürür.
```
console.log(Math.random()); // 0.5870397381056959
```

### Math.sin(x): 

Bir açının sinüsünü hesaplar.
```
console.log(Math.sin(Math.PI / 2)); // 1
```

### Math.cos(x): 

Bir açının kosinüsünü hesaplar.
```
console.log(Math.cos(Math.PI)); // -1
```

### Math.tan(x):

Bir açının tanjantını hesaplar.
```
console.log(Math.tan(Math.PI / 4)); // 0.9999999999999999
```

### Math.asin(x): 

Bir sayının arcsinüsünü hesaplar.
```
console.log(Math.asin(1)); // 1.5707963267948966
```

### Math.acos(x):

Bir sayının arccosinüsünü hesaplar.
```
console.log(Math.acos(-1)); // 3.141592653589793
```

### Math.atan(x): 

Bir sayının arctanjantını hesaplar.
```
console.log(Math.atan(1)); // 0.7853981633974483
```

## Dize Fonksiyonları

### charAt(index): 

Belirtilen dizindeki karakteri döndürür.
Örnek:
```
const str = 'Merhaba';
console.log(str.charAt(0)); // "M"
```

### concat(str1, str2, ...): 

Bir veya daha fazla dizeyi birleştirir.
Örnek:
```
const str1 = 'Merhaba';
const str2 = 'Dünya';
console.log(str1.concat(' ', str2)); // "Merhaba Dünya"
```

### includes(searchString, position): 

Belirtilen bir alt dizenin orijinal dizide var olup olmadığını kontrol eder.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.includes('Dünya')); // true
console.log(str.includes('dünya')); // false
```

### endsWith(searchString, length): 

Bir dizenin belirtilen alt dizelerle bitip bitmediğini kontrol eder.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.endsWith('Dünya')); // true
console.log(str.endsWith('Merhaba')); // false
```

### indexOf(searchValue, fromIndex): 

Belirtilen bir alt dizinin ilk oluşumunun dizinini döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.indexOf('Dünya')); // 8
console.log(str.indexOf('dünya')); // -1
```

### lastIndexOf(searchValue, fromIndex): Belirtilen bir alt dizinin son oluşumunun dizinini döndürür.

Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.lastIndexOf('a')); // 9
console.log(str.lastIndexOf('dünya')); // -1
```

### match(regexp): 

Bir dizedeki bir düzenli ifadeyi arar ve sonuçları döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.match(/Dünya/)); // ["Dünya", index: 8, input: "Merhaba Dünya", groups: undefined]
console.log(str.match(/dünya/)); // null
```

### replace(regexp|substr, newSubStr|function): 

Bir dizenin belirli karakterlerini yeni bir dizeyle değiştirir.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.replace('Dünya', 'Mars')); // "Merhaba Mars"
```

### search(regexp): 

Bir dizede belirli bir düzenli ifadeyi arar ve ilk eşleşmenin indeksini döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.search(/Dünya/)); // 8
console.log(str.search(/dünya/)); // -1
```

### slice(beginIndex, endIndex): 

Bir dizenin belirli bir kısmını bir başlangıç ve bir bitiş dizini aralığında keser.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.slice(0, 7)); // "Merhaba"
```

### split(separator, limit): Bir dizeyi belirli bir ayırıcı karakterine göre böler ve parçalarını bir diziye koyar.

Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.split(' ')); // ["Merhaba", "Dünya"]
```

### startsWith(searchString, position): 

Bir dizenin belirtilen bir alt dizeyle başlayıp başlamadığını kontrol eder.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.startsWith('Merhaba')); // true
console.log(str.startsWith('Dünya')); // false
```

### substring(indexStart, indexEnd): 

Bir dizenin belirtilen bir dizin aralığındaki karakterlerini döndürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.substring(0, 7)); // "Merhaba"
```

### toLocaleLowerCase(): 

Bir dizenin tüm karakterlerini küçük harfe dönüştürür.
Örnek:
```
const str = 'MERHABA DÜNYA';
console.log(str.toLocaleLowerCase()); // "merhaba dünya"
```

### toLocaleUpperCase(): 

Bir dizenin tüm karakterlerini büyük harfe dönüştürür.
Örnek:
```
const str = 'merhaba dünya';
console.log(str.toLocaleUpperCase()); // "MERHABA DÜNYA"
```

### toLowerCase(): 

Bir dizenin tüm karakterlerini küçük harfe dönüştürür.
Örnek:
```
const str = 'MERHABA DÜNYA';
console.log(str.toLowerCase()); // "merhaba dünya"
```

### toString(): 

Bir dizeyi string veri tipine dönüştürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.toString()); // "Merhaba Dünya"
```

### toUpperCase(): 

Bir dizenin tüm karakterlerini büyük harfe dönüştürür.
Örnek:
```
const str = 'merhaba dünya';
console.log(str.toUpperCase()); // "MERHABA DÜNYA"
```

### trim(): 

Bir dizenin başındaki ve sonundaki boşlukları kaldırır.
Örnek:
```
const str = '   Merhaba Dünya   ';
console.log(str.trim()); // "Merhaba Dünya"
```

### valueOf(): 

Bir dizeyi primitive veri tipine dönüştürür.
Örnek:
```
const str = 'Merhaba Dünya';
console.log(str.valueOf()); // "Merhaba Dünya"
```

### Dizi Fonksiyonları

## concat()
```
```

## copyWithin()
```
```
## entries()
```
```

## every()
```
```

## fill()
```
```

## filter()
```
```

## find()
```
```

## findIndex()
```
```

## flat()
```
```

## flatMap()
```
```

## forEach()
```
```

## from()
```
```

## includes()
```
```

## indexOf()
```
```

## isArray()
```
```

## join()
```
```

## keys()
```
```

## lastIndexOf()
```
```

## map()
```
```

## pop()
```
```

## push()
```
```

## reduce()
```
```

## reduceRight()
```
```

## reverse()
```
```

## shift()
```
```

## slice()
```
```

## some()
```
```

## sort()
```
```

## splice()
```
```

## toLocaleString()
```
```

## toString()
```
```

## unshift()
```
```

## values()
```
```

### Zamanlama Fonksiyonları
JavaScript'te kullanabileceğiniz birkaç zamanlama fonksiyonu şunlardır:

## setTimeout()

```
function showAlert() {
  alert("1 saniye sonra gösterildi!");
}
setTimeout(showAlert, 1000);
```

## setInterval()

```
let count = 0;
let intervalId = setInterval(() => {
  console.log(count);
  count++;
}, 1000);
```

## clearTimeout()

```
let timeoutId = setTimeout(() => {
  console.log("Bu mesaj bir saniye sonra yazdırılacak.");
}, 1000);
clearTimeout(timeoutId);
```

## clearInterval()

```
let count = 0;
let intervalId = setInterval(() => {
  console.log(count);
  count++;
  if (count === 5) {
    clearInterval(intervalId);
  }
}, 1000);
```

## requestAnimationFrame()

```
let box = document.getElementById("box");
let position = 0;
function animate() {
  position += 1;
  box.style.left = position + "px";
  requestAnimationFrame(animate);
}
```

## requestAnimationFrame(animate);

```
setImmediate()
setImmediate(() => {
  console.log("Bu mesaj hemen yazdırılacak.");
});
```

## clearImmediate()

```
let immediateId = setImmediate(() => {
  console.log("Bu mesaj hemen yazdırılacak.");
});
clearImmediate(immediateId);

process.nextTick()
console.log("1. adım");
process.nextTick(() => {
  console.log("3. adım");
});
console.log("2. adım");
```

### DOM Manipülasyon Fonksiyonları

## getElementById(): 
Belirtilen id değeri ile eşleşen ilk HTML elemanını döndürür.
```
```

## getElementsByClassName(): 
Belirtilen sınıf adına sahip tüm HTML elemanlarını bir HTMLCollection nesnesi olarak döndürür.
```
```

## getElementsByTagName(): 
Belirtilen etiket adı ile eşleşen tüm HTML elemanlarını bir HTMLCollection nesnesi olarak döndürür.
```
```

## querySelector(): 
CSS seçicisi ile eşleşen ilk HTML elemanını döndürür.
```
```

## querySelectorAll(): 
CSS seçicisi ile eşleşen tüm HTML elemanlarını bir NodeList nesnesi olarak döndürür.
```
```

## createElement(): 
Belirtilen HTML etiketi ile yeni bir HTML elemanı oluşturur.
```
```

## createTextNode(): 
Belirtilen metin içeriği ile yeni bir Text düğümü oluşturur.
```
```

## appendChild(): 
Belirtilen HTML elemanını bir başka HTML elemanının alt öğesi olarak ekler.
```
```

## removeChild(): 
Bir HTML elemanının alt öğesini kaldırır.
```
```

## replaceChild(): 
Bir HTML elemanının alt öğesini başka bir HTML elemanı ile değiştirir.
```
```

## insertBefore(): 
Bir HTML elemanını, belirtilen diğer bir HTML elemanının önüne ekler.
```
```

## setAttribute(): 
Bir HTML elemanına belirtilen nitelik adı ve değerini ekler veya günceller.
```
```

## getAttribute(): 
Belirtilen nitelik adına sahip bir HTML elemanının değerini döndürür.
```
```

## removeAttribute(): 
Bir HTML elemanından belirtilen niteliği kaldırır.
```
```

## classList.add(): 
Bir HTML elemanına belirtilen sınıf adını ekler.
```
```

## classList.remove(): 
Bir HTML elemanından belirtilen sınıf adını kaldırır.
```
```

## classList.toggle(): 
Bir HTML elemanında belirtilen sınıf adını ekler veya kaldırır.
```
```

## style.setProperty(): 
Belirtilen stil özelliğine belirtilen değeri atar veya günceller.
```
```

## style.removeProperty(): 
Belirtilen stil özelliğini kaldırır.
```
```

## addEventListener(): 
Belirtilen olay dinleyicisini bir HTML elemanına ekler.
```
```

## removeEventListener(): 
Belirtilen olay dinleyicisini bir HTML elemanından kaldırır.
```
```

## event.preventDefault(): 
Belirtilen olayın varsayılan davranışını önler.
```
```

## event.stopPropagation(): 
Bir olayın daha fazla elemanlara yayılmasını engeller.
```
```

## event.target: 
Bir olayın hedef HTML elemanını döndürür.
```
```

## event.currentTarget: 
Bir olayı dinleyen HTML elemanını döndürür.
```
```

### Koşullu İfadeler ve Döngüler
### Nesne Fonksiyonları
### Tarayıcı İşlevleri
### Ağ İşlevleri
### Dosya İşlevleri
### Local Storage Fonksiyonları
### JSON Fonksiyonları
### Hata Yakalama ve Ayıklama
### Yapıcı Fonksiyonlar ve Prototipler
### Asenkron Programlama (Promise, Async/Await, Callback)
### RegEx (Düzenli İfadeler) Fonksiyonları
### Fonksiyonlar için Argümanlar ve Değerleri
### Dosya İşlemleri
### Şifreleme ve Güvenlik
### Diğer Özellikler ve Fonksiyonlar

</details>
