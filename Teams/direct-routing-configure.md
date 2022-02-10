---
title: Konfigurieren von direktem Routing
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
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
description: Hier erfahren Sie, wie Sie Microsoft Direct Routing so konfigurieren, dass Ihre lokale Telefonieinfrastruktur mit ihrer Telefonie Teams Telefonsystem.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518577"
---
# <a name="configure-direct-routing"></a>Konfigurieren von direktem Routing

Mit Direct Routing können Sie Ihre lokale Telefonie-Infrastruktur mit Ihrem Microsoft Teams. In diesem Artikel werden die auf hoher Ebene erforderlichen Schritte zum Verbinden eines unterstützten lokalen Session Border Controller (SBC) mit Direct Routing sowie das Konfigurieren von Teams-Benutzern für die Verwendung von Direct Routing zum Herstellen einer Verbindung mit dem PstN (Public Switched Telephone Network) aufgeführt. In diesem Artikel finden Sie Links zu zugehörigen Artikeln, um weitere Informationen zu erhalten.  

Informationen dazu, ob Direct Routing die richtige Lösung für Ihre Organisation ist, finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md). Informationen zu den Voraussetzungen und zur Planung Ihrer Bereitstellung finden Sie unter [Planen von Direct-Routing](direct-routing-plan.md).

Administratoren müssen mit PowerShell-Cmdlets vertraut sein, um die in diesem Artikel erläuterten Schritte ausführen zu können. Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Bevor Sie die Schritte in diesen Artikeln ausführen, empfiehlt Microsoft Ihnen, zu bestätigen, dass Ihr SBC von Ihrem SBC-Anbieter empfohlen bereits konfiguriert wurde: 

- [AudioCodes-Bereitstellungsdokumentation](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Dokumentation zur Bereitstellung von Kommunikationen im Menüband](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Dokumentation zur TE-Systems-Bereitstellung (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Dokumentation zur Metaswitch-Bereitstellung](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Eine vollständige Liste der unterstützten SBCs finden Sie unter [Session Border Controller certified for Direct Routing (Session Border Controller certified for Direct Routing](direct-routing-border-controllers.md)).

Führen Sie die folgenden Telefonsystem aus, um benutzer die Verwendung von Direct-Routing zu konfigurieren und Benutzern die Verwendung von Direct-Routing zu ermöglichen: 

- **Schritt 1:** [Verbinden des SBC mit Telefonsystem und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md)
- **Schritt 2:** [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)
- **Schritt 3:** [Konfigurieren der Anrufrouting](direct-routing-voice-routing.md)
- **Schritt 4:** [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Wenn Sie einen SBC für mehrere Mandanten konfigurieren, sollten Sie auch Konfigurieren eines [SBC für mehrere Mandanten lesen](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Verwandte Themen

[Planen Ihrer Sprachlösung](cloud-voice-landing-page.md)

[PSTN-Konnektivitätsoptionen](pstn-connectivity.md)

[Planen von direktem Routing](direct-routing-plan.md)