flowchart LR
    %% Ana sorular ve değişkenler
    Cevap1["Soru1: Şu anki araç sigortası ihtiyacınızı aşağıdaki durumlardan hangileri daha iyi tanımlıyor?
    - Sadece trafik sigortası yaptıracağım
    - Şu an kaskom/trafik sigortam yok
    - İlk aracımı aldım
    - Evdeki ikinci araç için sigorta
    - Kaskom ve trafik sigortam var
    - Sıfır aracım için sigorta
    - Yeni aldığım ikinci el aracım"] --> |Sadece trafik sigortası| OneriBaslangicKasko("ÖNERİ: Başlangıç Kasko")
    Cevap1 --> |Diğer ihtiyaçlar| Cevap2["Soru2: Aracınıza araç sigortası yaptırırken sizin için en önemli faktör nedir?
    - En kapsamlı teminat ve limitlere sahip bir poliçe
    - Poliçedeki teminatlar yeterli olsun ama fiyatı çok yüksek olmasın
    - Dar kapsamlı ama en uygun fiyatlı poliçe"]
    
    %% Tercih faktörüne göre dallanma
    Cevap2 --> |En kapsamlı teminat| Cevap3_Kapsam["Soru3: Aracınızı hangi sıklıkla kullanıyorsunuz?
    - Aracımı her gün kullanıyorum
    - Aracımı haftada birkaç kez ihtiyacıma göre kullanıyorum
    - Aracımı nadiren kullanıyorum, genelde park halinde oluyor"]
    Cevap2 --> |Teminatlar yeterli| Cevap3_Yeterli["Soru3: Aracınızı hangi sıklıkla kullanıyorsunuz?
    - Aracımı her gün kullanıyorum
    - Aracımı haftada birkaç kez ihtiyacıma göre kullanıyorum
    - Aracımı nadiren kullanıyorum, genelde park halinde oluyor"]
    Cevap2 --> |Dar kapsamlı| Cevap3_Dar["Soru3: Aracınızı hangi sıklıkla kullanıyorsunuz?
    - Aracımı her gün kullanıyorum
    - Aracımı haftada birkaç kez ihtiyacıma göre kullanıyorum
    - Aracımı nadiren kullanıyorum, genelde park halinde oluyor"]
    
    %% Kullanım sıklığına göre dallanma
    Cevap3_Kapsam --> |Her gün| Cevap4_K_HG["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    Cevap3_Kapsam --> |Haftada birkaç| Cevap4_K_HB["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    Cevap3_Kapsam --> |Nadiren| Cevap4_K_ND["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    
    Cevap3_Yeterli --> |Her gün| Cevap4_Y_HG["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    Cevap3_Yeterli --> |Haftada birkaç| Cevap4_Y_HB["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    Cevap3_Yeterli --> |Nadiren| Cevap4_Y_ND["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    
    Cevap3_Dar --> |Her gün| Cevap4_D_HG["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    Cevap3_Dar --> |Haftada birkaç| Cevap4_D_HB["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    Cevap3_Dar --> |Nadiren| Cevap4_D_ND["Soru4: 0-6 yaş arası çocuğunuz var mı?
    - Evet
    - Hayır"]
    
    %% Çocuk durumuna göre öneriler - Kapsamlı + Her Gün
    Cevap4_K_HG --> |Evet| OneriBoBKasko["ÖNERİ: BoB Kasko
    En kapsamlı teminat içeren özel sigortamız"]
    Cevap4_K_HG --> |Hayır| OneriRayKasko["ÖNERİ: Ray Kasko
    Kapsamlı teminat sunan sigortamız"]
    
    %% Çocuk durumuna göre öneriler - Kapsamlı + Haftalık
    Cevap4_K_HB --> |Evet| OneriBoBKasko
    Cevap4_K_HB --> |Hayır| OneriRayTekKasko["ÖNERİ: Ray Kasko/Tek Kasko
    Haftalık kullanım için uygun kapsamlı sigortalar"]
    
    %% Çocuk durumuna göre öneriler - Kapsamlı + Nadiren
    Cevap4_K_ND --> |Evet| OneriBoBKasko
    Cevap4_K_ND --> |Hayır| OneriKaskHOMTekBaslangicKasko["ÖNERİ: KaskHOM/Tek Kasko/Başlangıç Kasko
    Nadiren kullanım için ideal sigortalar"]
    
    %% Çocuk durumuna göre öneriler - Yeterli + Her Gün
    Cevap4_Y_HG --> |Evet| OneriBoBKasko
    Cevap4_Y_HG --> |Hayır| OneriRayKaskHOMTekKasko["ÖNERİ: Ray Kasko/KaskHOM/Tek Kasko
    Dengeli teminat ve fiyat sunan sigortalar"]
    
    %% Çocuk durumuna göre öneriler - Yeterli + Haftalık
    Cevap4_Y_HB --> |Evet| OneriBoBKasko
    Cevap4_Y_HB --> |Hayır| OneriRayKaskHOMTekKasko
    
    %% Çocuk durumuna göre öneriler - Yeterli + Nadiren
    Cevap4_Y_ND --> |Evet| OneriBoBKasko
    Cevap4_Y_ND --> |Hayır| OneriKaskHOMTekBaslangicKasko
    
    %% Çocuk durumuna göre öneriler - Dar + Her Gün
    Cevap4_D_HG --> |Evet| OneriBoBKasko
    Cevap4_D_HG --> |Hayır| OneriRayKaskHOMTekKasko
    
    %% Çocuk durumuna göre öneriler - Dar + Haftalık
    Cevap4_D_HB --> |Evet| OneriBoBKasko
    Cevap4_D_HB --> |Hayır| OneriRayKaskHOMTekKasko
    
    %% Çocuk durumuna göre öneriler - Dar + Nadiren
    Cevap4_D_ND --> |Evet| OneriBoBKasko
    Cevap4_D_ND --> |Hayır| OneriKaskHOMTekBaslangicKasko
    
    OneriBaslangicKasko["ÖNERİ: Başlangıç Kasko
    Ekonomik ve temel teminatlar içeren sigortamız"]
        
    %% Stil tanımlamaları
    classDef question fill:#f0f8ff,stroke:#333,stroke-width:1px,font-size:12px
    classDef answer fill:#e6f7ff,stroke:#333,stroke-width:1px
    classDef recommendation fill:#e6ffe6,stroke:#333,stroke-width:2px,stroke-dasharray: 5 5
    
    class Cevap1,Cevap2,Cevap3_Kapsam,Cevap3_Yeterli,Cevap3_Dar,Cevap4_K_HG,Cevap4_K_HB,Cevap
