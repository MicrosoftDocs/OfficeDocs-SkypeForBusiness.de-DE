---
title: Vorbereiten des Netzwerks Ihrer Organisation für Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Erfahren Sie, wie Sie das Netzwerk Ihrer Organisation für Microsoft Teams vorbereiten, einschließlich Netzwerkanforderungen, Netzwerkoptimierung und Bandbreitenanforderungen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099572"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams 

## <a name="network-requirements"></a>Netzwerkanforderungen

Wenn Sie Ihr Netzwerk bereits für [Microsoft 365 oder Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)optimiert haben, sind Sie wahrscheinlich für Microsoft Teams bereit. Überprüfen Sie in jedem Fall – und insbesondere, wenn Sie Teams schnell als Ihre erste  Microsoft 365- oder Office 365-Arbeitsauslastung zur Unterstützung von Remotemitarbeitern verwenden – die folgenden Punkte, bevor Sie mit dem Rollout von Teams beginnen:

1.  Haben alle Ihre Standorte Internetzugriff (damit sie eine Verbindung mit Microsoft 365 oder Office 365 herstellen können)? Stellen Sie mindestens sicher, dass Sie zusätzlich zum normalen Webdatenverkehr für Medien in Teams für alle Speicherorte Folgendes geöffnet haben:

    |  |  |
    |---------|---------|
    |Ports     |UDP-Ports <strong>3478 bis</strong> <strong>3481</strong>        |
    |[IP-Adressen](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>und <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Wenn Sie eine Zusammenarbeit mit Skype for Business (lokal oder online) benötigen, müssen Sie einige zusätzliche DNS-Einträge konfigurieren.
    >
    >|CNAME Records/Host name  |TTL  |Verweist auf Adresse oder Wert  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Verfügen Sie über eine überprüfte Domäne für Microsoft 365 oder Office 365 (z. B. contoso.com)?
    
    - Wenn in Ihrer Organisation kein Microsoft 365- oder Office 365-Rollback ausgeführt wurde, lesen Sie ["Erste Schritte".](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - Wenn Ihre Organisation keine überprüfte Domäne für Microsoft 365 oder Office 365 hinzugefügt oder konfiguriert hat, lesen Sie die häufig gestellten Fragen zu [Domänen.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)

3.  Hat Ihre Organisation Exchange Online und SharePoint Online bereitgestellt?
    
    - Wenn Ihre Organisation nicht über Exchange Online verfügen, lesen Sie " Verstehen der [Interaktion zwischen Exchange und Microsoft Teams".](exchange-teams-interact.md)
    - Wenn Ihre Organisation nicht über SharePoint Online verfügen, erfahren Sie, wie SharePoint Online und [OneDrive for Business mit Microsoft Teams interagieren.](sharepoint-onedrive-interact.md)

Nachdem Sie überprüft haben, dass Sie diese Netzwerkanforderungen erfüllen, sind Sie möglicherweise bereit zum [Rollout von Teams.](How-to-roll-out-teams.md) Wenn Sie ein großes multinationales Unternehmen sind oder wissen, dass Sie einige Netzwerkeinschränkungen haben, lesen Sie weiter, um zu erfahren, wie Sie Ihr Netzwerk für Teams bewerten und optimieren können.

> [!IMPORTANT]
> **Für Bildungseinrichtungen:** Wenn Ihre Organisation eine Bildungseinrichtung ist und Sie ein Student Information System (SIS) verwenden, stellen Sie [School Data Sync](https://docs.microsoft.com/schooldatasync/) vor dem Rollout von Teams zur Verfügung.
>  
> Lokale Ausführung von **Skype for Business Server:** Wenn In Ihrer Organisation skype for Business Server (oder Lync Server) lokal ausgeführt wird, müssen Sie Azure AD [Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) so konfigurieren, dass Ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 synchronisiert wird.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Bewährte Methode: Überwachen Ihres Netzwerks mithilfe des AQD und der Anrufanalyse 

Verwenden Sie [das Anrufqualitätsdashboard,](turning-on-and-using-call-quality-dashboard.md) um einen Einblick in die Qualität von Anrufen und Besprechungen in Teams zu erhalten. Mit dem CQD können Sie Ihr Netzwerk optimieren, indem Qualität, Zuverlässigkeit und Benutzerfreundlichkeit im Auge behalten werden. Das CQD betrachtet die Aggregierte Telemetrie für eine gesamte Organisation, in der allgemeine Muster sichtbar werden können, mit denen Sie Probleme erkennen und eine Problembehebung planen können. Darüber hinaus bietet das CQD umfangreiche Metrikberichte, die Einen Einblick in die allgemeine Qualität, Zuverlässigkeit und Benutzererfahrung bieten. 

Sie verwenden [](set-up-call-analytics.md) die Anrufanalyse, um Anruf- und Besprechungsprobleme für einen einzelnen Benutzer zu untersuchen.

## <a name="network-optimization"></a>Netzwerkoptimierung

Die folgenden Aufgaben sind optional und für den Einstieg von Microsoft Teams nicht erforderlich, insbesondere, wenn Sie ein kleines Unternehmen sind und microsoft 365 oder Office 365 bereits als Roll out ausgeführt haben. Verwenden Sie diesen Leitfaden, um die Leistung Ihres Netzwerks und Ihrer Teams zu optimieren, oder wenn Sie wissen, dass einige Netzwerkeinschränkungen gelten.

Möglicherweise möchten Sie eine zusätzliche Netzwerkoptimierung durchführen, wenn:

  - Teams wird langsam ausgeführt (möglicherweise verfügen Sie über nicht genügend Bandbreite)
  - Anrufe fallen weiter ab (möglicherweise aufgrund von Firewalls oder Proxyblockern)
  - Anrufe sind statisch und ausgeschnitten, oder Stimmen klingen wie Nervos (kann Jitter oder Paketverlust sein)

Eine ausführliche Diskussion über die Netzwerkoptimierung, einschließlich Anleitungen zum Erkennen und Beheben von Netzwerkeinschränkungen, finden Sie unter ["Microsoft 365- und Office 365 Network Connectivity Principles".](https://aka.ms/pnc)

<table>
<thead>
<tr class="header">
<th><strong>Netzwerkoptimierungsaufgabe</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Netzwerkplaner</td>
<td><p>Hilfe bei der Bewertung Ihres Netzwerks, einschließlich Bandbreitenberechnungen und Netzwerkanforderungen an den physischen Standorten Ihrer Organisation, finden Sie im <a href="https://docs.microsoft.com/microsoftteams/network-planner">Teams</a> Admin Center im Netzwerkplaner-Tool. <a href="https://admin.teams.microsoft.com"></a> Wenn Sie Ihre Netzwerkdetails und die Nutzung von Teams bereitstellen, berechnet Network Planner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud Voice an den physischen Standorten Ihrer Organisation.</p>
<p>Ein Beispielszenario finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">"Verwenden von Network Planner – Beispielszenario".</a></p></td>
</tr>
<tr class="even">
<td>Berater für Teams</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Berater für Teams</a> ist Teil des <a href="https://admin.teams.microsoft.com">Teams Admin Centers.</a> Er analysiert Ihre Microsoft 365- oder Office 365-Umgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können.</td>
</tr>
<tr class="odd">
<td>Auflösung externer Namen</td>
<td>Stellen Sie sicher, dass alle Computer, auf denen der Teams-Client ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Microsoft 365 oder Office 365 bereitgestellten Dienste zu ermitteln, und dass Ihre Firewalls den Zugriff nicht verhindern. Informationen zum Konfigurieren von Firewallports finden Sie unter <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365- und Office 365-URLs und -IP-Bereiche.</a></td>
</tr>
<tr class="odd">
<td>Beibehalten der Sitzungs persistenz</td>
<td>Stellen Sie sicher, dass die Firewall die zugeordneten Netzwerkadressen (Network Address Translation, NAT) oder Ports für UDP nicht ändert.</td>
</tr><tr class="odd">
<td>Überprüfen der Größe des NAT-Pools</td>
<td>Überprüfen Sie die Für die Benutzerkonnektivität erforderliche Größe des Netzwerkadressenübersetzungspools (NAT). Wenn mehrere Benutzer und Geräte mit NAT <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">(Network Address Translation) oder Port Address Translation (PAT)</a>auf Microsoft 365 oder Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingbaren IP-Adresse verborgenen Geräte die unterstützte Zahl nicht überschreiten. Stellen Sie sicher, dass den NAT-Pools ausreichende öffentliche IP-Adressen zugewiesen sind, um eine Portausleitung zu verhindern. Die Portausleitung kann dazu beitragen, dass interne Benutzer und Geräte keine Verbindung mit dem Microsoft 365- oder Office 365-Dienst herstellen können.</td>
</tr>
<tr class="even">
<td>Routing an Die Rechenzentren von Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implementieren Sie das effizienteste Routing an Microsoft-Rechenzentren.</a> Identifizieren Sie Standorte, die lokale oder regionale Ausgangspunkte verwenden können, um eine möglichst effiziente Verbindung mit dem Microsoft-Netzwerk herzustellen.</td>
</tr>
<tr class="odd">
<td>Richtlinien zur Erkennung von Zugriffen und zur Verhinderung von Zugriffen</td>
<td>Wenn in Ihrer <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a> Umgebung ein Angriffserkennungs- oder -schutzsystem (IDS/IPS) für eine zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt ist, müssen Sie alle Microsoft 365- oder Office 365-URLs zulassen.</td>
</tr>
<tr class="even">
<td>Konfigurieren des VPN mit geteilten Tunneln</td>
<td><p>Es wird empfohlen, einen alternativen Pfad für den Datenverkehr in Teams zu erstellen, der das virtuelle private Netzwerk (VPN) umgeht, allgemein als VPN mit <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">geteilten Tunneln bezeichnet.</a> Ein geteilter Tunnel bedeutet, dass der Datenverkehr für Microsoft 365 oder Office 365 nicht über vpn läuft, sondern direkt zu Microsoft 365 oder Office 365. Die Umgehung Ihres VPN wirkt sich positiv auf die Qualität von Teams aus, und die Auslastung der VPN-Geräte und des Unternehmensnetzwerks wird reduziert. Um ein VPN mit geteilten Tunneln zu implementieren, arbeiten Sie mit Ihrem VPN-Anbieter zusammen.</p>
<p>Weitere Gründe für die Umgehung des VPN:
<ul>
<li><p>VPNs sind normalerweise nicht für die Unterstützung von Echtzeitmedien konzipiert oder konfiguriert.</p></li> 
<li><p>Einige VPNs unterstützen möglicherweise auch nicht UDP (dies ist für Teams erforderlich).</p></li> 
<li><p>VPNs führen außerdem zusätzlich zum bereits verschlüsselten Medienverkehr eine zusätzliche Verschlüsselungsebene ein.</p></li> 
<li><p>Die Konnektivität mit Teams ist aufgrund von hair-pinning-Datenverkehr über ein VPN-Gerät möglicherweise nicht effizient.</p></li></td>
</tr>
<tr class="odd">
<td>Implementieren von QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Verwenden Sie Quality of Service (QoS)</a> zum Konfigurieren der Paket priorisierung. Dies verbessert die Anrufqualität in Teams und hilft Ihnen bei der Überwachung und Problembehandlung der Anrufqualität. QoS sollte in allen Segmenten eines verwalteten Netzwerks implementiert werden. Auch wenn ein Netzwerk für die Bandbreite ausreichend bereitgestellt wurde, bietet QoS eine Risikoentschädung für den Fall unerwarteter Netzwerkereignisse. Bei QoS wird der Sprachdatenverkehr priorisiert, sodass sich diese unerwarteten Ereignisse nicht negativ auf die Qualität auswirken.</td>
</tr>
<tr class="even">
<td>WLAN optimieren</td>
<td><p>Ähnlich wie VPN sind WLAN-Netzwerke nicht unbedingt so konzipiert oder konfiguriert, dass sie Echtzeitmedien unterstützen. Die Planung oder Optimierung eines WLAN-Netzwerks zur Unterstützung von Teams ist ein wichtiger Aspekt für eine qualitativ hochwertige Bereitstellung. Berücksichtigen Sie die folgenden Faktoren:</p>
<ul>
<li><p>Implementieren Sie QoS oder WiFi Multimedia (WMM), um sicherzustellen, dass der Medienverkehr über Ihre WLAN-Netzwerke entsprechend priorisiert wird.</p></li>
<li><p>Planen und optimieren Sie die WLAN-Bänder und die Platzierung von Zugriffspunktn. Der 2,4-GHz-Bereich bietet zwar möglicherweise je nach Platzierung des Zugriffspunkts eine angemessene Qualität, Zugriffspunkte werden jedoch oft durch andere Heimanwendergeräte beeinflusst, die im gleichen Bereich betrieben werden. Der 5-GHz-Bereich eignet sich aufgrund des dichten Bereichs besser für Echtzeitmedien, benötigt jedoch mehr Zugriffspunkte, um ausreichend Schutz zu erhalten. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.</p></li>
<li><p>Wenn Sie Dual-Band-WLAN-Netzwerke verwenden, sollten Sie die Implementierung der Bandsteuerung in Betracht ziehen. <em>Die Bandsteuerung ist</em> eine Technik, die von WLAN-Anbietern implementiert wird, um die Verwendung des 5-GHz-Bereichs durch Dual-Band-Clients zu beeinflussen.</p></li>
<li><p>Wenn die Zugriffspunkte desselben Kanals zu nah beieinander liegen, können sie zu Signalüberlappungen und unbeabsichtigten Wettbewerben führen, was für den Benutzer zu einer schlechten Benutzererfahrung führt. Stellen Sie sicher, dass sich direkt daneben befindende Zugriffspunkte in Kanälen befinden, die sich nicht überlappen.</p></li>
</ul>
<p>Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Wenden Sie sich an Ihren WLAN-Anbieter, um spezifische Anleitungen zu erhalten.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Bandbreitenanforderungen

Teams wurde entwickelt, um unabhängig von ihren Netzwerkbedingungen die besten Audio-, Video- und Inhaltsfreigabeerfahrungen zu bieten. Wenn die Bandbreite jedoch nicht ausreicht, priorisiert Teams die Audioqualität vor der Videoqualität.

Wenn *die* Bandbreite nicht begrenzt ist, optimiert Teams die Medienqualität, einschließlich einer Videoauflösung von bis zu 1080p, bis zu 30fps für Video und 15fps für Inhalte und High-Fidelity-Audio. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Verwandte Themen

[Konnektivitätsprinzipien für Microsoft 365- und Office 365-Netzwerke](https://aka.ms/pnc)

[Weltweite Endpunkte: Skype for Business Online und Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Proxyserver für Teams](proxy-servers-for-skype-for-business-online.md)

[Medien in Teams: Warum Besprechungen einfach sind](https://aka.ms/teams-media)

[Medien in Teams: Tiefer Einblick in Medienflüsse](https://aka.ms/teams-media-flows)

[Identitätsmodelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md)

[Bereitstellen von Teams](How-to-roll-out-teams.md)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
