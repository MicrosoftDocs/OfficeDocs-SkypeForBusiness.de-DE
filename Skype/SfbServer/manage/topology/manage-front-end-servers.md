---
title: Verwalten von Front-End-Servern in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Zusammenfassung: Informationen zum Hinzufügen, Entfernen, Patchen oder Aktualisieren von Front-End-Servern in Skype for Business Server.'
ms.openlocfilehash: 16af245b3c49b21309edd3ee2843f2585814ce9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826325"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>Verwalten von Front-End-Servern in Skype for Business Server
 
In diesem Artikel wird erläutert, wie Sie Front-End-Server hinzufügen oder entfernen und wie Sie Upgrades oder Patches auf Front-End-Server anwenden.

  > [!NOTE]
> Skype for Business Server 2019 unterstützt keine Enterprise Edition-Front-End-Pools mit zwei Front-End-Servern und lässt die Veröffentlichung der Topologie in diesem Szenario nicht zu.

## <a name="add-or-remove-front-end-servers"></a>Hinzufügen oder Entfernen von Front-End-Servern
  
Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten. 
  
> [!IMPORTANT]
> Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig neu gestartet. Während die Server den Pool neu starten, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen für Benutzer zu verhindern, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
Sie können das folgende Verfahren beim Hinzufügen oder Entfernen eines Front-End-Servers verwenden.
  
> [!NOTE]
> Wenn Sie dem Pool neue Server hinzufügen, aktualisieren Sie die neuen Poolserver auf die gleiche kumulative Updatestufe wie die vorhandenen Server im Pool. 
  
### <a name="to-add-or-remove-front-end-servers"></a>So fügen Sie Front-End-Server hinzu oder entfernen sie

1. Wenn Sie Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie. 
    
3. Veröffentlichen Sie die Topologie.
    
    > [!IMPORTANT]
    > Wenn Sie einen Server zum Pool in Ihrer Topologie hinzufügen oder entfernen und dann die aktualisierte Topologie veröffentlichen, werden alle Server im Pool gleichzeitig neu gestartet. Während die Server den Pool neu starten, ist der Pool offline, wodurch der Dienst für die mit diesem Pool verbundenen Benutzer unterbrochen wird. Um Dienstunterbrechungen für Benutzer zu verhindern, planen Sie die Veröffentlichung der Topologie mit dem neuen Server im Pool außerhalb der Geschäftszeiten. 
  
  > [!NOTE]
> Wenn Sie dem Pool einen Server hinzufügen oder entfernen, müssen Sie außerdem den Skype for Business Server-Bereitstellungs-Assistenten auf jedem Computer ausführen, der hinzugefügt oder entfernt wurde. Weitere Informationen finden Sie unter "Installieren von Skype for Business Server auf Servern in der [Topologie".](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. Wenn Sie die Anzahl der Server in Ihrem Front-End-Pool auf eine der folgenden Arten geändert haben, setzen Sie den Pool mit dem folgenden Cmdlet zurück: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 bis 2
    
     - Von 2 bis 2
    
     - 3 bis 1
    
     - Von 3 bis 3
    
5. Starten Sie den Pool neu, indem Sie das folgende Cmdlet eingeben.
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>Patchen oder Aktualisieren von Front-End-Servern

Wenn Sie die Server in einem Front-End-Pool patchen, müssen Sie dies auf einem Server nach dem anderen tun. 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>So wenden Sie ein Upgrade auf die Front-End-Server in einem Pool an

1. Geben Sie das folgende Cmdlet ein:
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     Wenn dieses Cmdlet fehlende Replikate zeigt, führen Sie das folgende Cmdlet aus, um den Pool wiederhergestellt zu werden, bevor Sie Patches anwenden.
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. Führen Sie auf dem ersten Server, den Sie patchen möchten, das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    Mit diesem Cmdlet werden alle Dienste auf andere Front-End-Server im Pool verlagert und dieser Server offline geschaltet.
    
3. Wenden Sie das Upgrade oder den Patch auf diesen Server an.
    
4. Führen Sie auf dem aktualisierten Server das folgende Cmdlet aus:
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    Der Server wird an den Dienst zurückgegeben.
    
5. Wiederholen Sie die Schritte 2 bis 4 für jeden Server, der aktualisiert werden muss.
    
