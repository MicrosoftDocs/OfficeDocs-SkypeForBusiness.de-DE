---
title: Patchen oder Aktualisieren der Front-End-Server in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/4/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
description: 'Zusammenfassung: erfahren Sie, wie Upgrades oder Patches auf Front-End-Servern im Skype für Business Server angewendet.'
ms.openlocfilehash: 1f5ccd6531338d1e6b47dd8363b9386bcbeba0fc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-front-end-servers-in-skype-for-business-server-2015"></a>Patchen oder Aktualisieren der Front-End-Server in Skype for Business Server 2015
 
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
    

