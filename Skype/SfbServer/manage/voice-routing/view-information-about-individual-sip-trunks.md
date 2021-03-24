---
title: Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: In Skype for Business Server können mehrere Trunks einem einzelnen Get-CsTrunk zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht identisch sind, und Administratoren müssen das cmdlet Get-CsTrunk verwenden, um Informationen zu einem einzelnen SIP-Trunk anzeigen zu können.
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103001"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server

In Skype for Business Server können mehrere Trunks einem einzelnen #A0 zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht identisch sind und Administratoren das [Cmdlet Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzeigen zu können.

Das Get-CsTrunk-Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell.

**So zeigen Sie Informationen für alle Ihre SIP-Trunks an**

Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:

`Get-CsTrunk`

**So zeigen Sie Informationen für einen bestimmten SIP-Trunk an**

Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**Anzeigen von Informationen für alle einem Pool zugeordneten SIP-Trunks**

In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`