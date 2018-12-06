---
title: DNS-Zusammenfassung - SIP-, XMPP-Partnerverbund und öffentliche Chatdienste
TOCTitle: DNS-Zusammenfassung - SIP-, XMPP-Partnerverbund und öffentliche Chatdienste
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49293381
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Zusammenfassung - SIP-, XMPP-Partnerverbund und öffentliche Chatdienste

 

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die zum Definieren eines Verbunds mit Office Communications Server- oder Lync Server-Partnern erforderlichen DNS (Domain Name System)-Datensätze werden dadurch bestimmt, ob Sie die automatische DNS-Erkennung Ihrer Domäne durch andere perspektivische Partner zulassen. Wenn Sie den SRV-Eintrag "\_sipfederationtls.\_tcp. *\<SIP-Domänenname\>*" veröffentlichen, können andere SIP-Verbunddomänen Ihren Partnerverbund “erkennen”. Welche Verbunddomänen mit Ihnen kommunizieren können, können Sie mithilfe der Einstellungen für zugelassene und blockierte Domänen in der Lync Server-Systemsteuerung oder durch Festlegen der Konfiguration für zugelassene oder blockierte Domänen mithilfe der Lync Server-Verwaltungsshell und der PowerShell-Cmdlets **Get**, **Set**, **New**, **Remove-CsAllowedDomain** und **-CsBlockedDomain** steuern. Zusätzliche Informationen zum Konfigurieren dieser Einstellungen und zur Verwendung der PowerShell-Cmdlets finden Sie am Ende dieses Themas unter **Verwandte Themen**.

In der Tabelle mit der Übersicht zu den DNS-Datensätzen sind die erforderlichen Einträge für einen offenen, also einen erkennbaren, Verbund aufgeführt. Wenn Sie die Verbunderkennung nicht implementieren möchten, können Sie sich gegen die Konfiguration des Datensatzes "\_sipfederationtls.\_tcp. *\<SIP-Domänenname\>*" entscheiden.


> [!IMPORTANT]
> Es gibt bestimmte Szenarien, in denen der SRV-Eintrag "_sipfederationtls._tcp. <EM>&lt;SIP-Domänenname&gt;</EM>" erforderlich ist, Sie jedoch keinen ermittelbaren Verbund einrichten möchten. Ein Beispiel dafür ist die Bereitstellung von Mobilität für Ihre Benutzer. Push Notification Clearing House (PNCH) für Mobilität ist ein bestimmter Verbundtyp, der für Microsoft Lync Mobile-Clients auf dem Apple&nbsp;iPhone oder iPad mit dem Lync 2010 Mobile-Client oder Windows&nbsp;Phone mit dem Lync 2010 Mobile- oder Lync 2013 Mobile-Client verwendet wird. Der SRV-Eintrag "_sipfederationtls._tcp. <EM>&lt;SIP-Domänenname&gt;</EM>" wird im Fall von Mobilität und Pushbenachrichtigung verwendet. Um dieses Problem zu umgehen und die Erkennbarkeit zu steuern, deaktivieren Sie zum Deaktivieren der Erkennung die Einstellung <STRONG>Partnerdomänenerkennung aktivieren</STRONG>.



Zum Konfigurieren von XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung erstellen Sie zwei DNS (Domain Name System)-Einträge auf einem externen DNS-Server der die Einträge in den Zugriffs-Edgedienst ihres Edgeserver oder Edgepool auflöst.

Beim Konfigurieren von DNS (Domain Name System) für öffentliche Chatdienste werden Sie feststellen, dass die Konfiguration, mit der externe Benutzer unterstützt werden, auch öffentliche Chatdienste unterstützt werden. Falls Sie Ihren Edgeserver oder Edgepool bereits konfiguriert haben, sollten Sie über die erforderlichen DNS-Einträge zur Unterstützung öffentlicher Chatdienste verfügen.

## DNS-Zusammenfassung - SIP-Partnerverbund


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Standort/TYP/Port</th>
<th>FQDN (Fully Qualified Domain Name, vollqualifizierter Domänenname)</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externes DNS/SRV/5061</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Externe Zugriffs-Edgedienst-Schnittstelle: Diese Schnittstelle ist für die automatische DNS-Suche Ihres Verbunds durch andere potenzielle Verbundpartner erforderlich und wird als “Zugelassene SIP-Domänen” bezeichnet (in Vorgängerversionen: erweiterter Verbund). Wiederholen Sie sie je nach Bedarf für alle SIP-Domänen mit Lync-fähigen Benutzern.</p>
<div>

> [!IMPORTANT]
> Dieser SRV-Eintrag ist für Mobilität und Push Notification Clearing House erforderlich. Erstellen und veröffentlichen Sie bei mehreren SIP-Domänen SRV-Einträge für alle Domänen mit Lync Mobile-Clients. Der Pushbenachrichtigungsdienst und der Apple-Pushbenachrichtigungsdienst funktionieren möglicherweise nicht wie erwartet, wenn kein expliziter SRV-Eintrag für alle von der Bereitstellung unterstützten SIP-Domänen vorliegt.


</div></td>
</tr>
</tbody>
</table>


## DNS-Zusammenfassung - XMPP (Extensible Messaging and Presence Protocol)


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Speicherort/Typ/Port</th>
<th>FQDN</th>
<th>IP-Adresse/FQDN-Hosteintrag</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externes DNS/SRV/5269</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Externe XMPP-Proxyschnittstelle im Zugriffs-Edgedienst oder Edgepool. Wiederholen Sie den Vorgang ggf. für alle internen SIP-Domänen mit für Lync aktivierten Benutzern, denen der Kontakt mit XMPP-Kontakten aufgrund der Konfiguration der externen Zugriffsrichtlinie durch eine globale Richtlinie, eine Standortrichtlinie für den Standort des Benutzers oder eine Benutzerrichtlinie für den für Lync aktivierten Benutzer erlaubt ist. Eine zulässige XMPP-Domäne muss auch in der XMPP-Verbundpartner-Richtlinie konfiguriert sein. Weitere Details finden Sie in den <strong>Siehe auch</strong>-Themen.</p></td>
</tr>
<tr class="even">
<td><p>Externes DNS/A</p></td>
<td><p>xmpp.contoso.com (Beispiel)</p></td>
<td><p>IP-Adresse des Zugriffs-Edgediensts auf Ihrem Edgeserver oder Edgepool, von dem der XMPP-Proxy gehostet wird</p></td>
<td><p>Verweist auf den Zugriffs-Edgedienst oder Edgepool, von dem der XMPP-Proxydienst gehostet wird. In der Regel verweist der von Ihnen erstellte SRV-Eintrag auf diesen Hosteintrag (A oder AAAA).</p></td>
</tr>
</tbody>
</table>


## DNS-Zusammenfassung – Verbindung mit öffentlichen Chatdiensten


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Speicherort/Typ/Port</th>
<th>FQDN/DNS-Eintrag</th>
<th>IP-Adresse/FQDN</th>
<th>Zugeordnet zu/Kommentar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Externes DNS/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Zugriffs-Edgedienst-Schnittstelle</p></td>
<td><p>Externe Zugriffs-Edgedienst-Schnittstelle (Contoso). Wiederholen Sie dies nach Bedarf für alle SIP-Domänen mit Lync-aktivierten Benutzern.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Aufgaben

[Einrichten eines XMPP-Partnerverbunds in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Konfigurieren von Pushbenachrichtigungen in Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
[Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  

#### Konzepte

[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Weitere Ressourcen

[Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

