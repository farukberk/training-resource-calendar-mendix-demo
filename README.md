# Training Resource Calendar — Mendix Demo

Mendix Studio Pro 10.24.24 ile hazırlanmış, `Training Resource Calendar` pluggable widget'ının çalışır demo ve referans uygulamasıdır.

## Gereksinimler

- Mendix Studio Pro 10.24.24
- Yerel çalıştırma için Studio Pro'nun desteklediği Java/JDK bileşenleri

## İndirip çalıştırma

1. Repoyu indirin veya ZIP olarak açın.
2. `TRTrainingCalendarTest.mpr` dosyasını Mendix Studio Pro 10.24.24 ile açın.
3. Studio Pro isterse **Synchronize App Directory** çalıştırın.
4. Uygulamayı **Run Locally** ile başlatın.

`deployment`, `.mendix-cache`, kullanıcıya özel proje ayarları ve kilit dosyaları bilerek repoya dahil edilmez; Studio Pro bunları yerel bilgisayarda yeniden üretir.

## Widget'ı başka projede kullanma

Hazır MPK dosyası:

`widgets/tr.TRTrainingCalendar.mpk`

Bu dosyayı hedef Mendix uygulamasının `widgets` klasörüne kopyalayın ve **Synchronize App Directory** çalıştırın. Toolbox'ta widget **Training Resource Calendar** adıyla görünür. Widget kimliği ve paket adı geriye dönük uyumluluk için korunmuştur.

Demo uygulamasındaki sayfa, domain model, microflow ve örnek yapılandırmalar referans alınabilir. Kendi uygulamanıza aktarırken entity ve association adlarını kendi veri modelinize göre uyarlayın.

## Yerleşik özellikler

### Takvim ve dönem yönetimi

- Sınıfları satırlarda, tarihleri sütunlarda gösteren kaynak planlama matrisi
- Haftalık ve aylık görünüm arasında çalışma sırasında geçiş
- Haftalık görünümde tam Türkçe gün adları, dar alanlarda Türkçe kısaltmalar
- Aylık görünümde Türkçe gün kısaltması ve gün numarası
- Önceki/sonraki hafta veya aya geçiş için dönem navigasyonu
- Görünüme göre **Bu Hafta** veya **Bu Ay** olarak değişen bugüne dönüş kontrolü
- Bugünün tüm tarih sütunu boyunca isteğe bağlı ve kart renklerini bozmayan vurgu
- Tarihlerin saat dilimi kayması yaşamaması için date-only normalizasyonu

### Bölge, sınıf ve veri eşleştirme

- Mendix datasource üzerinden dinamik bölge ve sınıf listeleri
- Seçili bölgeye bağlı sınıf filtreleme
- Bölge kartlarında sınıf sayısı ve görünür dönemdeki eğitim sayısı
- Aktif/pasif bölge ve sınıf kayıtlarını filtreleme
- Sabit Region Key ve Classroom Key değerleri üzerinden güvenli eşleştirme
- Sınıf kapasitesini kaynak satırında gösterebilme
- Datasource loading, unavailable ve boş veri durumları için kontrollü durum ekranları
- Eksik veya geçersiz opsiyonel verilerde widget'ın çökmesini önleyen güvenli varsayılanlar

### Eğitim kartları

- Eğitim adı ve eğitmen adını birlikte gösteren dengeli kart yapısı
- Haftalık görünümde okunabilir tam adlar; aylık görünümde eğitim kısaltması ve eğitmen baş harfleri
- Mendix kaydından gelen CSS rengi, statik renk veya widget varsayılan rengini kullanabilme
- Kart rengine göre otomatik okunabilir yazı rengi seçimi
- Katılımcı sayısı ve kapasite bilgisi
- Durum, sınıf, bölge ve ek dosya göstergelerini ayrı ayrı açma/kapatma
- Kapasite aşımı, aynı sınıf/tarih tekrarı ve eğitmen çakışması için görsel uyarılar
- Aynı hücrede birden fazla eğitim olduğunda veri kaybı yaratmadan kontrollü gösterim

### Arama ve hızlı erişim

- Eğitim adı ve eğitmen adına göre isteğe bağlı arama alanı
- Türkçe `I/İ/ı/i` karakterlerine duyarlı olmayan case-insensitive arama
- Arama sonucundan ilgili bölge, dönem, sınıf ve tarih hücresine otomatik gitme
- Yapılandırılabilir arama placeholder metni

### Tatiller ve gün uygunluğu

- MPK içine gömülü **2025–2050 Türkiye resmî ve dinî tatil takvimi**
- Yerleşik resmî ve dinî tatilleri birbirinden bağımsız açma/kapatma
- İki tatil kategorisi için ayrı renk ayarı
- Bayram arifeleri ve yarım gün bilgisini destekleme
- Tatil gününü bütün sınıf satırlarında renklendirme ve yeni eğitim oluşturmayı engelleme
- Palmiye/güneş temalı çizgisel tatil ikonu
- Tatilin adını ve yarım gün durumunu gösteren widget'a ait özel tooltip
- Kuruma özel tatiller için ayrıca Mendix Holiday datasource desteği
- Tarih bazlı açık/kapalı günleri yönetmek için Day Settings datasource desteği
- Kapalı gün nedeni ve yapılandırılabilir kapalı gün etiketi
- Geçmiş günlerde **Allow**, **Read only** veya **Disabled** davranışı

### Mendix aksiyonları

- Mevcut bir eğitim kartı için datasource item context'iyle çalışan **Entry Click**
- TrainingEntry bulunmayan boş hücreler için primitive değerler gönderen **Empty Cell Click**:
  - `SelectedDate`
  - `SelectedRegionKey`
  - `SelectedClassroomKey`
- Gün uygunluğu değişiklikleri için **Availability Change**:
  - `SelectedDate`
  - `IsBookable`
- Microflow/Nanoflow aksiyonlarının çalışabilirlik ve executing durumlarına güvenli uyum

### Tooltip, dokunmatik kullanım ve erişilebilirlik

- Eğitim kartlarında içeriği ayrı ayrı yapılandırılabilen detay tooltip'i
- Eğitmen, bölge, sınıf, kapasite, durum, ek dosya ve açıklama alanlarını açma/kapatma
- Yapılandırılabilir tooltip açılma gecikmesi
- Dokunmatik cihazlarda tooltip yerine kullanılabilen touch popover davranışı
- Tam tarih ve bağlam içeren ARIA etiketleri
- Ok tuşlarıyla Sınıf × Tarih matrisi içerisinde klavye navigasyonu
- Focus göstergeleri, Escape ile kapatma ve ekran okuyucuya uygun durum metinleri

### Responsive tasarım ve Studio Pro ayarları

- Geniş, compact ve micro yoğunluk seviyelerine otomatik uyarlanan container-responsive tasarım
- Çok sayıda bölge olduğunda alt satıra geçebilen büyük ve bilgilendirici bölge seçim kartları
- Dar ekranlarda okunabilirliği koruyan yazı, boşluk ve kart yoğunluğu ayarları
- Yatay taşmayı azaltan ve dikey büyümeye izin veren kaynak matrisi
- Studio Pro'da Data, Regions & Classrooms, Holidays, Calendar, Card, Tooltip, Search, Actions ve Behavior şeklinde mantıksal ayar grupları
- Özellik durumuna göre gereksiz alanları gizleyen conditional visibility
- Zorunlu/opsiyonel alanları ve key eşleştirme sözleşmelerini açıklayan yerleşik yardım metinleri
- Mendix 10.24.x uyumluluğu için mevcut property ID, widget ID ve MPK paket adının korunması

## Notlar

- Yerleşik uzak gelecek dinî tatil tarihleri takvim projeksiyonudur; resmî takvim veya mevzuat değişikliklerinde yeniden kontrol edilmelidir.
- Bu repo çalışan demo uygulamasını ve derlenmiş MPK'yı içerir. Widget geliştirme kaynak kodu demo uygulamasının içine kopyalanmamıştır.
