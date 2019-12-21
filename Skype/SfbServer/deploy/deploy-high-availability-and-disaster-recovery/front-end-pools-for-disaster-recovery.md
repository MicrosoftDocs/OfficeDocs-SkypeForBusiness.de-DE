---
title: Bereitstellen gekoppelter Front-End-Pools für Disaster Recovery in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Sie können Front-End-Poolpaare verwenden, um Schutz durch Notfallwiederherstellung bereitzustellen. Dies ist jedoch nicht erforderlich.
ms.openlocfilehash: 550c336569b604ae20199b419dc104af0609c775
ms.sourcegitcommit: e43a66a7f769f855dc45c1bb7f83636d0390949b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "39254394"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Bereitstellen gekoppelter Front-End-Pools für Disaster Recovery in Skype for Business Server
 
Sie können Front-End-Poolpaare verwenden, um Schutz durch Notfallwiederherstellung bereitzustellen. Dies ist jedoch nicht erforderlich.
  
Sie können die Disaster Recovery-Topologie von gekoppelten Front-End-Pools auf einfache Weise mithilfe von Topology Builder bereitstellen. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>So stellen Sie ein Front-End-Poolpaar bereit

1. Wenn die Pools neu sind und noch nicht definiert sind, verwenden Sie den Topologie-Generator zum Erstellen der Pools.
    
2. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.
    
3. Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich die Option **Zugeordneter Sicherungspool** aus.
    
4. Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.
    
5. Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.
    
    Wenn Sie die Details zu diesem Pool anzeigen, erscheint der zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**.  
    
6. Verwenden Sie den Topologie-Generator zum Veröffentlichen der Topologie.
    
7. Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Sie können die letzten Schritte in diesem Verfahren überspringen.
    
    Wenn die Pools jedoch bereits bereitgestellt wurden, bevor Sie die gekoppelte Beziehung definiert haben, müssen Sie die folgenden letzten Schritte ausführen.
    
8. Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:
    
   ```
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.
    
9. Nachdem Bootstrapper die Installation der erforderlichen Komponenten für die Backup-Kopplung auf jedem Front-End-Server in beiden Pools abgeschlossen hat, stellen Sie sicher, dass Sie alle vorhandenen kumulativen Updates erneut anwenden, die zuvor auf diesen Front-End-Servern in beiden Pools angewendet wurden, und dann fortfahren. mit dem nächsten Schritt.

10. Führen Sie in der Eingabeaufforderung der Skype for Business Server-Verwaltungsshell die folgenden Aktionen aus: 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Erzwingen Sie die Synchronisierung der Benutzer-und Konferenzdaten beider Pools mit den folgenden Cmdlets:
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen. Sie können die folgenden Cmdlets verwenden, um den Status zu überprüfen. Stellen Sie sicher, dass der Status für beide Richtungen stabil ist.
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> Die Option **Automatisches Failover und Failback für VoIP** und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die Features der VoIP-Widerstandsfähigkeit, die in lync Server eingeführt wurden. Wenn Sie diese Option auswählen, bedeutet dies nicht, dass das in diesem Dokument beschriebene Pool-Failover automatisch erfolgt. Für Pool-Failover und Failback muss ein Administrator immer manuell die Failover-und Failback-Cmdlets aufrufen.
  
## <a name="see-also"></a>Siehe auch

[Disaster Recovery des Front-End-Pools in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
