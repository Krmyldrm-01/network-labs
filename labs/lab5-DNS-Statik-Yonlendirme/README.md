# Lab 5: DNS Yapılandırması, Paket Analizi ve Statik Yönlendirme

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup VLSM ile ağların bölümlendirilmesi, Router LAN/WAN yapılandırmaları, DNS mantığı, farklı protokollerin paket analizi ve Static Routing işlemlerini kapsamaktadır.

## Senaryo



- **Bölüm 1:** `192.168.1.0/24` ağının farklı host ihtiyaçlarına göre `/25`, `/26` ve `/27` alt ağlarına bölünmesi.
- **Bölüm 2:** R1 ve R2 Router'larının LAN/WAN arayüzlerinin yapılandırılması ve Router'lar arası bağlantının kurulması.
- **Bölüm 3:** Default Route kullanılarak iç ağ ile sunucu ağı arasında iletişim sağlanması.
- **Bölüm 4:** DNS yapılandırması ile IP adresleri ve alan adları arasında eşleştirme yapılması.
- **Bölüm 5:** ICMP, TCP ve UDP protokollerinin paket içerisindeki kullanımının incelenmesi.
- **Bölüm 6:** Dört Router'dan oluşan topolojide Routing Table ve alternatif yolların incelenmesi.
- **Bölüm 7:** Static Routing kullanılarak farklı ağlar arasında iletişimin sağlanması ve paketlerin neden `Drop` edildiğinin analiz edilmesi.

## Teknik Detaylar



- **VLSM:** Host ihtiyaçlarına göre `/25`, `/26` ve `/27` maskeleri kullanılarak IP adresleri verimli şekilde bölümlendirildi.
- **DNS:** IP adreslerinin isimlerle eşleştirilmesi ve bu isimler üzerinden sunuculara erişim mantığı incelendi.
- **Paket Analizi:** ICMP, HTTP/TCP ve DNS/UDP trafiğinin paket yapılarındaki farklılıklar gözlemlendi.
- **Routing Table:** Router'ların yalnızca doğrudan bağlı ağları başlangıçta bildiği ve bilinmeyen hedeflerde paketi `Drop` ettiği gösterildi.
- **Static Routing:** `ip route` komutu kullanılarak uzak ağların Router'lara manuel olarak tanıtılması sağlandı.

## Dosyalar



- **`Packet_tr5.pdf`**: Laboratuvar çalışmasının teorik ve uygulamalı dokümanı.
- **`Packet_tr5.pkt`**: Cisco Packet Tracer topoloji ve simülasyon dosyası.
