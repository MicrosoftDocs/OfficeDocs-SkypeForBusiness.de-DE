---
title: Verwalten von Front-End-Servern in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Front-End-Server in Skype for Business Server hinzufügen, entfernen, patchen oder aktualisieren.'
---

# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Verwalten von Front-End-Servern in Skype for Business Server
 
In diesem Artikel wird erläutert, wie Sie Front-End-Server hinzufügen oder entfernen und wie Sie Upgrades oder Patches auf Front-End-Server anwenden.

  > [!NOTE]
> Skype for Business Server 2019 unterstützt Enterprise Edition Front-End-Pools mit zwei Front-End-Servern nicht und lässt nicht zu, dass die Topologie in diesem Szenario veröffentlicht wird.

## <a name="add-or-remove-front-end-servers"></a>Hinzufügen oder Entfernen von Front-End-Servern
  
Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten. 
  
> [!IMPORTANT]
> Wenn Sie dem Pool in Ihrer Topologie einen Server hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, führt dies dazu, dass alle Server im Pool gleichzeitig neu gestartet werden. Während die Server den Pool neu starten, ist er offline, wodurch der Dienst für Die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen für Benutzer zu verhindern, planen Sie, die Topologie mit dem neuen Server im Pool während der Geschäftszeiten zu veröffentlichen. 
  
Sie können das folgende Verfahren verwenden, wenn Sie einen Front-End-Server hinzufügen oder entfernen.
  
> [!NOTE]
> Wenn Sie dem Pool neue Server hinzufügen, aktualisieren Sie ihre neuen Poolserver so, dass sie sich auf der gleichen kumulativen Updateebene befinden wie die vorhandenen Server im Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>So fügen Sie Front-End-Server hinzu oder entfernen sie

1. Wenn Sie Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie. 
    
3. Veröffentlichen Sie die Topologie.
    
    > [!IMPORTANT]
    > Wenn Sie dem Pool in Ihrer Topologie einen Server hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, führt dies dazu, dass alle Server im Pool gleichzeitig neu gestartet werden. Während die Server den Pool neu starten, ist er offline, wodurch der Dienst für Die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen für Benutzer zu verhindern, planen Sie, die Topologie mit dem neuen Server im Pool während der Geschäftszeiten zu veröffentlichen. 
  
  > [!NOTE]
> Wenn Sie dem Pool einen Server hinzufügen oder entfernen, müssen Sie außerdem den Skype for Business Server Bereitstellungs-Assistenten auf jedem hinzugefügten oder entfernten Computer ausführen. Weitere Informationen finden Sie unter [Installieren Skype for Business Server auf Servern in der Topologie](../../deploy/install/install-skype-for-business-server.md).
  
4. Wenn Sie die Anzahl der Server in Ihrem Front-End-Pool auf eine der folgenden Arten geändert haben, setzen Sie den Pool zurück, indem Sie das folgende Cmdlet eingeben: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 bis beliebig
    
     - Beliebig bis 2
    
     - 3 bis beliebig
    
     - Beliebig bis 3
    
5. Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben.
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patchen oder Aktualisieren von Front-End-Servern

Wenn Sie die Server in einem Front-End-Pool patchen, tun Sie dies jeweils für einen Server. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So wenden Sie ein Upgrade auf die Front-End-Server in einem Pool an

1. Geben Sie folgendes Cmdlet ein:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Wenn dieses Cmdlet fehlende Replikate anzeigt, führen Sie das folgende Cmdlet aus, um den Pool wiederherzustellen, bevor Sie Patches anwenden.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Führen Sie auf dem ersten Server, den Sie patchen möchten, das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Mit diesem Cmdlet werden alle Dienste auf andere Front-End-Server im Pool verschoben und dieser Server offline geschaltet.
    
3. Wenden Sie das Upgrade oder Patch auf diesen Server an.
    
4. Führen Sie auf dem aktualisierten Server das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Der Server wird an den Dienst zurückgegeben.
    
5. Wiederholen Sie die Schritte 2 bis 4 für jeden Server, der aktualisiert werden muss.
