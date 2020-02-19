---
title: 'Lync Server 2013: Bereitstellungsprozess für Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for mobility
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690023(v=OCS.15)
ms:contentKeyID: 48184220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59b6d6854c628a7f1077c0954d84ea9d82c4f715
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-mobility-in-lync-server-2013"></a>Bereitstellungsprozess für Mobilität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-19_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

In diesem Abschnitt wird die Abfolge der Schritte beschrieben, die für die Bereitstellung des lync Server 2013 Mobilitätsfeatures erforderlich sind.

### <a name="mobility-deployment-process"></a>Mobilitätsbereitstellungsprozess

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
<li><p>Erstellen Sie einen internen DNS-CNAME-oder einen (Host-, wenn IPv6-, AAAA-) Eintrag, um die interne AutoErmittlungsdienst-URL aufzulösen.</p></li>
<li><p>Erstellen Sie einen externen DNS-CNAME-oder einen (Host-, if IPv6, AAAA)-Eintrag, um die externe AutoErmittlungsdienst-URL aufzulösen.</p></li>
</ul></td>
<td><p>Domänen-Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ändern von Zertifikaten</p></td>
<td><p>Hinzufügen von Einträgen für alternative Antragstellernamen zu folgenden Zertifikaten, um sichere Verbindungen für mobile Benutzer zu unterstützen:</p>
<ul>
<li><p>Director-Zertifikat</p></li>
<li><p>Front-End-Pool Zertifikat</p></li>
<li><p>Reverseproxyzertifikat</p></li>
</ul></td>
<td><p>Lokaler Administrator</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Ändern von Zertifikaten für Mobilität in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren des Reverseproxys</p></td>
<td><ul>
<li><p>Zuweisen von aktualisierten Zertifikaten mit alternativen Antragstellernamen zum SSL-Listener (Secure Sockets Layer)</p></li>
<li><p>Konfigurieren Sie die Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL neu.</p></li>
<li><p>Stellen Sie sicher, dass für die externe lync Server 2013 Webdienste-URL auf Ihrem Front-End-Pool eine Webveröffentlichungsregel vorhanden ist.</p></li>
</ul>
<p>Oder:</p>
<ul>
<li><p>Wenn Sie http für die anfängliche Auto Ermittlungsanforderung verwenden und keine Listen alternativer Antragstellernamen auf den Zertifikaten aktualisieren, konfigurieren Sie eine neue Webveröffentlichungsregel, oder konfigurieren Sie eine vorhandene Veröffentlichungsregel für Port 80 http neu.</p></li>
</ul></td>
<td><p>Lokaler Administrator</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverse-Proxys für Mobilität in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Testen der Mobilitätsbereitstellung für lync 2010 Mobile mithilfe des MCX-mobilitätsdiensts</p></td>
<td><p>Führen Sie <strong>Test-CsMcxP2PIM</strong> aus, um das Senden einer Chatnachricht von einer Person an eine andere zu testen.</p>
<p>Eine vollständige Liste der Optionen finden Sie in der Dokumentation zu lync Server-Verwaltungsshell-Cmdlets für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Testen der Mobilitätsbereitstellung für lync 2013 Mobile Clients mithilfe der UCWA-Webkomponenten</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>Test-CsUcwaConference</strong> , um zu testen und zu überprüfen, ob vordefinierte Test Benutzer oder ein paar von tatsächlichen Benutzern UCWA zum Erstellen und teilnehmen an einer Konferenz verwenden können.</p>
<p>Eine vollständige Liste der Optionen finden Sie in der Dokumentation zu lync Server-Verwaltungsshell-Cmdlets für <a href="https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> .</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Pushbenachrichtigungen</p></td>
<td><ul>
<li><p>Fügen Sie für lync Server 2013-Edgeserver einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Partnerverbund für den Hostinganbieter.</p></li>
<li><p>Fügen Sie für lync Server 2010-Edgeserver einen lync Server Online-Hostinganbieter hinzu, und konfigurieren Sie den Partnerverbund für den Hostinganbieter.</p></li>
<li><p>Fügen Sie für Office Communications Server 2007 R2-Edgeserver einen Verbundpartner hinzu.</p></li>
<li><p>Wenn Sie Pushbenachrichtigungen über ein WLAN-Netzwerk unterstützen möchten, konfigurieren Sie eine ausgehende Firewallregel für TCP-Port 5223.</p></li>
<li><p>Verwenden Sie das <strong>Set-CsPushNotificationConfiguration</strong>-Cmdlet, um Pushbenachrichtigungen an den Apple Push Notification Service (APNS) und Microsoft Push Notification Service (MPNS) zu unterstützen. Dieses Feature ist standardmäßig deaktiviert.</p></li>
<li><p>Verwenden Sie das <strong>Test-CsFederatedPartner</strong>-Cmdlet zum Testen der Verbundkonfiguration und das <strong>Test-CsMCXPushNotification</strong>-Cmdlet zum Testen von Pushbenachrichtigungen.</p>
<div>

> [!NOTE]  
> Push-Benachrichtigungen werden für lync 2010 Mobile Clients auf Apple-Geräten und Windows Phone verwendet.<BR>Push-Benachrichtigung ist für lync 2013 Mobile Clients nur auf Windows Phone erforderlich


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Konfigurieren von Push-Benachrichtigungen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren der Mobilitätsrichtlinie</p></td>
<td><p>Verwenden Sie das Cmdlet " <strong>CsMobilityPolicy</strong> ", um Folgendes zuzulassen oder zu verweigern:</p>
<ul>
<li><p>Anruf über den Arbeitsplatz</p></li>
<li><p>IP-Audio und IP-Video aktivieren</p></li>
<li><p>WiFi für IP-Audio und/oder IP-Video erforderlich</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Konfigurieren von mobilitätsrichtlinien in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

