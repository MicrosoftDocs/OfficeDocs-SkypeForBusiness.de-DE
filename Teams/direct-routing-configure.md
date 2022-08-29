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
description: Erfahren Sie, wie Sie Microsoft Direct Routing so konfigurieren, dass Ihre lokale Telefonieinfrastruktur mit dem Microsoft Teams-Telefonsystem verbunden wird.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cf6a180b558edad23450fad3991ee2c646f6cf55
ms.sourcegitcommit: 830357674103c0c5c99bd73d40261afe02a2da49
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2022
ms.locfileid: "67291401"
---
# <a name="configure-direct-routing"></a>Konfigurieren von direktem Routing

Mit Direct Routing können Sie Ihre lokale Telefonieinfrastruktur mit Microsoft Teams verbinden. Der Artikel enthält die allgemeinen Schritte, die zum Verbinden eines unterstützten lokalen Session Border Controller (SBC) mit Direct Routing und zum Konfigurieren von Teams-Benutzern zur Verwendung von Direct Routing zum Herstellen einer Verbindung mit dem PSTN (Public Switched Telephone Network) erforderlich sind. Dieser Artikel enthält Links zu zugehörigen Artikeln für Details.  

Informationen dazu, ob Direct Routing die richtige Lösung für Ihre Organisation ist, finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md). Informationen zu den Voraussetzungen und zur Planung Ihrer Bereitstellung finden Sie unter [Planen von Direct Routing](direct-routing-plan.md).

Um die in diesem Artikel erläuterten Schritte auszuführen, benötigen Administratoren einige Kenntnisse mit PowerShell-Cmdlets. Weitere Informationen zur Verwendung von PowerShell finden [Sie unter Einrichten Ihres Computers für Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Bevor Sie die Schritte in diesen Artikeln ausführen, empfiehlt Microsoft, zu bestätigen, dass Ihr SBC bereits wie von Ihrem SBC-Anbieter empfohlen konfiguriert wurde: 

- [Dokumentation zur AudioCodes-Bereitstellung](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle-Bereitstellungsdokumentation](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Bereitstellungsdokumentation für die Menübandkommunikation](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Bereitstellungsdokumentation für TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Dokumentation zur Metaswitch-Bereitstellung](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Eine vollständige Liste der unterstützten SBCs finden Sie unter [Session Border Controller, die für Direct Routing zertifiziert sind](direct-routing-border-controllers.md).

Führen Sie die folgenden Schritte aus, um das Telefonsystem zu konfigurieren und Benutzern die Verwendung von Direct Routing zu ermöglichen: 

- **Schritt 1:** [Verbinden des SBC mit dem Telefonsystem und Überprüfen der Verbindung](direct-routing-connect-the-sbc.md)
- **Schritt 2:** [Aktivieren von Benutzern für Direct Routing, VoIP und Voicemail](direct-routing-enable-users.md)
- **Schritt 3:** [Konfigurieren der Anrufweiterleitung](direct-routing-voice-routing.md)
- **Schritt 4:** [Übersetzen von Zahlen in ein alternatives Format](direct-routing-translate-numbers.md) 

Wenn Sie einen SBC für mehrere Mandanten konfigurieren, sollten Sie auch " [Konfigurieren eines SBC für mehrere Mandanten"](direct-routing-sbc-multiple-tenants.md) lesen.

## <a name="support-boundaries"></a>Supportgrenzen
Microsoft unterstützt das Telefonsystem mit Direct Routing nur, wenn es mit zertifizierten Geräten verwendet wird. Wenn Probleme auftreten, müssen Sie sich zuerst an den Kundensupport Ihres SBC-Anbieters wenden. Bei Bedarf wird der SBC-Lieferant das Problem über interne Kanäle an Microsoft eskalieren. Microsoft behält sich das Recht vor, Supportfälle abzulehnen, in denen ein nicht zertifiziertes Gerät über Direct Routing mit dem Telefonsystem verbunden ist. Wenn Microsoft feststellt, dass das Direct Routing-Problem eines Kunden mit dem SBC-Gerät eines Lieferanten zusammenhängt, muss der Kunde den SBC-Anbieter erneut engagieren, um Support zu erhalten.

## <a name="related-topics"></a>Verwandte Themen

[Planen Ihrer VoIP-Lösung](cloud-voice-landing-page.md)

[PSTN-Konnektivitätsoptionen](pstn-connectivity.md)

[Planen von direktem Routing](direct-routing-plan.md)
