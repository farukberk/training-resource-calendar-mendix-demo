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

- Haftalık ve aylık sınıf/kaynak matrisi
- Bölge ve sınıf filtreleme
- Eğitim ve eğitmen gösterimi
- Entry Click, Empty Cell Click ve Availability Change aksiyonları
- 2025–2050 Türkiye resmî ve dinî tatil takvimi
- Ayrı tatil renkleri ve açma/kapatma seçenekleri
- Responsive görünüm, klavye erişimi, tooltip ve touch popover

## Notlar

- Yerleşik uzak gelecek dinî tatil tarihleri takvim projeksiyonudur; resmî takvim veya mevzuat değişikliklerinde yeniden kontrol edilmelidir.
- Bu repo çalışan demo uygulamasını ve derlenmiş MPK'yı içerir. Widget geliştirme kaynak kodu demo uygulamasının içine kopyalanmamıştır.
