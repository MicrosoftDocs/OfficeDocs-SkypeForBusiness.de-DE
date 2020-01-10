---
title: Anzeigen von Informationen zu einzelnen SIP-Stämmen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Informationen zu SIP-Stämmen in Skype for Business Server anzeigen können.'
ms.openlocfilehash: 366e03c1a3ceef345a52bca6e038c9311fcc3003
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001125"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen zu einzelnen SIP-Stämmen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Informationen zu SIP-Stämmen in Skype for Business Server anzeigen können.
  
SIP-Trunks werden verwendet, um das Skype for Business Server Voice-over-IP-Telefon Netzwerk mit dem öffentlich geschalteten Telefonnetz (PSTN) zu verbinden. In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt. Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch. Für Administratoren bedeutete dies, dass sie sich Informationen zu einem einzelnen SIP-Trunk anzeigen lassen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufriefen.
  
In Skype for Business Server können nun jedoch mehrere Trunks einem einzigen PSTN-Gateway zugewiesen werden. Das bedeutet, dass Gateways und Trunks nicht mehr identisch sind. Das bedeutet wiederum, dass Administratoren das neue Cmdlet " [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) " verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Anzeigen von Informationen für alle SIP-Trunks

- Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Anzeigen von Informationen für einen bestimmten SIP-Trunk

- Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Informationen für alle einem Pool zugeordneten SIP-Trunks anzeigen

- In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
