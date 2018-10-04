---
title: Patchen oder Aktualisieren von Front-End-Servern im Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Zusammenfassung: erfahren Sie, wie Upgrades oder Patches auf Front-End-Servern im Skype für Business Server angewendet.'
ms.openlocfilehash: cf209159391ef084d77b5adc639698ed766427ff
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371717"
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server"></a>Patchen oder Aktualisieren von Front-End-Servern im Skype für Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Upgrades oder Patches auf Front-End-Servern im Skype für Business Server angewendet.
  
Wenn Sie die Server in einem Front-End-Pool patchen, gehen Sie also einen Server zu einem Zeitpunkt vor. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch

1. Geben Sie das folgende Cmdlet ein:
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Wenn für dieses Cmdlet fehlende Replikate angezeigt werden, führen Sie vor dem Anwenden von Patches das folgende Cmdlet aus, um den Pool wiederherzustellen.
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Führen Sie auf dem ersten Server, auf den ein Patch angewendet werden soll, das folgende Cmdlet aus:
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Dieses Cmdlet verschiebt alle Dienste auf anderen Front-End-Servern im Pool, und wird von diesem Server offline geschaltet.
    
3. Wenden Sie das Upgrade oder Patch auf diesen Server an.
    
4. Führen Sie das folgende Cmdlet auf dem aktualisierten Server aus:
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Der Server ist wieder im Dienst.
    
5. Wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Server, der ein Upgrade erhalten soll.
    

