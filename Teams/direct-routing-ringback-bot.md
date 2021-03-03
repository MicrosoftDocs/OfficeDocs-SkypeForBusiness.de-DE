---
title: Einrichten des Ringbackbots für direktes Routing
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie den Ringbackbot für Direct Routing verwenden, um unerwartete Stille zu verhindern, die beim Erstellen eines Anrufs auftreten können.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827515"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Einrichten des Ringbackbots für direktes Routing

In diesem Artikel wird der Ringback-Bot beschrieben, mit dem Sie unerwartete Stille vermeiden können, die auftreten können, wenn das Erstellen von Anrufen länger dauert. Der Ringbackbot ist für direct Routing im Nicht-Medienumgehungsmodus verfügbar.

Manchmal dauern eingehende Anrufe aus dem öffentlichen Telefonnetz (PSTN) an die Teams-Clients länger als erwartet. Dies kann aus verschiedenen Gründen auftreten. In diesem Fall hört der Anrufer möglicherweise nichts, der Teams-Client klingelt nicht, und einige Telekommunikationsanbieter brechen den Anruf möglicherweise ab.

Der Ringbackbot hilft Dabei, unerwartete Stille zu vermeiden, die in diesem Szenario auftreten können. Bei eingehenden Anrufen aus dem PSTN an die Teams-Clients gibt der Ringbackbot ein unverkennbares Audiosignal für den Anrufer wieder, um anzugeben, dass Teams den Anruf anruft.

> [!NOTE]
> Der Ringbackbot generiert frühe Medien aus dem Teams-Back-End. In einigen Ländern und Regionen wird Ihnen der Anruf möglicherweise in Rechnung gestellt, wenn der Medienfluss beginnt.

## <a name="configure-the-ringback-bot"></a>Konfigurieren des Ringbackbots

Verwenden Sie das [Cmdlet "Set-CsOnlinePSTNGateway",](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) um eine zuvor definierte Konfiguration des Session Border Controllers (SBC) zu ändern, oder das [Cmdlet "New-CsOnlinePSTNGateway"](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) zum Erstellen einer neuen SBC-Konfiguration zusammen mit dem **Parameter "GenerateRingingWhileLocatingUser"** zum Konfigurieren des Ringbackbots:

- Um den Ringbackbot zu aktivieren, legen Sie den Parameter **"GenerateRingingWhileLocatingUser"** auf **$True.** Dies ist der Standardwert. 

- Um den Ringbackbot zu deaktivieren, legen Sie den **Parameter "GenerateRingingWhileLocatingUser"** auf **$False.** 

## <a name="related-topics"></a>Verwandte Themen

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
