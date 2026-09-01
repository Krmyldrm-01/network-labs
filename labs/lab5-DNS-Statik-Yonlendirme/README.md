# Lab 5: DNS Yapılandırması, Paket Analizi ve Statik Yönlendirme

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup VLSM ile ağların bölümlendirilmesi, Router LAN/WAN yapılandırmaları, DNS mantığı, farklı protokollerin paket analizi ve Static Routing işlemlerini kapsamaktadır. :contentReference[oaicite:0]{index=0}

## Senaryo

- **Bölüm 1:** `192.168.1.0/24` ağının farklı host ihtiyaçlarına göre `/25`, `/26` ve `/27` alt ağlarına bölünmesi. :contentReference[oaicite:1]{index=1}
- **Bölüm 2:** R1 ve R2 Router'larının LAN/WAN arayüzlerinin yapılandırılması ve Router'lar arası bağlantının kurulması. :contentReference[oaicite:2]{index=2}
- **Bölüm 3:** Default Route kullanılarak iç ağ ile sunucu ağı arasında iletişim sağlanması. :contentReference[oaicite:3]{index=3}
- **Bölüm 4:** DNS yapılandırması ile IP adresleri ve alan adları arasında eşleştirme yapılması. :contentReference[oaicite:4]{index=4}
- **Bölüm 5:** ICMP, TCP ve UDP protokollerinin paket içerisindeki kullanımının incelenmesi. :contentReference[oaicite:5]{index=5}
- **Bölüm 6:** Dört Router'dan oluşan topolojide Routing Table ve alternatif yolların incelenmesi. :contentReference[oaicite:6]{index=6}
- **Bölüm 7:** Static Routing kullanılarak farklı ağlar arasında iletişimin sağlanması ve paketlerin neden `Drop` edildiğinin analiz edilmesi. :contentReference[oaicite:7]{index=7}

## Teknik Detaylar

- **VLSM:** Host ihtiyaçlarına göre `/25`, `/26` ve `/27` maskeleri kullanılarak IP adresleri verimli şekilde bölümlendirildi. :contentReference[oaicite:8]{index=8}
- **DNS:** IP adreslerinin isimlerle eşleştirilmesi ve bu isimler üzerinden sunuculara erişim mantığı incelendi. :contentReference[oaicite:9]{index=9}
- **Paket Analizi:** ICMP, HTTP/TCP ve DNS/UDP trafiğinin paket yapılarındaki farklılıklar gözlemlendi. :contentReference[oaicite:10]{index=10}
- **Routing Table:** Router'ların yalnızca doğrudan bağlı ağları başlangıçta bildiği ve bilinmeyen hedeflerde paketi `Drop` ettiği gösterildi. :contentReference[oaicite:11]{index=11}
- **Static Routing:** `ip route` komutu kullanılarak uzak ağların Router'lara manuel olarak tanıtılması sağlandı. :contentReference[oaicite:12]{index=12}

## Dosyalar

- **`Packet_tr5.pdf`**: Laboratuvar çalışmasının teorik ve uygulamalı dokümanı.
- **`Packet_tr5.pkt`**: Cisco Packet Tracer topoloji ve simülasyon dosyası.
