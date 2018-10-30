---
title: 'Lync Server 2013: Bereitstellungsprozess für Mobilität'
TOCTitle: Bereitstellungsprozess für Mobilität
ms:assetid: 5a1cebda-c14b-4ff4-9c36-f7caa868160f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690023(v=OCS.15)
ms:contentKeyID: 49294102
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für Mobilität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013. It is noted accordingly.

In diesem Abschnitt werden die für die Bereitstellung des Lync Server 2013-Mobilitätsfeatures erforderlichen Schritte beschrieben.

### Mobilitätsbereitstellungsprozess

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
<li><p>Erstellen eines internen DNS-CNAME- oder DNS-A-Eintrags (Host oder bei IPv6 AAAA) zum Auflösen der internen AutoErmittlungsdienst-URL.</p></li>
<li><p>Erstellen eines externen DNS-CNAME- oder DNS-A-Eintrags (Host oder bei IPv6 AAAA) zum Auflösen der externen AutoErmittlungsdienst-URL.</p></li>
</ul></td>
<td><p>Domänen-Admins</p>
<p>DnsAdmins</p></td>
<td><p><a href="lync-server-2013-creating-dns-records-for-the-autodiscover-service.md">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Ändern von Zertifikaten</p></td>
<td><p>Hinzufügen von Einträgen für alternative Antragstellernamen zu folgenden Zertifikaten, um sichere Verbindungen für mobile Benutzer zu unterstützen:</p>
<ul>
<li><p>Director-Zertifikat</p></li>
<li><p>Front-End-Pool-Zertifikat</p></li>
<li><p>Reverseproxyzertifikat</p></li>
</ul></td>
<td><p>Lokaler Administrator</p></td>
<td><p><a href="lync-server-2013-modifying-certificates-for-mobility.md">Ändern der Zertifikate für Mobilität in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren des Reverseproxys</p></td>
<td><ul>
<li><p>Zuweisen von aktualisierten Zertifikaten mit alternativen Antragstellernamen zum SSL-Listener (Secure Sockets Layer)</p></li>
<li><p>Konfigurieren Sie die Webveröffentlichungsregel für die externe AutoErmittlungsdienst-URL erneut.</p></li>
<li><p>Stellen Sie sicher, dass eine Webveröffentlichungsregel für die externe Lync Server 2013-Webdienste-URL im Front-End-Pool vorhanden ist</p></li>
</ul>
<p>Oder</p>
<ul>
<li><p>Wenn Sie HTTP für die anfängliche AutoErmittlungsanforderung verwenden und die Listen der alternativen Antragstellernamen für Zertifikate nicht aktualisieren, konfigurieren Sie eine neue Webveröffentlichungsregel für HTTP-Port 80, oder konfigurieren Sie eine entsprechende bestehende Regel erneut.</p></li>
</ul></td>
<td><p>Lokaler Administrator</p></td>
<td><p><a href="lync-server-2013-configuring-the-reverse-proxy-for-mobility.md">Konfigurieren des Reverseproxys für Mobilität in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Testen Ihrer Mobilitätsbereitstellung für Lync 2010 Mobile mithilfe des Mcx-Mobilitätsdiensts</p></td>
<td><p>Führen Sie <strong>Test-CsMcxP2PIM</strong> aus, um das Senden einer Sofortnachricht von einer Person an eine andere zu testen.</p>
<p>In der Cmdlet-Dokumentation zu Lync Server-Verwaltungsshell für <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM">Test-CsMcxP2PIM</a> finden Sie eine vollständige Liste der Optionen.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Testen Ihrer Mobilitätsbereitstellung für Lync 2013 Mobile-Clients mithilfe der UCWA-Webkomponenten</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>Test-CsUcwaConference</strong> zum Testen und Überprüfen, ob vordefinierte Testbenutzer oder zwei tatsächliche Benutzer mithilfe der UCWA eine Konferenz erstellen und daran teilnehmen können.</p>
<p>In der Cmdlet-Dokumentation zu Lync Server-Verwaltungsshell für <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference">Test-CsUcwaConference</a> finden Sie eine vollständige Liste der Optionen.</p></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-verifying-your-mobility-deployment.md">Überprüfen der Mobilitätsbereitstellung in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von Pushbenachrichtigungen</p></td>
<td><ul>
<li><p>Fügen Sie für Lync Server 2013- Edgeserver einen Lync Server-Onlinehostinganbieter hinzu, und konfigurieren Sie den Hostinganbieterverbund.</p></li>
<li><p>Fügen Sie für Lync Server 2010- Edgeserver einen Lync Server-Onlinehostinganbieter hinzu und konfigurieren Sie den Hostinganbieterverbund.</p></li>
<li><p>Fügen Sie für Office Communications Server 2007 R2- Edgeserver einen Verbundpartner hinzu.</p></li>
<li><p>Wenn Sie Pushbenachrichtigungen über ein WLAN-Netzwerk unterstützen möchten, konfigurieren Sie eine ausgehende Firewallregel für TCP-Port 5223.</p></li>
<li><p>Verwenden Sie das <strong>Set-CsPushNotificationConfiguration</strong>-Cmdlet, um Pushbenachrichtigungen an den Apple Push Notification Service (APNS) und Microsoft Push Notification Service (MPNS) zu unterstützen. Dieses Feature ist standardmäßig deaktiviert.</p></li>
<li><p>Verwenden Sie das <strong>Test-CsFederatedPartner</strong>-Cmdlet zum Testen der Verbundkonfiguration und das <strong>Test-CsMCXPushNotification</strong>-Cmdlet zum Testen von Pushbenachrichtigungen.</p>
<div>

> [!NOTE]
> Pushbenachrichtigungen werden für Lync 2010 Mobile-Clients auf Apple-Geräten und Windows Phone verwendet.<BR>Pushbenachrichtigungen sind nur für Lync 2013&nbsp;Mobile-Clients auf Windows Phone-Geräten erforderlich.


</div></li>
</ul></td>
<td><p>RtcUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-for-push-notifications.md">Konfigurieren von Pushbenachrichtigungen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren der Mobilitätsrichtlinie</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>Set-CsMobilityPolicy</strong> um Folgendes zu erlauben oder zu verweigern:</p>
<ul>
<li><p>Anruf über den Arbeitsplatz</p></li>
<li><p>IP-Audio und IP-Video</p></li>
<li><p>Erfordern von WLAN für IP-Audio und/oder IP-Video</p></li>
</ul></td>
<td><p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configuring-mobility-policy.md">Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

