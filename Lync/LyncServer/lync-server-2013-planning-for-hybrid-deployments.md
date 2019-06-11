---
title: 'Lync Server 2013: Planen von hybridbereitstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planen der Bereitstellung von lync Server 2013-hybridbereitstellungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-05-25_

Berücksichtigen Sie beim Planen einer hybridbereitstellung die folgenden Anforderungen für Benutzer und Ihre Netzwerkinfrastruktur.

<div>

## <a name="infrastructure-requirements"></a>Infrastrukturanforderungen

Sie müssen die folgenden in Ihrer Umgebung konfiguriert haben, um eine hybridbereitstellung implementieren und bereitstellen zu können.

  - Ein Microsoft Office 365-Mandant mit aktiviertem Skype for Business Online. Beachten Sie, dass Sie nur einen einzelnen Mandanten für eine Hybrid Konfiguration mit Ihrer lokalen Bereitstellung verwenden können.

  - Eine einzelne lokale Bereitstellung (Infrastruktur) von Skype for Business Server oder lync Server, die in einer unterstützten Topologie bereitgestellt wird. Siehe Topologie-Anforderungen.
    
    Informationen zum Konfigurieren ihrer lync Server 2013-oder lync Server 2010-Bereitstellung für hybride finden Sie unter [Konfigurieren von lync Server 2013-hybridbereitstellungen](lync-server-2013-configuring-hybrid-deployments.md).

  - Skype for Business Server 2015-Verwaltungstools. Wenn Sie lync Server 2013 oder lync Server 2010 verwenden, können Sie die Verwaltungstools von lync Server 2013 verwenden.

  - Um die einmalige Anmeldung bei Office 365 zu unterstützen, damit Benutzer dieselben Anmeldeinformationen für die Anmeldung bei Office verwenden können, während Sie lokal tätig sind, können Sie die Kenn Wort Synchronisierungsfeatures von Azure Active Directory (AAD) Connect verwenden. Sie können auch die Active Directory Federation Services (AD FS) für das einmalige Anmelden mit Office 365 verwenden.
    
    Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Eine einzige Lösung für die Verzeichnissynchronisierung, damit Ihre lokalen und Online aktiven Active Directory-Objekte synchronisiert bleiben. Details zur Verzeichnissynchronisierung finden Sie unter [Tools für die Verzeichnis Integration](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Lync-Client Unterstützung

Es gibt einige Unterschiede bei den Features, die in lync-Clients unterstützt werden, sowie die Features, die in lokalen und Online Umgebungen zur Verfügung stehen. Bevor Sie sich entscheiden, wo Sie die Benutzer in Ihrer Organisation privatisieren möchten, können Sie die Clientunterstützung für die verschiedenen Konfigurationen von lync Server anzeigen. Die folgenden Clients werden von Skype for Business Online in einer lync-hybridbereitstellung unterstützt:

  - Lync 2010

  - Lync 2013

  - Windows Store-App für Lync

  - Lync Web App

  - Lync Mobile

  - Lync für Mac 2011

  - Lync Room System

  - Lync Basic 2013

Details zum Client Support finden Sie unter den folgenden Themen:

  - [Clients für lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Vergleichstabellen für mobile Clients für Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Anforderungen im Hinblick auf die Topologie

Wenn Sie Ihre Bereitstellung für Hybrid mit Skype for Business Online konfigurieren möchten, müssen Sie über eine der folgenden unterstützten Topologien verfügen:

  - Eine Skype for Business Server 2015-Bereitstellung mit allen Servern, auf denen Skype for Business Server 2015 ausgeführt wird.

  - Eine lync Server 2013-Bereitstellung mit allen Servern, auf denen lync Server 2013 ausgeführt wird.

  - Eine lync Server 2010-Bereitstellung mit allen Servern, auf denen lync Server 2010 mit den neuesten kumulativen Updates ausgeführt wird.
    
      - Auf dem Verbund-Edgeserver und dem Server für den nächsten Hop vom Verbund-Edgeserver muss lync Server 2010 mit den neuesten kumulativen Updates ausgeführt werden.
    
      - Die Verwaltungs Tools für Skype for Business Server 2015 oder lync Server 2013 müssen auf mindestens einem Server oder einer Verwaltungsarbeitsstation installiert sein.

  - Eine gemischte lync Server 2013-und Skype for Business Server 2015-Bereitstellung mit den folgenden Server Rollen in mindestens einer Website mit Skype for Business Server 2015:
    
      - Mindestens ein Enterprise-Pool- oder Standard Edition-Server 
    
      - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden
    
      - Der dem SIP-Partnerverbund zugeordnete Edgepool

  - Eine gemischte lync Server 2010-und Skype for Business Server 2015-Bereitstellung mit den folgenden Serverrollen in mindestens einer Website mit Skype for Business Server 2015:
    
      - Mindestens ein Enterprise-Pool- oder Standard Edition-Server 
    
      - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls vorhanden
    
      - Der dem SIP-Partnerverbund zugeordnete Edgepool für den Standort

  - Eine gemischte lync Server 2010-und lync Server 2013-Bereitstellung mit den folgenden Server Rollen in mindestens einer Website mit lync Server 2013:
    
      - Mindestens ein Enterprise-Pool- oder Standard Edition-Server am Standort
    
      - Der dem SIP-Partnerverbund zugeordnete Director-Pool, falls am Standort vorhanden
    
      - Der dem SIP-Partnerverbund zugeordnete Edgepool für den Standort

<div>


> [!IMPORTANT]  
> Die gesamte Benutzerverwaltung, einschließlich des Benutzers, der zwischen lokalen und UNRESOLVED_TOKEN_VAL (skypeforbusiness) Online wechselt, muss mithilfe der neuesten installierten Version der Verwaltungstools ausgeführt werden. Die Verwaltungstools müssen auf einem separaten Server installiert sein, auf dem der Zugriff auf die vorhandene lokale Bereitstellung und das Internet verbunden ist. Das Cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> zum Verschieben von Benutzern aus Ihrer lokalen Bereitstellung in UNRESOLVED_TOKEN_VAL (skype16_online) muss über die Verwaltungstools ausgeführt werden, die mit Ihrer lokalen Bereitstellung verbunden sind.



</div>

Weitere Informationen zu unterstützten Topologien finden Sie unter [Unterstützte Topologien in lync Server 2013](lync-server-2013-supported-topologies.md)und [lync Server 2013-Referenz Topologien für Enterprise-Hybrid Bereitstellungen](http://go.microsoft.com/fwlink/p/?linkid=398709).

Informationen zur Problembehandlung von hybridbereitstellungen und zum Verbinden von PowerShell mit lync Online finden Sie unter [lync online: Problembehandlung bei lync PowerShell und Hybrid](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Voraussetzungen für zugelassene/blockierte Listen für Föderationen

Die Liste der zugelassenen Domänen enthält Domänen, für die ein Partner-Edge-FQDN (vollqualifizierter Domänenname) konfiguriert ist. Diese werden mitunter als *zulässige Partnerserver* oder *direkte Verbundpartner* bezeichnet. Sie sollten mit dem Unterschied zwischen einem öffentlichen Partnerverbund und einem geschlossenen Partnerverbund vertraut sein, der in lokalen Bereitstellungen als *Partnerermittlung* bzw. *Liste der zulässigen Partnerdomänen* bezeichnet wird.

Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:

  - Der Domänenabgleich muss für die lokale Bereitstellung und den Office 365-Mandanten identisch konfiguriert sein. Wenn die Partnerermittlung für die lokale Bereitstellung aktiviert ist, muss der öffentliche Partnerverbund für den Onlinemandaten konfiguriert sein. Wenn die Partnerermittlung nicht aktiviert ist, muss für den Onlinemandanten der geschlossene Partnerverbund konfiguriert sein.

  - Die Liste der blockierten Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Onlinemandanten übereinstimmen.

  - Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Onlinemandanten übereinstimmen.

  - Der Verbund muss für die externe Kommunikation für den Online Mandanten aktiviert sein, der über die lync Online-Systemsteuerung konfiguriert wird.

</div>

<div>

## <a name="dns-settings"></a>DNS-Einstellungen

Beim Erstellen von DNS-Einträgen für hybridbereitstellungen sollten alle externen lync-DNS-Einträge auf die lokale Infrastruktur verweisen. Details zu den erforderlichen DNS-Einträgen finden Sie unter [Domain Name System (DNS) Requirements for lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Darüber hinaus müssen Sie sicherstellen, dass die in der folgenden Tabelle erläuterte DNS-Auflösung in Ihrer lokalen Bereitstellung funktioniert:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DNS-Eintrag</p></td>
<td><p>Aufzulösen durch</p></td>
<td><p>DNS-Anforderung</p></td>
</tr>
<tr class="even">
<td><p>DNS-SRV-Eintrag für _sipfederationtls. _tcp. &lt;sipdomain.com&gt; für alle unterstützten SIP-Domänen, die in Access Edge external IP (s) aufgelöst werden</p></td>
<td><p>Edgeserver</p></td>
<td><p>Aktivieren Sie Partnerverbundkommunikation in einer Hybridkonfiguration. Der Edgeserver muss wissen, wohin der Datenverkehr im Partnerverbund für die zwischen lokal und online aufgeteilte SIP-Domäne geleitet werden soll.</p></td>
</tr>
<tr class="odd">
<td><p>DNS-A-Eintrag/Einträge für den Edge-Webkonferenzdienst-FQDN, zum Beispiel „webcon.contoso.com“, aufgelöst zu der externen IP/den IPs des Webkonferenzdienst-Edgeservers</p></td>
<td><p>Über internes Unternehmensnetzwerk verbundene Benutzercomputer</p></td>
<td><p>Versetzen Sie Onlinebenutzer in die Lage, in lokal gehosteten Besprechungen Inhalte zu präsentieren oder zu betrachten. Entsprechende Inhalte sind unter anderem PowerPoint-Dateien, Whiteboards, Umfragen und freigegebene Notizen. </p></td>
</tr>
</tbody>
</table>


Je nachdem, wie DNS in Ihrer Organisation konfiguriert ist, müssen Sie möglicherweise der intern gehosteten DNS-Zone für die entsprechenden SIP-Domäne(n) diese Einträge hinzufügen, um die interne DNS-Auflösung dieser Datensätze zu gewährleisten.

</div>

<div>

## <a name="firewall-considerations"></a>Firewall-Überlegungen

Die Computer in Ihrem Netzwerk müssen Standard-Internet-DNS-Lookups ausführen können. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Je nach Standort Ihres Microsoft Online Services-Rechenzentrums müssen Sie auch Ihre Netzwerkfirewall-Geräte so konfigurieren, dass Sie Verbindungen basierend auf Platzhalter-Domänennamen (beispielsweise alle Daten \*Verkehr von Outlook.com) akzeptieren. Wenn die Firewalls Ihrer Organisation Konfigurationen mit Platzhalternamen nicht unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell festlegen.

Weitere Informationen finden Sie im Hilfethema [Office 365-URLs und IP-Adressbereiche](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Port-und Protokollanforderungen

Zusätzlich zu den Portanforderungen für die interne lync Server 2013-Kommunikation müssen Sie auch die folgenden Ports konfigurieren.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/Port</th>
<th>Anwendungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Eingehend öffnen</p>
<ul>
<li><p>Active Directory-Verbunddienste (Verbundserver Rolle)</p>
<p>Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Grundlegendes zu AD FS-Rollendiensten</a>.</p></li>
<li><p>Active Directory-Verbunddienste (Proxy Serverrolle)</p></li>
<li><p>Microsoft Online Services-Portal</p></li>
<li><p>Mein Unternehmens Portal</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync-Client (Kommunikation mit lync Online von einem lokalen lync-Server)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 und 443</p></td>
<td><p>Eingehend öffnen</p>
<ul>
<li><p>Microsoft Online Services-Verzeichnis Synchronisierungs Tool</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Inbound/Outbound auf dem Edgeserver öffnen</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Eingehende/ausgehende Datenfreigabesitzungen öffnen</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Eingehend/ausgehend für Audio-, Video-und Anwendungsfreigabesitzungen öffnen</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Eingehende/ausgehende für Audio-und Videositzungen öffnen</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Open Outbound für Audio-und Videositzungen</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Benutzerkonten und-Daten

In einer lync Server 2013-hybridbereitstellung müssen alle Benutzer, die Sie in lync Online verwenden möchten, zunächst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in den Active Directory-Domänendiensten erstellt wird. Sie können den Benutzer dann in Skype for Business Online verschieben, wodurch die Kontaktliste des Benutzers verschoben wird.

Wenn Sie Benutzerkonten zwischen Ihren lokalen lync-und lync Online-Bereitstellungen mit AD FS und Dirsync synchronisieren, müssen Sie die Ad-Konten für alle lync-Benutzer in Ihrer Organisation zwischen Ihren lokalen und Online lync-Bereitstellungen synchronisieren, auch wenn Benutzer werden nicht in lync Online verschoben. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.

<div>


> [!IMPORTANT]  
> Wenn der Benutzer mithilfe des Online Portals für Office 365 erstellt wird, wird das Benutzerkonto nicht mit lokalem Active Directory synchronisiert, und der Benutzer ist nicht im lokalen Active Directory vorhanden. Wenn Sie bereits Benutzer in lync online erstellt haben und Hybrid mit einem lokalen lync-Server konfigurieren möchten, lesen Sie <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Verschieben von Benutzern aus lync Online in lync lokal in lync Server 2013</A>.



</div>

Sie sollten bei der Planung einer Hybridbereitstellung auch die folgenden benutzerbezogenen Aspekte berücksichtigen.

  - **Benutzer Kontakte**   die Höchstgrenze für Kontakte für lync Online-Benutzer lautet 250. Alle darüber hinausgehenden Kontakte werden aus der Kontaktliste des Benutzers entfernt, wenn das Konto nach Lync Online verschoben wird.

  - **Sofortnachrichten und Anwesenheits**   Benutzer-Kontaktlisten, Gruppen und Zugriffssteuerungslisten (ACLs) werden mit dem Benutzerkonto migriert.

  - **Konferenzdaten, Besprechungsinhalte und geplante Besprechungen**   dieser Inhalt wird nicht mit dem Benutzerkonto migriert. Benutzer müssen Besprechungen neu planen, nachdem ihre Konten zu Lync Online migriert wurden.

</div>

<div>

## <a name="user-policies-and-features"></a>Benutzerrichtlinien und-Features

  - In einer lync Server 2013-Hybridumgebung können Benutzer für Sofortnachrichten, Sprachanrufe und Besprechungen entweder lokal oder Online aktiviert sein, jedoch nicht beides gleichzeitig.

  - **Lync-Client**     einige Benutzer benötigen möglicherweise eine neue Client Version, wenn Sie nach lync Online verschoben werden. Für Office Communications Server 2007 R2 müssen Benutzer vor der Migration zu lync Online in einen lync Server 2013-Pool verschoben werden.
    
    Weitere Informationen zum Client Support finden Sie unter [Clients für lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) und [unterstützte lync-Clients und Netzwerk-Portkonfigurationen](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Lokale Richtlinien und Konfiguration (nicht-Benutzer)**   Online-und lokale Richtlinien erfordern eine separate Konfiguration. Sie können keine globalen Richtlinien festlegen, die für beide Umgebungen gelten.

</div>

</div>

<span> </span>

</div>

</div>

</div>

