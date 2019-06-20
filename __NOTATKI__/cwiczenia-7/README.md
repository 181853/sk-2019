NAT - Network address translation
----------------------------------

  * https://linux.die.net/man/8/iptables

Zadanie
------------

![zadanie 7](nat-1.svg)

1.
   * Przygotuj konfigurację sieci zgodnie z powyższym diagramem
   * Zweryfikuj poprawność połączenia z siecią internet dla ``PC0``
      * adresacja
   * W pierwszej kolejności przygotuj ``PC0``, ``PC-1``
   * Uruchom usługe ``ip_forward`` dla ``PC0``
   * Do konfiguracji wykorzystaj właściwą konfigurację ``VirtualBox`` która pozwoli na dostęp do internetu dla ``PC-1`` za pomocą interfejsu ``eth0``
   * Wykonaj konfigurację translacji adresów tak aby udostępnic komunikację z siecią internet dla ``PC-2``
   * Przygotuj dokumentację powyższego procesu
   *  **czy istnieje różnica keżeli adres eth0 statyczny/dynamiczny? Jeżeli to jaka?**


![zadanie 7](nat-2.svg)

2. 
    * Przygotuj konfigurację sieci zgodnie z powyższym diagramem
    * Wykonaj konfigurację translacji adresów tak aby udostępnic komunikację z siecią internet dla ``PC-2`` oraz ``PC-3``
    
3. 
    * Rozszerz architekturę o automatyczną konfigurację hostów w podsieciach ``192.168.64.192/27`` oraz ``172.16.95.216/29`` z wyykorzystaniem usługi ``DHCP``
    * Rozpocznij od zapoznania się z dokumentacją oraz instalacji programu ``isc-dhcp-server`` dla ``PC1``

 
 PC1
 
 ![1](1.png)
 
 PC2
 
 ![2](2.png)

 ip_forward: \
 dla sesji: `echo 1 > /proc/sys/net/ipv4/ip_forward` \
 na stałe: 
 
 ![3](3.png)
 
 iptables \
 -o output \
 -j jump 

 ![4](4.png)

 isc-dhcp-server
 `apt-get install isc-dhcp-server` 

 ![5](5.png)

 ![6](6.png)

 `journalctl -u isc-dhcp-server`

 ![7](7.png)

 ![8](8.png)
 
 dnsmasq
 `apt-get install dnsmasq`
 `apt-get update`
 
 ![9](9.png)

 ![10](10.png)

 ![11](11.png)

Zadanie do domu
---------------

1. Wykorzystując program ``dia`` oraz ikony CISCO
  * Przygotuj diagram powyższej sieci uwzględniając urządzenia tj:
    * ROUTER
    * SWITCH
    * PC
  
