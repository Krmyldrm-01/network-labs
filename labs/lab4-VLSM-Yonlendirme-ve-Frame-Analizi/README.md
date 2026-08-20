# Lab 4: Gelişmiş Subnetting (VLSM), Yönlendirme ve Frame Kapsülleme Analizi

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup, ağların ihtiyaçlara göre esnek boyutlarda bölünmesi (VLSM), Router'lar arası seri bağlantıların (Point-to-Point) yapılandırılması, varsayılan yönlendirme (Default Route) mantığı ve Layer 2 frame tiplerinin (Ethernet, HDLC, PPP) analizini kapsamaktadır.

### Senaryo

* **Bölüm 1:** `192.168.1.0/24` ağının, 100 hostluk Muhasebe, 50 hostluk Pazarlama ve 10 hostluk Sunucu departmanlarının ihtiyaçlarına göre sırasıyla `/25`, `/26` ve `/28` alt ağ maskeleriyle (VLSM) çakışma olmadan bölünmesi.
* **Bölüm 2:** Router'lar arasına HWIC-2T modülleri takılarak seri arayüz bağlantısı çekilmesi ve bu bağlantı için IP israfını önleyen `/30` alt ağ maskesinin yapılandırılması.
* **Bölüm 3:** Simülasyon modunda ARP, ICMP süreçlerinin incelenmesi, bilinmeyen hedeflerde yaşanan paket düşmesi (Drop) sorununun tespit edilmesi ve `0.0.0.0 0.0.0.0` Default Route ile uçtan uca ağ haberleşmesinin sağlanması.

### Teknik Detaylar

* **IP Verimliliği (VLSM):** Bir ağı eşit parçalara bölmek (FLSM) yerine, ihtiyaç duyulan cihaz sayısına göre farklı boyutlarda maskeler kullanılarak IP adres israfının önüne geçildiği kanıtlanmıştır.
* **Ağ Geçidi ve ARP Çözümleme:** PC0, hedef IP'nin kendi ağında olmadığını alt ağ maskesiyle (ilk 25 bit kontrolü) tespit ettiğinde paketi ağ geçidine yollar. Ağ geçidinin MAC adresi bilinmiyorsa ARP Request (broadcast) gönderilerek öğrenilir.
* **Layer 2 vs Layer 3 Davranışı:** Paket router'dan geçerken uçtan uca kaynak ve hedef IP adresleri (Layer 3) sabit kalır. Ancak yönlendirme sırasında kaynak ve hedef MAC adresleri (Layer 2) her segmentte (hop) router tarafından yeniden yazılır.
* **Seri Bağlantı ve /30 Maskesi:** İki cihaz (R1 ve R2) arasındaki izole point-to-point ağda, sadece 2 adet kullanılabilir IP adresi veren `/30` (`255.255.255.252`) maskesi kullanılmıştır.
* **Yönlendirme (Routing) Sınırları:** Router'lar sadece doğrudan bağlı (Directly Connected) oldukları ağları bildikleri için, R1 tablosunda olmayan Sunucu ağına giden paketi doğrudan çöpe atar (drop). Bu durum statik bir Default Route atamasıyla çözülmüştür.
* **Frame Kapsülleme Farklılıkları:** Router'ın yerel ağ (LAN) bacağında Ethernet frame'leri kullanılırken, seri bacağında varsayılan olarak HDLC frame'leri kullanıldığı tespit edilmiştir. CLI üzerinden `enc ppp` komutu girilerek bu bağlantıdaki HDLC yapısının PPP frame'ine dönüştürülebildiği doğrulanmıştır.

### Dosyalar

* **Packet_Tr_4.pdf:** VLSM hesaplamaları, Router CLI yapılandırmaları, ARP/ICMP simülasyon analizleri ve kapsülleme farklılıklarını içeren laboratuvar dokümanı.
* **Alt_aglara_Bolme_ve_Frame.pkt:** Packet Tracer simülasyon ve uygulamalı topoloji dosyası.
