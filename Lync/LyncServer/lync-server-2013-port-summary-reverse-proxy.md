---
title: 'Lync Server 2013: Portzusammenfassung für Reverseproxy'
TOCTitle: Portzusammenfassung für Reverseproxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204932(v=OCS.15)
ms:contentKeyID: 49294095
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portzusammenfassung für Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Firewall- und die Port- bzw. Protokollanforderungen des Reverseproxys sind minimal.

  - Die Anforderungen an die externe Firewall ist HTTPS/TCP/443 und optional HTTP/TCP/80. HTTPS wird für sichere SSL- und TLS-Kommunikationen über den Reverseproxy verwendet. HTTP wird verwendet, wenn Sie sich dafür entscheiden, den Zugriff auf den AutoErmittlungsdienst zuzulassen, wenn sich das Ändern von Zertifikaten als schwierig erweist oder die Kosten nicht gerechtfertigt werden können.

  - Clients erwarten den Kontakt mit dem Office Web Apps-Server auf HTTPS. Der Office Web Apps-Server erwartet die Kommunikation von internen Clients auf HTTPS/TCP/443. Die empfohlene Konfiguration sieht vor, HTTPS/TCP/443 vom Reverseproxy zum Office Web Apps-Server zuzulassen.

  - Der Port 8080 wird zum Routen von Datenverkehr von der internen Reverseproxyschnittstelle zum Front-End-Server, zur virtuellen IP-Adresse (VIP) des Front-End-Pool oder zur optionalen VIP des Directors bzw. des Directorpools verwendet. Der TCP-Port 8080 ist erforderlich für mobile Geräte, auf denen Lync ausgeführt wird, um den AutoErmittlungsdienst ermitteln können, wenn das Ändern des Zertifikats für die Veröffentlichungsregel externer Webdienste nicht erwünscht ist (da beispielsweise eine große Anzahl von SIP-Domänen vorhanden ist). Wenn Sie neue Zertifikate mit den erforderlichen SAN-Einträgen abrufen, ist der TCP-Port 8080 optional.

  - Der Port 4443 wird für Datenverkehr von der internen Reverseproxyschnittstelle zum Front-End-Server, zur VIP des Front-End-Pool oder zur optionalen VIP des Director bzw. des Directorpool verwendet.
    
    ![Reverseproxy und externe Webdienste](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "Reverseproxy und externe Webdienste")  
    
    > [!CAUTION]  
	> Verwechseln Sie den TCP-Port 4443 des Reverseproxys nicht mit der internen Bereitstellung für den Datenverkehr über den TCP-Port 4443 vom Standard Edition-Server oder Front-End-Pool, mit dem die zentralen Verwaltungsspeicher-Rolle verwaltet wird.


## Port- und Protokolldetails

### Firewalldetails für Reverseproxyserver: externe Schnittstelle

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverseproxylistener</p></td>
<td><p>(Optional) Umleitung an HTTPS, wenn Benutzer &quot;http:// <em>&lt;FQDN_des_veröffentlichten_Standorts&gt;</em> eingeben.</p>
<p>Diese Angabe ist ferner erforderlich, wenn Office Web Apps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte verwendet wird, auf denen Lync ausgeführt wird, und die Organisation das Zertifikat für die Veröffentlichungsregel externer Webdienste nicht verändern möchte.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverseproxylistener</p></td>
<td><p>Adressbuchdownloads, Adressbuch-Webabfragedienst, AutoErmittlung, Clientupdates, Konferenzinhalte, Geräteaktualisierungen, Gruppenerweiterung, Office Web Apps für Konferenzen, Einwahlkonferenzen und Konferenzen.</p></td>
</tr>
</tbody>
</table>


### Firewalldetails für Reverseproxyserver: interne Schnittstelle

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/TCP oder UDP/Port</th>
<th>Quell-IP-Adresse</th>
<th>Ziel-IP-Adresse</th>
<th>Hinweise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Directorpool</p></td>
<td><p>Diese Angabe ist erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte verwendet wird, auf denen Lync ausgeführt wird, und die Organisation das Zertifikat für die Veröffentlichungsregel externer Webdienste nicht verändern möchte.</p>
<p>Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Directorpool</p></td>
<td><p>Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
<tr class="odd">
<td><p>HTTPS/TCP/443</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Office Web Apps für Konferenzen</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>

