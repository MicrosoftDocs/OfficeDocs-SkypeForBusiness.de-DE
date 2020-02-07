---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Hier erfahren Sie, wie Sie Ihr Microsoft Teams-Netzwerk vorbereiten und verwalten. Unter anderem erhalten Sie Informationen zu den Netzwerkanforderungen, den Bandbreitenanforderungen und zusätzlichen Überlegungen.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d331a063feacbaea5cb510c316d2b27d982eb03
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834635"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams


Microsoft Teams kombiniert drei Arten von Datenverkehr:

-   Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)

-   Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)

-   Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)

Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.


Damit Sie die optimale Nutzung von Echt Zeit Medien in Microsoft Teams erzielen können, muss Ihr Netzwerk die Netzwerkanforderungen für Office 365 erfüllen. Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Bei den beiden Definitions Netz Segmenten (Client zu Microsoft Edge und Customer Edge to Microsoft Edge) sollten die folgenden Empfehlungen berücksichtigt werden.


|Wert  |Vom Client zum Edge von Microsoft  |Vom Kundenedge zum Edge von Microsoft  |
|:--- |:--- |:--- |
|**Latenz (unidirektional)** \*  |< 50ms          |< 30ms         |
|**Latenz (RTT oder Round-Trip-Zeit)**\* |< 100M   |< 60ms |
|**Burstverlust von Paketen**    |<10% während eines 200M-Intervalls         |<1% während eines 200M-Intervalls         |
|**Paketverlust**     |<1% in einem 15-minütigen Intervall          |<0,1% in einem 15-15-Intervall         |
|**Paket Inter-arrival Jitter**    |<30ms während eines 15-15-Intervalls         |<15ms während eines 15-15-Intervalls         |
|**Neuanordnung von Paketen**    |< 0,05 % Pakete in falscher Reihenfolge         |< 0,01 % Pakete in falscher Reihenfolge         |

\*Bei den Metrikdaten für Latenzen wird davon ausgegangen, dass Ihre Unternehmenswebsite oder Ihre Websites und die Microsoft-Ränder auf demselben Kontinent sind.

Die Verbindung Ihres Firmenstandorts mit dem Microsoft-Netzwerk-Edge umfasst den Zugriff auf den First Hop-Netzwerkzugriff, der WLAN-oder eine andere drahtlose Technologie sein kann.

Die Netzwerk Leistungsziele gehen von der richtigen Bandbreiten-und/oder [QoS-Planung](QoS-in-Teams.md)aus. Anders ausgedrückt: die Anforderungen gelten direkt für Teams in Echtzeit-Mediendatenverkehr, wenn die Netzwerkverbindung unter einer Spitzenauslastung liegt.

Weitere Hilfe zur Vorbereitung Ihres Netzwerks für Teams finden Sie unter [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).


## <a name="bandwidth-requirements"></a>Bandbreitenanforderungen
Microsoft Teams bietet unabhängig von Ihren Netzwerkbedingungen optimale Funktionen für Audio, Video und Inhaltsfreigabe. Mit variablen Codecs können Medien in Umgebungen mit eingeschränkter Bandbreite mit minimalen Auswirkungen ausgehandelt werden. Wenn hingegen die Bandbreite kein Problem darstellt, kann die Benutzererfahrung qualitativ optimiert werden, bis hin zu einer Videoauflösung von 1080p, 30 fps für Video und 15fps für Inhalte sowie HiFi-Audio.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>Zusätzliche Netzwerküberlegungen
---------------

#### <a name="external-name-resolution"></a>Auflösung externer Namen

Stellen Sie sicher, dass alle Clientcomputer, auf denen der Team Client ausgeführt wird, externe DNS-Abfragen beheben können, um die von Office 365 bereitgestellten Dienste zu ermitteln, und dass ihre Firewalls keinen Zugriff verhindern. Informationen zum Konfigurieren von Firewall-Ports finden Sie unter [Office 365-URLs und IP-Bereiche](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Größe des NAT-Pools

Wenn mehrere Benutzer/Geräte über die Netzwerkadressübersetzung (NAT) oder die Port Address Translation (Pat) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter jeder öffentlich routingfähigen IP-Adresse verborgenen Geräte die unterstützte Nummer nicht überschreiten.

Um dieses Risiko zu verringern, stellen Sie sicher, dass den NAT-Pools angemessene öffentliche IP-Adressen zugewiesen sind, um die Port Erschöpfung zu verhindern. Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten. Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Leitfaden zur Intrusionserkennung und-Prävention**

Wenn in Ihrer Umgebung ein Intrusion Detection-und/oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt wird, stellen Sie sicher, dass alle Datenverkehr mit Ziel-zu-Office-365-URLs in der Whitelist aufgeführt sind.

<a name="network-health-determination"></a>Netzwerk Integritäts Bestimmung
-----------------

Bei der Planung der Implementierung von Microsoft Teams in Ihrem Netzwerk müssen Sie sicherstellen, dass Sie über die erforderliche Bandbreite verfügen, Zugriff auf alle erforderlichen IP-Adressen haben, die richtigen Ports öffnen und die Leistungsanforderungen für echt Zeit Medien erfüllen. .

Wenn Sie wissen, dass Sie diese Kriterien nicht erfüllen, erhalten Ihre Endbenutzer keine optimale Erfahrung aus Teams aufgrund schlechter Qualität bei Anrufen und Besprechungen.

Wenn Sie diese Kriterien nicht erfüllen, ist es an der Zeit, das Projekt zu pausieren, um sicherzustellen, dass Sie die Kriterien erfüllen, bevor Sie fortfahren.


|  |  |  |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Entscheidungspunkt         |Haben Sie Ihre Netzwerkfunktionen zur Unterstützung von Echt Zeit Medien bewertet?<br></br>Wenn Ihr Netzwerk nicht richtig bewertet wurde oder Sie wissen, dass es keine Echt Zeit Medien unterstützt, können Sie die Video-und Bildschirmfreigabe Funktionen deaktivieren, um die Auswirkungen auf das Netzwerk und schlechte Teams zu verringern?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Nächste Schritte         |Netzwerkqualität unbekannt: führen Sie eine Netzwerk Bereitschaftsbewertung durch, um festzustellen, ob Ihr Netzwerk für echt Zeit Medien bereit ist.<br></br>Schlechte Netzwerkqualität: führen Sie die Schritte zur Netzwerk Sanierung durch, um eine geeignete Umgebung für hochwertige Echt Zeit Medien bereitzustellen.<br></br>Netzwerk zufrieden stellend: Stellen Sie sicher, dass alle IP-Adressen und Ports ordnungsgemäß verfügbar sind.           |

## <a name="related-topics"></a>Verwandte Themen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)
