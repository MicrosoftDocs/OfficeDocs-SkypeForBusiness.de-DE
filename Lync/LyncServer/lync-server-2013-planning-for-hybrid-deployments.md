---
title: 'Lync Server 2013: Planen von hybridbereitstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f9572df29681d6b2ee754fe51702fcc8f0b0163
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planen von lync Server 2013 hybridbereitstellungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-05-25_

Bei der Planung einer hybridbereitstellung sollten Sie die folgenden Anforderungen für Benutzer und Ihre Netzwerkinfrastruktur berücksichtigen.

<div>

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen

In Ihrer Umgebung muss Folgendes konfiguriert sein, damit Sie eine hybridbereitstellung implementieren und bereitstellen können.

  - Ein Microsoft Office 365-Mandant mit aktivierter Skype for Business Online. Beachten Sie, dass Sie für eine Hybrid Konfiguration mit Ihrer lokalen Bereitstellung nur einen einzelnen Mandanten verwenden können.

  - Eine einzelne lokale Bereitstellung (Infrastruktur) von Skype for Business Server oder lync Server, die in einer unterstützten Topologie bereitgestellt wird. Siehe Topologie-Anforderungen.
    
    Informationen zum Konfigurieren der lync Server 2013 oder lync Server 2010-Bereitstellung für hybridbereitstellungen finden Sie unter [Configuring lync Server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).

  - Skype for Business Server 2015 Verwaltungstools. Wenn Sie lync Server 2013 oder lync Server 2010 verwenden, können Sie die lync Server 2013 Verwaltungstools verwenden.

  - Zur Unterstützung des einmaligen Anmeldens mit Office 365, damit Benutzer dieselben Anmeldeinformationen für die Anmeldung bei Office verwenden können, wenn diese lokal Vorgehen, können Sie die Kenn Wort Synchronisierungsfeatures von Azure Active Directory (AAD) Connect verwenden. Sie können auch Active Directory Verbunddienste (AD FS) für einmaliges Anmelden mit Office 365 verwenden.
    
    Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Identitäten in Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).

  - Eine einzelne Verzeichnis Synchronisierungslösung, mit der Sie Ihre lokalen und Online Active Directory-Objekte synchron halten. Ausführliche Informationen zur Verzeichnissynchronisierung finden Sie unter [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Lync-Client Unterstützung

Es gibt einige Unterschiede in den Features, die in lync-Clients unterstützt werden, sowie die Features, die in lokalen und Online-Umgebungen zur Verfügung stehen. Bevor Sie entscheiden, wo Benutzer in Ihrer Organisation zu Hause sein sollen, können Sie die Clientunterstützung für die verschiedenen Konfigurationen von lync Server anzeigen. Die folgenden Clients werden mit Skype for Business Online in einer lync-hybridbereitstellung unterstützt:

  - Lync 2010

  - Lync 2013

  - Lync Windows Store-App

  - Lync Web App

  - Lync Mobile

  - Lync für Mac 2011

  - Lync-Raumsystem

  - Lync Basic 2013

Ausführliche Informationen zur Clientunterstützung finden Sie in den folgenden Themen:

  - [Clients für lync Online](https://go.microsoft.com/fwlink/?linkid=281902)

  - [Client Vergleichstabellen für lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Vergleichstabellen für mobile Clients für lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Um Ihre Bereitstellung für Hybrid mit Skype for Business Online zu konfigurieren, müssen Sie über eine der folgenden unterstützten Topologien verfügen:

  - Eine Skype for Business Server 2015 Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 läuft.

  - Eine lync Server 2013 Bereitstellung mit allen Servern, auf denen lync Server 2013 läuft.

  - Eine lync Server 2010 Bereitstellung mit allen Servern, auf denen lync Server 2010 mit den neuesten kumulativen Updates läuft.
    
      - Der Verbund Edgeserver und der Server für den nächsten Hop aus dem Verbund Edgeserver müssen lync Server 2010 mit den neuesten kumulativen Updates laufen.
    
      - Die Skype for Business Server 2015-oder lync Server 2013-Verwaltungs Tools müssen auf mindestens einem Server oder einer Verwaltungsarbeitsstation installiert sein.

  - Eine gemischte lync Server 2013-und Skype for Business Server 2015-Bereitstellung mit den folgenden Server Rollen an mindestens einer Website mit Skype for Business Server 2015:
    
      - Mindestens ein Enterprise-Pool oder Standard Edition-Server
    
      - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden
    
      - Dem SIP-Partnerverbund zugeordneter Edge-Pool

  - Eine gemischte lync Server 2010-und Skype for Business Server 2015-Bereitstellung mit den folgenden Serverrollen an mindestens einem Standort, auf dem Skype for Business Server 2015 läuft:
    
      - Mindestens ein Enterprise-Pool oder Standard Edition-Server
    
      - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden
    
      - Der dem SIP-Partnerverbund für den Standort zugeordnete Edge-Pool

  - Eine gemischte lync Server 2010-und lync Server 2013-Bereitstellung mit den folgenden Server Rollen an mindestens einer Website mit lync Server 2013:
    
      - Mindestens ein Enterprise-Pool oder Standard Edition-Server am Standort
    
      - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls dieser in der Website vorhanden ist
    
      - Der dem SIP-Partnerverbund für den Standort zugeordnete Edge-Pool

<div>


> [!IMPORTANT]  
> Die gesamte Benutzerverwaltung, einschließlich der Benutzer Verschiebungen zwischen lokalen und UNRESOLVED_TOKEN_VAL Online (skypeforbusiness), muss mithilfe der neuesten installierten Version der Verwaltungstools ausgeführt werden. Die Verwaltungstools müssen auf einem separaten Server installiert sein, der über einen Connect-Zugriff auf die vorhandene lokale Bereitstellung und das Internet verfügt. Das Cmdlet " <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">CsUser</A> ", um Benutzer von Ihrer lokalen Bereitstellung in UNRESOLVED_TOKEN_VAL (skype16_online) zu verlagern, muss über die Verwaltungstools ausgeführt werden, die mit Ihrer lokalen Bereitstellung verbunden sind.



</div>

Weitere Informationen zu unterstützten Topologien finden Sie unter [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md)und [lync Server 2013 Referenz Topologien für Enterprise-Hybrid Bereitstellungen](https://go.microsoft.com/fwlink/p/?linkid=398709).

Informationen zur Problembehandlung bei hybridbereitstellungen und zum Verbinden von PowerShell mit lync Online finden Sie unter [lync online: lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Anforderungen für zugelassene/blockierte Verbund Listen

Die Liste der zugelassenen Domänen enthält Domänen, für die der vollqualifizierte Domänenname (FQDN) des Partner Edges konfiguriert ist. Diese werden manchmal als *zugelassene Partnerserver* oder *direkte Verbundpartner*bezeichnet. Sie sollten mit dem Unterschied zwischen Open Federation und Closed Federation vertraut sein, der in lokalen Bereitstellungen als *Partner Discovery* und *zugelassene Partnerdomänen Liste*bezeichnet wird.

Die folgenden Anforderungen müssen erfüllt sein, um eine hybridbereitstellung erfolgreich zu konfigurieren:

  - Der Domänen Abgleich muss für die lokale Bereitstellung und den Office 365 Mandanten identisch konfiguriert werden. Wenn die Partner Ermittlung für die lokale Bereitstellung aktiviert ist, muss Open Federation für Ihren Online-Mandanten konfiguriert werden. Wenn die Partner Ermittlung nicht aktiviert ist, muss Closed Federation für Ihren Online-Mandanten konfiguriert werden.

  - Die Liste blockierter Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Online Mandanten übereinstimmen.

  - Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Online Mandanten übereinstimmen.

  - Der Partnerverbund muss für die externe Kommunikation für den Online Mandanten aktiviert sein, der über die lync Online-Systemsteuerung konfiguriert ist.

</div>

<div>

## <a name="dns-settings"></a>DNS-Einstellungen

Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle externen lync-DNS-Einträge auf die lokale Infrastruktur hinweisen. Ausführliche Informationen zu den erforderlichen DNS-Einträgen finden Sie unter [Domain Name System (DNS) Anforderungen für lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Außerdem müssen Sie sicherstellen, dass die in der folgenden Tabelle beschriebene DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS-Eintrag</p></td>
<td><p>Auflösbar durch</p></td>
<td><p>DNS-Anforderung</p></td>
</tr>
<tr class="even">
<td><p>DNS-SRV-Eintrag für _sipfederationtls. _tcp. &lt;sipdomain.com&gt; für alle unterstützten SIP-Domänen, die auf Edge-externe IP (s) zugreifen</p></td>
<td><p>Edgeserver (s)</p></td>
<td><p>Aktivieren Sie die Verbundkommunikation in einer Hybrid Konfiguration. Die Edgeserver müssen wissen, wo der Verbunddatenverkehr für die SIP-Domäne, die zwischen lokal und Online aufgeteilt ist, weitergeleitet werden soll.</p></td>
</tr>
<tr class="odd">
<td><p>DNS-A-Einträge für den FQDN des Edge-Webkonferenz Diensts, beispielsweise webcon.contoso.com auflösen in Webkonferenz-Edge-externe IP (s)</p></td>
<td><p>Interne Unternehmensnetzwerk verbundene Benutzer Computer</p></td>
<td><p>Ermöglichen Sie Online-Benutzern das präsentieren oder Anzeigen von Inhalten in lokalen gehosteten Besprechungen. Der Inhalt enthält PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen.</p></td>
</tr>
</tbody>
</table>


Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie diese Einträge möglicherweise der internen gehosteten DNS-Zone für die entsprechenden SIP-Domänen hinzufügen, um die interne DNS-Auflösung für diese Einträge bereitzustellen.

</div>

<div>

## <a name="firewall-considerations"></a>Überlegungen zu Firewalls

Computer in Ihrem Netzwerk müssen in der Lage sein, standardmäßige Internet-DNS-Lookups durchzuführen. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Je nach Speicherort Ihres Microsoft Online Services-Rechenzentrums müssen Sie auch die Netzwerkfirewall-Geräte so konfigurieren, dass Verbindungen basierend auf Platzhalterdomänen Namen akzeptiert werden (beispielsweise der gesamte \*Datenverkehr von. Outlook.com). Wenn die Firewalls Ihrer Organisation keine Platzhalternamen Konfigurationen unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell bestimmen.

Weitere Informationen finden Sie im Hilfethema [Office 365 URLs und IP-Adressbereiche](https://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Port-und Protokollanforderungen

Zusätzlich zu den Portanforderungen für die interne lync Server 2013 Kommunikation müssen Sie auch die folgenden Ports konfigurieren.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/Port</th>
<th>Applications</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Geöffnet, eingehend</p>
<ul>
<li><p>Active Directory-Verbunddienste (Active Directory Federation Services, AD FS) (Verbundserverrolle)</p>
<p>Weitere Informationen finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</p></li>
<li><p>Active Directory-Verbunddienste (Proxyserverrolle)</p></li>
<li><p>Microsoft Online Services-Portal</p></li>
<li><p>Unternehmensportal</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync-Client (Kommunikation mit lync Online von lokalen lync Server)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 und 443</p></td>
<td><p>Geöffnet, eingehend</p>
<ul>
<li><p>Microsoft Online Services-Verzeichnissynchronisierungstool</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Eingehend/ausgehend im Edgeserver öffnen</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Öffnen von eingehenden/ausgehenden Datenfreigabesitzungen</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Öffnen eines eingehenden/ausgehenden für Audio-, Video-, Anwendungsfreigabesitzungen</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Öffnen von eingehenden/ausgehenden Daten für Audio-und Videositzungen</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Offener Ausgang für Audio-und Videositzungen</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Benutzerkonten und-Daten

In einer lync Server 2013 hybridbereitstellung müssen alle Benutzer, die in lync online zu Hause sein sollen, zuerst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in Active Directory-Domänendienste erstellt wird. Anschließend können Sie den Benutzer zu Skype for Business Online, der die Kontaktliste des Benutzers verschiebt, weitergeben.

Wenn Sie Benutzerkonten zwischen Ihren lokalen lync-und lync Online-Bereitstellungen mit AD FS und Dirsync synchronisieren, müssen Sie die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online-lync-Bereitstellungen synchronisieren, selbst wenn Benutzer werden nicht in lync Online verschoben. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Online Benutzern in Ihrer Organisation möglicherweise nicht wie erwartet.

<div>


> [!IMPORTANT]  
> Wenn der Benutzer mithilfe des Online Portals für Office 365 erstellt wird, wird das Benutzerkonto nicht mit lokalen Active Directory synchronisiert, und der Benutzer wird nicht in der lokalen Active Directory vorhanden sein. Wenn Sie bereits Benutzer in lync online erstellt haben und Hybrid mit einer lokalen lync Server konfigurieren möchten, finden Sie weitere Informationen unter <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Verschieben von Benutzern von lync Online in lync lokal in lync Server 2013</A>.



</div>

Bei der Planung einer hybridbereitstellung sollten Sie auch die folgenden benutzerbezogenen Probleme berücksichtigen.

  - **Benutzer Kontakte**   der Grenzwert für Kontakte für lync Online Benutzer lautet 250. Alle Kontakte außerhalb dieser Nummer werden aus der Kontaktliste des Benutzers entfernt, wenn das Konto in lync Online verschoben wird.

  - ****   Kontaktlisten, Gruppen und Zugriffssteuerungslisten (ACLs) für Chatnachrichten und Anwesenheits Benutzer werden mit dem Benutzerkonto migriert.

  - **Konferenzdaten, Besprechungsinhalte und geplante Besprechungen**   dieser Inhalt wird nicht mit dem Benutzerkonto migriert. Benutzer müssen Besprechungen neu planen, nachdem Ihre Konten zu lync Online migriert wurden.

</div>

<div>

## <a name="user-policies-and-features"></a>Benutzerrichtlinien und-Features

  - In einer lync Server 2013-Hybridumgebung können Benutzer sowohl lokal als auch online, aber nicht beides gleichzeitig für Chatnachrichten, VoIP und Besprechungen aktiviert werden.

  - **Lync-Client**     einige Benutzer benötigen möglicherweise eine neue Client Version, wenn Sie in lync Online verschoben werden. Für Office Communications Server 2007 R2 müssen Benutzer vor der Migration zu lync Online in einen lync Server 2013 Pool verschoben werden.
    
    Weitere Informationen zur Clientunterstützung finden Sie unter [Clients for lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) und [Supported lync Clients and Network Port Configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Lokale Richtlinien und Konfiguration (nicht-Benutzer)**   Online-und lokale Richtlinien erfordern eine separate Konfiguration. Sie können keine globalen Richtlinien festlegen, die für beides gelten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

