# Flux Files — Privacy Policy / Gizlilik Politikası

**Last updated / Son güncelleme:** 12 October 2026 / 12 Ekim 2026

**Scope / Kapsam:** Flux Files for Android / Android için Flux Files 0.9.1 (22), `app.p1p3kc1.fluxfiles`.

**Language / Dil:** [English](#english) · [Türkçe](#türkçe)

## English

### Overview

Flux Files is a file manager that helps you browse, organize, search, preview, and manage files on your Android device. This policy explains how file management and the optional Private Vault feature process data.

### File access and APK installation

The app requests storage access for browsing, copying, moving, renaming, deleting, restoring, and archive operations. Depending on the Android version, it uses storage permissions or All Files Access (`MANAGE_EXTERNAL_STORAGE`). Within the access you grant, it may process file contents, names, location references, types, sizes, and modification information. Android's restrictions on other apps' protected storage continue to apply.

When you explicitly choose an APK file for installation, the app may request permission to install apps from this source. This permission is not requested at ordinary startup. Installation is handled by Android's system installer.

### On-device processing, internet access, and sharing

File management, search, previews, thumbnails, storage analysis, archives, and Private Vault operations run on the device. No application flow sending files, PINs, or recovery keys to a developer server, and no advertising, usage analytics, remote crash reporting, or cloud synchronization integration was identified in the reviewed 0.9.1+22 release. This release's AAB manifest does not declare the `INTERNET` permission. It declares `ACCESS_NETWORK_STATE`, which concerns network connection status and is not the same as the `INTERNET` permission.

This does not mean that other apps or the operating system do not process data. When you choose sharing or opening in another app, the receiving app is given access to the selected content. It may use the internet or transmit data under its own privacy practices.

The privacy policy link opens in an external browser. Visiting the GitHub Pages site requires an internet connection; the host, browser, and providers of resources loaded by the page may process connection information such as your IP address. The current page theme also loads a script from cdnjs. The [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) explains that service's practices. If you contact us by email, the information you send is transmitted through email services; do not send your PIN or recovery key.

### Local application data

The app may keep preferences and pinned references, operation/Trash records that can include file names and location references, cached thumbnails, and file index/storage analysis snapshots in its private storage. Activity history is limited to the latest 200 records. Trash records do not automatically expire. Caches may be refreshed or removed during operation. These ordinary file management records are outside Private Vault encryption and rely on Android's app storage protection.

### Private Vault: storage and previews

The contents and original names of files imported into Private Vault are stored as encrypted files in the app-private `noBackupFilesDir/vault` directory on the device. This is not a shared gallery or user folder. Encryption uses authenticated AES-GCM-based streaming encryption. Technical information, including encrypted copies of the vault key, a random salt, and a vault identifier, is also stored privately. Technical file identifiers, encrypted file sizes, and filesystem timestamps are not hidden by the same content encryption.

Supported image/video previews and vault thumbnails are decrypted and processed in memory during the session. The app does not create decrypted preview files on disk for these preview flows. Leaving the vault screen or placing the app in the background locks the vault and clears session/preview resources. The vault screen uses Android's secure window flag to restrict screenshots. These measures are not a guarantee of absolute security or irreversible erasure of every memory copy.

Moving a file into Private Vault first creates and verifies the encrypted copy, then attempts to delete the source. If source deletion fails, the original copy may remain outside the vault and the app reports this. Other existing copies, other apps' caches, or backups are not removed by this operation.

### PIN

The vault PIN consists of six digits. On the device, the entered PIN is processed using HMAC-SHA256 with an installation-associated key held in Android Keystore. The result is passed through Argon2id key derivation with a random salt. The derived key is used to unlock the vault key. The app does not write the PIN to persistent storage in plaintext. The PIN and derived values are processed in memory during entry and authentication.

Unlock attempt counts and waiting periods are stored in private, backup-excluded storage on the device. Repeated unsuccessful attempts trigger a waiting period. The PIN-associated Keystore key is not included in a portable vault backup; the old PIN alone cannot be relied on to restore the vault in another installation.

### Recovery key and backups

A random 256-bit recovery key is generated on the device during setup or key renewal and shown to you. The app does not persist the recovery key itself in a plaintext file; it stores a copy of the vault key protected by the recovery key. The key screen provides no copy button and does not make the text selectable. You need to keep the recovery key separately in a safe place.

The recovery key can unlock the local vault and restore an exported vault backup. After recovery-based unlocking, the interface asks you to set a new PIN. There is no mechanism to send the key to the developer or recover it from the developer.

A `.fluxvault` backup created at your request writes encrypted files, the key header, and integrity verification information to your chosen destination. Original file names and contents remain encrypted; technical archive information is not entirely hidden. Restoration requires the recovery key that applied when the backup was created. Renewing the recovery key or changing the PIN does not update or invalidate previously exported backups. Protect backup files and their corresponding keys separately.

**Exporting an individual file is different:** it creates a decrypted copy at the destination you choose. That copy is outside Private Vault protection. The backup/export picker asks Android to show local destinations only; Flux Files does not control subsequent synchronization or backup by the selected document provider, destination folder, or other apps.

### Biometric authentication

Biometric unlocking is optional and enabled through Android's system authentication prompt on supported devices. The app does not receive or store fingerprint or face images or biometric templates. Android supplies the authentication result and the authorized cryptographic operation to the app.

When you enable it, a copy of the vault key is encrypted with a separate Android Keystore key that requires biometric authentication. This encrypted copy and associated technical information are kept in app-private, backup-excluded storage on the device; they are not biometric templates. Enrolling a new biometric may invalidate the key. Disabling biometric unlocking deletes the associated encrypted copy and Keystore key. Biometrics do not replace the recovery key for restoring a backup in another installation.

### Retention, deletion, and uninstalling

Vault files remain in private storage until you delete them or the app's data is removed. Clearing app data or uninstalling the app causes loss of the local vault, settings, and records. A recovery key alone cannot recreate deleted files; an appropriate vault backup is also required. Exported files and backups remain at their chosen destinations and must be managed separately.

Android automatic app backup is disabled, and the app's cloud backup and device transfer rules exclude its data. The vault also uses Android's private no-backup area. A `.fluxvault` backup explicitly created by you is separate from these settings. No guarantee is made about every manufacturer's or third-party tool's backup behavior.

Removing app data also loses Trash restoration records; files remaining in shared storage or a document provider may no longer be automatically restorable. File deletion does not guarantee that data on the storage medium is forensically unrecoverable.

### Children's privacy and changes

Flux Files is a general-purpose utility and is not specifically designed for children. This policy may be updated when features or data practices change; the update date is shown on this page.

### Contact

For privacy-related questions: [ipekci.ismail18@gmail.com](mailto:ipekci.ismail18@gmail.com).

---

## Türkçe

### Genel bakış

Flux Files, Android cihazınızdaki dosyaları görüntülemenize, düzenlemenize, aramanıza, önizlemenize ve yönetmenize yardımcı olan bir dosya yöneticisidir. Bu politika, dosya yönetimi ile isteğe bağlı Gizli Depo özelliğinin verileri nasıl işlediğini açıklar.

### Dosya erişimi ve APK yükleme

Uygulama; gezinme, kopyalama, taşıma, yeniden adlandırma, silme, geri yükleme ve arşiv işlemleri için depolama erişimi ister. Android sürümüne göre depolama izinleri veya Tüm Dosyalara Erişim (`MANAGE_EXTERNAL_STORAGE`) kullanılır. Verdiğiniz erişim kapsamında dosya içerikleri, adları, konumları, türleri, boyutları ve değiştirilme bilgileri işlenebilir. Android'in diğer uygulamalara ait korunan alanlarına erişim sınırları geçerlidir.

Bir APK dosyasını yüklemek üzere açıkça seçtiğinizde, uygulama bu kaynaktan uygulama yükleme izni isteyebilir. Bu izin normal açılışta istenmez. Yükleme Android'in sistem yükleyicisi üzerinden yürütülür.

### Cihaz üzerinde işleme, internet ve paylaşım

Dosya yönetimi, arama, önizleme, küçük resim oluşturma, depolama analizi, arşiv ve Gizli Depo işlemleri cihaz üzerinde yürütülür. İncelenen 0.9.1+22 sürümünde geliştirici sunucusuna dosya, PIN veya kurtarma anahtarı gönderen bir uygulama akışı; reklam, kullanım analitiği, uzaktan hata raporlama veya bulut eşitleme entegrasyonu tespit edilmemiştir. Bu sürümün release AAB manifestinde `INTERNET` izni bulunmamaktadır. Ağ bağlantı durumunu sorgulamaya ilişkin `ACCESS_NETWORK_STATE` izni bulunmaktadır; bu izin `INTERNET` izniyle aynı değildir.

Bu açıklama, cihazdaki diğer uygulamaların veya işletim sisteminin veri işlemediği anlamına gelmez. Paylaşma veya başka uygulamada açma işlemini seçtiğinizde, seçilen içeriğe alıcı uygulamanın erişmesi sağlanır. Alıcı uygulama kendi gizlilik kurallarına göre internet kullanabilir veya verileri aktarabilir.

Gizlilik politikası bağlantısı harici tarayıcıda açılır. GitHub Pages üzerindeki sayfayı ziyaret etmek internet bağlantısı gerektirir; barındırma hizmeti, tarayıcı ve sayfanın yüklediği kaynak sağlayıcıları IP adresi gibi bağlantı bilgilerini işleyebilir. Sayfanın mevcut teması ayrıca cdnjs üzerinden bir betik yüklemektedir. [GitHub Gizlilik Bildirimi](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement) bu hizmetin uygulamalarını açıklar. E-posta ile iletişim kurarsanız, gönderdiğiniz bilgiler e-posta hizmetleri üzerinden iletilir; PIN'inizi veya kurtarma anahtarınızı göndermeyin.

### Yerel uygulama verileri

Uygulama; ayarları ve sabitlenmiş başvuruları, dosya adları ve konum başvuruları içerebilen işlem/Çöp Kutusu kayıtlarını, küçük resim önbelleğini ve dosya indeksi/depolama analizi özetlerini kendi özel alanında saklayabilir. İşlem geçmişi son 200 kayıtla sınırlandırılır. Çöp Kutusu kayıtlarının otomatik süre sonunda silinmesi uygulanmaz. Önbellekler işleyiş sırasında yenilenebilir veya temizlenebilir. Normal dosya yönetimine ait bu kayıtlar Gizli Depo şifrelemesinin kapsamına girmez; Android'in uygulama alanı korumasına tabidir.

### Gizli Depo: saklama ve önizleme

Gizli Depo'ya alınan dosyaların içerikleri ve özgün dosya adları, cihazda uygulamaya özel `noBackupFilesDir/vault` dizininde şifreli dosyalar olarak saklanır. Burası ortak bir galeri veya kullanıcı klasörü değildir. Şifreleme, kimliği doğrulanmış AES-GCM tabanlı akış şifrelemesi kullanır. Anahtarı korumak için kullanılan şifreli anahtar kopyaları, rastgele tuz ve depo kimliği gibi teknik bilgiler de özel alanda tutulur. Teknik dosya kimlikleri, şifreli dosya boyutları ve dosya sistemi zaman bilgileri aynı içerik şifrelemesiyle gizlenmez.

Desteklenen görsel/video önizlemeleri ve Gizli Depo küçük resimleri, şifresi çözülerek oturum sırasında bellekte işlenir. Bu önizleme akışları için uygulama diskte şifresi çözülmüş bir önizleme dosyası oluşturmaz. Depo ekranından çıkışta veya uygulama arka plana geçtiğinde depo kilitlenir ve oturum/önizleme kaynakları temizlenir. Gizli Depo ekranı Android'in ekran görüntüsünü sınırlandıran güvenli pencere bayrağını kullanır. Bunlar mutlak güvenlik veya bellekteki her kopyanın geri getirilemez biçimde silindiği garantisi değildir.

Dosyayı Gizli Depo'ya taşıma işlemi, önce şifreli kopyayı oluşturur ve doğrular, ardından kaynak dosyayı silmeyi dener. Kaynak silinemezse dışarıdaki özgün kopya kalabilir ve uygulama bunu bildirir. Önceden oluşmuş başka kopyalar, diğer uygulamaların önbellekleri veya yedekleri bu işlemle ortadan kalkmaz.

### PIN

Gizli Depo PIN'i altı rakamdan oluşur. Girilen PIN, cihazda Android Keystore içinde tutulan kurulumla ilişkili bir anahtarla HMAC-SHA256 işleminden geçirilir; sonuç rastgele tuzla Argon2id anahtar türetme işleminde kullanılır. Böylece elde edilen anahtar, depo anahtarını açmak için kullanılır. PIN, uygulama tarafından kalıcı depolamaya açık metin olarak yazılmaz. Giriş sırasında PIN ve türetilen değerler bellekte işlenir.

Kilit açma deneme sayısı ve bekleme süresi cihazdaki özel, yedekleme dışı alanda tutulur. Tekrarlanan başarısız denemelerde bekleme uygulanır. PIN'e bağlı Keystore anahtarı taşınabilir depo yedeğine dahil edilmez; başka bir kurulumda yalnızca eski PIN'e güvenerek geri yükleme yapılamaz.

### Kurtarma anahtarı ve yedekler

Kurulumda veya anahtar yenilemede cihaz üzerinde rastgele 256 bitlik bir kurtarma anahtarı üretilir ve kullanıcıya gösterilir. Kurtarma anahtarının kendisi uygulama tarafından açık metin olarak kalıcı dosyaya yazılmaz; onunla korunan depo anahtarı kopyası saklanır. Anahtar ekranı kopyalama düğmesi sunmaz ve metni seçilebilir yapmaz. Anahtarı güvenli bir yerde ayrıca saklamanız gerekir.

Kurtarma anahtarı, yerel depoyu açmak ve dışa aktarılmış depo yedeğini geri yüklemek için kullanılabilir. Kurtarma yoluyla kilit açtıktan sonra arayüz yeni bir PIN belirlemenizi ister. Geliştiriciye anahtar gönderen veya geliştiriciden anahtar kurtaran bir mekanizma yoktur.

İsteğinizle oluşturulan `.fluxvault` yedeği, şifreli dosyaları, anahtar başlığını ve bütünlük denetimi bilgilerini seçtiğiniz konuma yazar. Özgün dosya adları ve içerikleri şifreli kalır; teknik arşiv bilgileri tümüyle gizlenmez. Geri yükleme, yedeğin oluşturulduğu zamandaki kurtarma anahtarını gerektirir. Kurtarma anahtarını yenilemek veya PIN'i değiştirmek daha önce dışa aktarılmış yedekleri güncellemez ya da geçersiz kılmaz. Yedek dosyalarını ve onlara ait anahtarları ayrıca koruyun.

**Tek dosyayı dışa aktarma farklıdır:** seçtiğiniz hedefte dosyanın şifresi çözülmüş bir kopyasını oluşturur. Bu kopya Gizli Depo korumasının dışında kalır. Yedekleme/dışa aktarma seçicisi Android'den yalnızca yerel hedefleri göstermesini ister; seçilen belge sağlayıcısının, hedef klasörün veya başka uygulamaların sonraki eşitleme/yedekleme davranışları Flux Files tarafından kontrol edilmez.

### Biyometrik doğrulama

Biyometrik kilit açma isteğe bağlıdır ve desteklenen cihazlarda Android'in sistem doğrulama penceresiyle etkinleştirilir. Uygulama parmak izi veya yüz görüntüsünü ya da biyometrik şablonlarını almaz veya saklamaz. Android doğrulamanın sonucunu ve izin verilen kriptografik işlemi uygulamaya sağlar.

Etkinleştirdiğinizde depo anahtarının bir kopyası, biyometrik doğrulama gerektiren ayrı bir Android Keystore anahtarıyla şifrelenir. Bu şifreli kopya ve ilgili teknik bilgiler, cihazdaki uygulamaya özel yedekleme dışı alanda tutulur; bunlar biyometrik şablon değildir. Yeni biyometrik kayıt yapılması anahtarı geçersiz kılabilir. Biyometrik kilit açmayı kapattığınızda ilgili şifreli kopya ve Keystore anahtarı silinir. Biyometri, başka bir kurulumda yedeği geri yüklemek için kurtarma anahtarının yerini almaz.

### Saklama, silme ve uygulamayı kaldırma

Gizli Depo dosyaları siz silene veya uygulamanın verileri kaldırılana kadar özel alanda tutulur. Uygulama verilerini temizlemek veya uygulamayı kaldırmak yerel depoyu, ayarları ve kayıtları kaybettirir. Kurtarma anahtarı tek başına silinen dosyaları yeniden oluşturamaz; geri dönüş için ayrıca uygun bir depo yedeği gerekir. Dışa aktarılan dosyalar ve yedekler seçtiğiniz konumlarda kalır ve ayrıca yönetilmelidir.

Android otomatik uygulama yedeklemesi kapatılmış; bulut yedeği ve cihaz aktarımı kurallarında uygulama verileri dışlanmıştır. Gizli Depo ayrıca Android'in yedekleme dışı özel alanını kullanır. Kullanıcının açıkça oluşturduğu `.fluxvault` yedeği bundan ayrıdır. Üreticilerin veya üçüncü taraf araçların tüm yedekleme davranışları için garanti verilmez.

Uygulama verilerinin kaldırılması, Çöp Kutusu geri yükleme kayıtlarını da kaybettirir; ortak depolamada veya belge sağlayıcısında kalan dosyalar otomatik olarak geri yüklenemeyebilir. Dosya silme işlemleri, depolama ortamında adli yöntemlerle geri getirilemez silme garantisi vermez.

### Çocukların gizliliği ve değişiklikler

Flux Files genel amaçlı bir yardımcı uygulamadır ve özellikle çocuklar için tasarlanmamıştır. Uygulamanın özellikleri veya veri işleme uygulamaları değiştiğinde bu politika güncellenebilir; güncelleme tarihi bu sayfada gösterilir.

### İletişim

Gizlilikle ilgili sorular için: [ipekci.ismail18@gmail.com](mailto:ipekci.ismail18@gmail.com).
