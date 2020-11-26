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
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420955"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Einrichten des Begrüssungs-bot für direktes Routing

In diesem Artikel wird der Begrüssungs-bot beschrieben, mit dem Sie unerwartete Stille vermeiden können, die auftreten können, wenn es längere Zeit dauert, bis die Anrufe eingerichtet werden. Der Rückruf-bot steht für das direkte Routing im nicht-Media-Bypass-Modus zur Verfügung.

Manchmal können eingehende Anrufe aus dem PSTN (Public Switched Telephone Network) an Teams-Clients länger als erwartet dauern. Dies kann aus verschiedenen Gründen erfolgen. In diesem Fall hört der Anrufer möglicherweise nichts, der Team-Client klingelt nicht, und einige Telekommunikationsanbieter kündigen den Anruf möglicherweise an.

Der Rückruf-bot hilft, unerwartete Stille zu vermeiden, die in diesem Szenario auftreten können. Für eingehende Anrufe vom PSTN an Teams-Clients spielt der Rückruf-bot ein unverwechselbares Audiosignal an den Anrufer ab, um anzugeben, dass die Mannschaft den Anruf annimmt.

> [!NOTE]
> Der Rückruf-bot generiert frühe Medien aus dem Back-End von Teams. In einigen Ländern und Regionen wird Ihnen möglicherweise der Anruf in Rechnung gestellt, wenn das Medium in den Fluss geht.

## <a name="configure-the-ringback-bot"></a>Konfigurieren des Rückruf-bot

Verwenden Sie das Cmdlet " [festlegen-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) ", um eine zuvor definierte SBC-Konfiguration (Session Border Controller) zu ändern, oder das Cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) , um eine neue SBC-Konfiguration zusammen mit dem **GenerateRingingWhileLocatingUser** -Parameter zum Konfigurieren des Rückruf-bot zu erstellen:

- Um den Rückruf-bot zu aktivieren, setzen Sie den **GenerateRingingWhileLocatingUser** -Parameter auf **$true**. Dies ist der Standardwert. 

- Um den Rückruf-bot zu deaktivieren, setzen Sie den **GenerateRingingWhileLocatingUser** -Parameter auf **$false**. 

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
