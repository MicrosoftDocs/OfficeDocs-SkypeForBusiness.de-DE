---
title: Verwalten von Front-End-Servern im Skype für Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Informationen Sie zum Hinzufügen, entfernen, Patch, oder Front-End-Servern im Skype für Business Server aktualisieren.'
ms.openlocfilehash: c7ccaee0ee70c10b855053fb63c39cfead148f4e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875222"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Verwalten von Front-End-Servern im Skype für Business Server
 
In diesem Artikel wird erläutert, wie hinzufügen oder Entfernen von Front-End-Servern und Anwenden von upgrades oder patches für Front-End-Server.

## <a name="add-or-remove-front-end-servers"></a>Hinzufügen oder Entfernen von Front-End-Servern
  
Wenn Sie einen Front-End-Server zu einem Pool hinzufügen oder eines Front-End-Servers aus einem Pool entfernen, müssen Sie dann den Pool neu starten. 
  
> [!IMPORTANT]
> Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
Sie können das folgende Verfahren beim Hinzufügen oder Entfernen eines Front-End-Servers.
  
> [!NOTE]
> Wenn Sie neue Server zum Pool hinzufügen, aktualisieren Sie Ihre neuen Poolserver, sodass diese im Hinblick auf das kumulative Update auf demselben Stand sind wie die bereits bestehenden Server in dem Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>Zum Hinzufügen oder Entfernen von Front-End-Servern

1. Wenn Sie alle Front-End-Server entfernen, beenden Sie zuerst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. Öffnen Sie den Topologie-Generator und fügen Sie hinzu oder entfernen Sie die benötigten Server. 
    
3. Veröffentlichen Sie die Topologie.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
4. Wenn Sie die Anzahl der Server im Front-End-Pool in einer der folgenden Methoden geändert haben, müssen Sie den Pool mit dann zurücksetzen, indem Sie das folgende Cmdlet eingeben: Reset-CsPoolRegistrarState - ResetType FullReset - PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 bis beliebig
    
     - Beliebig bis 2
    
     - 3 bis beliebig
    
     - Beliebig bis 3
    
5. Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patchen oder Aktualisieren der Front-End-Server

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
    
