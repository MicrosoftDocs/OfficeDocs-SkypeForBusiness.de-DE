---
title: 'Lync Server 2013: Bereitstellungsprozess für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dec6f1e089a9418db3d8ece1f390615226687cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Bereitstellungsprozess für Mobilität in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

In diesem Abschnitt werden die Schritte beschrieben, die für die Bereitstellung des lync Server 2013-Mobilitätsfeatures erforderlich sind.

### <a name="mobility-deployment-process"></a>Mobilitäts Bereitstellungsprozess

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Berechtigungen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Erstellen von DNS-Einträgen (Domain Name System)</p></td>
<td><ul>
<li><p>Erstellen Sie einen internen DNS-CNAME-oder einen (Host-, wenn IPv6-, AAAA)-Eintrag, um die interne AutoErmittlungsdienst-URL aufzulösen.</p></li>
<li><p>Erstellen Sie einen externen DNS-CNAME-oder einen (Host-, wenn IPv6-, AAAA)-Eintrag, um die URL des externen AutoErmittlungsdiensts aufzulösen.</p></li>
</ul></td>
<td><p>Domänen-Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ändern von Zertifikaten</p></td>
<td><p>Hinzufügen von Einträgen für Alternativen Betreff für die folgenden Zertifikate zur Unterstützung sicherer Verbindungen für mobile Benutzer:</p>
<ul>
<li><p>Director-Zertifikat</p></li>
<li><p>Front-End-Pool Zertifikat</p></li>
<li><p>Reverse-Proxy Zertifikat</p></li>
</ul></td>
<td><p>Lokaler Administrator</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Ändern der Zertifikate für Mobilität in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren des Reverseproxys</p></td>
<td><ul>
<li><p>Weisen Sie dem SSL-Listener (Secure Sockets Layer) Zertifikate zu, die mit alternativen Subjektnamen aktualisiert wurden.</p></li>
<li><p>Konfigurieren Sie die Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL neu.</p></li>
<li><p>Stellen Sie sicher, dass eine Webveröffentlichungsregel für die externe lync Server 2013-Webdienste-URL im Front-End-Pool vorhanden ist.</p></li>
</ul>
<p>Oder</p>
<ul>
<li><p>Wenn Sie sich für die Verwendung von http für die ursprüngliche AutoErmittlungs-Anforderung entscheiden und die Listen Betreff alternativer Namen nicht auf den Zertifikaten aktualisieren, konfigurieren Sie eine neue Webveröffentlichungsregel, oder konfigurieren Sie eine vorhandene Veröffentlichungsregel für Port 80 http neu.</p></li>
</ul></td>
<td><p>Lokaler Administrator</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Testen Ihrer Mobilitätsbereitstellung für lync 2010 Mobile mithilfe des MCX-mobilitätsdiensts</p></td>
<td><p>Führen Sie <strong>Test-CsMcxP2PIM</strong> aus, um das Senden einer Chatnachricht von einer Person an eine andere zu testen.</p>
<p>Eine vollständige Liste der Optionen finden Sie in der Dokumentation zum lync Server-Verwaltungsshell-Cmdlet für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Testen Ihrer Mobilitätsbereitstellung für Mobile lync 2013-Clients mithilfe der UCWA-Webkomponenten</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>Test-CsUcwaConference</strong> , um zu testen und zu überprüfen, ob vordefinierte Test Benutzer oder ein paar von tatsächlichen Benutzern UCWA zum Erstellen und teilnehmen an einer Konferenz verwenden können.</p>
<p>Eine vollständige Liste der Optionen finden Sie in der Dokumentation zum lync Server-Verwaltungsshell-Cmdlet für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Pushbenachrichtigungen</p></td>
<td><ul>
<li><p>Bei lync Server 2013-Edgeserver fügen Sie einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Hostinganbieter.</p></li>
<li><p>Bei lync Server 2010-Edgeserver fügen Sie einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Hostinganbieter.</p></li>
<li><p>Fügen Sie für Office Communications Server 2007 R2-Edgeserver einen Verbundpartner hinzu.</p></li>
<li><p>Wenn Sie Push-Benachrichtigungen über ein WLAN-Netzwerk unterstützen möchten, konfigurieren Sie eine Firewall-Regel ausgehende TCP-Port 5223.</p></li>
<li><p>Verwenden Sie das Cmdlet " <strong>Satz-CsPushNotificationConfiguration</strong> ", um Push-Benachrichtigungen für den Apple Push Notification Service (APNS) und den Microsoft Push Notification Service (MPNS) zu aktivieren. Dieses Feature ist standardmäßig deaktiviert.</p></li>
<li><p>Verwenden Sie das Cmdlet <strong>Test-CsFederatedPartner</strong> , um die Verbund Konfiguration und das <strong>Test-CsMCXPushNotification-</strong> Cmdlet zu testen, um Push-Benachrichtigungen zu testen.</p>
<div>

> [!NOTE]  
> Push-Benachrichtigungen werden für Mobile lync 2010-Clients auf Apple-Geräten und Windows Phone verwendet<BR>Für lync 2013 Mobile-Clients nur auf Windows Phone ist eine Push-Benachrichtigung erforderlich


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Konfigurieren von Pushbenachrichtigungen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren von mobilitätsrichtlinien</p></td>
<td><p>Verwenden Sie das Cmdlet " <strong>Satz-CsMobilityPolicy</strong> ", um Folgendes zuzulassen oder zu verhindern:</p>
<ul>
<li><p>Anruf über den Arbeitsplatz</p></li>
<li><p>Aktivieren von IP-Audio und IP-Video</p></li>
<li><p>WLAN für IP-Audio und/oder IP-Video erforderlich</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

