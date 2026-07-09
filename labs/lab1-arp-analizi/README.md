# Lab 1: ARP Analizi ve Temel Yönlendirme

Bu laboratuvar, Cisco Packet Tracer kullanılarak gerçekleştirilmiş olup, ağ içi haberleşme protokollerini ve yönlendirme mantığını kapsamaktadır.

## Senaryo
- **Bölüm 1:** Aynı ağdaki iki cihazın (PC0 ve PC2) ARP süreci üzerinden MAC adresi öğrenme ve haberleşme analizi.
- **Bölüm 2:** Farklı networklerdeki (192.168.1.0/24 ve 192.168.2.0/24) cihazların bir Router/Gateway aracılığıyla haberleşmesi.

## Teknik Detaylar
- **Protokoller:** ARP (Address Resolution Protocol), ICMP (Ping).
- **Gözlem:** Switch'in Layer 2 yapısı gereği router'a doğrudan ping atamaması ve bunun yerine uç cihazların (PC) gateway üzerinden haberleşmesi.
- **Kritik Bulgular:** Farklı ağa giden paketlerde hedef IP'nin değişmediği, ancak hedef MAC adresinin her ağ geçişinde (Hop) gateway'in MAC'i ile güncellendiği doğrulandı.

## Dosyalar
- `Packet_Tr_1.pdf`: Çalışma notlarının detaylı dökümanı.
- `.pkt` dosyaları: Packet Tracer simülasyon dosyaları.
