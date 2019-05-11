---
title: Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: In Skype für Business Server können mehrere Trunks mit einem einzelnen PSTN-Gateway zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht ein und dieselbe sind und Administratoren das Cmdlet "Get-CsTrunk" verwenden müssen, um Informationen zu einer einzelnen SIP-Trunk anzuzeigen.
ms.openlocfilehash: bf9229dba17b7b2e49eb9a05d9469f42c0b9b998
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930820"
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
