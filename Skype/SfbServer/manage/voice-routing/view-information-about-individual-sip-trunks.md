---
title: Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype für Business Server können mehrere Trunks mit einem einzelnen PSTN-Gateway zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht ein und dieselbe sind und Administratoren das Cmdlet "Get-CsTrunk" verwenden müssen, um Informationen zu einer einzelnen SIP-Trunk anzuzeigen.
ms.openlocfilehash: c8463fb23ea09167d760a1b9068235da871792c2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222793"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server

In Skype für Business Server können mehrere Trunks mit einem einzelnen PSTN-Gateway zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht ein und dieselbe sind und Administratoren das Cmdlet " [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) " verwendet werden müssen, um Informationen zu einer einzelnen SIP-Trunk anzuzeigen.

Das Cmdlet "Get-CsTrunk" kann die Skype für Business Server-Verwaltungsshell oder von einer Remotesitzung von Windows PowerShell ausgeführt werden.

**Anzeigen von Informationen für alle SIP-Trunks**

Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:

`Get-CsTrunk`

**Anzeigen von Informationen für einen bestimmten SIP-Trunk**

Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Anzeigen von Informationen für alle einem Pool zugewiesenen SIP-Trunks**

In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`