---
title: 'Lync Server 2013: Anforderungen an Zertifikate für interne Server'
TOCTitle: Anforderungen an Zertifikate für interne Server
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398094(v=OCS.15)
ms:contentKeyID: 49293025
ms.date: 02/18/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen an Zertifikate für interne Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2017-02-17_

Zu den internen Servern, auf denen Lync Server ausgeführt wird und die Zertifikate benötigen, gehören z. B. Standard Edition-Server, Enterprise Edition-Front-End-Server, Vermittlungsserver und Director. Die folgende Tabelle enthält die Zertifikatanforderungen für diese Server. Sie können den Zertifikat-Assistenten von Lync Server verwenden, um diese Zertifikate anzufordern.


> [!TIP]
> Platzhalterzertifikate werden für die alternativen Antragstellernamen unterstützt, die den einfachen URLs auf dem Front-End-Pool, dem Front-End-Server oder dem Director zugeordnet sind. Ausführliche Informationen zur Platzhalterzertifikatunterstützung finden Sie unter <A href="lync-server-2013-wildcard-certificate-support.md">Unterstützung von Platzhalterzertifikaten in Lync Server 2013</A>.



Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden. Eine Liste öffentlicher Zertifizierungsstellen, die Zertifikate bereitstellen, die den speziellen Anforderungen an Unified Communications-Zertifikate entsprechen und eine Partnerschaft mit Microsoft eingegangen sind, um sicherzustellen, dass ihre Zertifikate mit dem Zertifikat-Assistenten von Lync Server verwendet werden können, finden Sie im Microsoft Knowledge Base-Artikel 929395, "Partner für Unified Communications-Zertifikate für Exchange Server und Communications Server", unter [http://go.microsoft.com/fwlink/?linkid=202834\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=202834%26clcid=0x407).

Für die Kommunikation mit anderen Anwendungen und Servern, z. B. Exchange 2013, ist ein Zertifikat erforderlich, das von anderen Anwendungen und Produkten unterstützt wird. Für Version 2013 unterstützen Lync Server 2013 und andere Microsoft-Serverprodukte, darunter Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Authentifizierung und Autorisierung von Server zu Server. Ausführliche Informationen finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungs- oder Betriebsdokumentation.

Für Verbindungen von Clients, auf denen Windows 7-Betriebssystem, Windows Server 2008-Betriebssystem, Windows Server 2008 R2-Betriebssystem, Windows Vista-Betriebssystem und Microsoft Lync Phone Edition ausgeführt wird, umfasst Lync Server 2013 Unterstützung für Zertifikate, die mithilfe der kryptografischen Hashfunktion SHA-256 signiert wurden (diese jedoch nicht erfordern). Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.

In der folgenden Tabelle werden die Zertifikatanforderungen nach Serverrolle für Front-End-Pools und Standard Edition-Server aufgeführt. Es handelt sich in allen Fällen um standardmäßige, nicht exportierbare Webserverzertifikate mit privatem Schlüssel.

Beachten Sie, dass die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server automatisch konfiguriert wird, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.


> [!NOTE]
> Der Anzeigename jedes Zertifikats muss im Computerspeicher eindeutig sein.




> [!NOTE]
> Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie diese zum alternativen Antragstellernamen des Zertifikats hinzufügen.



### Zertifikate für Standard Edition-Server

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
<th>Antragstellername/ Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Pools</p></td>
<td><p>FQDN des Pools und FQDN des Servers</p>
<p>Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für &quot;sip.sipDomäne&quot; (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch &quot;SAN=sip.contoso.com; SAN=sip.fabrikam.com&quot;</p></td>
<td><p>Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.</p>
<p>Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</p>
<p>Sie können dieses Zertifikat auch für die Authentifizierung zwischen Servern verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht dem FQDN des Servers)</p></li>
<li><p>Einfache URLs vom Typ &quot;Meet&quot;</p></li>
<li><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></li>
<li><p>Einfache URL vom Typ &quot;Admin&quot;</p>
<p></p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul>
<p></p></td>
<td><p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=se01.contoso.com; SAN=se01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Sie können den internen Web-FQDN im Topologie-Generator nicht überschreiben.</p>
<p>Wenn Sie über mehrere einfache URLs vom Typ &quot;Meet&quot; verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></li>
<li><p>Einfache Besprechungs-URLs pro SIP-Domäne</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs vom Typ &quot;Meet&quot; verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
</tbody>
</table>


### Zertifikate für Front-End-Server in einem Front-End-Pool

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
<th>Antragstellername/ Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
<th>Kommentare</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>FQDN des Pools und FQDN des Servers</p>
<p>Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für &quot;sip.sipDomäne&quot; (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch &quot;SAN=sip.contoso.com; SAN=sip.fabrikam.com&quot;.</p></td>
<td><p>Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</p>
<p>Sie können dieses Zertifikat auch für die Authentifizierung zwischen Servern verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht NICHT dem FQDN des Servers)</p></li>
<li><p>Server-FQDN</p></li>
<li><p>FQDN des Lync-Pools</p></li>
<li><p>Einfache URLs vom Typ &quot;Meet&quot;</p></li>
<li><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></li>
<li><p>Einfache URL vom Typ &quot;Admin&quot;</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul>
<p></p></td>
<td><p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs vom Typ &quot;Meet&quot; verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Pools</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></li>
<li><p>Einfache URL vom Typ &quot;Admin&quot;</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>Mit einem Platzhalterzertifikat:</p>
<p>SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=*.contoso.com</p></td>
<td><p>Wenn Sie über mehrere einfache URLs vom Typ &quot;Meet&quot; verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</p>
<p>Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</p></td>
</tr>
</tbody>
</table>


### Zertifikate für Director

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
<th>Antragstellername/ Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN des Director-Pools</p></td>
<td><p>Director-FQDN, FQDN des Director-Pools</p>
<p>Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für &quot;sip.sipDomäne&quot; (für jede vorhandene SIP-Domäne).</p></td>
<td><p>SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</p>
<p>Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch &quot;SAN=sip.contoso.com; SAN=sip.fabrikam.com&quot;.</p></td>
</tr>
<tr class="even">
<td><p>Web, intern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Interner Web-FQDN (entspricht dem FQDN des Servers)</p></li>
<li><p>Einfache URLs vom Typ &quot;Meet&quot;</p></li>
<li><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></li>
<li><p>Einfache URL vom Typ &quot;Admin&quot;</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul>
<p></p></td>
<td><p>SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=*.contoso.com</p></td>
</tr>
<tr class="odd">
<td><p>Web, extern</p></td>
<td><p>FQDN des Servers</p></td>
<td><p>Jeder der folgenden:</p>
<ul>
<li><p>Externer Web-FQDN</p></li>
<li><p>Einfache URLs vom Typ &quot;Dialin&quot;</p></li>
<li><p>Einfache URL vom Typ &quot;Admin&quot;</p></li>
<li><p>Oder ein Platzhaltereintrag für die einfachen URLs</p></li>
</ul></td>
<td><p>Der externe Web-FQDN für den Director muss anders lauten als der des Front-End-Pools oder des Front-End-Servers.</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</p>
<p>SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=*.contoso.com</p></td>
</tr>
</tbody>
</table>


Wenn Sie über einen eigenständigen Vermittlungsserverpool verfügen, muss jeder der darin enthaltenen Vermittlungsserver über die in der folgenden Tabelle aufgelisteten Zertifikate verfügen. Wenn Sie einen Vermittlungsserver mit den Front-End-Servern verbinden, reichen die in der Tabelle "Zertifikate für Front-End-Server im Front-End-Pool" (weiter oben) aufgeführten Zertifikate aus.

### Zertifikate für eigenständige Vermittlungsserver

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
<th>Antragstellername/ Allgemeiner Name</th>
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
<td><p>SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</p></td>
</tr>
</tbody>
</table>


### Zertifikate für eine Survivable Branch Appliance

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
<th>Antragstellername/ Allgemeiner Name</th>
<th>Alternativer Antragstellername</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standard</p></td>
<td><p>FQDN der Appliance</p></td>
<td><p>SIP.&lt;SIP-Domäne&gt; (ein Eintrag pro SIP-Domäne erforderlich)</p></td>
<td><p>SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Konzepte

[Unterstützung von Platzhalterzertifikaten in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)

