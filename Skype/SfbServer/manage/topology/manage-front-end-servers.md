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
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098413"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Verwalten von Front-End-Servern in Skype for Business Server
 
In diesem Artikel wird erläutert, wie Sie Front-End-Server hinzufügen oder entfernen und wie Sie Upgrades oder Patches auf Front-End-Server anwenden.

  > [!NOTE]
> Skype for Business Server 2019 unterstützt keine Enterprise Edition-Front-End-Pools mit zwei Front-End-Servern und lässt nicht zu, dass die Topologie in diesem Szenario veröffentlicht wird.

## <a name="add-or-remove-front-end-servers"></a>Hinzufügen oder Entfernen von Front-End-Servern
  
Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten. 
  
> [!IMPORTANT]
> Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, führt dies dazu, dass alle Server im Pool gleichzeitig neu gestartet werden. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die Benutzer unterbrochen wird, die mit diesem Pool verbunden sind. Um eine Unterbrechung des Diensts für Benutzer zu verhindern, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
Sie können das folgende Verfahren verwenden, wenn Sie ein Front-End-Server hinzufügen oder entfernen.
  
> [!NOTE]
> Wenn Sie dem Pool neue Server hinzufügen, aktualisieren Sie die neuen Pool Server so, dass Sie auf der gleichen kumulativen Update Ebene wie die vorhandenen Server im Pool sind. 
  
### <a name="to-add-or-remove-front-end-servers"></a>So können Sie Front-End-Server hinzufügen oder entfernen

1. If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie. 
    
3. Veröffentlichen Sie die Topologie.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, führt dies dazu, dass alle Server im Pool gleichzeitig neu gestartet werden. Während die Server neu gestartet werden, ist der Pool offline, wodurch der Dienst für die Benutzer unterbrochen wird, die mit diesem Pool verbunden sind. Um eine Unterbrechung des Diensts für Benutzer zu verhindern, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
  > [!NOTE]
> Wenn Sie einen Server zum Pool hinzufügen oder entfernen, müssen Sie den Assistenten für die Skype for Business Server-Bereitstellung auf jedem Computer ausführen, der hinzugefügt oder entfernt wurde, weitere Informationen finden Sie unter [install Skype for Business Server on Servers in The Topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Wenn Sie die Anzahl der Server in Ihrem Front-End-Pool auf eine der folgenden Arten geändert haben, setzen Sie den Pool durch Eingeben des folgenden Cmdlets zurück: Reset-CsPoolRegistrarState-resettype FullReset-poolfqdn " 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 bis any
    
     - Beliebig bis 2
    
     - 3 bis any
    
     - Beliebig bis 3
    
5. Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben:
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patchen oder Aktualisieren von Front-End-Servern

Wenn Sie die Server in einem Front-End-Pool Patchen, tun Sie dies jeweils auf einem Server. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So wenden Sie ein Upgrade auf die Front-End-Server in einem Pool an

1. Geben Sie das folgende Cmdlet ein:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Wenn in diesem Cmdlet fehlende Replikate angezeigt werden, führen Sie das folgende Cmdlet aus, um den Pool wiederherzustellen, bevor Sie Patches anwenden.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Führen Sie auf dem ersten Server, den Sie Patchen möchten, das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Mit diesem Cmdlet werden alle Dienste auf andere Front-End-Server im Pool verschoben, und dieser Server wird offline geschaltet.
    
3. Wenden Sie das Upgrade oder Patch auf diesen Server an.
    
4. Führen Sie auf dem aktualisierten Server das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Der Server wird an den Dienst zurückgegeben.
    
5. Wiederholen Sie die Schritte 2-4 für jeden Server, der aktualisiert werden muss.
    
