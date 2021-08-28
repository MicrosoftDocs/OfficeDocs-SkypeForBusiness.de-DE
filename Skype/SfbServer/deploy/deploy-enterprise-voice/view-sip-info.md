---
title: Anzeigen von SIP-Trunkinformationen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Erfahren Sie, wie Sie Informationen zu SIP-Trunks in Skype for Business Server anzeigen.'
ms.openlocfilehash: f4bd3ba4560980243fefe06b49a8f4aaa4a9625e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624407"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>Skype for Business Server: Anzeigen von Informationen zu einzelnen SIP-Trunks 
 
**Zusammenfassung:** Erfahren Sie, wie Sie Informationen zu SIP-Trunks in Skype for Business Server anzeigen.
  
SIP-Trunks werden verwendet, um Skype for Business Server Voice over IP-Telefonnetzwerk mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) zu verbinden. In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet, und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt. Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch. Für Administratoren bedeutete dies, dass sie Informationen zu einem einzelnen SIP-Trunk anzeigen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufrufen.
  
In Skype for Business Server können nun jedoch mehrere Trunks einem einzelnen PSTN-Gateway zugewiesen werden. Dies bedeutet, dass Gateways und Trunks nicht mehr identisch sind. Dies bedeutet wiederum, dass Administratoren das neue [Cmdlet "Get-CsTrunk"](/powershell/module/skype/get-cstrunk) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>So zeigen Sie Informationen für alle SIP-Trunks an

- Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>So zeigen Sie Informationen zu einem bestimmten SIP-Trunk an

- Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Anzeigen von Informationen zu allen SIP-Trunks, die einem Pool zugewiesen sind

- In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
