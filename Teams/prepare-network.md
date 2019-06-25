---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
description: Hier erfahren Sie, wie Sie Ihr Microsoft Teams-Netzwerk vorbereiten und verwalten. Unter anderem erhalten Sie Informationen zu den Netzwerkanforderungen, den Bandbreitenanforderungen und zusätzlichen Überlegungen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d203aefa4ba6991fbe6cf6a2ac463f4649f2aaa9
ms.sourcegitcommit: a388aec386b1a72b44c24d5f189a8c1cd401f706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "35198421"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams


Microsoft Teams kombiniert drei Arten von Datenverkehr:

-   Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)

-   Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)

-   Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)

Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.

> [!NOTE]
> Besprechungen werden auf mobilen IOS-und Android-Geräten unterstützt. 

Damit Sie die optimale Nutzung von Echt Zeit Medien in Microsoft Teams erzielen können, muss Ihr Netzwerk die Netzwerkanforderungen für Office 365 erfüllen. Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Für die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) gelten die folgenden Empfehlungen.


|Wert  |Client zu Microsoft Edge  |Kundenedge zu Microsoft Edge  |
|:--- |:--- |:--- |
|**Latenz (eine Möglichkeit)**\*  |< 50 ms          |< 30 ms         |
|**Latenz (RTT oder Round-Trip-Zeit)**\* |< 100 ms   |< 60 ms |
|**Burstverlust von Paketen**    |< 10 % in einem Intervall von 200 ms         |< 1% in einem Intervall von 200 ms         |
|**Paketverlust**     |< 1% in einem Intervall von 15 s          |< 0,1% in einem Intervall von 15 s         |
|**Jitter zwischen der Ankunftszeit von Paketen**    |< 30 ms in einem Intervall von 15 s         |< 15 ms in einem Intervall von 15 s         |
|**Neuanordnung von Paketen**    |< 0,05 % Pakete in falscher Reihenfolge         |< 0,01% Pakete in falscher Reihenfolge         |

\*Bei den Metrikdaten für Latenzen wird davon ausgegangen, dass Ihre Unternehmenswebsite oder Ihre Websites und die Microsoft-Ränder auf demselben Kontinent sind.

Die Verbindung Ihres Firmenstandorts mit dem Microsoft-Netzwerk-Edge umfasst den Zugriff auf den First Hop-Netzwerkzugriff, der WLAN-oder eine andere drahtlose Technologie sein kann.

Die Netzwerk Leistungsziele gehen von der richtigen Bandbreiten-und/oder [QoS-Planung](QoS-in-Teams.md)aus. Anders ausgedrückt: die Anforderungen gelten direkt für Teams in Echtzeit-Mediendatenverkehr, wenn die Netzwerkverbindung unter einer Spitzenauslastung liegt.

Zum Testen beider Netzwerksegmente können Sie das [Tool Netzwerkbewertung](https://go.microsoft.com/fwlink/?linkid=855799)verwenden. Dieses Tool kann sowohl auf dem Client-PC direkt als auch auf einem PC bereitgestellt werden, der mit dem Kundennetzwerk-Edge verbunden ist. Das Tool enthält eine begrenzte Dokumentation, aber eine umfassendere Dokumentation rund um die Verwendung des Tools finden Sie hier: [Netzwerk Bereitschaftsbewertung](https://go.microsoft.com/fwlink/?linkid=855800). Wenn Sie diese Netzwerk Bereitschaftsbewertung ausführen, können Sie die Bereitschaft Ihres Netzwerks zur Ausführung von Echt Zeit Medienanwendungen wie Microsoft Teams überprüfen.

> [!NOTE]
> Hierbei handelt es sich um die gleiche Netzwerk Bereitschaftsbewertung, die für Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.


## <a name="bandwidth-requirements"></a>Bandbreitenanforderungen
Microsoft Teams bietet Ihnen optimale Audio-, Video-und Inhaltsfreigabe Funktionen unabhängig von ihren Netzwerkbedingungen. Mit Variablen Codecs können Medien in Umgebungen mit begrenzter Bandbreite mit minimalen Auswirkungen ausgehandelt werden. Wenn die Bandbreite jedoch kein Problem darstellt, können die Erfahrungen für die Qualität optimiert werden, einschließlich einer Videoauflösung von bis zu 1080p, bis zu 30 bps für Video-und 15bps für Inhalte und HiFi-Audio.

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

Um dieses Risiko zu verringern, stellen Sie sicher, dass den NAT-Pools angemessene öffentliche IP-Adressen zugewiesen sind, um die Port Erschöpfung zu verhindern. Die Port Erschöpfung führt zu internen Endbenutzern und Geräten, die Probleme beim Herstellen einer Verbindung mit den Office 365-Diensten verursachen. Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

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
