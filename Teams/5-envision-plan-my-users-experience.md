---
title: Planen der Funktionen für die Benutzer in Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Wählen Sie Teams-Client-Apps aus, planen Sie die Endpunkt Qualität, erhalten Sie Empfehlungen für die Bereitstellung von WLAN-Endpunkten und das Auswählen von Audiogeräten.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8f12b80fa1914166d48860b15cda7a928ca94ece
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069196"
---
# <a name="plan-my-users-experience"></a>Planen der Benutzererfahrung

In diesem Artikel finden Sie eine Übersicht über die Anforderungen für die ordnungsgemäße Identifizierung der Elemente Ihrer Cloud Voice Services-Bereitstellung, die sich direkt auf die Benutzererfahrung auswirken. Wenn Sie sich vor der Bereitstellung auf diese Elemente vorbereiten, erhöhen Sie Ihre Chancen, dass Benutzer eine qualitativ hochwertige und zuverlässige Ober Leistung erzielen können. 

## <a name="client-deployment"></a>Client Bereitstellung

Microsoft Teams verfügt über Clients für Web, Desktop (Windows und Mac) und Mobile (Android und IOS). Weitere Informationen dazu, wie der Desktop (Windows und Mac) und die mobilen Clients installiert werden, finden Sie unter [Abrufen von Clients für Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="client-updates"></a>Clientupdates

Einer der Hauptvorteile von Teams besteht darin, dass der Client automatisch auf dem neuesten Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planen der Endpunktqualität

Wie Sie aus dem nachstehenden Diagramm sehen können, stellen Endpunkte einen wichtigen Baustein dar, um Benutzern eine Qualität zu ermöglichen.

![Diagramm, in dem die drei Komponenten der Qualität beschrieben werden](media/plan-my-users-experience-image1.png "Diagramm, in dem die drei Komponenten der Qualität beschrieben sind und wie die Dienstverwaltung alle drei Komponenten überlappt. Mit einem Fokus auf Endpunkte.")

Die Endpunkte von Teams können auf vielen Geräten, einschließlich PCs, Macs, Tablets und mobilen Geräten, ausgeführt werden. Ein Teil der Oberfläche umfasst nicht nur das Gerät, sondern auch, wie ein Benutzer eine Verbindung mit dem Gerät herstellt, beispielsweise mit dem integrierten Mikrofon/Lautsprecher, Ohrhörer oder einem optimierten Headset. Die Verwendung eines optimierten Headsets kann sich positiv auf die allgemeine Benutzerfreundlichkeit auswirken.

Die folgenden Anleitungen zur Endpunktplanung sollen Ihnen helfen, für Ihre Organisation ein erfolgreiches Onboarding in Microsoft Teams sicherzustellen.

## <a name="endpoint-capability"></a>Endpunktfunktionen

Der erste Teil der Planung besteht darin, sicherzustellen, dass alle PCs und andere Geräte in Ihrer Organisation Teams ausführen können. Dazu müssen Sie nicht nur die Hardwareanforderungen betrachten, sondern sich auch verdeutlichen, was außerdem im Hintergrund auf dem PC geschieht. Viele Organisationen führen weitere Software aus, beispielsweise Angriffserkennungssysteme und Antischadsoftware, die Basisleistung eines Geräts beeinflussen kann.

Informationen zu den Softwareanforderungen für Teams-Clients auf jeder Plattform (Web, Desktop und Mobiltelefon) finden Sie unter [Abrufen von Clients für Microsoft Teams](https://docs.microsoft.com/microsoftteams/get-clients).

## <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können nicht nur verhindern, dass ein Anruf aufgebaut wird, sondern sich auch auf die Anrufqualität auswirken. Konfigurieren Sie die entsprechenden Ausschlüsse in der Clientfirewall anhand der Informationen unter [URLs und IP-Adressbereiche von Office 365](https://aka.ms/o365ips). Ihr Drittanbieter sollte über konkrete Anleitungen zum Erstellen der Ausschlüsse verfügen.

>[!NOTE]
> Microsoft Teams aktualisiert automatisch die Windows-Firewall mit einer entsprechenden Firewallkonfiguration.

## <a name="wi-fi-recommendations-for-endpoints"></a>WLAN-Empfehlungen für Endpunkte

Für die Bereitstellungeines optimierten Wi-Fi-Netzwerks zur Unterstützung von Arbeitslasten in Microsoft Teams in Echtzeit ist eine beträchtliche Planung erforderlich. In den folgenden Abschnitten finden Sie einige allgemeine Anleitungen, die Ihnen bei der Planung von Endpunkten helfen, häufige Fehler zu vermeiden.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Einige WLAN-Treiber können problematisch sein. So kann beispielsweise ein Treiber ein sehr aggressives Verhalten beim Roaming zwischen Zugriffspunkten aufweisen, was zu einer mangelhaften Anrufqualität führt.
Dies ist keine häufige Erscheinung, aber es ist wichtig, sicherzustellen, dass die WLAN-Treiber auf dem PC vor der Bereitstellung aktualisiert und getestet wurden.

### <a name="wi-fi-bands"></a>WLAN-Bänder

WLAN-Geräte verwenden heute im Wesentlichen zwei Bänder: 2,4 GHz und 5,0 GHz. Wenn Ihre Organisation beide Bänder bereitstellt, sollten Sie die Treibereinstellungen so konfigurieren, dass das 5,0-GHz-Band bevorzugt wird. Dieses Band ist im Hinblick auf den Durchsatz erheblich dichter und von den im 2,4-GHz-Band auftretenden Störungen weniger betroffen.
Bei dieser Empfehlung wird angenommen, dass Sie das 5,0-GHz-Netzwerkband richtig optimiert haben.

### <a name="wi-fi-radio-type"></a>WLAN-Funkstandard

Planen Sie mit Geräten, die neueren WLAN-Funkstandards unterstützen. Sie können eine sehr gute WLAN-Leistung erzielen, wenn Sie auf den bereitgestellten Geräten 802.11ac oder einen neueren Standard nutzen.

### <a name="wireless-avoidance"></a>WLAN-Vermeidung

Manche Organisationen möchten WLAN ganz vermeiden. In diesem Zusammenhang wird Benutzern manchmal empfohlen, eine direkte Verbindung mit einem Kabelnetzwerk herzustellen. In manchen Fällen sieht die Reihenfolge der Netzwerkbindungen eine Bevorzugung der WLAN-Verbindung vor, die dann weiterhin verwendet wird, obwohl der PC über die Kabelverbindung verbunden ist. Wenn Sie dieses unbeabsichtigte Verhalten vermeiden möchten, konfigurieren Sie die Bindungsreihenfolge so, dass dieses Szenario vermieden wird.

### <a name="80211-power-save-protocol"></a>802,11 Power Save-Protokoll

Wenn Ihre Organisation Drahtloszugriffspunkte oder Router verwendet, die das 802,11-Power Save-Protokoll nicht unterstützen, können Sie in Microsoft Teams, die auf Windows-Geräten ausgeführt werden, Ausfälle oder schlechte Anrufqualität auftreten. Wenn die WLAN-Zugriffspunkte oder -Router nicht aktualisiert werden können, sollten Sie auf Geräten, die mit Akku betrieben werden, die Windows-Einstellungen für den Energiesparplan aktualisieren. Weitere Details und Konfigurationsanleitungen finden Sie im folgenden [Supportartikel](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Welche Teams-Clients werden in Ihrer Organisation bereitgestellt?</li><li>Wie werden Sie zunächst Teams-Clients für Ihre Benutzer bereitstellen?</li><li>Wer ist für die Bewertung von Endpunkten und Geräten verantwortlich, um zu bestätigen, dass Sie die Anforderungen von Teams für eine Qualitätserfahrung erfüllen?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie den Prozess, der zum Bereitstellen von Teams-Clients befolgt wird.</li><li>Auswerten von Endpunkten und Geräten sowie ausführen und Behebung erforderlich.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Geräte für Microsoft Teams

Microsoft Teams kann für Besprechungen oder als Telefonsystem verwendet werden. Bei der Verwendung dieser Funktionen spielt das für Microsoft Teams verwendete Gerät eine wichtige Rolle für die Benutzerfreundlichkeit.

Benutzer, die einen integrierten PC-Lautsprecher und ein integriertes Mikrofon verwenden, empfinden diese Konfiguration möglicherweise als akzeptabel. In der Regel sind diese Geräte jedoch nicht für die Rauschunterdrückung optimiert, und jeder Typ von Umgebungsgeräuschen kann eine nachgeschaltete Auswirkung auf andere Personen beim Anruf haben. Die Nutzung von für diese Szenarien optimierten Geräten kann eine hohe Qualität sicherstellen.

Alle Geräte müssen den Anforderungen der Benutzer entsprechen. Sie müssen Geräte wie beispielsweise Headsets auf die verschiedenen Personas und Anwendungsfälle in der Organisation abstimmen.
Im Rahmen des Planungsprozesses sollte eine Zuordnung von Personas zu Geräten erstellt werden.

Wenn Sie die Geräte ausgewählt haben, nehmen Sie sie zur endgültigen Validierung in den Pilottestplan auf. Nutzen Sie in der Pilotphase Umfragen, um Feedback zu sammeln, damit Sie sicherstellen können, dass Sie die optimale Gerätestrategie verwenden.

> [!NOTE]
> Zurzeit empfehlen wir die Verwendung von Geräten, die über das Skype for Business-Zertifizierungsprogramm zertifiziert wurden. Informationen zu Geräten, die unter diesem Programm zertifiziert sind, finden Sie auf den [Microsoft Teams-Geräten](https://products.office.com/en-us/microsoft-teams/across-devices/devices) und [USB-Audio-und-Videogeräten](https://docs.microsoft.com/SkypeForBusiness/certification/devices-usb-devices).



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie sich für die gesamte Geräte Strategie Ihrer Organisation für Benutzer-und Besprechungsraum Erlebnisse.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Führen Sie eine Aufgaben-zu-Gerät-Zuordnungsübung für Ihre Organisation durch.</li><li>Dokumentieren Sie den Prozess zum Abrufen von Geräten für Benutzer und Besprechungsräume.</li><li>Dokumentieren des Prozesses zum Bereitstellen und Konfigurieren von Geräten für Benutzer und Besprechungsräume</li><li>Beschaffen Sie die ersten Geräte, um Ihre Bereitstellung zu starten.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
