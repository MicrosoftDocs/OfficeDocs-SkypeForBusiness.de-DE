---
title: Vorbereiten des Netzwerks Ihres Unternehmens für Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Erfahren Sie, wie Sie das Netzwerk Ihres Unternehmens für Microsoft Teams vorbereiten, einschließlich Netzwerkanforderungen, Netzwerkoptimierung und Bandbreitenanforderungen.
localization_priority: Priority
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
ms.openlocfilehash: 282a6646c321d14618b9aaede36918db8db58c774d7bd99ff79f15cac729f83e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312693"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihres Unternehmens für Microsoft Teams 

## <a name="network-requirements"></a>Netzwerkanforderungen

Wenn Sie [Ihr Netzwerk bereits für Microsoft 365 oder Office 365 optimiert haben](/Office365/Enterprise/assessing-network-connectivity), dann sind Sie wahrscheinlich bereit für Microsoft Teams. In jedem Fall – und besonders, wenn Sie Teams schnell als Ihren ersten Microsoft 365- oder Office 365-Workload zur Unterstützung von **Remotemitarbeitern** einführen – müssen Sie Folgendes überprüfen, bevor Sie mit der Einführung von Teams beginnen:

1.  Haben alle Ihre Standorte Internetzugriff (damit Sie sich zu Microsoft 365 oder Office 365 verbinden können)? Stellen Sie zusätzlich zum normalen Webdatenverkehr sicher, dass Sie die TCP-Ports und IP-Adressen geöffnet haben, die für Teams in [URLs und IP-Adressbereiche für Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)aufgeführt sind.

    > [!IMPORTANT]
    > Wenn Sie lokal oder online mit Skype for Business einen Verbund erstellen müssen, dann müssen Sie einen zusätzlichen DNS-Eintrag konfigurieren.
    >
    >|DNS-Eintrag  |Dienst  |Protocol  |Priority  |Gewichtung  |Port  |Target  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |1     |5061     |sipfed.online.lync.com     |
    
2.  Haben Sie eine verifizierte Domäne für Microsoft 365 oder Office 365 (z. B. contoso.com)?
    
    - Wenn Ihre Organisation Microsoft 365 oder Office 365 noch nicht eingeführt hat, finden Sie weitere Informationen unter [Erste Schritte](/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Wenn Ihre Organisation noch keine verifizierte Domäne für Microsoft 365 oder Office 365 hinzugefügt oder konfiguriert hat, finden Sie weitere Informationen unter [Domänen – Häufig gestellte Fragen](/microsoft-365/admin/setup/domains-faq).

3.  Hat Ihre Organisation Exchange Online oder SharePoint Online bereitgestellt?
    
    - Wenn Ihre Organisation Exchange Online nicht implementiert hat, finden Sie weitere Informationen unter [Verstehen, wie Exchange und Microsoft Teams interagieren](exchange-teams-interact.md).
    - Wenn Ihre Organisation SharePoint Online nicht implementiert hat, finden Sie weitere Informationen unter [Verstehen, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren](sharepoint-onedrive-interact.md).

Sobald Sie überprüft haben, dass Sie diese Netzwerkvoraussetzungen erfüllen, sind Sie wahrscheinlich bereit für die [Einführung von Teams](./deploy-overview.md). Wenn Sie ein großes multinationales Unternehmen sind, oder wenn Sie wissen, dass Sie einige Netzwerkbeschränkungen haben, lesen Sie weiter, um zu erfahren, wie Sie Ihr Netzwerk für Teams bewerten und optimieren können.

> [!IMPORTANT]
> **Für Bildungseinrichtungen**: Wenn Ihre Organisation eine Bildungseinrichtung ist und Sie ein Schülerinformationssystem (Student Information System, SIS) verwenden, [stellen Sie School Data Sync bereit](/schooldatasync/), bevor Sie Teams einführen.
>  
> **Auf einem lokalen Skype for Business Server ausführen**: Wenn Ihre Organisation einen lokalen Skype for Business-Server (oder Lync-Server) verwendet, müssen Sie [Azure AD Connect konfigurieren](/skypeforbusiness/hybrid/configure-azure-ad-connect), um Ihr lokales Verzeichnis mit Microsoft 365 oder Office 365 zu synchronisieren.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Bewährte Methoden: Überwachen Sie Ihr Netzwerk mit dem AQD und Anrufanalysen 

Verwenden Sie das [Anrufqualitäts-Dashboard (AQD)](turning-on-and-using-call-quality-dashboard.md), um Erkenntnisse in die Qualität von Anrufen und Besprechungen in Teams zu erhalten. Das AQD kann Ihnen helfen, Ihr Netzwerk zu optimieren, indem es die Qualität, die Verlässlichkeit und die Benutzerfreundlichkeit genau im Auge behält. Das AQD befasst sich mit der aggregierten Telemetrie eines ganzen Unternehmens, in der sich allgemeine Muster erkennen lassen, die Sie in die Lage versetzen, Probleme zu erkennen und Behebungsmaßnahmen zu planen. Das AQD bietet zusätzlich umfangreiche Metrikberichte, die Einblicke in die Qualität, Zuverlässigkeit und Benutzerfreundlichkeit bieten. 

Sie werden [Anrufanalysen](set-up-call-analytics.md) verwenden, um Probleme eines einzelnen Benutzers mit Anrufen und Besprechungen zu untersuchen.

## <a name="network-optimization"></a>Netzwerkoptimierung

Die folgenden Aufgaben sind optional und für die Einführung von Teams nicht erforderlich, insbesondere wenn Sie ein kleines Unternehmen sind und bereits Microsoft 365 oder Office 365 eingeführt haben. Verwenden Sie diese Anleitung, um die Leistung Ihres Netzwerks und von Teams zu optimieren oder wenn Sie wissen, dass Sie einige Netzwerkbeschränkungen haben.

Sie werden weitere Netzwerk-Optimierungen durchführen wollen, wenn:

  - Teams langsam läuft (vielleicht haben Sie ungenügende Bandbreite)
  - Anrufen verloren gehen (möglicherweise aufgrund Firewall- oder Proxy-Sperren)
  - Anrufe Störungen haben und unterbrochen werden, oder wenn die Stimmen wie Roboter klingen (kann Jitter oder Paketverlust sein).

Eine ausführliche Beschreibung der Netzwerkoptimierung, einschließlich Anleitungen zum Erkennen und Beheben von Netzwerkbeeinträchtigungen, finden Sie unter[ Microsoft 365- und Office 365-Netzwerkverbindungsprinzipien](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

<table>
<thead>
<tr class="header">
<th>Netzwerkoptimierungsaufgabe</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Netzwerkplaner</td>
<td><p>Hilfe bei der Bewertung Ihres Netzwerks, einschließlich Bandbreitenberechnungen und Netzwerkanforderungen über die physischen Standorten Ihrer Organisation hinweg, erhalten Sie mit dem <a href="/microsoftteams/network-planner">Netzwerkplaner</a>-Tool im <a href="https://admin.teams.microsoft.com">Teams Admin Center</a>. Wenn Sie Ihre Netzwerkdetails und die Teams-Nutzung angeben, berechnet der Netzwerkplaner Ihre Netzwerkanforderungen für die Bereitstellung von Teams und Cloud Voice über die physischen Standorte Ihrer Organisation hinweg.</p>
<p>Ein Beispielszenario finden Sie unter <a href="/microsoftteams/tutorial-network-planner-example">Netzwerkplaner verwenden – Beispielszenario</a>.</p></td>
</tr>
<tr class="even">
<td>Advisor für Teams</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor für Teams</a> ist Teil des <a href="https://admin.teams.microsoft.com">Teams Admin Center</a>. Er analysiert Ihre Microsoft 365- oder Office 365-Umgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können.</td>
</tr>
<tr class="odd">
<td>Externe Namensauflösung</td>
<td>Stellen Sie sicher, dass Computer, auf denen der Teams-Client ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Microsoft 365 oder Office 365 bereitgestellten Dienste zu ermitteln, und dass Ihre Firewalls diesen Zugriff nicht verhindern. Informationen über das Konfigurieren von Firewall-Ports finden Sie unter <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365- und Office 365-URLs und IP-Bereiche</a>.</td>
</tr>
<tr class="odd">
<td>Sitzungspersistenz beibehalten</td>
<td>Stellen Sie sicher, dass Ihre Firewall die zugeordneten NAT-Adressen (Network Address Translation) oder Ports für UDP nicht ändert.</td>
</tr><tr class="odd">
<td>Validieren der NAT-Poolgröße</td>
<td>Validieren Sie die NAT (Network Address Translation)-Poolgröße, die für die Benutzerverbindung notwendig ist. Wenn mehrere Benutzer und Geräte mit <a href="/office365/enterprise/nat-support-with-office-365">NAT (Network Address Translation) oder PAT (Port Address Translation)</a> auf Microsoft 365 oder Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingfähigen IP-Adresse verborgenen Geräte die unterstützte Anzahl nicht überschreiten. Stellen Sie sicher, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um die Portausschöpfung zu verhindern. Die Portausschöpfung wird dazu beitragen, dass interne Benutzer und Geräte nicht mehr zu den Microsoft 365- und Office 365-Diensten verbinden können.</td>
</tr>
<tr class="even">
<td>Routing zu Microsoft-Rechenzentren</td>
<td><a href="/office365/enterprise/client-connectivity">Implementieren Sie das effizienteste Routing zu Microsoft-Rechenzentren</a>. Identifizieren Sie Standorte, die lokale oder regionale Ausgangspunkte verwenden können, um eine möglichst effiziente Verbindung zum Microsoft-Netzwerk herzustellen.</td>
</tr>
<tr class="odd">
<td>Anleitung zur Angriffserkennung und zum Eindringschutz</td>
<td>Wenn in Ihrer Umgebung ein System zur <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Angriffserkennung</a> oder zum Eindringschutz (IDS/IPS) als zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt ist, stellen Sie sicher, dass Microsoft 365- und Office 365-URLs zugelassen sind.</td>
</tr>
<tr class="even">
<td>Konfigurieren eines VPNs mit geteiltem Tunnel</td>
<td><p>Wir empfehlen, dass Sie einen alternativen Pfad für den Teams-Datenverkehr angeben, der das virtuelle private Netzwerk (VPN) umgeht, was allgemein als <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN mit geteiltem Tunnel</a> bezeichnet wird. „Geteilter Tunnel“ bedeutet, dass Datenverkehr von Microsoft 365 oder Office 365 nicht durch den VPN läuft, sondern direkt zu Microsoft 365 oder Office 365. Das Umgehen Ihres VPN wird einen positiven Einfluss auf die Teams-Qualität haben, und die Last für die VPN-Geräte und das Netzwerk der Organisation verringern. Wenn Sie ein VPN mit geteiltem Tunnel implementieren möchten, arbeiten Sie mit Ihrem VPN-Anbieter zusammen.</p>
<p>Andere Gründe, warum wie die Umgehung des VPN empfehlen:
<ul>
<li><p>VPNs werden in der Regel nicht für die Unterstützung von Echtzeitmedien entworfen oder konfiguriert.</p></li> 
<li><p>Einige VPNs unterstützen möglicherweise auch kein UDP (was für Teams notwendig ist).</p></li> 
<li><p>Außerdem entsteht durch VPNs eine zusätzliche Verschlüsselungsebene über den bereits verschlüsselten Mediendatenverkehr hinaus.</p></li> 
<li><p>Die Verbindung zu Teams ist möglicherweise nicht effizient, weil das VPN-Gerät ein Nadelöhr für den Datenverkehr darstellt.</p></li></td>
</tr>
<tr class="odd">
<td>Implementieren von QoS</td>
<td><a href="/microsoftteams/qos-in-teams">Verwenden Sie Dienstqualität (Quality of Service, QoS)</a>, um die Paketpriorisierung zu konfigurieren. Dies wird die Anrufqualität in Teams verbessern und bei der Überwachung und Problembehandlung der Anrufqualität helfen. QoS sollte in allen Segmenten des verwalteten Netzwerks implementiert werden. Selbst wenn ein Netzwerk ausreichend mit Bandbreite versorgt wurde, bietet QoS eine Risikominderung im Falle von unvorhergesehenen Netzwerkereignissen. Mit QoS wird Sprachdatenverkehr priorisiert, sodass sich diese unvorhergesehenen Ereignisse nicht negativ auf die Qualität auswirken.</td>
</tr>
<tr class="even">
<td>Optimieren von WLAN</td>
<td><p>Ähnlich wie VPNs werden auch WLAN-Netzwerke nicht zwangsläufig für die Unterstützung von Echtzeitmedien entworfen oder konfiguriert. Die Planung oder Optimierung eines WLAN-Netzwerks zur Unterstützung von Teams ist für eine qualitativ hochstehende Bereitstellung eine wichtige Überlegung. Die folgenden Faktoren sollten Sie in Ihrem Plan berücksichtigen:</p>
<ul>
<li><p>Implementieren Sie QoS oder WLAN-Multimedia (WMM), um sicherzustellen, dass Mediendatenverkehr über Ihre WLAN-Netzwerken angemessen priorisiert wird.</p></li>
<li><p>Planen und optimieren Sie die WLAN-Bänder und die Platzierung der Zugriffspunkte. Der 2,4-GHz-Bereich bietet zwar möglicherweise je nach Platzierung des Zugriffspunkts eine angemessene Qualität, Zugriffspunkte werden jedoch oft durch andere Heimanwendergeräte beeinflusst, die im gleichen Bereich betrieben werden. Der 5-GHz-Bereich ist aufgrund seines dichten Bereichs besser für Echtzeitmedien geeignet, erfordert jedoch mehr Zugriffspunkte, um eine ausreichende Abdeckung zu erzielen. Außerdem müssen die Endpunkte diesen Bereich unterstützen und so konfiguriert sein, dass sie diese Bänder entsprechend nutzen.</p></li>
<li><p>Wenn Sie Dualband-WLAN-Netzwerke verwenden, ziehen Sie die Implementierung von Band-Steering in Betracht. Das <em>Band-Steering</em> ist eine Technik, die von WLAN-Anbietern implementiert wird, um Dualband-Kunden zur Verwendung des 5-GHz-Bereichs zu veranlassen.</p></li>
<li><p>Wenn Zugriffspunkte im gleichen Kanal zu nah beieinander positioniert sind, können sie Signalüberlappung verursachen und unbeabsichtigt in Wettstreit miteinander treten. Dies führt zu einer mangelhaften Benutzererfahrung. Stellen Sie sicher, dass Zugriffspunkte, die sich nah beieinander befinden, Kanäle verwenden, die sich nicht überlappen.</p></li>
</ul>
<p>Jeder WLAN-Anbieter hat seine eigenen Empfehlungen für die Bereitstellung seiner WLAN-Lösung. Besprechen Sie sich mit Ihrem WLAN-Anbieter für spezifische Anleitungen.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Bandbreitenanforderungen

Teams wurde dafür entwickelt, Ihnen unabhängig von Ihren Netzwerkbedingungen optimale Erfahrungen für Audio, Video und Inhaltsfreigabe zu geben. Dies bedeutet, dass Teams bei ungenügender Bandbreite die Audioqualität gegenüber der Videoqualität priorisiert.

Wenn die Bandbreite nicht begrenzt ist, wird Teams die Medienqualität optimieren, bis hin zu einer Videoauflösung von 1080 Pixel, 30 Bilder pro Sekunde (Frames per Second, FPS) für Video und für Inhalte.

In dieser Tabelle wird veranschaulicht, wie Teams Bandbreite nutzt. Microsoft Teams verhält sich hinsichtlich der Bandbreitennutzung immer konservativ und kann in weniger als 1,5 MBit/s High-Definition-Videoqualität bereitstellen. Die tatsächliche Bandbreitennutzung in den einzelnen Audio/Video-Anrufen oder Besprechungen variiert abhängig von verschiedenen Faktoren, z. B. Videolayout, Videoauflösung und Videoframes pro Sekunde. Wenn mehr Bandbreite verfügbar ist, werden Qualität und Nutzung erhöht, um die besten Ergebnisse zu erzielen.

:::row:::
   :::column span="":::
      **Modalität**
   :::column-end:::
   :::column span="3":::
      **Erforderliche Bandbreite (Bitrate KB/s hoch/ herunter)**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **Minimum**
   :::column-end:::
   :::column span="":::
      **Empfohlen**
   :::column-end:::
   :::column span="":::
      **Bietet optimale Leistung**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Audio**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        1:1-Beziehung
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Besprechungen
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Video**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        1:1-Beziehung
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1 500/1 500
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Besprechungen
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2 500/4 000
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Bildschirmfreigabe**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        1:1-Beziehung
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1 500/1 500
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Besprechungen
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2 500/2 500
   :::column-end:::
   :::column span="":::
        4 000/4 000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Zusammen-Modus**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        1:1-Beziehung
   :::column-end:::
   :::column span="":::
        Nicht zutreffend
   :::column-end:::
   :::column span="":::
        Nicht zutreffend
   :::column-end:::
   :::column span="":::
        Nicht zutreffend
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Besprechungen
   :::column-end:::
   :::column span="":::
        1 000/1 500
   :::column-end:::
   :::column span="":::
        1 500/2 500
   :::column-end:::
   :::column span="":::
        2 500/4 000
   :::column-end:::
:::row-end:::

Die **minimalen**, **empfohlenen** und **besten** Bandbreitenanforderungen basieren auf der Nutzung pro Endpunkt. In der Regel gibt es einen Endpunkt pro Benutzer, z. B. einen Computer oder ein mobiles Gerät. Wenn ein Benutzer jedoch *sowohl* auf einem Computer *als auch* auf einem mobilen Gerät an einer Teams-Besprechung teilnimmt, sind diesem Benutzer zwei Endpunkte zugeordnet.

- **Mindestanforderungen an die** Bandbreite für Videoanrufe sind eine Auflösung von bis zu 240p, bildbasierte Bildfrequenzen für Bildschirmfreigabeinhalte von 1,875 bis 7,5 fps und Video im Zusammen-Modus/Große Galerie mit einer Auflösung von bis zu 540p.  

- **Die empfohlenen Anforderungen an die** Bandbreite für Videoanrufe sind eine Auflösung von bis zu 1080p <sup>\*</sup>, bildbasierte Bildfrequenzen für Bildschirmfreigabeinhalte von 7,5 bis 30 fps und Video im Zusammen-Modus/Große Galerie mit einer Auflösung von bis zu 1080p <sup>\*</sup>.  

- **Die Anleitung für beste Leistung** ermöglicht Videos mit höherer Wiedergabetreue für Besprechungen mit mehreren Teilnehmern, Umgebungen mit hohen Verlusten und Inhalten mit höherer Bewegung, wobei die Bildwiederholrate von Bildschirmfreigabeinhalten auf 15 bis 30 fps angepasst werden kann.

<sup>\*</sup>Erwarten Sie eine Qualität von bis zu 1080p, aber je nach Netzwerkbedingungen werden die Videoauflösung und -qualität entsprechend optimiert.  

## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365- und Office 365-Netzwerkverbindungsprinzipien](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Weltweite Endpunkte: Skype for Business Online und Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Proxyserver für Teams](proxy-servers-for-skype-for-business-online.md)

[Medien in Teams: Warum Besprechungen einfach sind](https://aka.ms/teams-media)

[Medien in Teams: Vertiefte Einblicke in Medienflüsse](https://aka.ms/teams-media-flows)

[Identitätsmodelle und Authentifizierung in Teams](identify-models-authentication.md)

[Bereitstellen von Teams](./deploy-overview.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
