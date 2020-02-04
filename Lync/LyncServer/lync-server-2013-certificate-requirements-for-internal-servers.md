---
title: 'Lync Server 2013: Anforderungen an Zertifikate für interne Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Anforderungen an Zertifikate für interne Server in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2017-02-17_

Zu den internen Servern, auf denen lync Server ausgeführt wird und für die Zertifikate erforderlich sind, gehören Standard Edition-Server, Enterprise Edition-Front-End-Server, Vermittlungsserver und Director. In der folgenden Tabelle sind die Zertifikatanforderungen für diese Server aufgeführt. Sie können den lync Server-Zertifikat-Assistenten verwenden, um diese Zertifikate anzufordern.

<div>


> [!TIP]  
> Platzhalterzertifikate werden für die alternativen Subjektnamen unterstützt, die mit den einfachen URLs im Front-End-Pool, Front-End-Server oder Director verknüpft sind. Details zur Unterstützung von Platzhalterzertifikaten finden Sie unter <A href="lync-server-2013-wildcard-certificate-support.md">Unterstützung für Platzhalterzertifikate in lync Server 2013</A>.



</div>

Obwohl eine interne Unternehmenszertifizierungsstelle für interne Server empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden. Eine Liste der öffentlichen Zertifizierungsstellen, die Zertifikate zur Verfügung stellen, die bestimmte Anforderungen für Unified Communications (UC)-Zertifikate erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem lync Server-Zertifikat-Assistenten funktionieren, finden Sie im [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)Artikel Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners für Exchange Server und für Communications Server" unter.

Die Kommunikation mit anderen Anwendungen und Servern, wie etwa Exchange 2013, erfordert ein Zertifikat, das von den anderen Anwendungen und Produkten unterstützt wird. Für die 2013-Version unterstützen lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Ausführliche Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

Für Verbindungen von Clients mit Windows 7-Betriebssystem, Windows Server 2008-Betriebssystem, Windows Server 2008 R2-Betriebssystem, Windows Vista-Betriebssystem und Microsoft lync Phone Edition umfasst lync Server 2013 Unterstützung für (aber nicht require) Zertifikate, die mit der SHA-256-kryptografischen Hashfunktion signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.

In den folgenden Tabellen werden die Zertifikatanforderungen nach Serverrolle für Front-End-Pools und Standard Edition-Server angezeigt. Dies sind standardmäßige Webserverzertifikate, privater Schlüssel, nicht exportierbarer Server.

Beachten Sie, dass die erweiterte Schlüsselverwendung von Server automatisch konfiguriert wird, wenn Sie mit dem Zertifikat-Assistenten Zertifikate anfordern.

<div>


> [!NOTE]  
> Jeder Zertifikatsanzeige Name muss im Computerspeicher eindeutig sein.



</div>

<div>


> [!NOTE]  
> Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie diese im alternativen Antragstellernamen des Zertifikats hinzufügen.



</div>

### <a name="certificates-for-standard-edition-server"></a>Zertifikate für den Standard Edition-Server

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Zertifikat</th>
<th>Name des Antragstellers/gebräuchlicher Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools</p></td>
<td><p>FQDN des Pools und der FQDN des Servers</p>
<p>Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.</p></td>
<td><p>Auf dem Standard Edition-Server entspricht der Server-FQDN dem FQDN des Pools.</p>
<p>Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.</p>
<p>Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht dem FQDN des Servers)</p></li>
<li><p>Einfache Besprechungs-URLs</p></li>
<li><p>Einfache URLs vom Typ „Dialin“</p></li>
<li><p>Einfache URLs vom Typ „Admin“</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Sie können den internen Web-FQDN im Topologie-Generator nicht außer Kraft setzen.</p>
<p>Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ „Dialin“</p></li>
<li><p>Einfache Besprechungs-URLs pro SIP-Domäne</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Zertifikate für den Front-End-Server in einem Front-End-Pool

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Zertifikat</th>
<th>Name des Antragstellers/gebräuchlicher Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>FQDN des Pools und FQDN des Servers.</p>
<p>Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</p>
<p>Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für SIP. sipdomain (für jede SIP-Domäne, die Sie haben).</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.</p></td>
<td><p>Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.</p>
<p>Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Web-intern</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht NICHT dem FQDN des Servers)</p></li>
<li><p>Server-FQDN</p></li>
<li><p>Lync-Pool-FQDN</p></li>
<li><p>Einfache Besprechungs-URLs</p></li>
<li><p>Einfache URLs vom Typ „Dialin“</p></li>
<li><p>Einfache URLs vom Typ „Admin“</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ „Dialin“</p></li>
<li><p>Einfache URLs vom Typ „Admin“</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a>Zertifikate für Director

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Zertifikat</th>
<th>Name des Antragstellers/gebräuchlicher Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Director-Pools</p></td>
<td><p>FQDN des Directors, FQDN des Director-Pools</p>
<p>Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für SIP. sipdomain (für jede SIP-Domäne, die Sie haben).</p></td>
<td><p>SN = dir-Pool.contoso.com; San = dir-Pool.contoso.com; San = dir01. contoso. com</p>
<p>Wenn dieser Director-Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch San = SIP. contoso. com; San = SIP. fabrikam. com</p></td>
</tr>
<tr class="even">
<td><p>Web-intern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht dem FQDN des Servers)</p></li>
<li><p>Server-FQDN</p></li>
<li><p>Lync-Pool-FQDN</p></li>
<li><p>Einfache Besprechungs-URLs</p></li>
<li><p>Einfache URLs vom Typ „Dialin“</p></li>
<li><p>Einfache URLs vom Typ „Admin“</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ „Dialin“</p></li>
<li><p>Einfache URLs vom Typ „Admin“</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>Der FQDN des Director External Web muss vom Front-End-Pool oder Front-End-Server abweichen.</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Wenn Sie über einen eigenständigen vermittlungsserverpool verfügen, benötigen die Vermittlungsserver jeweils die in der folgenden Tabelle aufgelisteten Zertifikate. Wenn Sie den Vermittlungs Server mit den Front-End-Servern collocate, genügen die Zertifikate, die in der Tabelle "Zertifikate für Front-End-Server im Front-End-Pool" weiter oben in diesem Thema aufgeführt sind.

### <a name="certificates-for-stand-alone-mediation-server"></a>Zertifikate für eigenständigen Vermittlungs Server

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Zertifikat</th>
<th>Name des Antragstellers/gebräuchlicher Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>FQDN des Pools</p>
<p>FQDN des Pool Mitgliedsservers</p></td>
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Zertifikate für Survivable Branch Appliance

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Zertifikat</th>
<th>Name des Antragstellers/gebräuchlicher Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN der Anwendung</p></td>
<td><p>SIP. &lt;sipdomain&gt; (benötigt einen Eintrag pro SIP-Domäne)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[Unterstützung von Platzhalterzertifikaten in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

