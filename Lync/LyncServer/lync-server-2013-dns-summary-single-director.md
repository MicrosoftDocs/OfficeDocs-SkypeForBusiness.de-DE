---
title: 'Lync Server 2013: DNS-Zusammenfassung für einen einzelnen Director'
TOCTitle: DNS-Zusammenfassung für einen einzelnen Director
ms:assetid: 790ecb56-92cd-41f4-baf6-c290a707aa4d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205021(v=OCS.15)
ms:contentKeyID: 49294477
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für einen einzelnen Director in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der folgenden Tabelle wird eine Übersicht über die DNS-Einträge gezeigt, die erforderlich sind, um einen einzelnen Director zu unterstützen. Für die Rolle des Directors sind ähnliche DNS-Einträge wie für den Front-End-Server erforderlich. Die Anzahl der benötigten Einträge wird in der Liste der alternativen Antragstellernamen angegeben, die für das Director-Zertifikat erforderlich ist. Im Gegensatz zum Front-End-Server werden auf dem Director keine Bentzerkonten bzw. keine Mobilitätsdienste gehostet.

### Für den Director benötigte DNS-Einträge

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ort/TYP/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>dir01.contoso.net</p></td>
<td><p>Director</p></td>
<td><p>Für die Replikation und zwischen Servern verwendeter Director-Hosteintrag</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Eingehender SIP-Datenverkehr (Session Initiation Protocol) von der internen Edgeschnittstelle des Edgeservers</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlichte Dialin-Webdienste vom Reverseproxyserver</p></td>
</tr>
<tr class="even">
<td><p>Internes DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlichte Meet-Webdienste vom Reverseproxyserver</p></td>
</tr>
<tr class="odd">
<td><p>Internes DNS/A</p></td>
<td><p>webdirexternal.contoso.com</p></td>
<td><p>Director</p></td>
<td><p>Veröffentlicht und definiert durch die externen Reverseproxyserver-Webticket-Webdienste für den Director</p></td>
</tr>
</tbody>
</table>

