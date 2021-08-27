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
description: Wählen Teams Client-Apps aus, planen Sie die Qualität von Endpunkten, erhalten Sie Empfehlungen für die Bereitstellung Wi-Fi Endpunkte, und wählen Sie Audiogeräte aus.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6482baa6738d4f7c3495085f86ae9b9a054d0eb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624837"
---
# <a name="plan-my-users-experience"></a>Planen der Benutzererfahrung

Dieser Artikel bietet eine Übersicht über die Anforderungen für das ordnungsgemäß Identifizieren der Elemente Ihrer Cloud-Sprachdienstbereitstellung, die sich direkt auf die Benutzererfahrung auswirken. Indem Sie diese Elemente vor der Bereitstellung vorbereiten, erhöhen Sie die Chancen, erfolgreich eine qualitativ hochwertige und zuverlässige Benutzererfahrung zu bieten. 

## <a name="client-deployment"></a>Clientbereitstellung

Microsoft Teams enthält Clients für Web, Desktop (Windows und Mac) und mobile Geräte (Android und iOS). Weitere Details zur Installation von Desktopclients (Windows und Mac) und mobilen Clients finden Sie unter [Kunden für Microsoft Teams.](./get-clients.md)

## <a name="client-updates"></a>Clientupdates

Einer der Wichtigsten von Teams besteht in der automatischen Veröffentlichung des Clients. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planen der Endpunktqualität

Wie Sie aus dem nachstehenden Diagramm sehen können, sind Endpunkte ein wichtiger Baustein bei der Bereitstellung einer Qualitätserfahrung für die Benutzer.

![Diagramm zur Beschreibung der drei Qualitätskomponenten](media/plan-my-users-experience-image1.png "Diagramm, das die drei Komponenten der Qualität beschreibt und wie die Dienstverwaltung alle drei Komponenten überlappt. Mit Fokus auf Endpunkte.")

Teams-Endpunkte können auf vielen Geräten ausgeführt werden, darunter PCs, Macs, Tablets und mobile Geräte. Ein Teil der Erfahrung umfasst nicht nur das Gerät, sondern auch die Art und Weise, wie Ein Benutzer eine Verbindung mit dem Gerät herstellt – z. B. mithilfe des integrierten Mikrofons/Lautsprechers, der Ohrhörer oder eines optimierten Headsets. Die Verwendung eines optimierten Headsets kann sich positiv auf die allgemeine Benutzerfreundlichkeit auswirken.

Die folgenden Anleitungen zur Endpunktplanung sollen Ihnen helfen, für Ihre Organisation ein erfolgreiches Onboarding in Microsoft Teams sicherzustellen.

## <a name="endpoint-capability"></a>Endpunktfunktionen

Der erste Teil der Planung besteht in der Sicherstellung, dass alle PCs und anderen Geräte in Ihrer Organisation die Teams. Dazu müssen Sie nicht nur die Hardwareanforderungen betrachten, sondern sich auch verdeutlichen, was außerdem im Hintergrund auf dem PC geschieht. Viele Organisationen führen weitere Software aus, beispielsweise Angriffserkennungssysteme und Antischadsoftware, die Basisleistung eines Geräts beeinflussen kann.

Informationen zu den Softwareanforderungen für Teams-Clients auf jeder Plattform (Web, Desktop und mobile Geräte) finden Sie unter Kunden [für](./get-clients.md)Microsoft Teams.

## <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können nicht nur verhindern, dass ein Anruf aufgebaut wird, sondern sich auch auf die Anrufqualität auswirken. Konfigurieren Sie die geeigneten Ausschlüsse für die Clientfirewall anhand der Informationen in Microsoft 365 oder Office 365 URLs und [IP-Adressbereichen.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Ihr Drittanbieter sollte über konkrete Anleitungen zum Erstellen der Ausschlüsse verfügen.

>[!NOTE]
> Microsoft Teams aktualisiert automatisch die Windows-Firewall mit einer entsprechenden Firewallkonfiguration.

## <a name="wi-fi-recommendations-for-endpoints"></a>WLAN-Empfehlungen für Endpunkte

Die Bereitstellung eines optimierten Netzwerk Wi-Fi zur Unterstützung von Echtzeitarbeitsauslastungen in Echtzeit ist in erheblichem Microsoft Teams. Die folgenden Abschnitte enthalten einige allgemeine Anleitungen, mit denen Sie häufige Fallgruben bei der Planung von Endpunkten vermeiden können.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Einige Wi-Fi Treiber können problematisch sein. So kann beispielsweise ein Treiber ein sehr aggressives Verhalten beim Roaming zwischen Zugriffspunkten aufweisen, was zu einer mangelhaften Anrufqualität führt.
Dies kommt nicht häufig vor, doch ist es wichtig sicherzustellen, dass Wi-Fi-Treiber auf dem PC vor der Bereitstellung aktualisiert und getestet wurden.

### <a name="wi-fi-bands"></a>WLAN-Bänder

WLAN-Geräte verwenden heute im Wesentlichen zwei Bänder: 2,4 GHz und 5,0 GHz. Wenn Ihre Organisation beide Bänder bereitstellt, sollten Sie die Treibereinstellungen so konfigurieren, dass das 5,0-GHz-Band bevorzugt wird. Dieses Band ist im Hinblick auf den Durchsatz erheblich dichter und von den im 2,4-GHz-Band auftretenden Störungen weniger betroffen.
Bei dieser Empfehlung wird angenommen, dass Sie das 5,0-GHz-Netzwerkband richtig optimiert haben.

### <a name="wi-fi-radio-type"></a>WLAN-Funkstandard

Planen Sie mit Geräten, die neueren WLAN-Funkstandards unterstützen. Sie können eine sehr gute WLAN-Leistung erzielen, wenn Sie auf den bereitgestellten Geräten 802.11ac oder einen neueren Standard nutzen.

### <a name="wireless-avoidance"></a>WLAN-Vermeidung

Manche Organisationen möchten WLAN ganz vermeiden. In diesem Zusammenhang wird Benutzern manchmal empfohlen, eine direkte Verbindung mit einem Kabelnetzwerk herzustellen. In manchen Fällen sieht die Reihenfolge der Netzwerkbindungen eine Bevorzugung der WLAN-Verbindung vor, die dann weiterhin verwendet wird, obwohl der PC über die Kabelverbindung verbunden ist. Wenn Sie dieses unbeabsichtigte Verhalten vermeiden möchten, konfigurieren Sie die Bindungsreihenfolge so, dass dieses Szenario vermieden wird.

### <a name="80211-power-save-protocol"></a>802.11 Power Save-Protokoll

Wenn Ihre Organisation Funkzugriffspunkte oder Router verwendet, die das Power Save-Protokoll 802.11 nicht unterstützen, kann es zu Gesprächsausfall oder einer schlechten Anrufqualität in Microsoft Teams auf Windows-Geräten kommt. Wenn die WLAN-Zugriffspunkte oder -Router nicht aktualisiert werden können, sollten Sie auf Geräten, die mit Akku betrieben werden, die Windows-Einstellungen für den Energiesparplan aktualisieren. Weitere Details und Konfigurationsanleitungen finden Sie im folgenden [Supportartikel](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Welche Teams Kunden werden in Ihrer Organisation bereitgestellt?</li><li>Wie werden Sie die Teams zunächst für Ihre Benutzer bereitstellen?</li><li>Wer ist für die Bewertung von Endpunkten und Geräten verantwortlich, um deren Teams Qualitätsanforderungen zu erfüllen?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie den Prozess, der zum Bereitstellen von Clients Teams wird.</li><li>Auswerten von Endpunkten und Geräten sowie Ausführen und Wartung erforderlich.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Geräte für Microsoft Teams

Microsoft Teams kann für Besprechungen oder als Telefonsystem verwendet werden. Bei der Verwendung dieser Funktionen spielt das für Microsoft Teams verwendete Gerät eine wichtige Rolle für die Benutzerfreundlichkeit.

Benutzer, die einen integrierten PC-Lautsprecher und ein integriertes Mikrofon verwenden, empfinden diese Konfiguration möglicherweise als akzeptabel. In der Regel sind diese Geräte jedoch nicht für die Rauschunterdrückung optimiert, und Umgebungsgeräusche können sich auf andere Benutzer des Anrufs auswirken. Die Nutzung von für diese Szenarien optimierten Geräten kann eine hohe Qualität sicherstellen.

Alle Geräte müssen den Anforderungen der Benutzer entsprechen. Sie müssen Geräte wie beispielsweise Headsets auf die verschiedenen Personas und Anwendungsfälle in der Organisation abstimmen.
Im Rahmen des Planungsprozesses sollte eine Zuordnung von Personas zu Geräten erstellt werden.

Wenn Sie die Geräte ausgewählt haben, nehmen Sie sie zur endgültigen Validierung in den Pilottestplan auf. Nutzen Sie in der Pilotphase Umfragen, um Feedback zu sammeln, damit Sie sicherstellen können, dass Sie die optimale Gerätestrategie verwenden.

> [!NOTE]
> Zurzeit empfehlen wir die Verwendung von Geräten, die über das Skype for Business-Zertifizierungsprogramm zertifiziert wurden. Informationen zum Suchen nach Geräten, die unter diesem Programm zertifiziert sind, finden Sie [unter Microsoft Teams und](https://products.office.com/microsoft-teams/across-devices/devices) [USB-Audio- und -Videogeräte.](/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie die allgemeine Gerätestrategie Ihrer Organisation für Die Benutzer- und Besprechungsraumerfahrungen.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Führen Sie eine Übung zur Persona-zu-Geräte-Zuordnung für Ihre Organisation durch.</li><li>Dokumentieren Sie den Prozess zum Beziehen von Geräten für Benutzer und Besprechungsräume.</li><li>Dokumentieren Sie den Prozess für die Bereitstellung und Konfiguration von Geräten für Benutzer und Besprechungsräume.</li><li>Beschaffen Sie erste Geräte, um mit der Bereitstellung zu beginnen.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->