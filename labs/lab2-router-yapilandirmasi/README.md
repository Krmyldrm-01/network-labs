# Lab 2: Router Temel Yapılandırması ve Uzaktan Erişim

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup, router donanım mimarisini, temel konfigürasyon adımlarını ve güvenli uzaktan yönetim mantığını kapsamaktadır.

## Senaryo

* **Bölüm 1:** Console kablosu ile Router CLI arayüzüne bağlanarak temel ayarların (Hostname, Banner MOTD, Console/Enable parolaları) yapılması.
* **Bölüm 2:** Router arayüzlerine (Interface) IP adreslerinin atanması, iki farklı ağın (192.168.1.0/24 ve 192.168.2.0/24) haberleştirilmesi ve uç cihazlara Default Gateway tanımlanması.
* **Bölüm 3:** Cihazların uzaktan yönetilebilmesi için Telnet ve güvenli iletişim için SSH bağlantılarının (RSA key ile asimetrik anahtarlama) yapılandırılması.

## Teknik Detaylar

* **Cihaz Modları:** User EXEC, Privileged EXEC ve Global Configuration modları hiyerarşisi kullanılarak yetkilendirme işlemleri test edildi.
* **Bellek Yönetimi (RAM & NVRAM):** Yapılan konfigürasyonların geçici bellekten (`running-config`), kalıcı belleğe (`startup-config`) aktarılarak cihazın yeniden başlatılması durumunda veri kaybının önüne geçildi.
* **Güvenlik (Şifreleme):** `service password-encryption` ile düz metin parolalar maskelendi. Telnet'in güvensiz yapısı (cleartext) analiz edilerek, yerine Public/Private Key mantığıyla çalışan şifreli SSH protokolü devreye alındı.
* **Kritik Bulgular:** Switch'lerin (Layer 2) fiziksel portlarına IP atanamayacağı; ancak uzaktan yönetilebilmesi için sanal bir arayüze (VLAN 1 SVI) IP adresi ve Default Gateway verilmesi gerektiği doğrulandı.

## Dosyalar

* `Packet_Tr_2.pdf`: Router bileşenleri, açılış süreci, CLI komutları ve topoloji adımlarının detaylı dokümanı.
* `Router_Yapılandırması.pkt`: Packet Tracer simülasyon ve uygulamalı topoloji dosyası.
