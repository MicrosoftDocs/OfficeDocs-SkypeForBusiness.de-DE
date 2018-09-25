---
title: Planen der Benutzer den Endbenutzer von Microsoft-Teams
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
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fa7f3450f563dad6be2bfc857724e7c6fe2ba16
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016765"
---
# <a name="plan-my-users-experience"></a>Planen von meiner Benutzer-Erlebnis

Dieser Artikel bietet eine Übersicht über die Anforderungen für ordnungsgemäß Identifizieren der Elemente des Ihrer Bereitstellung Cloud VoIP-Dienste, die der Benutzer direkt beeinflussen. Durch die für diese Elemente vor der Bereitstellung vorbereiten, müssen Sie Ihre Chancen erfolgreich spielt eine hohe Qualität und zuverlässige Erfahrung für Benutzer zu erhöhen. 

## <a name="client-deployment"></a>Client-Bereitstellung

Microsoft-Teams, hat Clients verfügbaren Web, desktop (Windows und Mac) und Mobil (Android-, IOS- und Windows Phone). Weitere Details zu den Desktop (Windows und Mac) und mobilen Clients wie installiert werden finden Sie unter [Get-Clients für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Clientupdates

Einer der wichtigsten Vorteile von Teams ist, dass der Client automatisch auf dem aktuellen Stand ist. Die Clients auf dem PC und Mac werden aktualisiert, mit einem Hintergrund, die für neue Builds überprüft und den neuen Client heruntergeladen, wenn die app im Leerlauf befindet.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Plan für die Qualität der Endpunkt

Wie Sie aus der folgenden Abbildung sehen können, sind Endpunkte als wichtiger Baustein einer Quality of Experience für Benutzer bereitzustellen.

![Diagramm beschreibt die drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf Endpunkten.] (media/plan-my-users-experience-image1.png "Diagramm beschreibt die drei Komponenten der Qualität und wie Service-Management für alle drei Komponenten überlappt. Mit Schwerpunkt auf Endpunkten.")

Teams Endpunkte können auf vielen Geräten, einschließlich PCs, Macs, Tablets und mobilen Geräten ausführen. Teil der Erfahrung umfasst nicht nur das Gerät, aber wie ein Benutzer auf das Gerät verbindet – beispielsweise mithilfe des Geräts integrierten Mikrofon/Lautsprecher, Ohrstöpsel oder eine optimierte Kopfhörer. Mithilfe einer optimierten Kopfhörer kann die gesamten Benutzeroberfläche erweitern.

Die folgende Anleitung für die Planung der Endpunkt helfen Ihnen beim sicherstellen, dass Ihre Organisation eine erfolgreiche Onboarding Erfahrung mit Teams verfügt.

## <a name="endpoint-capability"></a>Endpunkt-Funktion

Der erste Teil der Planung ist, um sicherzustellen, dass alle PCs und andere Geräte in Ihrer Organisation können Teams ausführen. Dieser Schritt umfasst nicht nur die hardwareanforderungen betrachten, aber auch zu verstehen, was der PC im Hintergrund Aufgaben verwendet wird. Viele Organisationen führen Sie andere Software, einschließlich Eindringungserkennungssysteme und Antischadsoftware, die die Leistung des base eines Geräts auswirken kann.

Informationen über die erforderliche Software für Teams finden Sie unter Clients auf jeder Plattform (Web, Desktops und Mobile), [erhalten die Clients für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Endpunkt firewalls

Mithilfe der clientseitigen Firewalls können eine erhebliche Auswirkungen Benutzerinteraktion haben.
Mithilfe der clientseitigen Firewalls können die Anrufqualität zusätzlich zu verhindern, dass einen Anruf aufgebaut wird beeinflussen. Konfigurieren Sie die entsprechenden Ausnahmen auf der Grundlage der Informationen in [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365ips)Clientfirewall. Ihre Drittanbieter müssen spezifische Leitfäden zum die Ausnahmen zu erstellen.

>[!NOTE]
> Microsoft-Teams, wird automatisch die Windows-Firewall mit einer geeigneten Firewallkonfiguration aktualisiert.

## <a name="wi-fi-recommendations-for-endpoints"></a>Wi-Fi Empfehlungen für Endpunkte

Es dauert erhebliche planen die Bereitstellung einer optimierten Wi-Fi-Netzwerk zur Unterstützung von Real-Time Arbeitslasten in Microsoft-Teams. Die folgenden Abschnitte enthalten einige allgemeine Richtlinien, die Sie häufige Probleme zu vermeiden, bei der Planung für Endpunkte helfen kann.

### <a name="wi-fi-drivers"></a>Wi-Fi-Treiber

Einige Wi-Fi-Treiber können problematisch sein. Als Beispiel möglicherweise ein Treiber sehr aggressive roaming-Verhaltens zwischen Zugriffspunkten, verursacht schlechter Anrufqualität.
Dies nicht häufig auftreten, aber es ist wichtig, um sicherzustellen, dass Wi-Fi-Treiber auf dem PC aktualisiert und vor der Bereitstellung getestet wurden.

### <a name="wi-fi-bands"></a>Wi-Fi-Bereichen

Es gibt hauptsächlich zwei Arten von Bereichen in Wi-Fi modernen Geräte, 2,4 GHz und 5,0 GHz verwendet. Wenn Ihre Organisation die beiden Bereichen bereitstellt, sollten Sie Ihre Einstellungen für Treiber, um die 5,0 GHz Band bevorzugen konfigurieren. Dieses Band ist viel dichter im Hinblick auf den Durchsatz und von der Störungen gesehen im Band mit 2,4 GHz kleiner betroffen waren.
Diese Empfehlung wird davon ausgegangen, dass Sie ordnungsgemäß das 5,0 GHz Netzwerk Band optimiert haben.

### <a name="wi-fi-radio-type"></a>Wi-Fi Radio-Typ

Planen von Geräten, die die neueren Wi-Fi Radio Typen unterstützen. Sie können eine sehr gute Wi-Fi Leistung erhalten, wenn Sie die 802.11ac nutzen oder höher auf den Geräten, die Sie bereitstellen.

### <a name="wireless-avoidance"></a>Drahtlose Vermeidung

Manche Organisationen möchten Wi-Fi ganz zu vermeiden. In einigen Fällen wird dieser Anleitung über eine Empfehlung an Benutzer, um eine direkte Verbindung mit einem verkabelten Netzwerk bereitgestellt. In einigen Fällen kann die Reihenfolge der Bindung die drahtlose Verbindung bevorzugte haben und weiterhin, diese Verbindung verwenden, obwohl der PC verbunden ist, die eine drahtgebundene Verbindung verwenden. Um dieses unerwünschte Verhalten zu vermeiden, konfigurieren Sie die Bindungsreihenfolge für dieses Szenario zu vermeiden.

### <a name="80211-power-save-protocol"></a>802.11-Energiesparmodus-Protokoll

Wenn Ihre Organisation verwendet Drahtloszugriffspunkte oder Router, die das 802.11-Energiesparmodus Protokoll nicht unterstützen, können Sie Verworfene Anrufe oder Anrufe schlechter Qualität Qualität in Microsoft-Teams, die auf Windows-Geräten ausgeführt auftreten. Ist es nicht möglich, Ihre drahtlosen Zugriffspunkt oder Router zu aktualisieren, sollten Sie Windows Power Planen der Einstellungen auf Geräten aktualisieren, die auf Batterie ausgeführt. Weitere Details und Konfiguration Leitlinien wird in der folgenden [Artikel unterstützen](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you)bereitgestellt.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Welche Teams Clients in Ihrer Organisation bereitgestellt werden?</li><li>Wie werden Sie zunächst Teams Clients für die Benutzer bereitstellen?</li><li>Wer für die Auswertung von Endpunkten und Geräte überprüfen verantwortlich ist diese Teams Anforderungen für eine Quality of Experience entsprechen?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren des Prozesses, der zum Bereitstellen von Teams-Clients ausgeführt wird.</li><li>Auswertung von Endpunkten und Geräten, und führen und-Wartung erforderlich.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Geräte für Teams

Microsoft-Teams können für Besprechungen oder als Telefonsystem verwendet werden. Wenn Sie diese Features verwenden, spielt Schnittstellengerät für Teams verwendet wird eine wichtige Rolle, die Benutzeroberfläche.

Verwenden eine integrierte PC-Lautsprecher und ein Mikrofon mag für den Benutzer akzeptable, diese Konfiguration hat. Aber in der Regel diesen Geräten sind nicht für Noise Abbruch optimiert, und jede Art von Umgebung Noise kann wirken sich downstream auf anderen auf den Anruf. Nutzen für diese Szenarien optimierte Geräte können Sie eine hohe Qualität Erfahrung sicherstellen.

Jedes Gerät muss die Anforderungen Ihrer Benutzer. Sie müssen auf Geräten wie Headsets für die verschiedenen Rollen anpassen und Anwendungsfälle in Ihrer Organisation.
Eine Rolle-Geräte-Zuordnung Übung sollte als Teil des Planungsprozesses abgeschlossen werden.

Nachdem Sie die Geräte ausgewählt haben, können Sie diese in den Pilottest Plan für die endgültige Überprüfung. Optimal nutzen Umfragen während des Pilotprojekts zum Sammeln von Feedback, um Ihre Strategie für die Geräte stellen Sie sicher ist.

> [!NOTE]
> Zu diesem Zeitpunkt sollten mithilfe von Audiogeräte, die über die Skype für Business Zertifizierungsprogramm zertifiziert wurden. Finden Sie unter dieses Programm zertifizierte Geräte in den Lösungskatalog für [USB-Geräte zertifiziert für Skype für Unternehmen](http://partnersolutions.skypeforbusiness.com/solutionscatalog/personal-peripherals-pcs) .

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Legen Sie allgemeine Gerät-Strategie für Benutzer- und meeting Room Erfahrungen Ihres Unternehmens.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Führen Sie eine Übung Persona-Geräte-Zuordnung für Ihre Organisation.</li><li>Den Prozess zum Abrufen von Geräten für Benutzer und Besprechungsräumen des Dokuments.</li><li>Den Prozess für die Bereitstellung und Konfiguration von Geräten für Benutzer und Besprechungsräumen des Dokuments.</li><li>Bereitstellen von anfänglichen Geräte mit der Bereitstellung beginnen.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->