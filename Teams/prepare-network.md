---
title: "Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier erfahren Sie, wie Sie Ihr Microsoft Teams-Netzwerk vorbereiten und verwalten. Unter anderem erhalten Sie Informationen zu den Netzwerkanforderungen, den Bandbreitenanforderungen und zusätzlichen Überlegungen."
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: a89d4f201a0ea8f9392146e23629e6dd671bb7c3
ms.sourcegitcommit: 3faedb6057da8650b06b05f9c9bdd941d5ade175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2017
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams
=================================================

Microsoft Teams kombiniert drei Arten von Datenverkehr:

-   Datenverkehr zwischen der Office 365 Online-Umgebung und dem Microsoft Teams-Client (Signalisierung, Anwesenheit, Chat, Dateiupload und -download, OneNote-Synchronisierung)

-   Datenverkehr für Peer-zu-Peer-Echtzeitkommunikation (Audio, Video, Desktopfreigabe)

-   Datenverkehr für Echtzeitkommunikation in Konferenzen (Audio, Video, Desktopfreigabe)

Dies wirkt sich auf zwei Ebenen auf das Netzwerk aus: Der Datenverkehr fließt bei Peer-zu-Peer-Kommunikation direkt zwischen den Microsoft Teams-Clients und in Besprechungsszenarien zwischen der Office 365-Umgebung und den Microsoft Teams-Clients. Um den optimalen Datenverkehrsfluss sicherzustellen, muss der Datenverkehr zwischen den internen Netzwerksegmenten (zum Beispiel zwischen den Standorten über das WAN) sowie zwischen den Netzwerkstandorten und Office 365 fließen können. Wenn Sie nicht die richtigen Ports öffnen oder bestimmte Ports aktiv blockieren, führt dies zu Beeinträchtigungen.



> [!IMPORTANT]
> Zurzeit werden Besprechungen auf mobilen Geräten unter iOS und Android unterstützt, aber nicht unter Windows Phone (Unterstützung für Windows Phone kommt bald).

Für die optimale Verwendung von Echtzeitmedien in Microsoft Teams müssen die Netzwerkanforderungen für Office 365 erfüllt sein (weitere Details finden Sie unter [Medienqualität und Leistung der Netzwerkkonnektivität für Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US)).

Die beiden definierenden Netzwerksegmente (Client zu Microsoft Edge und Kundenedge zu Microsoft Edge) müssen die folgenden Anforderungen erfüllen:


|Wert  |Client zu Microsoft Edge  |Kundenedge zu Microsoft Edge  |
|---------|---------|---------|
|**Latenz (ein Weg)**     |< 50 ms          |< 30 ms          |
|**Latenz (RTT oder Roundtripzeit)** |< 100 ms         |< 60 ms         |
|**Burstverlust von Paketen**    |< 10 % in einem Intervall von 200 ms         |< 1% in einem Intervall von 200 ms         |
|**Paketverlust**     |< 1% in einem Intervall von 15 s          |< 0,1% in einem Intervall von 15 s         |
|**Jitter zwischen der Ankunftszeit von Paketen**    |< 30 ms in einem Intervall von 15 s         |< 15 ms in einem Intervall von 15 s         |
|**Neuanordnung von Paketen**    |< 0,05 % Pakete in falscher Reihenfolge         |< 0,01 % Pakete in falscher Reihenfolge         |

Um beide Netzwerksegmente zu testen, können Sie ein Netzwerkbewertungstool verwenden (Quelle: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799)). Dieses Tool kann direkt auf dem Client-PC sowie auf einem PC oder Laptop, der mit dem Netzwerkedge des Kunden verbunden ist, bereitgestellt werden. Das Tool enthält begrenzte Dokumentation, eine eingehendere Dokumentation zur Verwendung des Tools finden Sie hier: [Bewertung der Netzwerkbereitschaft](https://go.microsoft.com/fwlink/?linkid=855800). Indem Sie diese Bewertung der Netzwerkbereitschaft ausführen, können Sie die Bereitschaft Ihres Netzwerks für die Ausführung von Echtzeitmedienanwendungen wie beispielsweise Microsoft Teams validieren.



> [!NOTE]
> Dabei handelt es sich um die gleiche Bewertung der Netzwerkbereitschaft, deren Ausführung Kunden empfohlen wird, die Skype for Business erfolgreich bereitstellen möchten.

<a name="bandwidth-requirements"></a>Bandbreitenanforderungen
----------

Bandbreitenberechnungen für Microsoft Teams sind komplex. Zu Ihrer Unterstützung wurde ein Rechner erstellt. Hier können Sie auf den Rechner zugreifen: <http://aka.ms/bwcalc/>.

Den folgenden Inhalt können Sie als ergänzende Hintergrundinformationen nutzen. Kunden wird jedoch empfohlen, ihren Bedarf mit dem [Bandbreitenrechner](https://aka.ms/bwcalc) zu ermitteln.



> [!IMPORTANT]
>Wenn die erforderliche Bandbreite nicht verfügbar ist, verringert der Medienstapel in Microsoft Teams die Qualität der Audio/Video-Sitzung, um der niedrigeren verfügbaren Bandbreite Rechnung zu tragen. Dies wirkt sich auf die Qualität des Anrufs bzw. der Besprechung aus. Der Microsoft Teams-Client versucht, die Audioqualität gegenüber der Videoqualität zu priorisieren. Daher ist es äußerst wichtig, dass die erwartete Bandbreite verfügbar ist.


|Aktivität  |Downloadbandbreite  |Uploadbandbreite  |Datenverkehrsfluss |
|---------|---------|---------|---------|
|**Peer-zu-Peer-Audioanruf**     |0,1 MB         |0,1 MB         |Client <> Client         |
|**Peer-zu-Peer-Videoanruf (Vollbild)**     |4 MB         |4 MB         |Client <> Client          |
|**Peer-zu-Peer-Desktopfreigabe (Auflösung 1920x*1080)**     |4 MB         |4 MB         |Client <> Client          |
|**Besprechung mit zwei Teilnehmern**     |4 MB         |4 MB         |Client <> Office 365         |
|**Besprechung mit drei Teilnehmern**     |8 MB         |6,5 MB         |Client <> Office 365           |
|**Besprechung mit vier Teilnehmern**     |5,5 MB         |4 MB         |Client <> Office 365           |
|**Besprechung mit fünf oder mehr Teilnehmern**     |6 MB         |1,5 MB         |Client <> Office 365           |


<a name="additional-network-considerations"></a>Zusätzliche Netzwerküberlegungen
---------------

#### <a name="external-name-resolution"></a>**Externe Namensauflösung**

Stellen Sie sicher, dass alle Clientcomputer, auf denen Microsoft Teams ausgeführt wird, externe DNS-Abfragen auflösen können, um die von Office 365 bereitgestellten Dienste zu ermitteln.

#### <a name="nat-pool-size"></a>**NAT-Poolgröße**

Wenn mehrere Benutzer/Geräte mit NAT (Network Address Translation, Netzwerkadressenübersetzung) oder PAT (Port Address Translation, Portadressenübersetzung) auf Office 365 zugreifen, müssen Sie sicherstellen, dass die hinter den einzelnen öffentlich routingfähigen IP-Adressen verborgenen Geräte nicht die unterstützte Anzahl überschreiten.

Verringern Sie dieses Risiko, indem Sie sicherstellen, dass den NAT-Pools entsprechend viele öffentliche IP-Adressen zugewiesen sind, um Portauslastung zu verhindern. Portauslastung führt dazu, dass für interne Endbenutzer und Geräte Probleme beim Herstellen der Verbindung mit den Office 365-Diensten auftreten. Weitere Informationen finden Sie im Leitfaden [NAT-Unterstützung für Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

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
|![Symbol für „Nächste Schritte“](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Nächste Schritte         |Netzwerkqualität unbekannt: Ermitteln Sie anhand des Leitfadens zur Bewertung der Netzwerkbereitschaft unter skypeoperationsframework.com, ob Ihr Netzwerk für Echtzeitmedien bereit ist.<br></br>Netzwerkqualität schlecht: Führen Sie die Netzwerkwiederherstellungsschritte aus, um eine geeignete Umgebung für Echtzeitmedien von hoher Qualität bereitzustellen.<br></br>Netzwerk zufriedenstellend: Stellen Sie sicher, dass der Zugriff auf alle IP-Adressen und Ports ordnungsgemäß möglich ist.           |

