---
title: Konfigurieren von direktem Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Microsoft-Telefon Direktes Systemrouting konfigurieren, um Ihre lokale Telefonieinfrastruktur mit Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122239"
---
# <a name="configure-direct-routing"></a>Konfigurieren von direktem Routing

Microsoft-Telefon Mit Dem Direct-Routing des Systems können Sie Ihre lokale Telefonie-Infrastruktur mit ihrem Microsoft Teams. In diesem Artikel werden die auf hoher Ebene erforderlichen Schritte zum Verbinden eines unterstützten lokalen Session Border Controller (SBC) mit Direct Routing sowie das Konfigurieren von Teams-Benutzern für die Verwendung von Direct Routing zum Herstellen einer Verbindung mit dem PstN (Public Switched Telephone Network) aufgeführt. In diesem Artikel finden Sie Links zu zugehörigen Artikeln, um details zu erfahren.  

Informationen dazu, ob Direct-Routing die richtige Lösung für Ihre Organisation ist, finden Sie unter verwenden [Telefonsystem Direct-Routing.](direct-routing-landing-page.md) Informationen zu den Voraussetzungen und zur Planung Ihrer Bereitstellung finden Sie unter [Planen von Direct-Routing.](direct-routing-plan.md)

> [!Tip]
> In der folgenden Sitzung erfahren Sie außerdem mehr über die Vorteile von Direct-Routing, die Planung und die Bereitstellung: [Direct-Routing in Microsoft Teams.](https://aka.ms/teams-direct-routing)

Administratoren müssen mit PowerShell-Cmdlets vertraut sein, um die in diesem Artikel erläuterten Schritte ausführen zu können. Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten des Computers für Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Bevor Sie die Schritte in diesen Artikeln ausführen, empfiehlt Microsoft Ihnen, zu bestätigen, dass Ihr SBC von Ihrem SBC-Anbieter empfohlen bereits konfiguriert wurde: 

- [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Dokumentation zur Bereitstellung von Kommunikationen im Menüband](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Dokumentation zur TE-Systems-Bereitstellung (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Dokumentation zur Metaswitch-Bereitstellung](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Eine vollständige Liste der unterstützten SBCs finden Sie unter Liste [der Session Border Controller, die für Direct Routing zertifiziert sind.](direct-routing-border-controllers.md)

Führen Sie die folgenden Microsoft-Telefon aus, um das System zu konfigurieren und Benutzern die Verwendung von Direct-Routing zu ermöglichen: 

- **Schritt 1:** [Verbinden des SBC mit Microsoft-Telefon System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md)
- **Schritt 2:** [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)
- **Schritt 3:** [Konfigurieren von Voice Routing](direct-routing-voice-routing.md)
- **Schritt 4:** [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Wenn Sie einen SBC für mehrere Mandanten konfigurieren, sollten Sie auch Konfigurieren eines SBC für [mehrere Mandanten lesen.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Verwandte Themen

[Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)

[Planen von direktem Routing](direct-routing-plan.md)