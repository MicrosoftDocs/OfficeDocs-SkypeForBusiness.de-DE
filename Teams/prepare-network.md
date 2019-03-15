---
title: Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 08/21/2018
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
ms.openlocfilehash: 57f8ffc7d5cedeb6117deffb99ad48ccbe17b48f
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640730"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams

> [!Tip]
> Sehen Sie sich die folgenden Sitzung erfahren, wie Sie Teams nutzt Ihr Netzwerk und am besten für die optimale Netzwerkkonnektivität planen: [Teams Netzwerkplanung](https://aka.ms/teams-networking)


Teams sind drei Arten von Datenverkehr kombiniert:

-   Datenverkehr zwischen online Office 365-Umgebung und dem Client Teams (Signale, Anwesenheit, Chat, Dateien hochladen und herunterladen, OneNote-Synchronisierung).

-   Real-Time Communications Peer-zu-Peer-Datenverkehr (audio, video, desktop freigeben).

-   Echtzeitkommunikation konferenzdatenverkehr (audio, video, desktop freigeben).

Dies wirkt sich auf das Netzwerk auf zwei Ebenen: Datenverkehr fließt zwischen den Clients Microsoft-Teams, direkt für Peer-zu-Peer-Szenarien und Datenverkehr fließt zwischen Office 365-Umgebung und den Clients Microsoft-Teams zur Erfüllung Szenarien. Um eine optimale mediendatenfluss zu gewährleisten, Datenverkehr muss dürfen beide zwischen dem internen Netzwerksegmente (beispielsweise zwischen Standorten über das WAN) wie sowie zwischen flow der Netzwerkstandorte und Office 365. Nicht die richtigen Ports öffnen oder aktiv bestimmte Ports Sperren führt zu einer beeinträchtigter wünschen.

> [!NOTE]
> Besprechungen werden auf iOS und Android mobilen Geräten unterstützt. 

Wenn Sie eine optimale wünschen mit Echtzeit-Medien in Microsoft-Teams erhalten möchten, muss Ihr Netzwerk Netzwerken Anforderungen für Office 365 erfüllen. Weitere Informationen finden Sie unter [Medienqualität und Leistung des Netzwerks Konnektivität für Skype für Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Sollten Sie für die zwei definierenden Netzwerksegmente (Client Microsoft Edge) und Customer Kante Microsoft Edge die folgenden Empfehlungen.


|Wert  |Client für Microsoft-Edge  |Customer Edge zum Microsoft Rand  |
|:--- |:--- |:--- |
|**Wartezeit (unidirektional)**\*  |< 50 ms          |< 30ms         |
|**Wartezeit (Zeit oder Roundtripzeit)**\* |< 100 ms   |< 60ms |
|**Bursts von Paketverlusten**    |<10 % Intervall 200 ms         |<1 % Intervall 200 ms         |
|**Paketverlust**     |<1 % während alle 15 s Intervall          |<0.1% während alle 15 s Intervall         |
|**Die Kommunikation zwischen hinzukommen Jitter Paket**    |<30ms während alle 15 s Intervall         |<15ms während alle 15 s Intervall         |
|**Paket neu anordnen**    |<0.05% außerhalb der Reihenfolge Pakete         |<0.01% außerhalb der Reihenfolge Pakete         |

\*Die Wartezeit metrischen Ziele gehen davon aus Ihrer Firma Website oder Websites und die Microsoft Kanten auf dem gleichen Kontinent.

Die Unternehmen Website-Verbindung mit der Microsoft-Netzwerkgrenze enthält ersten Hop Netzwerkzugriff, WiFi oder einer anderen drahtlosen Technologie werden kann.

Die Netzwerk-Leistungsziele wird vorausgesetzt, ordnungsgemäße Bandbreite und/oder [QoS planen](QoS-in-Teams.md). Mit anderen Worten, gelten die Anforderungen direkt in Echtzeit Mediendatenverkehr Teams, wenn eine spitzenauslastung die Netzwerkschnittstelle ist.

Um beide Netzwerksegmente zu testen, können Sie das [Tool zur Bewertung der Netzwerk](https://go.microsoft.com/fwlink/?linkid=855799)verwenden. Dieses Tool kann auf dem Client PC direkt und auf einem PC verbunden mit dem Kunden Netzwerkgrenze bereitgestellt werden. Das Tool umfasst begrenzte Dokumentation, aber eine tiefere Dokumentation entsprechend der Verwendung des Tools finden Sie hier: [Bereitschaft des Netzwerks](https://go.microsoft.com/fwlink/?linkid=855800). Diese Bereitschaft Netzwerk ausführen, können Sie Netzwerks auszuführenden Real-Time Media-Anwendungen wie Microsoft-Teams überprüfen.

> [!NOTE]
> Dies ist die gleiche Netzwerk Bereitschaft, die für Kunden ausgeführt werden soll, die erfolgreiche Bereitstellung von Skype für Unternehmen suchen empfohlen wird.


## <a name="bandwidth-requirements"></a>Erforderliche Bandbreite

Bandbreite Berechnungen für Microsoft-Teams sind komplex und dabei zu unterstützen, um ein Rechner erstellt wurde. Um den Rechner zuzugreifen, wechseln Sie zur [Netzwerk Planner](https://aka.ms/bwcalc/) in MyAdvisor.

> [!NOTE]
> Behandlung von Teams Bandbreite wurden verbessert Skype für Business Online: für eine hohe Qualität aufrufen oder meeting-Erfahrung (mit Audio, Video und Freigabe), Teams nur 1,2 Mbit/s benötigt. Sie können auch Skalieren bis super hochwertige weiter, wenn genügend Bandbreite vorhanden ist. Wenn eine Anforderung Teams eine Bedingung geringer Bandbreite stößt, können Teams schnell Auslastung der Bandbreite Anpassung an die verfügbare Bandbreite textlichen.

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

<a name="additional-network-considerations"></a>Zusätzliche Netzwerkaspekte
---------------

#### <a name="external-name-resolution"></a>Externe namensauflösung

Stellen Sie sicher, dass alle Clientcomputer unter Teams Client externe DNS-Abfragen zum Ermitteln der Dienste von Office 365 beheben können und Ihrer Firewalls Access nicht verhindern. Informationen zum Konfigurieren von Firewallports wechseln Sie zu [Office 365-URLs und IP-Adressbereichen](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>NAT-Pool-Größe

Bei Office 365 (Network Address Translation, NAT) oder Port Address Translation (PAT) mit Zugriff auf mehrere Benutzer/Geräte müssen Sie sicherstellen, dass die Geräte hinter jeder öffentlich routingfähige IP-Adresse ausgeblendet unterstützte Anzahl nicht überschritten werden.

Um dieses Risiko zu verringern, stellen Sie sicher, über ausreichend öffentliche IP-Adressen in der NAT-Pools zu verhindern, dass Port Erschöpfung zugewiesen sind. Port Erschöpfung bewirkt, dass interne Endbenutzer und Geräten, um Probleme mit der Vorderseite nach beim Verbinden mit Office 365-Dienste. Weitere Informationen finden Sie unter [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Erkennung und Prevention Anleitungen**

Wenn Ihre Umgebung eine Erkennung und/oder Prevention-System (IDS/IPS) für eine zusätzliche Sicherheitsebene für ausgehende Verbindungen bereitgestellt hat, sicher, dass jeder Datenverkehr mit Ziel zu Office 365-URLs White.

<a name="network-health-determination"></a>Bestimmung der Netzwerk-Integrität
-----------------

Bei der Planung der Implementierung des Microsoft-Teams innerhalb des Netzwerks, müssen Sie darauf achten Sie über die erforderliche Bandbreite verfügen, haben Sie Zugriff auf alle erforderlichen IP-Adressen, die richtigen Ports geöffnet, und Sie sind die leistungsanforderungen für Real-Time Media meeting .

Wenn Sie, dass Sie diese Kriterien nicht erfüllt werden wissen, erhalten die Endbenutzer nicht optimal arbeiten von Teams aufgrund ungültiger Qualität während der Anrufe und Besprechungen.

Sie diesen Kriterien nicht entsprechen soll, ist dies die Zeit, zu berücksichtigen sind Anhalten des Projekts, um sicherzustellen, dass Sie die Kriterien erfüllen, bevor Sie fortfahren.


|  |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Entscheidungspunkt         |Haben Sie Ihr Netzwerkfunktionen zur Unterstützung von Real Time Media ausgewertet?<br></br>Wenn Ihr Netzwerk nicht ordnungsgemäß bewertet oder wissen Sie, dass Real Time Media nicht unterstützt wird, werden Sie Video- und Freigabefunktionen Reduzierung der Netzwerklast und schlechte Erfahrungen von Teams Bildschirm deaktivieren?         |
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Nächste Schritte         |Netzwerk-Qualität unbekannt: befolgen Sie die [Bereitschaft des Netzwerks](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Offers?pageState=NetworkReadiness) -Anweisungen, um festzustellen, ob Ihr Netzwerk für Real Time Media bereit ist.<br></br>Anrufe schlechter Qualität der Netzwerk: Führen Sie Netzwerk Remediation Schritte aus, um eine ordnungsgemäße Umgebung für hohe Qualität Real Time Media bieten.<br></br>Netzwerk befriedigend: Sicher, dass alle IP-Adressen und Ports sind ordnungsgemäß zugegriffen werden.           |

## <a name="related-topics"></a>Verwandte Themen

[Video: Netzwerkplanung](https://aka.ms/teams-networking)