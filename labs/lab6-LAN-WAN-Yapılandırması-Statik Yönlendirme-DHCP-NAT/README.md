
---

### Lab 6: LAN/WAN Yapılandırması, Statik Yönlendirme, DHCP ve NAT (PAT)

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup, temel LAN/WAN arayüz yapılandırmalarını, yönlendiriciler arası (Static Routing) statik rotaların belirlenmesini, cihazlara otomatik IP dağıtımı için DHCP kurulumunu ve özel IP ağlarının internete çıkabilmesi için NAT (PAT) işlemlerini kapsamaktadır[cite: 1].

#### Senaryo

*   **Bölüm 1:** Router'lar (R1, R2, R3, R4) üzerinde doğrudan bağlı olan LAN (GigabitEthernet) ağları ve yönlendiricileri birbirine bağlayan WAN (Serial) arayüzlerinin IP atamalarının yapılarak aktif (no shut) hale getirilmesi[cite: 1].
*   **Bölüm 2:** Yönlendiricilerin fiziksel olarak bağlı olmadıkları uzak ağları öğrenebilmesi için Yönlendirme Tablosuna (Routing Table) statik rotaların eklenmesi[cite: 1]. R1'den R4'e giden yolda R2 ve R3 üzerinden alternatif rotalar yazılarak Yük Dengeleme (Load Balancing) senaryolarının test edilmesi[cite: 1]. 
*   **Bölüm 3:** Yönlendiriciler (R1, R3 ve R4) üzerinde DHCP havuzları (pool) oluşturularak, ağ geçidi (Default Gateway) ve alt ağ maskesi (Subnet Mask) bilgilerinin uç cihazlara dinamik olarak dağıtılması[cite: 1].
*   **Bölüm 4:** RFC 1918 standardına sahip iç ağ cihazlarının internete çıkabilmesi için, Servis Sağlayıcıya (ISP) doğru Varsayılan Statik Rota (Default Route: 0.0.0.0/0) yazılması ve Sınır Yönlendiricisi (R2) üzerinde NAT (Overload / PAT) yapılandırmasının uygulanması[cite: 1].

#### Teknik Detaylar

*   **Statik Yönlendirme Mantığı:** Hedef ağa (örneğin 192.168.2.0/24) ulaşmak için rotayı Çıkış Arayüzü (Exit Interface) üzerinden belirtmenin Point-to-Point olmayan bağlantılarda performans düşüklüğüne yol açtığı görülmüştür[cite: 1]. Bunun yerine paketin iletileceği Sonraki Atlama (Next-Hop) IP adresinin kullanılması tercih edilmiştir[cite: 1].
*   **DHCP Keşif Süreci (DORA):** IP adresi olmayan bir uç cihazın, "Yok mu bana IP dağıtan?" mantığıyla ortama Kaynak IP: 0.0.0.0 ve Hedef IP: 255.255.255.255 olacak şekilde UDP üzerinden bir "DHCP Discover" yayın (broadcast) paketi gönderdiği incelenmiştir[cite: 1]. Sunucunun buna "DHCP Offer" ile yanıt verdiği, istemcinin "DHCP Request" ile talep ettiği ve sunucunun "DHCP Acknowledge" ile IP atamasını onayladığı arka plan işlemleri analiz edilmiştir[cite: 1].
*   **ARP ile IP Çakışması Kontrolü:** Cihazın DHCP'den yeni bir IP aldığında, bu IP adresinin ağda başka biri tarafından kullanılıp kullanılmadığını doğrulamak amacıyla kendi aldığı IP'nin MAC adresini soran bir ARP Request gönderdiği tespit edilmiştir[cite: 1].
*   **Özel (Private) IP Kısıtlaması:** 192.168.0.0/16 ve 10.0.0.0/8 gibi özel (private) IP bloklarının dünya genelinde milyonlarca kurum/ev tarafından aynı anda kullanıldığı için yönlendirilemez (non-routable) olduğu açıklanmıştır[cite: 1]. Bu adreslerin internet (ISP) ortamına çıkamayacağı belirtilmiştir[cite: 1].
*   **Ağ Adresi Çevirisi (NAT/PAT) ve Paket Analizi:** İnternete erişim problemini çözmek için R2 üzerinde `ip nat inside source list 1 interface Serial0/1/1 overload` komutu ile iç ağ IP'lerinin dış bacak IP'sine (78.1.1.1) dönüştürüldüğü kanıtlanmıştır[cite: 1]. PDU/Simülasyon analizi ile paketin R2'ye girerken Kaynak IP'sinin 192.168.1.3 olduğu, R2'den ISP'ye çıkarken ise 78.1.1.1 (Public IP) olarak değiştirildiği ve ISP'den gelen yanıtların başarıyla iç ağa geri çevrildiği doğrulanmıştır[cite: 1].

#### Dosyalar

*   `Packet_tr_6.pdf`: LAN/WAN konfigürasyonları, statik yönlendirme teorisi, DHCP arka plan paket analizleri ve NAT işlemlerinin ekran görüntüleriyle desteklendiği teorik analiz dokümanı.
*   `Packet_tr_6_1/6_2.pkt`: Cisco Packet Tracer simülasyon ve uygulamalı çalışma dosyası.
