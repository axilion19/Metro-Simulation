# Metro Simülasyonu (Rota Optimizasyonu)

Bu projede bir metro ağındaki iki istasyon arasındaki en hızlı ve en az aktarmalı rotaları bulan bir simülasyon geliştirilmiştir.

Yaygın bir gerçek dünya problemine BFS ve A\* algoritmalarıyla çözüm üretilmek amaçlandı.

## Kullanılan Teknolojiler ve Kütüphaneler

- collections: BFS algoritmasında kuyruk yapısı (deque) oluşturmak için kullanıldı

- heapq: A\* algoritmasında en kısa süreye sahip rotayı bulmak için öncelik kuyruğu yapısı kullanıldı

- typing: Veri tiplerini belirtmek için kullanıldı

## BFS ve A\* Algoritmalarının Çalışma Mantığı

### BFS Algoritması

- **Amaç:** En az aktarmalı rotayı bulmak.
- **Nasıl Çalışır:**

  - Bir kuyruk yapısı (deque) oluşturulur.

  - Ziyaret edilen istasyonlar kaydedilir.

  - Her adımda komşu istasyonlar kontrol edilerek rota genişletilir.

  - Hedef istasyon bulunduğunda rota döndürülür.

### A\* Algoritması

- **Amaç:** En hızlı rotayı bulmak.
- **Nasıl Çalışır:**

  - Bir öncelik kuyruğu (priority queue) oluşturulur.

  - Ziyaret edilen istasyonlar takip edilir.

  - Her adımda en kısa süreye sahip rota seçilir.

  - En hızlı rota bulunduğunda süre ve rota bilgisi döndürülür.

### Neden Bu Algoritmalar Kullanıldı?

- **BFS:** En az aktarma gerektiren rotayı bulmak için idealdir, çünkü arama yapısı en kısa yolu garantiler.

- **A\*:** En hızlı rota bulma konusunda etkili ve verimli bir yaklaşımdır. Öncelik kuyruğu sayesinde optimal rota en düşük maliyetle bulunur.

## Örnek Kullanım ve Test Sonuçları

### Örnek Kullanım

python HakanCobanoglu_MetroSimulation.py ile main dosyasını çalıştırın.

### Test Sonuçları

1. **AŞTİ'den OSB'ye:**
   En az aktarmalı rota: AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB
   En hızlı rota (25 dakika): AŞTİ -> Kızılay -> Kızılay -> Ulus -> Demetevler -> OSB

2. **Batıkent'ten Keçiören'e:**
   En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
   En hızlı rota (21 dakika): Batıkent -> Demetevler -> Gar -> Keçiören

3. **Keçiören'den AŞTİ'ye:**
   En az aktarmalı rota: Keçiören -> Gar -> Gar -> Sıhhiye -> Kızılay -> AŞTİ
   En hızlı rota (19 dakika): Keçiören -> Gar -> Gar -> Sıhhiye -> Kızılay -> AŞTİ

## Projeyi Geliştirme Fikirleri

- Kullanıcı dostu bir arayüz geliştirilebilir.
- Dijkstra gibi daha verimli bir algoritma tercih edilebilir.
- A\* algoritmasının heuristic fonksiyonu optimize edilerek istasyon sayısının fazla olduğu durumlarda daha verimli çalışması sağlanabilir.
