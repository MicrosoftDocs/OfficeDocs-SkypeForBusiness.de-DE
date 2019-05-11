---
title: Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von Informationen zu SIP-Trunks in Skype für Business Server.'
ms.openlocfilehash: a7cf290bf245092e08babcaa86c642dd0f0a4265
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892237"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>Anzeigen von Informationen über die einzelnen SIP-Trunks in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Anzeigen von Informationen zu SIP-Trunks in Skype für Business Server.
  
SIP-Trunks dienen zum Skype für Business Server Voice over IP-Telefon Netzwerk mit im Public Switched Telephone Network, (PSTN) eine Verbindung herstellen. In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt. Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch. Für Administratoren bedeutete dies, dass sie sich Informationen zu einem einzelnen SIP-Trunk anzeigen lassen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufriefen.
  
In Skype für Business Server können jedoch mehrere Trunks jetzt ein einzelnes PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht länger ein und dieselbe sind. Wiederum bedeutet dies, dass das neue [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) -Cmdlet, um das Anzeigen von Informationen zu einer einzelnen SIP-Trunk Administratoren verwendet werden müssen.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>Anzeigen von Informationen für alle SIP-Trunks

- Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>Anzeigen von Informationen für einen bestimmten SIP-Trunk

- Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert „PstnGateway:192.168.0.240“ Informationen zurück:
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Informationen für alle einem Pool zugeordneten SIP-Trunks anzeigen

- In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool „atl-cs-001.litwareinc.com“ zugeordnet sind:
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
