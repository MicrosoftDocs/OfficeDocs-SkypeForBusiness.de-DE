---
title: Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server können mehrere Trunks einem einzelnen PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht identisch sind, und Administratoren müssen das Cmdlet Get-cstrunk "verwenden, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048178"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server

In Skype for Business Server können mehrere Trunks einem einzelnen PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht identisch sind und dass Administratoren das Cmdlet [Get-cstrunk "](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.

Das Cmdlet Get-cstrunk "kann entweder über die Skype for Business Server Management-Shell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.

**So zeigen Sie Informationen für alle SIP-Trunks an**

Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:

`Get-CsTrunk`

**So zeigen Sie Informationen für einen bestimmten SIP-Trunk an**

Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Anzeigen von Informationen für alle einem Pool zugeordneten SIP-Trunks**

In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
