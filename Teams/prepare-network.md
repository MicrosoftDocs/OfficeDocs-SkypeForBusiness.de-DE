---
title: Vorbereiten des Netzwerks Ihrer Organisation für Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Hier erfahren Sie, wie Sie das Netzwerk Ihrer Organisation für Microsoft Teams vorbereiten, einschließlich Netzwerkanforderungen, Netzwerkoptimierung und Bandbreitenanforderungen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 8c67d7f7006720849f4e14ecf7b22e65cdfa9d2f
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177560"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams 

## <a name="network-requirements"></a>Netzwerkanforderungen

Wenn Sie [Ihr Netzwerk bereits für Microsoft 365 oder Office 365 optimiert](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)haben, sind Sie wahrscheinlich bereit für Microsoft Teams. In jedem Fall-und besonders, wenn Sie Teams schnell als erste Microsoft 365-oder Office 365-Arbeitsauslastung zur Unterstützung von **Remotemitarbeitern** bereitstellen – überprüfen Sie die folgenden Punkte, bevor Sie mit dem Rollout von Teams beginnen:

1.  Verfügen alle Ihre Standorte über Internetzugriff (damit Sie eine Verbindung mit Microsoft 365 oder Office 365 herstellen können)? Stellen Sie mindestens zusätzlich zum normalen Webverkehr sicher, dass Sie die folgenden für alle Speicherorte für Medien in Microsoft Teams geöffnet haben:

    |  |  |
    |---------|---------|
    |Ports     |UDP-Ports <strong>3478</strong> bis <strong>3481</strong>        |
    |[IP-Adressen](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>und <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Wenn Sie mit Skype for Business (lokal oder Online) eine Föderation eingehen müssen, müssen Sie einige zusätzliche DNS-Einträge konfigurieren.
    >
    >|CNAME-Einträge/Hostname  |TTL  |Verweist auf die Adresse oder den Wert  |
    >|---------|---------|---------|
    >|SIP     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Verfügen Sie über eine verifizierte Domäne für Microsoft 365 oder Office 365 (beispielsweise contoso.com)?
    
    - Wenn Ihre Organisation Microsoft 365 oder Office 365 noch nicht ausgeführt hat, lesen Sie [Erste Schritte](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Wenn Ihre Organisation keine verifizierte Domäne für Microsoft 365 oder Office 365 hinzugefügt oder konfiguriert hat, lesen Sie die [FAQ zu Domains](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).

3.  Hat Ihre Organisation Exchange Online und SharePoint Online bereitgestellt?
    
    - Wenn Ihre Organisation nicht über Exchange Online verfügt, lesen Sie [verstehen, wie Exchange und Microsoft Teams interagieren](exchange-teams-interact.md).
    - Wenn Ihre Organisation nicht über SharePoint Online verfügt, lesen Sie Grund [Legendes zur Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](sharepoint-onedrive-interact.md).

Nachdem Sie überprüft haben, dass Sie diese Netzwerkanforderungen erfüllen, sind Sie möglicherweise bereit, [Teams zu Rollen](How-to-roll-out-teams.md). Wenn Sie ein großes multinationales Unternehmen sind oder wissen, dass Sie einige Netzwerkeinschränkungen haben, lesen Sie weiter, um zu erfahren, wie Sie Ihr Netzwerk für Teams bewerten und optimieren können.

> [!IMPORTANT]
> **Für Bildungseinrichtungen**: Wenn Ihre Organisation eine Bildungseinrichtung ist und Sie ein Student Information System (SIS) verwenden, [Stellen Sie School Data Sync bereit](https://docs.microsoft.com/schooldatasync/) , bevor Sie Teams Ausrollen.
>  
> **Lokale Skype for Business-Server**: Wenn in Ihrer Organisation lokales Skype for Business Server (oder lync Server) ausgeführt wird, müssen Sie [Azure AD Connect so konfigurieren](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) , dass Ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 synchronisiert wird.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Bewährte Methode: Überwachen Ihres Netzwerks mithilfe von CQD und anrufanalyse 

Verwenden Sie das Dashboard für die [Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md) , um Einblicke in die Qualität von Anrufen und Besprechungen in Teams zu erhalten. CQD kann Ihnen dabei helfen, Ihr Netzwerk zu optimieren, indem Sie die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit im Auge behält. CQD untersucht die aggregierte Telemetrie für eine ganze Organisation, in der allgemeine Muster sichtbar werden können, mit denen Sie Probleme erkennen und die Sanierung planen können. Darüber hinaus bietet CQD reichhaltige Metriken, die Einblicke in die Gesamtqualität, Zuverlässigkeit und Benutzerfreundlichkeit bieten. 

Sie verwenden [anrufanalyse](set-up-call-analytics.md) , um Anruf-und Besprechungs Probleme für einen einzelnen Benutzer zu untersuchen.

## <a name="network-optimization"></a>Netzwerkoptimierung

Die folgenden Aufgaben sind optional und werden für das Rollout von Teams nicht benötigt, besonders, wenn Sie ein kleines Unternehmen sind und bereits Microsoft 365 oder Office 365 eingeführt haben. Verwenden Sie diese Anleitung, um Ihre Netzwerk-und Teamleistung zu optimieren, oder wenn Sie wissen, dass Sie einige Netzwerkeinschränkungen haben.

Möglicherweise möchten Sie zusätzliche Netzwerkoptimierung durchführen, wenn:

  - Teams läuft langsam (Vielleichthaben Sie nicht genügend Bandbreite)
  - Anrufe fallen weiter (möglicherweise aufgrund von Firewall-oder Proxy-Blockern)
  - Anrufe sind statisch und ausgeschnitten, oder Stimmen klingen wie Roboter (könnten Jitter oder Paketverlust sein)

Eine ausführliche Erläuterung der Netzwerkoptimierung, einschließlich Anleitungen zum Identifizieren und Beheben von Netzwerkbeeinträchtigungen, finden Sie unter [Grundlagen der Netzwerkkonnektivität von Microsoft 365 und Office 365](https://aka.ms/pnc).

<table>
<thead>
<tr class="header">
<th><strong>Netzwerk Optimierungsaufgabe</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Netzwerk Planner</td>
<td><p>Informationen zum bewerten Ihres Netzwerks, einschließlich der Bandbreiten Berechnungen und Netzwerkanforderungen über die physischen Standorte Ihrer Organisation, finden Sie im <a href="https://docs.microsoft.com/microsoftteams/network-planner">Netzwerk Planner</a> -Tool im <a href="https://admin.teams.microsoft.com">Team Admin Center</a>. Wenn Sie Ihre Netzwerkdetails und die Verwendung von Teams angeben, berechnet der Netzwerk Planner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud-VoIP über die physischen Standorte Ihrer Organisation hinweg.</p>
<p>Ein Beispielszenario finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Verwenden von Network Planner – Beispielszenario</a>.</p></td>
</tr>
<tr class="even">
<td>Berater für Teams</td>
<td>Der <a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Berater für Teams</a> ist Teil des <a href="https://admin.teams.microsoft.com">Teams admin Centers</a>. Er analysiert Ihre Microsoft 365- oder Office 365-Umgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können.</td>
</tr>
<tr class="odd">
<td>Auflösung externer Namen</td>
<td>Stellen Sie sicher, dass auf allen Computern, auf denen der Client für Teams ausgeführt wird, externe DNS-Abfragen aufgelöst werden können, um die von Microsoft 365 oder Office 365 bereitgestellten Dienste zu ermitteln, und dass ihre Firewalls keinen Zugriff verhindern. Informationen zum Konfigurieren von Firewall-Ports finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 und Office 365-URLs und IP-Bereiche</a>.</td>
</tr>
<tr class="odd">
<td>Verwalten der Dauerhaftigkeit von Sitzungen</td>
<td>Stellen Sie sicher, dass Ihre Firewall die zugeordneten NAT-Adressen (Network Address Translation) oder Ports für UDP nicht ändert.</td>
</tr><tr class="odd">
<td>Überprüfen der Größe des NAT-Pools</td>
<td>Überprüfen Sie die für die Benutzerkonnektivität erforderliche NAT-Poolgröße (Network Address Translation). Wenn mehrere Benutzer und Geräte mit der <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">Netzwerkadressübersetzung (NAT) oder der Port Address Translation (Pat)</a>auf Microsoft 365 oder Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingfähigen IP-Adresse verborgenen Geräte die unterstützte Nummer nicht überschreiten. Stellen Sie sicher, dass den NAT-Pools adäquate öffentliche IP-Adressen zugewiesen sind, um die Port Erschöpfung zu verhindern. Die Port Erschöpfung trägt dazu bei, dass interne Benutzer und Geräte nicht mit dem Microsoft 365-oder Office 365-Dienst verbunden werden können.</td>
</tr>
<tr class="even">
<td>Weiterleiten an Microsoft-Rechenzentren</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implementieren des effizientesten Routings an Microsoft-Rechenzentren</a> Ermitteln Sie Standorte, die lokale oder regionale Ausgangspunkte verwenden können, um die Verbindung mit dem Microsoft-Netzwerk so effizient wie möglich herzustellen.</td>
</tr>
<tr class="odd">
<td>Leitfaden zur Intrusionserkennung und-Prävention</td>
<td>Wenn in Ihrer Umgebung ein <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> -oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt wird, stellen Sie sicher, dass alle Microsoft 365-oder Office 365-URLs zugelassen sind.</td>
</tr>
<tr class="even">
<td>Konfigurieren des Split-Tunnel-VPN</td>
<td><p>Wir empfehlen, dass Sie einen alternativen Pfad für Teams-Datenverkehr bereitstellen, der das VPN (virtuelles privates Netzwerk) umgeht, das gemeinhin als <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">Split-Tunnel-VPN</a>bezeichnet wird. Split-Tunneling bedeutet, dass der Datenverkehr für Microsoft 365 oder Office 365 nicht über das VPN geht, sondern direkt zu Microsoft 365 oder Office 365 führt. Das umgehen Ihres VPNs hat eine positive Auswirkung auf die Qualität von Teams und verringert die Auslastung von VPN-Geräten und dem Netzwerk der Organisation. Wenn Sie ein VPN mit geteilten Tunneln implementieren möchten, arbeiten Sie mit Ihrem VPN-Anbieter zusammen.</p>
<p>Weitere Gründe, warum wir empfehlen, das VPN zu umgehen:
<ul>
<li><p>VPNs sind in der Regel nicht für die Unterstützung von Echt Zeit Medien konzipiert oder konfiguriert.</p></li> 
<li><p>Einige VPNs unterstützen möglicherweise auch keine UDP (Dies ist für Teams erforderlich).</p></li> 
<li><p>VPNs führen auch eine zusätzliche Verschlüsselungsschicht über den bereits verschlüsselten Mediendatenverkehr ein.</p></li> 
<li><p>Die Konnektivität zu Teams ist möglicherweise aufgrund des Haar befestigenden Datenverkehrs über ein VPN-Gerät nicht effizient.</p></li></td>
</tr>
<tr class="odd">
<td>Implementieren von QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Verwenden Sie Quality of Service (QoS)</a> , um die Paket Priorisierung zu konfigurieren. Dadurch wird die Anrufqualität in Teams verbessert, und Sie können die Anrufqualität überwachen und beheben. QoS sollte in allen Segmenten eines verwalteten Netzwerks implementiert werden. Auch wenn ein Netzwerk ausreichend für die Bandbreite bereitgestellt wurde, bietet QoS Risikominderung bei unvorhergesehenen Netzwerkereignissen. Mit QoS wird der VoIP-Datenverkehr priorisiert, damit sich diese unvorhergesehenen Ereignisse nicht negativ auf die Qualität auswirken.</td>
</tr>
<tr class="even">
<td>WLAN optimieren</td>
<td><p>Ähnlich wie bei VPN sind WLAN-Netzwerke nicht unbedingt so konzipiert oder konfiguriert, dass Sie Echt Zeit Medien unterstützen. Die Planung oder Optimierung eines WLAN-Netzwerks zur Unterstützung von Teams ist eine wichtige Überlegung für eine hochwertige Bereitstellung. Berücksichtigen Sie die folgenden Faktoren:</p>
<ul>
<li><p>Implementieren Sie QoS oder WLAN-Multimedia (WMM), um sicherzustellen, dass der Medien Verkehr in Ihren WLAN-Netzwerken entsprechend priorisiert wird.</p></li>
<li><p>Planen und optimieren Sie die WLAN-Bänder und die Position des Zugriffspunkts. Der 2,4-GHz-Bereich bietet zwar möglicherweise je nach Platzierung des Zugriffspunkts eine angemessene Qualität, Zugriffspunkte werden jedoch oft durch andere Heimanwendergeräte beeinflusst, die im gleichen Bereich betrieben werden. Der 5-GHz-Bereich ist aufgrund seines dichten Bereichs besser für echt Zeit Medien geeignet, erfordert aber mehr Zugriffspunkte, um genügend Deckung zu erhalten. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.</p></li>
<li><p>Wenn Sie Dual-Band-WLAN-Netzwerke verwenden, sollten Sie die Implementierung von Bandsteuerungen in Frage stellen. <em>Band Lenkung</em> ist eine Technik, die von WLAN-Anbietern implementiert wird, um die Nutzung des 5-GHz-Bereichs für Dual-Band-Clients zu beeinflussen.</p></li>
<li><p>Wenn Zugriffspunkte desselben Kanals zu eng zusammen sind, können Sie zu einer Signal Überlappung führen und unbeabsichtigt konkurrieren, was zu einem schlechten Nutzererlebnis führt. Stellen Sie sicher, dass sich die benachbarten Zugriffspunkte auf Kanälen befinden, die sich nicht überlappen.</p></li>
</ul>
<p>Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Wenden Sie sich an Ihren WLAN-Anbieter, um spezifische Anleitungen zu erhalten.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Bandbreitenanforderungen

Teams ist so konzipiert, dass Sie die beste Audio-, Video-und Inhaltsfreigabe unabhängig von ihren Netzwerkbedingungen erhalten. Wenn die Bandbreite jedoch unzureichend ist, priorisiert Teams die Audioqualität über die Videoqualität.

Wenn die Bandbreite *nicht* begrenzt ist, optimiert Teams die Medienqualität, einschließlich bis zu 1080p-Videoauflösung, bis zu 30 bps für Video-und 15bps für Inhalte und HiFi-Audio. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Verwandte Themen

[Grundlagen von Microsoft 365 und Office 365-Netzwerkkonnektivität](https://aka.ms/pnc)

[Weltweite Endpunkte: Skype for Business Online und Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Proxy Server für Teams](proxy-servers-for-skype-for-business-online.md)

[Medien in Teams: Warum Besprechungen einfach sind](https://aka.ms/teams-media)

[Medien in Teams: tief in die Medienströme eintauchen](https://aka.ms/teams-media-flows)

[Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md)

[Bereitstellen von Teams](How-to-roll-out-teams.md)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
