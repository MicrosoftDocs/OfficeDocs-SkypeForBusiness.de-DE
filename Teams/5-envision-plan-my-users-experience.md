---
title: Planen der Funktionen für die Benutzer in Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Wählen Sie Teams Clientanwendungen, Plan für die Qualität der Endpunkt, Empfehlungen für die Bereitstellung von Wi-Fi-Endpunkten und Audiogeräte auswählen möchten.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95777c59da635631c1493fc15351521248eead34
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459036"
---
# <a name="plan-my-users-experience"></a>Planen von meiner Benutzer-Erlebnis

Dieser Artikel bietet eine Übersicht über die Anforderungen für ordnungsgemäß Identifizieren der Elemente des Ihrer Bereitstellung Cloud VoIP-Dienste, die der Benutzer direkt beeinflussen. Durch die für diese Elemente vor der Bereitstellung vorbereiten, müssen Sie Ihre Chancen erfolgreich spielt eine hohe Qualität und zuverlässige Erfahrung für Benutzer zu erhöhen. 

## <a name="client-deployment"></a>Client-Bereitstellung

Microsoft-Teams, hat Clients verfügbaren Web, desktop (Windows und Mac) und Mobil (Android und iOS). Weitere Details zu den Desktop (Windows und Mac) und mobilen Clients wie installiert werden finden Sie unter [Get-Clients für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Clientupdates

Einer der wichtigsten Vorteile von Teams ist, dass der Client automatisch auf dem aktuellen Stand ist. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planen der Endpunktqualität

Wie Sie aus der folgenden Abbildung sehen können, sind Endpunkte als wichtiger Baustein einer Quality of Experience für Benutzer bereitzustellen.

![Diagramm beschreibt die drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf Endpunkten.] (media/plan-my-users-experience-image1.png "Diagramm beschreibt die drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf Endpunkten.")

Teams Endpunkte können auf vielen Geräten, einschließlich PCs, Macs, Tablets und mobilen Geräten ausführen. Teil der Erfahrung umfasst nicht nur das Gerät, aber wie ein Benutzer auf das Gerät verbindet – beispielsweise mithilfe des Geräts integrierten Mikrofon/Lautsprecher, Ohrstöpsel oder eine optimierte Kopfhörer. Die Verwendung eines optimierten Headsets kann sich positiv auf die allgemeine Benutzerfreundlichkeit auswirken.

Die folgenden Anleitungen zur Endpunktplanung sollen Ihnen helfen, für Ihre Organisation ein erfolgreiches Onboarding in Microsoft Teams sicherzustellen.

## <a name="endpoint-capability"></a>Endpunktfunktionen

Der erste Teil der Planung ist, um sicherzustellen, dass alle PCs und andere Geräte in Ihrer Organisation können Teams ausführen. Dazu müssen Sie nicht nur die Hardwareanforderungen betrachten, sondern sich auch verdeutlichen, was außerdem im Hintergrund auf dem PC geschieht. Viele Organisationen führen weitere Software aus, beispielsweise Angriffserkennungssysteme und Antischadsoftware, die Basisleistung eines Geräts beeinflussen kann.

Informationen über die erforderliche Software für Teams finden Sie unter Clients auf jeder Plattform (Web, Desktops und Mobile), [erhalten die Clients für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können nicht nur verhindern, dass ein Anruf aufgebaut wird, sondern sich auch auf die Anrufqualität auswirken. Konfigurieren Sie die entsprechenden Ausschlüsse in der Clientfirewall anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips). Ihr Drittanbieter sollte über konkrete Anleitungen zum Erstellen der Ausschlüsse verfügen.

>[!NOTE]
> Microsoft Teams aktualisiert automatisch die Windows-Firewall mit einer entsprechenden Firewallkonfiguration.

## <a name="wi-fi-recommendations-for-endpoints"></a>WLAN-Empfehlungen für Endpunkte

Es dauert erhebliche planen die Bereitstellung einer optimierten Wi-Fi-Netzwerk zur Unterstützung von Real-Time Arbeitslasten in Microsoft-Teams. Die folgenden Abschnitte enthalten einige allgemeine Richtlinien, die Sie häufige Probleme zu vermeiden, bei der Planung für Endpunkte helfen kann.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Einige Wi-Fi-Treiber können problematisch sein. So kann beispielsweise ein Treiber ein sehr aggressives Verhalten beim Roaming zwischen Zugriffspunkten aufweisen, was zu einer mangelhaften Anrufqualität führt.
Dies nicht häufig auftreten, aber es ist wichtig, um sicherzustellen, dass Wi-Fi-Treiber auf dem PC aktualisiert und vor der Bereitstellung getestet wurden.

### <a name="wi-fi-bands"></a>WLAN-Bänder

WLAN-Geräte verwenden heute im Wesentlichen zwei Bänder: 2,4 GHz und 5,0 GHz. Wenn Ihre Organisation beide Bänder bereitstellt, sollten Sie die Treibereinstellungen so konfigurieren, dass das 5,0-GHz-Band bevorzugt wird. Dieses Band ist im Hinblick auf den Durchsatz erheblich dichter und von den im 2,4-GHz-Band auftretenden Störungen weniger betroffen.
Bei dieser Empfehlung wird angenommen, dass Sie das 5,0-GHz-Netzwerkband richtig optimiert haben.

### <a name="wi-fi-radio-type"></a>WLAN-Funkstandard

Planen Sie mit Geräten, die neueren WLAN-Funkstandards unterstützen. Sie können eine sehr gute WLAN-Leistung erzielen, wenn Sie auf den bereitgestellten Geräten 802.11ac oder einen neueren Standard nutzen.

### <a name="wireless-avoidance"></a>WLAN-Vermeidung

Manche Organisationen möchten WLAN ganz vermeiden. In diesem Zusammenhang wird Benutzern manchmal empfohlen, eine direkte Verbindung mit einem Kabelnetzwerk herzustellen. In manchen Fällen sieht die Reihenfolge der Netzwerkbindungen eine Bevorzugung der WLAN-Verbindung vor, die dann weiterhin verwendet wird, obwohl der PC über die Kabelverbindung verbunden ist. Wenn Sie dieses unbeabsichtigte Verhalten vermeiden möchten, konfigurieren Sie die Bindungsreihenfolge so, dass dieses Szenario vermieden wird.

### <a name="80211-power-save-protocol"></a>802.11-Energiesparmodus-Protokoll

Wenn Ihre Organisation verwendet Drahtloszugriffspunkte oder Router, die das 802.11-Energiesparmodus Protokoll nicht unterstützen, können Sie Verworfene Anrufe oder Anrufe schlechter Qualität Qualität in Microsoft-Teams, die auf Windows-Geräten ausgeführt auftreten. Wenn die WLAN-Zugriffspunkte oder -Router nicht aktualisiert werden können, sollten Sie auf Geräten, die mit Akku betrieben werden, die Windows-Einstellungen für den Energiesparplan aktualisieren. Weitere Details und Konfigurationsanleitungen finden Sie im folgenden [Supportartikel](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Welche Teams Clients in Ihrer Organisation bereitgestellt werden?</li><li>Wie werden Sie zunächst Teams Clients für die Benutzer bereitstellen?</li><li>Wer für die Auswertung von Endpunkten und Geräte überprüfen verantwortlich ist diese Teams Anforderungen für eine Quality of Experience entsprechen?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren des Prozesses, der zum Bereitstellen von Teams-Clients ausgeführt wird.</li><li>Auswertung von Endpunkten und Geräten, und führen und-Wartung erforderlich.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Geräte für Microsoft Teams

Microsoft Teams kann für Besprechungen oder als Telefonsystem verwendet werden. Bei der Verwendung dieser Funktionen spielt das für Microsoft Teams verwendete Gerät eine wichtige Rolle für die Benutzerfreundlichkeit.

Benutzer, die einen integrierten PC-Lautsprecher und ein integriertes Mikrofon verwenden, empfinden diese Konfiguration möglicherweise als akzeptabel. Aber in der Regel diesen Geräten sind nicht für Noise Abbruch optimiert, und jede Art von Umgebung Noise kann wirken sich downstream auf anderen auf den Anruf. Die Nutzung von für diese Szenarien optimierten Geräten kann eine hohe Qualität sicherstellen.

Alle Geräte müssen den Anforderungen der Benutzer entsprechen. Sie müssen Geräte wie beispielsweise Headsets auf die verschiedenen Personas und Anwendungsfälle in der Organisation abstimmen.
Im Rahmen des Planungsprozesses sollte eine Zuordnung von Personas zu Geräten erstellt werden.

Wenn Sie die Geräte ausgewählt haben, nehmen Sie sie zur endgültigen Validierung in den Pilottestplan auf. Nutzen Sie in der Pilotphase Umfragen, um Feedback zu sammeln, damit Sie sicherstellen können, dass Sie die optimale Gerätestrategie verwenden.

> [!NOTE]
> Zurzeit empfehlen wir die Verwendung von Geräten, die über das Skype for Business-Zertifizierungsprogramm zertifiziert wurden. Finden Sie unter dieses Programm zertifizierte Geräte in den Lösungskatalog für [USB-Geräte zertifiziert für Skype für Unternehmen](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Legen Sie allgemeine Gerät-Strategie für Benutzer- und meeting Room Erfahrungen Ihres Unternehmens.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Führen Sie eine Übung Persona-Geräte-Zuordnung für Ihre Organisation.</li><li>Den Prozess zum Abrufen von Geräten für Benutzer und Besprechungsräumen des Dokuments.</li><li>Den Prozess für die Bereitstellung und Konfiguration von Geräten für Benutzer und Besprechungsräumen des Dokuments.</li><li>Bereitstellen von anfänglichen Geräte mit der Bereitstellung beginnen.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->