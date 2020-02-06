---
title: Verwalten von Front-End-Servern in Skype for Business Server
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
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Front-End-Server in Skype for Business Server hinzufügen, entfernen, Patchen oder aktualisieren.'
ms.openlocfilehash: bc97faaf3ac36ff5cb74d6286aa7e75facbd98cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817261"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Verwalten von Front-End-Servern in Skype for Business Server
 
In diesem Artikel wird erläutert, wie Sie Front-End-Server hinzufügen oder entfernen und wie Sie Upgrades oder Patches auf Front-End-Server anwenden.

## <a name="add-or-remove-front-end-servers"></a>Hinzufügen oder Entfernen von Front-End-Servern
  
Wenn Sie einen Front-End-Server zu einem Pool hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool erneut starten. 
  
> [!IMPORTANT]
> Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
Sie können das folgende Verfahren verwenden, wenn Sie einen Front-End-Server hinzufügen oder entfernen.
  
> [!NOTE]
> Wenn Sie neue Server zum Pool hinzufügen, aktualisieren Sie Ihre neuen Poolserver, sodass diese im Hinblick auf das kumulative Update auf demselben Stand sind wie die bereits bestehenden Server in dem Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>So können Sie Front-End-Server hinzufügen oder entfernen

1. Wenn Sie alle Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Öffnen Sie den Topologie-Generator, und fügen Sie die erforderlichen Server hinzu, oder entfernen Sie Sie. 
    
3. Veröffentlichen Sie die Topologie.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder daraus entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig gestartet. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen zu vermeiden, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
  > [!NOTE]
> Wenn Sie dem Pool einen Server hinzufügen oder daraus entfernen, müssen Sie auch den Skype for Business Server-Bereitstellungs-Assistenten auf jedem Computer ausführen, der hinzugefügt oder entfernt wurde, und weitere Informationen finden Sie unter [Installieren von Skype for Business Server auf Servern in der Topologie](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server) .
  
4. Wenn Sie die Anzahl der Server im Front-End-Pool auf eine der folgenden Arten geändert haben, setzen Sie den Pool zurück, indem Sie folgendes Cmdlet eingeben: Reset-CsPoolRegistrarState-resettype FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 bis beliebig
    
     - Beliebig bis 2
    
     - 3 bis beliebig
    
     - Beliebig bis 3
    
5. Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patchen oder Aktualisieren der Front-End-Server

Wenn Sie die Server in einem Front-End-Pool Patchen, tun Sie dies jeweils auf einem Server. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So führen Sie ein Upgrade für die Front-End-Server in einem Pool durch

1. Geben Sie das folgende Cmdlet ein:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Wenn für dieses Cmdlet fehlende Replikate angezeigt werden, führen Sie vor dem Anwenden von Patches das folgende Cmdlet aus, um den Pool wiederherzustellen.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Führen Sie auf dem ersten Server, auf den ein Patch angewendet werden soll, das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Mit diesem Cmdlet werden alle Dienste auf andere Front-End-Server im Pool verschoben, und der Server wird offline geschaltet.
    
3. Wenden Sie das Upgrade oder Patch auf diesen Server an.
    
4. Führen Sie das folgende Cmdlet auf dem aktualisierten Server aus:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Der Server ist wieder im Dienst.
    
5. Wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Server, der ein Upgrade erhalten soll.
    
