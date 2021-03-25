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
description: Erfahren Sie, wie Sie Microsoft Phone System Direct Routing konfigurieren, um Ihre lokale Telefonieinfrastruktur mit Microsoft Teams zu verbinden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122239"
---
# <a name="configure-direct-routing"></a>Konfigurieren von direktem Routing

Mit microsoft Phone System Direct Routing können Sie Ihre lokale Telefonieinfrastruktur mit Microsoft Teams verbinden. In diesem Artikel werden die schritte auf hoher Ebene aufgeführt, die zum Verbinden eines unterstützten lokalen Session Border Controllers (SBC) mit Direct Routing erforderlich sind, und es wird erläutert, wie Sie Teams-Benutzer für die Verwendung von Direct Routing zum Herstellen einer Verbindung mit dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) konfigurieren. Dieser Artikel enthält Links zu zugeordneten Artikeln, um Details zu erhalten.  

Informationen dazu, ob Direct Routing die richtige Lösung für Ihre Organisation ist, finden Sie unter [Telefonsystem-Direct-Routing](direct-routing-landing-page.md). Informationen zu den Voraussetzungen und der Planung Ihrer Bereitstellung finden Sie unter [Planen von Direct Routing](direct-routing-plan.md).

> [!Tip]
> Sie können sich auch die folgende Sitzung ansehen, um mehr über die Vorteile von Direct Routing zu erfahren, wie Sie das Routing planen und wie Sie es bereitstellen: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).

Um die in diesem Artikel erläuterten Schritte ausführen zu können, benötigen Administratoren einige Vertrautheit mit PowerShell-Cmdlets. Weitere Informationen zur Verwendung von PowerShell finden Sie unter [Einrichten Ihres Computers für Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Bevor Sie die Schritte in diesen Artikeln ausführen, empfiehlt Microsoft, dass Sie bestätigen, dass Ihr SBC bereits wie von Ihrem SBC-Anbieter empfohlen konfiguriert wurde: 

- [Dokumentation zur Audiocodes-Bereitstellung](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Dokumentation zur Oracle-Bereitstellung](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Dokumentation zur Bereitstellung von Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Te-Systems (Anynode)-Bereitstellungsdokumentation](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Dokumentation zur Metaswitchbereitstellung](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Eine vollständige Liste der unterstützten SBCs finden Sie unter Liste der für Direct [Routing zertifizierten Sitzungsgrenzcontroller.](direct-routing-border-controllers.md)

Führen Sie die folgenden Schritte aus, um Microsoft Phone System zu konfigurieren und Benutzern die Verwendung von Direct Routing zu ermöglichen: 

- **Schritt 1:** [Verbinden des SBC mit Microsoft Phone System und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md)
- **Schritt 2:** [Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail](direct-routing-enable-users.md)
- **Schritt 3:** [Konfigurieren des Sprachroutings](direct-routing-voice-routing.md)
- **Schritt 4:** [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Wenn Sie einen SBC für mehrere Mandanten konfigurieren, sollten Sie auch Konfigurieren eines SBC für [mehrere Mandanten lesen.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Verwandte Themen

[Direktes Routing für Telefonsysteme](direct-routing-landing-page.md)

[Planen von direktem Routing](direct-routing-plan.md)