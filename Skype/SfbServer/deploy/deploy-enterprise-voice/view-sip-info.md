---
title: Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Informationen zum Anzeigen von Informationen zu SIP-Trunks in Skype for Business Server.'
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103231"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen zu einzelnen SIP-Trunks in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Informationen zu SIP-Trunks in Skype for Business Server anzeigen.
  
SIP-Trunks werden verwendet, um skype for Business Server Voice over IP phone network mit dem Public Switched Telephone Network (PSTN) zu verbinden. In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet, und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt. Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch. Für Administratoren bedeutete dies, dass sie Informationen zu einem einzelnen SIP-Trunk anzeigen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufrufen.
  
In Skype for Business Server können nun jedoch mehrere Trunks einem einzelnen #A0 zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht mehr eins und dasselbe sind. Das bedeutet wiederum, dass Administratoren das neue [Cmdlet Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzeigen zu können.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>So zeigen Sie Informationen für alle Ihre SIP-Trunks an

- Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>So zeigen Sie Informationen für einen bestimmten SIP-Trunk an

- Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Anzeigen von Informationen für alle EINEM Pool zugewiesenen SIP-Trunks

- In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```