# JET-CUBE Turbofan MVP — Proje Talimatları (AGENTS)

## Proje Amacı (MVP)
Bu proje, turbofan motorları için
RUL + Anomaly çıktılarından
bakım kararına giden
decision-support (orchestration) katmanını
çalışır bir prototip olarak göstermeyi amaçlar.

Model geliştirmek ana hedef değildir;
amaç, model çıktılarının
bakım kararına nasıl dönüştüğünü göstermektir.

---

## Kullanılan Girdiler
Projede şu çıktılar referans alınır:

- fd001_processed.csv  
  (sensör + cycle verisi)

- fd001_rul_predictions.csv  
  (RUL tahminleri)

- fd001_anomaly_scores.csv  
  (anomaly skorları)

Bu dosyalar decision-support katmanının
tek zorunlu girdileridir.

---

## Decision-Support Mantığı
Bakım kararları, literatürde kullanılan
eşik tabanlı (alpha–theta) yaklaşımla verilir.

- RUL için eşik (θ_RUL)
- Anomaly için eşik (α_anomaly)

Karar, RUL ve anomaly skorlarının
birlikte yorumlanmasıyla üretilir.

Karar çıktıları:
- Risk seviyesi (low / medium / high)
- Önerilen aksiyon (monitor / plan / immediate maintenance)
- Gerekçe (hangi sinyaller tetikledi)

---

## Çalışma Kuralları
- Notebook sırası korunur:
  00_setup  
  01_eda  
  02_preprocess  
  03_rul  
  04_anomaly  
  05_decision_support

- Büyük veri dosyaları repoya commit edilmez.
  (Drive veya harici link kullanılır)

- Varsayımlar açıkça yazılır.
  (assumption ≠ gerçek)

---

## Agent / Codex Kullanımı
- Kod veya doküman üretirken
  bu dosyadaki kurallar referans alınır.
- Yeni bir yaklaşım öneriliyorsa:
  MVP seviyesi + gerekçesi belirtilir.