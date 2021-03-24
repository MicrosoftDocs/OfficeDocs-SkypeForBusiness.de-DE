---
title: Einrichten des Ringback-Bots für Direct Routing
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie den Ringback-Bot für Direct Routing verwenden, um unerwartete Stille zu verhindern, die auftreten können, wenn ein Anruf eingerichtet wird.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098421"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Einrichten des Ringback-Bots für Direct Routing

In diesem Artikel wird der Ringback-Bot beschrieben, mit dem Sie unerwartete Stille vermeiden können, die auftreten können, wenn es länger dauert, bis Anrufe eingerichtet werden. Der Ringback-Bot steht für Direct Routing im Modus "Umgehungsmodus ohne Medien" zur Verfügung.

Manchmal können eingehende Anrufe aus dem öffentlichen Telefonnetz (PSTN) zu Teams-Clients länger dauern als erwartet. Dies kann aus verschiedenen Gründen auftreten. In diesem Fall hört der Anrufer möglicherweise nichts, der Teams-Client klingelt nicht, und einige Telekommunikationsanbieter können den Anruf abbrechen.

Der Ringback-Bot hilft, unerwartete Stille zu vermeiden, die in diesem Szenario auftreten können. Bei eingehenden Anrufen aus dem PSTN an Teams-Clients gibt der Ringback-Bot ein unverwechselbares Audiosignal an den Anrufer ab, um anzugeben, dass Teams den Anruf vor sich hat.

> [!NOTE]
> Der Ringback-Bot generiert frühe Medien aus dem Teams-Back-End. In einigen Ländern und Regionen wird ihnen möglicherweise der Anruf in Rechnung gestellt, wenn die Medien fließen.

## <a name="configure-the-ringback-bot"></a>Konfigurieren des Ringback-Bots

Verwenden Sie das [Cmdlet Set-CsOnlinePSTNGateway,](/powershell/module/skype/set-csonlinepstngateway) um eine zuvor definierte SBC-Konfiguration (Session Border Controller) oder das [New-CsOnlinePSTNGateway-Cmdlet](/powershell/module/skype/new-csonlinepstngateway) zu ändern, um eine neue SBC-Konfiguration zusammen mit dem **Parameter GenerateRingingWhileLocatingUser** zum Konfigurieren des Ringback-Bots zu erstellen:

- Um den Ringback-Bot zu aktivieren, legen Sie **den Parameter GenerateRingingWhileLocatingUser** auf **$True.** Dies ist der Standardwert. 

- Um den Ringback-Bot zu deaktivieren, legen Sie **den Parameter GenerateRingingWhileLocatingUser** auf **$False.** 

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)