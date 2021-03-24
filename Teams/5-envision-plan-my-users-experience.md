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
description: Wählen Sie Teams-Client-Apps aus, planen Sie die Endpunktqualität, erhalten Sie Empfehlungen zum Bereitstellen Wi-Fi Endpunkten und zum Auswählen von Audiogeräten.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d20d914ab6ceca1d264a23662c9c8a067798a82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094733"
---
# <a name="plan-my-users-experience"></a>Planen der Benutzererfahrung

Dieser Artikel bietet einen Überblick über die Anforderungen für die ordnungsgemäßen Identifizierung der Elemente Ihrer Cloud-Voicedienstbereitstellung, die sich direkt auf die Benutzererfahrung auswirken. Wenn Sie sich vor der Bereitstellung auf diese Elemente vorbereiten, erhöhen Sie ihre Chancen, erfolgreich eine qualitativ hochwertige und zuverlässige Benutzererfahrung zu bieten. 

## <a name="client-deployment"></a>Clientbereitstellung

Microsoft Teams verfügt über Clients für Web, Desktop (Windows und Mac) und Mobile (Android und iOS). Weitere Informationen zur Installation des Desktops (Windows und Mac) und mobiler Clients finden Sie unter [Clients für Microsoft Teams herunterladen.](./get-clients.md)

## <a name="client-updates"></a>Clientupdates

Einer der wichtigsten Vorteile von Teams ist, dass der Client automatisch auf dem neuesten Stand gehalten wird. Die Clients für PC und Mac werden mit einem Hintergrundprozess aktualisiert, der nach neuen Builds sucht und den neuen Client herunterlädt, wenn sich die App im Leerlauf befindet.

<!--ENDOFSECTION-->

## <a name="plan-for-endpoint-quality"></a>Planen der Endpunktqualität

Wie aus dem folgenden Diagramm zu sehen ist, stellen Endpunkte einen wichtigen Baustein für die Bereitstellung einer Qualitätserfahrung für Benutzer dar.

![Diagramm zur Beschreibung der drei Komponenten der Qualität](media/plan-my-users-experience-image1.png "Diagramm, in dem die drei Komponenten der Qualität und die Überlappung der Dienstverwaltung auf alle drei Komponenten beschrieben werden. Mit Fokus auf Endpunkten.")

Teams-Endpunkte können auf vielen Geräten ausgeführt werden, einschließlich PCs, Macs, Tablets und mobilen Geräten. Ein Teil der Erfahrung umfasst nicht nur das Gerät, sondern auch die Art und Weise, wie ein Benutzer eine Verbindung mit dem Gerät herstellt – beispielsweise mithilfe des integrierten Mikrofons/Lautsprechers, der Ohrhörer oder eines optimierten Headsets. Die Verwendung eines optimierten Headsets kann sich positiv auf die allgemeine Benutzerfreundlichkeit auswirken.

Die folgenden Anleitungen zur Endpunktplanung sollen Ihnen helfen, für Ihre Organisation ein erfolgreiches Onboarding in Microsoft Teams sicherzustellen.

## <a name="endpoint-capability"></a>Endpunktfunktionen

Der erste Teil der Planung besteht in der Sicherstellung, dass alle PCs und anderen Geräte in Ihrer Organisation Teams ausführen können. Dazu müssen Sie nicht nur die Hardwareanforderungen betrachten, sondern sich auch verdeutlichen, was außerdem im Hintergrund auf dem PC geschieht. Viele Organisationen führen weitere Software aus, beispielsweise Angriffserkennungssysteme und Antischadsoftware, die Basisleistung eines Geräts beeinflussen kann.

Informationen zu den Softwareanforderungen für Teams-Clients auf jeder Plattform (Web, Desktop und Mobile) finden Sie unter [Clients für Microsoft Teams herunterladen.](./get-clients.md)

## <a name="endpoint-firewalls"></a>Endpunktfirewalls

Clientseitige Firewalls können erhebliche Auswirkungen auf die Benutzerfreundlichkeit haben.
Clientseitige Firewalls können nicht nur verhindern, dass ein Anruf aufgebaut wird, sondern sich auch auf die Anrufqualität auswirken. Konfigurieren Sie die entsprechenden Ausschlüsse für die Clientfirewall basierend auf den Informationen in [Microsoft 365- oder Office 365-URLs und -IP-Adressbereichen.](/microsoft-365/enterprise/urls-and-ip-address-ranges) Ihr Drittanbieter sollte über konkrete Anleitungen zum Erstellen der Ausschlüsse verfügen.

>[!NOTE]
> Microsoft Teams aktualisiert automatisch die Windows-Firewall mit einer entsprechenden Firewallkonfiguration.

## <a name="wi-fi-recommendations-for-endpoints"></a>WLAN-Empfehlungen für Endpunkte

Es ist eine wichtige Planung erforderlich, um ein optimiertes netzwerk Wi-Fi, um Arbeitsauslastungen in Echtzeit in Microsoft Teams zu unterstützen. Die folgenden Abschnitte enthalten einige allgemeine Anleitungen, die Ihnen helfen können, häufige Fallstricke bei der Planung von Endpunkten zu vermeiden.

### <a name="wi-fi-drivers"></a>WLAN-Treiber

Einige Wi-Fi können problematisch sein. So kann beispielsweise ein Treiber ein sehr aggressives Verhalten beim Roaming zwischen Zugriffspunkten aufweisen, was zu einer mangelhaften Anrufqualität führt.
Dies ist nicht üblich, aber es ist wichtig sicherzustellen, dass Wi-Fi Treiber auf dem PC vor der Bereitstellung aktualisiert und getestet wurden.

### <a name="wi-fi-bands"></a>WLAN-Bänder

WLAN-Geräte verwenden heute im Wesentlichen zwei Bänder: 2,4 GHz und 5,0 GHz. Wenn Ihre Organisation beide Bänder bereitstellt, sollten Sie die Treibereinstellungen so konfigurieren, dass das 5,0-GHz-Band bevorzugt wird. Dieses Band ist im Hinblick auf den Durchsatz erheblich dichter und von den im 2,4-GHz-Band auftretenden Störungen weniger betroffen.
Bei dieser Empfehlung wird angenommen, dass Sie das 5,0-GHz-Netzwerkband richtig optimiert haben.

### <a name="wi-fi-radio-type"></a>WLAN-Funkstandard

Planen Sie mit Geräten, die neueren WLAN-Funkstandards unterstützen. Sie können eine sehr gute WLAN-Leistung erzielen, wenn Sie auf den bereitgestellten Geräten 802.11ac oder einen neueren Standard nutzen.

### <a name="wireless-avoidance"></a>WLAN-Vermeidung

Manche Organisationen möchten WLAN ganz vermeiden. In diesem Zusammenhang wird Benutzern manchmal empfohlen, eine direkte Verbindung mit einem Kabelnetzwerk herzustellen. In manchen Fällen sieht die Reihenfolge der Netzwerkbindungen eine Bevorzugung der WLAN-Verbindung vor, die dann weiterhin verwendet wird, obwohl der PC über die Kabelverbindung verbunden ist. Wenn Sie dieses unbeabsichtigte Verhalten vermeiden möchten, konfigurieren Sie die Bindungsreihenfolge so, dass dieses Szenario vermieden wird.

### <a name="80211-power-save-protocol"></a>802.11 Power Save-Protokoll

Wenn Ihre Organisation funklose Zugriffspunkte oder Router verwendet, die das Power Save-Protokoll 802.11 nicht unterstützen, kann es zu ausgelassenen Anrufen oder einer schlechten Anrufqualität in Microsoft Teams, die auf Windows-Geräten ausgeführt werden. Wenn die WLAN-Zugriffspunkte oder -Router nicht aktualisiert werden können, sollten Sie auf Geräten, die mit Akku betrieben werden, die Windows-Einstellungen für den Energiesparplan aktualisieren. Weitere Details und Konfigurationsanleitungen finden Sie im folgenden [Supportartikel](https://support.microsoft.com/help/928152/you-may-experience-connectivity-issues-or-performance-issues-when-you).

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Welche Teams-Clients werden in Ihrer Organisation bereitgestellt?</li><li>Wie stellen Sie ihre Teams-Clients zunächst für Ihre Benutzer zur Verfügung?</li><li>Wer ist für die Auswertung von Endpunkten und Geräten verantwortlich, um zu überprüfen, ob sie den Teams-Anforderungen für eine Qualitätserfahrung entsprechen?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie den Prozess, der zum Bereitstellen von Teams-Clients befolgt wird.</li><li>Auswerten von Endpunkten und Geräten sowie Ausführen und Behebung erforderlich.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="devices-for-teams"></a>Geräte für Microsoft Teams

Microsoft Teams kann für Besprechungen oder als Telefonsystem verwendet werden. Bei der Verwendung dieser Funktionen spielt das für Microsoft Teams verwendete Gerät eine wichtige Rolle für die Benutzerfreundlichkeit.

Benutzer, die einen integrierten PC-Lautsprecher und ein integriertes Mikrofon verwenden, empfinden diese Konfiguration möglicherweise als akzeptabel. In der Regel sind diese Geräte jedoch nicht für die Rauschunterdrückung optimiert, und jede Art von Umgebungsgeräusch kann sich auf andere Benutzer des Anrufs nach unten auswirken. Die Nutzung von für diese Szenarien optimierten Geräten kann eine hohe Qualität sicherstellen.

Alle Geräte müssen den Anforderungen der Benutzer entsprechen. Sie müssen Geräte wie beispielsweise Headsets auf die verschiedenen Personas und Anwendungsfälle in der Organisation abstimmen.
Im Rahmen des Planungsprozesses sollte eine Zuordnung von Personas zu Geräten erstellt werden.

Wenn Sie die Geräte ausgewählt haben, nehmen Sie sie zur endgültigen Validierung in den Pilottestplan auf. Nutzen Sie in der Pilotphase Umfragen, um Feedback zu sammeln, damit Sie sicherstellen können, dass Sie die optimale Gerätestrategie verwenden.

> [!NOTE]
> Zurzeit empfehlen wir die Verwendung von Geräten, die über das Skype for Business-Zertifizierungsprogramm zertifiziert wurden. Informationen zu Geräten, die unter diesem Programm zertifiziert sind, finden Sie unter [Microsoft Teams-Geräte](https://products.office.com/microsoft-teams/across-devices/devices) und [USB-Audio- und Videogeräte.](/SkypeForBusiness/certification/devices-usb-devices)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie über die allgemeine Gerätestrategie Ihrer Organisation für Benutzer- und Besprechungsraumerfahrungen.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Führen Sie eine Persona-zu-Gerät-Zuordnungsübung für Ihre Organisation aus.</li><li>Dokumentieren Sie den Prozess zum Abrufen von Geräten für Benutzer und Besprechungsräume.</li><li>Dokumentieren Sie den Prozess zum Bereitstellen und Konfigurieren von Geräten für Benutzer und Besprechungsräume.</li><li>Beschaffen Sie erste Geräte, um ihre Bereitstellung zu beginnen.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->