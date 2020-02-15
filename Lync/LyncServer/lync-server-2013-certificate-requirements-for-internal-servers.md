---
title: 'Lync Server 2013: Zertifikatanforderungen für interne Server'
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
ms.openlocfilehash: f5b3da640ca4aa9f7b53c072802a2f7f727759dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a>Zertifikatanforderungen für interne Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2017-02-17_

Zu den internen Servern, auf denen lync Server ausführt und für die Zertifikate erforderlich sind, gehören Standard Edition-Server, Enterprise Edition Front-End-Server, Vermittlungsserver und Director. Die folgende Tabelle zeigt die Zertifikatanforderungen für diese Server. Sie können den Assistenten für lync Server Zertifikate verwenden, um diese Zertifikate anzufordern.

<div>


> [!TIP]  
> Platzhalterzertifikate werden für die alternativen Antragstellernamen unterstützt, die den einfachen URLs im Front-End-Pool, Front-End-Server oder Director zugeordnet sind. Ausführliche Informationen zur Unterstützung von Platzhalterzertifikaten finden Sie unter <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard Certificate Support in lync Server 2013</A>.



</div>

Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden. Eine Liste der öffentlichen Zertifizierungsstellen mit Zertifikaten, die bestimmte Anforderungen an Unified Communications-Zertifikate (UC) erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem Assistenten für lync Server Zertifikate kompatibel sind, finden Sie in [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)Artikel Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server" unter.

Für die Kommunikation mit anderen Anwendungen und Servern wie Exchange 2013 ist ein Zertifikat erforderlich, das von den anderen Anwendungen und Produkten unterstützt wird. Für das 2013-Release, lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, wird das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung unterstützt. Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

Für Verbindungen von Clients, die Windows 7 Betriebssystem, Windows Server 2008 Betriebssystem, Windows Server 2008 R2-Betriebssystem, Windows Vista Betriebssystem und Microsoft lync Phone Edition ausführen, enthält lync Server 2013 Unterstützung für (aber keine erfordern) Zertifikate, die mit der kryptografischen Hashfunktion von SHA-256 signiert wurden. Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.

In der folgenden Tabelle werden die Zertifikatanforderungen nach Serverrolle für Front-End-Pools und Standard Edition-Server aufgeführt. Es handelt sich in allen Fällen um standardmäßige, nicht exportierbare Webserverzertifikate mit privatem Schlüssel.

Beachten Sie, dass die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server automatisch konfiguriert wird, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.

<div>


> [!NOTE]  
> Jeder Zertifikatanzeige Name muss im Computerspeicher eindeutig sein.



</div>

<div>


> [!NOTE]  
> Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie Sie im alternativen Antragstellernamen des Zertifikats hinzufügen.



</div>

### <a name="certificates-for-standard-edition-server"></a>Zertifikate für Standard Edition-Server

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
<th>Antragstellername/Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Pools</p></td>
<td><p>FQDN des Pools und FQDN des Servers</p>
<p>Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN = SE01. contoso. com; San = SE01. contoso. com</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</p></td>
<td><p>Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.</p>
<p>Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</p>
<p>Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht dem FQDN des Servers)</p></li>
<li><p>Einfache URLs vom Typ "Meet"</p></li>
<li><p>Einfache URLs vom Typ "Dialin"</p></li>
<li><p>Einfache URL vom Typ "Admin"</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; San = SE01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN = SE01. contoso. com; San = SE01. contoso. com; San = *. contoso. com</p></td>
<td><p>Sie können den internen webfqdn im Topologie-Generator nicht außer Kraft setzen.</p>
<p>Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ "Dialin"</p></li>
<li><p>Erfüllen einfacher URLs pro SIP-Domäne</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN = SE01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN = SE01. contoso. com; San = webcon01. contoso. com; San = *. contoso. com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a>Zertifikate für Front-End-Server in einem Front-End-Pool

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
<th>Antragstellername/Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
<th>Anmerkungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>FQDN des Pools und FQDN des Servers</p>
<p>Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN = EEpool. contoso. com; San = EEpool. contoso. com; San = ee01. contoso. com</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</p></td>
<td><p>Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</p>
<p>Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner FQDN des Webs (nicht identisch mit dem FQDN des Servers)</p></li>
<li><p>Server-FQDN</p></li>
<li><p>Lync-Pool-FQDN</p></li>
<li><p>Einfache URLs vom Typ "Meet"</p></li>
<li><p>Einfache URLs vom Typ "Dialin"</p></li>
<li><p>Einfache URL vom Typ "Admin"</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; San = ee01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN = ee01. contoso. com; San = ee01. contoso. com; San = *. contoso. com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ "Dialin"</p></li>
<li><p>Einfache URL vom Typ "Admin"</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN = ee01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN = ee01. contoso. com; San = webcon01. contoso. com; San = *. contoso. com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
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
<th>Antragstellername/Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Director-Pools</p></td>
<td><p>Director-FQDN, FQDN des Director-Pools</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN = dir-Pool.contoso.com; San = dir-Pool.contoso.com; San = dir01. contoso. com</p>
<p>Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht dem FQDN des Servers)</p></li>
<li><p>Server-FQDN</p></li>
<li><p>Lync-Pool-FQDN</p></li>
<li><p>Einfache URLs vom Typ "Meet"</p></li>
<li><p>Einfache URLs vom Typ "Dialin"</p></li>
<li><p>Einfache URL vom Typ "Admin"</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN = dir01. contoso. com; San = dir01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</p>
<p>SN = dir01. contoso. com; San = dir01. contoso. com San = *. contoso. com</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ "Dialin"</p></li>
<li><p>Einfache URL vom Typ "Admin"</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>Der externe Director-webfqdn muss sich von dem Front-End-Pool oder Front-End-Server unterscheiden.</p>
<p>SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</p>
<p>SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = *. contoso. com</p></td>
</tr>
</tbody>
</table>


Wenn Sie über einen eigenständigen Vermittlungsserverpool verfügen, muss jeder der darin enthaltenen Vermittlungsserver über die in der folgenden Tabelle aufgelisteten Zertifikate verfügen. Wenn Sie einen Vermittlungsserver mit den Front-End-Servern verbinden, reichen die in der Tabelle "Zertifikate für Front-End-Server im Front-End-Pool" (weiter oben) aufgeführten Zertifikate aus.

### <a name="certificates-for-stand-alone-mediation-server"></a>Zertifikate für eigenständige Vermittlungsserver

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
<th>Antragstellername/Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>FQDN des Pools</p>
<p>FQDN des Poolmitgliedsservers</p></td>
<td><p>SN = medsvr-Pool.contoso.net; San = medsvr-Pool.contoso.net; San = medsvr01. contoso. net</p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a>Zertifikate für eine Survivable Branch Appliance

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
<th>Antragstellername/Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN der Appliance</p></td>
<td><p>SIP. &lt;sipdomain "&gt; (benötigt einen Eintrag pro SIP-Domäne)</p></td>
<td><p>SN = sba01. contoso. net; San = SIP. contoso. com; San = SIP. fabrikam. com</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[Unterstützung von Platzhalterzertifikaten in lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

