Elbette reisim, doğrudan kopyalayıp GitHub reposundaki `README.md` dosyana yapıştırabileceğin, kod blokları ve vurguları ayarlanmış Markdown formatı aşağıdadır. Sağ üstteki "Copy code" (Kodu kopyala) butonuna basarak direkt alabilirsin:

```markdown
# Lab 3: IPv6 Adresleme, Yönlendirme ve Gelişmiş Subnetting (VLSM)

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup, IPv4 ve IPv6 adresleme mantığını, ağları daha verimli kullanmak için alt ağlara bölme (Subnetting) işlemlerini ve temel yönlendirme (Routing) yapılandırmalarını kapsamaktadır.

## Senaryo

* **Bölüm 1:** 32-bitlik IPv4 yapısından farklı olarak, arayüzlere 128-bitlik onaltılık (hexadecimal) bloklardan oluşan IPv6 adreslerinin atanması ve router üzerinde IPv6 yönlendirmesinin (`ipv6 unicast-routing`) aktif hale getirilmesi.
* **Bölüm 2:** `2000:db80:fb:1907::/64` ve `2000:db80:fb:1906::/64` şeklinde iki farklı IPv6 ağının yapılandırılması, uç cihazlara adres ve Default Gateway tanımlanarak ping testi ile ağlar arası haberleşmenin doğrulanması.
* **Bölüm 3:** `192.168.1.0/24` ağının `/25`, `/26` ve `/27` gibi farklı alt ağ maskeleriyle (Subnetting) daha küçük bloklara bölünmesi ve Router bacaklarına çakışma olmadan atanması.

## Teknik Detaylar

* **Adresleme Kapasitesi:** Dünya genelindeki cihaz artışı sebebiyle, IPv4'ün tam 4 katı uzunluğunda olan ve mevcut alandan 2<sup>96</sup> kat daha büyük bir kapasite sunan IPv6 mimarisinin avantajları analiz edildi.
* **Otomatik Adres Üretimi (EUI-64):** Bir arayüze IPv6 atandığında, cihazın MAC adresini kullanarak ortasına `FF:FE` eklemesi ve 7. biti tersine çevirmesiyle sadece o ağda geçerli `FE80::` başlangıçlı Link-Local adresini otomatik ürettiği incelendi.
* **Cihaz Davranışları (Layer 2 vs Layer 3):** Switch cihazlarının bilinmeyen hedef MAC adresleri için paketi geldiği port hariç her yere yolladığı (Flooding), Router'ların ise hedef IP adresini tabloda bulamazsa paketi doğrudan çöpe attığı (Drop) gözlemlendi.
* **Ağ Maskesi ve Mantıksal AND İşlemi:** Cihazların, sahip oldukları IP adresi ile Subnet Mask'ı bit düzeyinde mantıksal AND (VE) işlemine sokarak bulundukları ağı (Network ID) matematiksel olarak nasıl tespit ettikleri test edildi.
* **IP Verimliliği (VLSM):** Bir ağı sabit eşit parçalara bölmek (FLSM) yerine, ihtiyaç duyulan cihaz sayısına göre farklı boyutlarda maskeler (VLSM) kullanarak IP adres israfının önüne geçildiği kanıtlandı.

## Dosyalar

* **`Packet_tr_3.pdf`**: IPv6 adresleme kuralları, EUI-64 mantığı, Subnetting matematiksel işlemleri ve VLSM uygulamalarının detaylı teorik analiz dokümanı.
* **`Packet_tr_3.pkt`**: Packet Tracer simülasyon ve uygulamalı topoloji dosyası.

```
