#  AFO Veri Seti ile YOLOv9 Kullanılarak Deniz Ortamında Küçük Nesne Tespiti

##  Grup: AFODEN  
**Üyeler:**  
- İsmail Can Dağ  
- Murat Turan  
- Doğukan Olağ  
- Alperen Kaya  
- Zafer Göktaş  

##  Proje Amacı
Bu projede, deniz ortamında yürütülen arama kurtarma operasyonlarına katkı sağlamak amacıyla AFO (Aerial Floating Object) veri seti kullanılarak küçük nesnelerin tespiti hedeflenmiştir. YOLOv9 modeli ile insan, bot, sal gibi kritik nesneler yüksek doğrulukla tespit edilmiştir.

##  Kullanılan Model: YOLOv9
- Model: `yolov9-c.pt` (önceden eğitilmiş)
- Eğitim Ortamı: Google Colab
- Görüntü Boyutu: 640x640
- Epoch: 300
- Veri artırma teknikleri kullanıldı (flip, hue, mosaic vb.)

##  Veri Seti: AFO (Aerial Floating Object)
- 6 ülkede, 35 lokasyonda drone ile çekilmiş 50 video
- 3647 görüntü, 39.991 etiketli nesne
- 6 sınıf: İnsan, Bot, Tahta, Şamandıra, Yelkenli, Kayak
- Özellikle küçük nesne tespiti için optimize edilmiştir

##  Performans Sonuçları
| Metrik        | Değer    |
|---------------|----------|
| mAP@0.5       | 0.9546   |
| mAP@0.5:0.95  | 0.7097   |
| Precision     | 0.9339   |
| Recall        | 0.9214   |

###  Kategori Bazlı mAP
| Kategori   | mAP   | Precision | Recall |
|------------|-------|-----------|--------|
| İnsan      | 0.950 | 0.952     | 0.915  |
| Tahta      | 0.994 | 0.984     | 0.994  |
| Bot        | 0.969 | 0.844     | 0.962  |
| Şamandıra  | 0.866 | 0.933     | 0.670  |
| Yelkenli   | 0.995 | 0.948     | 1.000  |
| Kayak      | 0.987 | 0.937     | 0.973  |

##  Gerçek Hayat Kullanımı
Bu proje, denizcilik sektöründe İHA’lar ile entegre edilerek kaybolan bireylerin hızlı ve etkili şekilde tespiti için kullanılabilir. Özellikle arama kurtarma ekiplerinin işini kolaylaştırmak adına önemlidir.

##  Gelecek Geliştirme Önerileri
- Daha büyük ve çeşitli veri setleriyle yeniden eğitim
- Model varyantlarının test edilmesi (YOLOv9-s, YOLOv9-e vs.)
- Gerçek zamanlı sistem entegrasyonu (örneğin İHA donanımıyla)
- Termal/LiDAR gibi sensör verisi füzyonu
- Nesne takibi (Object Tracking) eklenmesi
- Kullanıcı arayüzü ile sahada kullanım kolaylığı

##  Kaggle Notebook Linki
[Kaggle'da Projeye Git](https://www.kaggle.com/code/doukanola/yolov9-afo-object-detection-project) 

##  Kaynak Kod
- YOLOv9 mimarisi: [YOLOv9 Paper](https://arxiv.org/abs/2402.13616)
- AFO Dataset: [Official Page](https://github.com/AFO-dataset)

##  Lisans
MIT License – Açık kaynak olarak sunulmuştur.
