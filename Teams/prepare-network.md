---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: arachman
description: Hier erfahren Sie, wie Sie Ihr Microsoft Teams-Netzwerk vorbereiten und verwalten. Unter anderem erhalten Sie Informationen zu den Netzwerkanforderungen, den Bandbreitenanforderungen und zusätzlichen Überlegungen.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a470ddec93526fe5ea3aa5a24a835d37d971426c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892690"
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
=================================================

Microsoft Teams kombiniert drei Arten von Datenverkehr:

-   Datenverkehr zwischen der Office 365-Onlineumgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)

-   Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)

-   Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)

Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt in Peer-zu-Peer-Szenarien direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.

> [!IMPORTANT]
> Zurzeit werden Besprechungen auf mobilen Geräten unter iOS und Android unterstützt, aber nicht unter Windows Phone.

Für die optimale Verwendung von Echtzeitmedien in Microsoft Teams müssen die Netzwerkanforderungen für Office 365 erfüllt sein. Weitere Informationen finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität in Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Für die beiden definierenden Netzwerksegmente (Client zum Edge von Microsoft und Kundenedge zum Edge von Microsoft) gelten die folgenden Empfehlungen.


|Wert  |Client zu Microsoft Edge  |Kundenedge zu Microsoft Edge  |
|---------|---------|---------|
|**Latenz (ein Weg)**     |< 50 ms          |< 30 ms          |
|**Latenz (RTT oder Roundtripzeit)** |< 100 ms         |< 60 ms         |
|**Burstverlust von Paketen**    |< 10 % in einem Intervall von 200 ms         |< 1% in einem Intervall von 200 ms         |
|**Paketverlust**     |< 1% in einem Intervall von 15 s          |< 0,1% in einem Intervall von 15 s         |
|**Jitter zwischen der Ankunftszeit von Paketen**    |< 30 ms in einem Intervall von 15 s         |< 15 ms in einem Intervall von 15 s         |
|**Neuanordnung von Paketen**    |< 0,05 % Pakete in falscher Reihenfolge         |< 0,01% Pakete in falscher Reihenfolge         |

Um beide Netzwerksegmente zu testen, können Sie das [Network Assessment-Tool](https://go.microsoft.com/fwlink/?linkid=855799) verwenden. Dieses Tool kann direkt auf dem Client-PC sowie auf einem PC, der mit dem Netzwerkedge des Kunden verbunden ist, bereitgestellt werden. Das Tool selbst enthält eine begrenzte Dokumentation, eine umfassendere Dokumentation zur Verwendung des Tools finden Sie hier: [Bewertung der Netzwerkbereitschaft](https://go.microsoft.com/fwlink/?linkid=855800). Indem Sie diese Bewertung der Netzwerkbereitschaft ausführen, können Sie die Bereitschaft Ihres Netzwerks für die Ausführung von Echtzeitmedienanwendungen wie beispielsweise Microsoft Teams validieren.

> [!NOTE]
> Dabei handelt es sich um die gleiche Bewertung der Netzwerkbereitschaft, deren Ausführung Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.

<a name="bandwidth-requirements"></a>Bandbreitenanforderungen
----------

Bandbreitenberechnungen für Microsoft Teams sind komplex. Zu Ihrer Unterstützung wurde ein Rechner erstellt. Den Rechner finden Sie unter [„Network Planner“ in MyAdvisor](https://aka.ms/bwcalc/).

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

#### <a name="external-name-resolution"></a>**Externe Namensauflösung**

Stellen Sie sicher, dass alle Clientcomputer, auf denen Microsoft Teams ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Office 365 bereitgestellten Dienste zu ermitteln.

#### <a name="nat-pool-size"></a>**NAT-Poolgröße**

Wenn mehrere Benutzer/Geräte mit NAT (Network Address Translation, Netzwerkadressenübersetzung) oder PAT (Port Address Translation, Portadressenübersetzung) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter den einzelnen öffentlich routingfähigen IP-Adressen verborgenen Geräte nicht die unterstützte Anzahl überschreiten.

Verringern Sie dieses Risiko, indem Sie sicherstellen, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um Portauslastung zu verhindern. Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten. Weitere Informationen finden Sie unter [NAT-Unterstützung für Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Leitfaden zur Angriffserkennung und zum Eindringschutz**

Wenn in Ihrer Umgebung ein Angriffserkennungs- und/oder Eindringschutzsystem (Intrusion Detection System/Prevention System, IDS/IPS) als zusätzliche Sicherheitsstufe für ausgehende Verbindungen bereitgestellt ist, stellen Sie sicher, dass Datenverkehr, dessen Ziel Office 365-URLs sind, in der Whitelist enthalten ist.

<a name="network-health-determination"></a>Ermittlung der Netzwerkintegrität
-----------------

Beim Planen der Implementierung von Microsoft Teams in Ihrem Netzwerk müssen Sie sicherstellen, dass die erforderliche Bandbreite sowie Zugriff auf alle erforderlichen IP-Adressen verfügbar ist, dass die richtigen Ports geöffnet sind und dass die Leistungsanforderungen für Echtzeitmedien erfüllt sind.

Wenn Sie wissen, dass Sie diese Kriterien nicht erfüllen, können Ihre Endbenutzer Microsoft Teams aufgrund der schlechten Qualität bei Anrufen und Besprechungen nicht optimal nutzen.

Falls diese Kriterien nicht erfüllt sind, sollten Sie in Betracht ziehen, das Projekt zu pausieren, um die Erfüllung der Kriterien sicherzustellen, bevor Sie fortfahren.


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Entscheidungspunkt         |Haben Sie die Möglichkeiten für die Unterstützung von Echtzeitmedien in Ihrem Netzwerk bewertet?<br></br>Werden Sie, wenn das Netzwerk nicht ordnungsgemäß bewertet wurde oder Sie wissen, dass Echtzeitmedien nicht unterstützt werden, Video- und Bildschirmübertragungsfunktionen deaktivieren, um die Auswirkungen auf das Netzwerk und Beeinträchtigungen der Verwendung von Teams zu verringern?         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Nächste Schritte         |Netzwerkqualität unbekannt: Ermitteln Sie anhand des Leitfadens zur [Bewertung der Netzwerkbereitschaft](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness), ob Ihr Netzwerk für Echtzeitmedien bereit ist.<br></br>Netzwerkqualität schlecht: Führen Sie die Netzwerkwiederherstellungsschritte aus, um eine geeignete Umgebung für Echtzeitmedien von hoher Qualität bereitzustellen.<br></br>Netzwerk zufriedenstellend: Stellen Sie sicher, dass der Zugriff auf alle IP-Adressen und Ports ordnungsgemäß möglich ist.           |

