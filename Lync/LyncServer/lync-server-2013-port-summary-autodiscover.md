---
title: Portübersicht – AutoErmittlung in Lync Server 2013
TOCTitle: Portübersicht – AutoErmittlung in Lync Server 2013
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945642(v=OCS.15)
ms:contentKeyID: 52056385
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Portübersicht – AutoErmittlung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-04-06_

Der Lync Server 2013-AutoErmittlungsdienst wird auf Director- und Front-End-Poolservern ausgeführt. Ist der AutoErmittlungsdienst in DNS mit den Hosteinträgen `lyncdiscover.<domain>` und `lyncdiscoverinternal.<domain>` veröffentlicht ist, kann er von Clients zum Suchen von Lync Server-Features verwendet werden. Damit mobile Geräte, auf denen Lync Mobile ausgeführt wird, die AutoErmittlung nutzen können, müssen u. U. die Listen mit den alternativen Zertifikatantragstellernamen auf jedem Director und Front-End-Server geändert werden, auf dem der AutoErmittlungsdienst ausgeführt wird. Zudem kann es notwendig sein, die Liste der alternativen Antragstellernamen für Zertifikate zu ändern, die von Veröffentlichungsregeln für externe Webdienste auf Reverseproxys verwendet werden.

Die Entscheidung, ob auf Reverseproxys alternative Antragstellernamen verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst an Port 80 oder an Port 443 veröffentlichen:

  - **Veröffentlicht an Port 80**   Für mobile Geräte sind keine Zertifikatänderungen erforderlich, wenn die anfängliche Abfrage des AutoErmittlungsdiensts über den Port 80 erfolgt. Dies ist darauf zurückzuführen, dass mobile Geräte, auf denen Lync ausgeführt wird, extern auf den Reverseproxy an Port 80 zugreifen und dann intern an einen Director oder Front-End-Server an Port 8080 umgeleitet werden.

  - **Veröffentlicht an Port 443**   Die Liste der alternativen Antragstellennamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, müssen einen `lyncdiscover.<sipdomain>`-Eintrag für jede SIP-Domäne in der Organisation enthalten.
    

    > [!IMPORTANT]
    > Für neue Installationen oder Upgrades von Lync Server 2010, in denen Sie Mobilität bereitgestellt haben, haben Sie entweder Port&nbsp;80 für die automatische Ermittlung des Mobilitätsdiensts verwendet, oder Zertifikate mit dem richtigen Antragstellernamen oder alternativen Antragstellernamen neu ausgestellt. Überprüfen Sie die Zertifikate auf Ihrem Director und Front-End-Server, um den gewählten Pfad zu bestätigen.



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
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/80</p></td>
<td><p>Beliebig</p></td>
<td><p>Reverseproxylistener</p></td>
<td><p>(Optional) Umleitung an HTTPS, wenn Benutzer &quot;http://<em>&lt;FQDN_des_veröffentlichten_Standorts&gt;</em> eingeben. Diese Angabe ist ferner erforderlich, wenn Office Web Apps für Konferenzen und der AutoErmittlungsdienst für mobile Geräte verwendet wird, auf denen Lync ausgeführt wird, und die Organisation das Zertifikat für die Veröffentlichungsregel externer Webdienste nicht verändern möchte.</p></td>
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
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTTP/TCP/8080</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Directorpool und Office Web Apps für Konferenzen</p></td>
<td><p>Diese Angabe ist erforderlich, wenn der AutoErmittlungsdienst für mobile Geräte verwendet wird, auf denen Lync ausgeführt wird, und die Organisation das Zertifikat für die Veröffentlichungsregel externer Webdienste nicht verändern möchte. Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
<tr class="even">
<td><p>HTTPS/TCP/4443</p></td>
<td><p>Interne Reverseproxyschnittstelle</p></td>
<td><p>Front-End-Server, Front-End-Pool, Director, Directorpool und Office Web Apps für Konferenzen</p></td>
<td><p>Datenverkehr, der an Port 80 der externen Reverseproxyschnittstelle gesendet wird, wird an einen Pool an Port 8080 der internen Reverseproxyschnittstelle umgeleitet, sodass die Poolwebdienste diesen vom internen Webdatenverkehr unterscheiden können.</p></td>
</tr>
</tbody>
</table>

