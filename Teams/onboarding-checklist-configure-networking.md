---
title: Onboardingcheckliste für das Konfigurieren von Netzwerken für Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Befolgen Sie die grundlegenden Aufgaben und Aktivitäten in dieser Checkliste, wenn Sie Ihr Netzwerk für Teams konfigurieren.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97a59ede284474069f39dc166d77d0a4a6ebc167
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862885"
---
# <a name="configure-networking"></a>Netzwerk konfigurieren

| Nein | Aktivität oder Aufgabe | Beschreibung | Abgeschlossen? | Weitere Informationen |
|----|--------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Überprüfen der Netzwerkanforderungen für Teams | Sie haben eine Gesamtübersicht über Ihre Netzwerkanforderungen, bevor Sie in die Netzwerkdetails eingehen. | | [Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)                                                               |
| 2  | Bereitstellen des Network Readiness-Workshops | Führen Sie eine Netzwerk Bereitschafts Beurteilung durch. | |  |
| 3  | Verwenden des Network Planner | Durchführen der Netzwerkband breiten Planung | | |
| 4  | Überprüfen der für die Benutzerkonnektivität erforderlichen NAT-Poolgröße | Stellen Sie sicher, dass den NAT-Pools adäquate öffentliche IP-Adressen zugewiesen sind, um die Port Erschöpfung zu verhindern. Die Port Erschöpfung trägt dazu bei, dass interne Benutzer und Geräte nicht mit dem Office 365-Dienst verbunden werden können. <br/><br/>Verbindungsprobleme sind eine der Hauptursachen für Benutzer wahrnehmungsprobleme bei Cloud-Diensten. | | [NAT-Unterstützung mit Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9) |
| 5  | Implementieren des effizientesten Routings an Microsoft-Rechenzentren | Ermitteln Sie Standorte, die lokale oder regionale Ausgangspunkte verwenden können, um die Verbindung mit dem Microsoft-Netzwerk so effizient wie möglich herzustellen. <br/><br/>Der Artikel in der Spalte **zusätzliche Informationen** beschreibt, wie Clients die Features in der Office 365-Namensauflösung und dem IP-Routing nutzen können, um effizient mit dem nächstgelegenen regionalen Rechenzentrum verbunden zu werden. | | [Office 365-Client Konnektivität](https://support.office.com/article/Client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b) |
| 6  | Konfigurieren der für die Verbindung mit Teams angeforderten Firewall-Ports | Überprüfen Sie die Office 365-URLs und-IPS, um die Firewall-Ports zu identifizieren und zu testen, die für die Konnektivität zwischen lokalen Clients und Servern und Office 365-Diensten erforderlich sind. <br/><br/>Für eine unterstützte Umgebung müssen Sie alle Ports auf Ihren Firewalls öffnen. Wenn Sie einige Ports oder Bereiche nicht öffnen, wirkt sich dies negativ auf die Benutzererfahrung aus. Konfigurieren Sie die Medienanschlüsse auf Ihren Firewalls basierend auf den Anleitungen in der Spalte **zusätzliche Informationen** . | | [Office 365-URLs und-IP-Adressen – Microsoft Teams](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) |
| 7  | Konfigurieren von Proxyservern | Konfigurieren Sie Ihre Umgebung so, dass Proxy Server umgangen werden, und Sie können Benutzer mithilfe von UDP direkt mit Office 365 verbinden, um die beste Audio-und Videoqualität zu erzielen. Wenn Echt Zeit Medien gezwungen sind, einen Proxy Server zu durchlaufen, wird der Medien Stapel in Microsoft Teams gezwungen, auf TCP zurückzukehren, was sich negativ auf die Qualität auswirkt. <br/><br/>Für eine optimale Benutzererfahrung sollten Sie immer UDP über TCP bevorzugen. | | [Planen von Dienstverwaltung und-Qualität](https://docs.microsoft.com/MicrosoftTeams/prepare-network) |
| 8  | Konfigurieren des Split-Tunnel-VPN | Wir empfehlen, dass Sie einen alternativen Pfad für Teams-Datenverkehr bereitstellen, der das VPN umgeht, das gemeinhin als *Split-Tunnel-VPN*bezeichnet wird. Split-Tunneling bedeutet, dass der Datenverkehr für Office 365 das VPN nicht durchlaufen, sondern direkt zu Office 365 wechselt. Diese Änderung wirkt sich positiv auf die Qualität aus, bietet aber auch den sekundären Vorteil, dass die Last für die VPN-Geräte und das Netzwerk der Organisation reduziert wird. | | Wenn Sie ein VPN mit geteilten Tunneln implementieren möchten, erkundigen Sie sich bei Ihrem VPN-Anbieter nach Konfigurationsdetails. |
| 9  | Konfigurieren der Paket Priorisierung mithilfe von QoS | QoS sollte in allen Segmenten eines verwalteten Netzwerks implementiert werden. Auch wenn ein Netzwerk ausreichend für die Bandbreite bereitgestellt wurde, bietet QoS Risikominderung bei unvorhergesehenen Netzwerkereignissen. Wenn QoS implementiert ist, wird der VoIP-Datenverkehr priorisiert, damit sich diese unvorhergesehenen Ereignisse nicht negativ auf die Qualität auswirken. | | [Planen von Dienstverwaltung und-Qualität](https://docs.microsoft.com/MicrosoftTeams/prepare-network) <br/><br/>[Quality of Service in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams) |
| 10 | Optimieren von Wi-Fi-Netzwerken für Qualität und Leistung | Wenn Sie Ihr Wi-Fi-Netzwerk optimieren, kommen verschiedene Faktoren ins Spiel: <ul><li>Implementieren von QoS oder Wi-Fi-Multimedia (WMM), um sicherzustellen, dass der Mediendatenverkehr über die WLAN-Netzwerke priorisiert wird.</li><li>Planen und Optimieren von WLAN-Bändern und Platzierung von Zugriffspunkten. Der 2,4-GHz-Bereich bietet je nach Position des Zugriffspunkts möglicherweise eine ausreichende Leistung.</li></ul> Wenden Sie sich an Ihren WLAN-Anbieter, um bestimmte Anleitungen zu erhalten. | | [WLAN-Empfehlungen für Endpunkte](https://docs.microsoft.com/MicrosoftTeams/prepare-network#wi-fi-recommendations-for-endpoints) |
| 11 | Überprüfen der Netzwerkkonnektivität mithilfe des Tools für die Netzwerkbewertung | Verwenden Sie das Netzwerk Bewertungs Tool für Skype for Business und Teams, um die Konnektivität zu allen IP-Adressen und Ports zu testen, die in Skype for Business Online und in Teams-anrufen und-Besprechungen verwendet werden. Laden Sie das Tool herunter, und lesen Sie Usage. docx, um Details zur Verwendung des Tools und zum Interpretieren der Testergebnisse anzuzeigen. Wir empfehlen, dass Sie das Tool von einem Client-PC an jedem Standort ausführen, an dem Teams verwendet werden. | | [Netzwerk Bewertungs Tool für Skype for Business und Teams](https://go.microsoft.com/fwlink/?linkid=855799) |
