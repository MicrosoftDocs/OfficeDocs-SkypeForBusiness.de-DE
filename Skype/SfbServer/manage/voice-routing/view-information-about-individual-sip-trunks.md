---
title: Anzeigen von Informationen zu einzelnen SIP-Stämmen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype for Business Server können mehrere Trunks einem einzigen PSTN-Gateway zugewiesen werden. Das bedeutet, dass Gateways und Trunks nicht identisch sind und Administratoren das Cmdlet "Get-CsTrunk" verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274877"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen zu einzelnen SIP-Stämmen in Skype for Business Server

In Skype for Business Server können mehrere Trunks einem einzigen PSTN-Gateway zugewiesen werden. Das bedeutet, dass Gateways und Trunks nicht identisch sind und dass Administratoren das Cmdlet " [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) " verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.

Das Cmdlet "Get-CsTrunk" kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

**Anzeigen von Informationen für alle SIP-Trunks**

Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:

`Get-CsTrunk`

**Anzeigen von Informationen für einen bestimmten SIP-Trunk**

Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Anzeigen von Informationen zu allen SIP-Stämmen, die einem Pool zugewiesen sind**

In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
