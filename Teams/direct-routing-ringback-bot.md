---
title: Einrichten des Begrüssungs-bot für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie den Rückruf-bot für das direkte Routing verwenden, um unerwartete Stille zu verhindern, die auftreten können, wenn ein Anruf eingerichtet wird.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1db113a610c153f821a0d92187744e6ca34e3ce3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951190"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Einrichten des Begrüssungs-bot für direktes Routing

In diesem Artikel wird der Begrüssungs-bot beschrieben, mit dem Sie unerwartete Stille vermeiden können, die auftreten können, wenn es längere Zeit dauert, bis die Anrufe eingerichtet werden. Der Rückruf-bot steht für das direkte Routing im nicht-Media-Bypass-Modus zur Verfügung.

Manchmal können eingehende Anrufe aus dem PSTN (Public Switched Telephone Network) an Teams-Clients länger als erwartet dauern. Dies kann aus verschiedenen Gründen erfolgen. In diesem Fall hört der Anrufer möglicherweise nichts, der Team-Client klingelt nicht und der Anruf kann von einigen Telekommunikationsanbietern abgebrochen werden.

Der Rückruf-bot hilft, unerwartete Stille zu vermeiden, die in diesem Szenario auftreten können. Für eingehende Anrufe vom PSTN an Teams-Clients spielt der Rückruf-bot ein unverwechselbares Audiosignal an den Anrufer ab, um anzugeben, dass die Mannschaft den Anruf annimmt.

> [!NOTE]
> Der Rückruf-bot generiert frühe Medien aus dem Back-End von Teams. In einigen Ländern und Regionen wird Ihnen möglicherweise der Anruf in Rechnung gestellt, wenn das Medium in den Fluss geht.

## <a name="configure-the-ringback-bot"></a>Konfigurieren des Rückruf-bot

Verwenden Sie die Cmdlets " [Satz-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) " und " [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) " zusammen mit dem **GenerateRingingWhileLocatingUser** -Parameter, um den Rückruf-bot zu konfigurieren.

Um den Rückruf-bot zu aktivieren, setzen Sie den **GenerateRingingWhileLocatingUser** -Parameter auf **$true**. Dies ist der Standardwert. 

Um den Rückruf-bot zu deaktivieren, setzen Sie den **GenerateRingingWhileLocatingUser** -Parameter auf **$false**. 

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)