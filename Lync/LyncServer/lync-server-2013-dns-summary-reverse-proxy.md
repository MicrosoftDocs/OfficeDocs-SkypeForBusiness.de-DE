---
title: 'Lync Server 2013: DNS-Zusammenfassung für Reverseproxy'
TOCTitle: DNS-Zusammenfassung für Reverseproxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204781(v=OCS.15)
ms:contentKeyID: 49293577
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung für Reverseproxy in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Sie können die zwei Netzwerkadapter auf Ihrem Reverseproxy folgendermaßen konfigurieren:

## Netzwerkadapteranforderungen für Reverseproxy

  - Beispiel **Netzwerkadapter 1 (interne Schnittstelle)**
    
    Interne Schnittstelle mit zugewiesener Adresse 172.25.33.40.
    
    Es ist kein Standardgateway definiert.
    
    Stellen Sie sicher, dass eine Route vom Netzwerk mit der internen Reverseproxyschnittstelle zu beliebigen Netzwerken vorhanden ist, die Lync Server  Front-End-Pool-Server enthalten (z. B. von 172.25.33.0 zu 192.168.10.0).

  - Beispiel **Netzwerkadapter 2 (interne Schnittstelle)**
    
    Diesem Netzwerkadapter ist mindestens eine öffentliche IP-Adresse zugewiesen.
    
    Das Gateway ist so definiert, dass es auf den Router oder die integrierte Firewall in Ihrem äußeren Umkreis zeigt (10.45.16.1 in den Szenariobeispielen).

### Für Reverseproxy erforderliche DNS-Einträge

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
<th>FQDN</th>
<th>IP-Adresse</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externe Webdienste aus der internen Bereitstellung. Zusätzliche Einträge können definiert und für alle Pools und einzelne Server für eine beliebige SIP-Domäne konfiguriert werden, die diesen Reverseproxy verwendet und für die externe Webdienste definiert sind.</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externe Webdienste für die Directors- oder Director-Pools in Ihrer Bereitstellung. Sie können so viele Directors definieren, wie separate Directors vorhanden sind, die ggf. mit anderen SIP-Domänen verknüpft sind.</p>
<div>

> [!IMPORTANT]
> Das Definieren der DNS-Einträge für und das Veröffentlichen der Directors ist keine Entscheidung für entweder den Front-End-Pool oder die Director. Sie müssen sowohl die externen Webdienste für Director als auch Front-End-Pool definieren und veröffentlichen, wenn Sie Directors verwenden. Bestimmte Datenverkehrstypen (zur Authentifizierung und zu anderen Zwecken) werden zuerst an die Director gesendet, sofern in der Topologie definiert.


</div></td>
</tr>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Extern veröffentlichte Einwahlkonferenzen</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Extern veröffentlichte Konferenzen</p></td>
</tr>
<tr class="odd">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Zugewiesener Listener für Office Web Apps-Server</p></td>
<td><p>Office Web Apps-Server intern oder im Umkreisnetzwerks bereitgestellt und für den externen Clientzugriff veröffentlicht</p></td>
</tr>
<tr class="even">
<td><p>Externer DNS-Eintrag/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Zugewiesener Listener für extern veröffentlichte Ressourcen</p></td>
<td><p>Externer Eintrag zur Lync-Ermittlung für extern veröffentliche AutoErmittlung; beinhaltet Mobilität, Microsoft Lync Web App und Web-App zur Planung</p></td>
</tr>
</tbody>
</table>

