---
title: DNS-Anforderungen für die Mobilität
TOCTitle: DNS-Anforderungen für die Mobilität
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690040(v=OCS.15)
ms:contentKeyID: 49295649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für die Mobilität

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn Sie das Lync Server 2013-Mobilitätsfeature bereitstellen, können Sie die neuen URLs, die für den Microsoft Lync Server 2013-AutoErmittlungsdienst verfügbar sind, oder Ihre vorhandenen Webdienste-URLs verwenden. Wenn Sie vorhandene URLs verwenden, müssen Benutzer in den Einstellungen des mobilen Geräts die URLs manuell eingeben. Diese Option wird normalerweise zur Problembehandlung verwendet. Wenn Sie die neuen URLs verwenden, können mobile Clients Lync Server 2013-Ressourcen automatisch ermitteln. Wenn Sie die automatische Ermittlung unterstützen möchten, müssen Sie neue DNS-Einträge (Domain Name System) hinzufügen. In diesem Abschnitt werden die DNS-Einträge beschrieben, die für die automatische Ermittlung erforderlich sind.

Zur Unterstützung der AutoErmittlung müssen Sie für jede SIP-Domäne die folgenden DNS-Einträge erstellen:

  - Einen internen DNS-Eintrag zur Unterstützung mobiler Benutzer, die über das Netzwerk Ihrer Organisation eine Verbindung herstellen

  - Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen

Die interne AutoErmittlung-URL sollte nicht von außerhalb des Netzwerks adressierbar sein. Die externe AutoErmittlung-URL sollte nicht von innerhalb des Netzwerks adressierbar sein. Wenn Sie diese Anforderung für die externe URL nicht erfüllen können, sollte dies allerdings nicht die Funktionen des mobilen Clients beeinträchtigen.

Bei den DNS-Einträgen kann es sich entweder um A-Einträge (Host) oder um CNAME-Einträge handeln.

**Interne DNS-Einträge**

Sie müssen einen der folgenden internen DNS-Einträge erstellen:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname oder SRV-Definition</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;SIP-Domäne&gt;</em></p></td>
<td><p>Interner Webdienste-FQDN für den Directorpool, sofern vorhanden, oder für den Front-End-Pool, wenn kein Director vorhanden ist</p></td>
</tr>
<tr class="even">
<td><p>A (Host)</p></td>
<td><p>lyncdiscoverinternal.<em>&lt;SIP-Domäne&gt;</em></p></td>
<td><p>Interne Webdienste-IP-Adresse (virtuelle IP-Adresse bei Verwendung eines Lastenausgleichs) des Directorpools, sofern vorhanden, oder des Front-End-Pools, wenn kein Director vorhanden ist</p></td>
</tr>
</tbody>
</table>


**Externe DNS-Einträge**

Sie müssen einen der folgenden externen DNS-Einträge erstellen:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Eintragstyp</th>
<th>Hostname</th>
<th>Auflösung in</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. <em>&lt;SIP-Domäne&gt;</em></p></td>
<td><p>Externer Webdienste-FQDN für den Directorpool, falls vorhanden, oder für den Front-End-Pool , wenn kein Director vorhanden ist</p></td>
</tr>
<tr class="even">
<td><p>A (Host)</p></td>
<td><p>lyncdiscover. <em>&lt;SIP-Domäne&gt;</em></p></td>
<td><p>Externe oder öffentliche IP-Adresse (VIP-Adresse bei Verwendung eines Lastenausgleichs) des Reverseproxys</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. <em>&lt;sipdomain&gt;</em></p>
<p>Wird in Hosteinträge (A oder AAAA) für den Zugriffs-Edgedienst aufgelöst</p></td>
<td><p>Zur Unterstützung des Pushbenachrichtigungsdiensts und des Apple-Pushbenachrichtigungsdiensts erstellen Sie einen SRV-Eintrag für jede SIP-Domäne, die Microsoft Lync Mobile-Clients aufweist.</p>
<div>

> [!IMPORTANT]
> Diese Anforderung gilt nur für Microsoft Lync Mobile-Clients auf Apple- oder Microsoft-basierten mobilen Geräten. Android- und Nokia Symbian-Geräte verwenden die Pushbenachrichtigung nicht.


</div></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Der Datenverkehr von Lyncdiscover, auch als AutoErmittlung bekannt, wird über den Reverseproxy geleitet. Der SRV-Eintrag zeigt auf einen Eintrag, der über den Zugriffs-Edgedienst aufgelöst wird.


