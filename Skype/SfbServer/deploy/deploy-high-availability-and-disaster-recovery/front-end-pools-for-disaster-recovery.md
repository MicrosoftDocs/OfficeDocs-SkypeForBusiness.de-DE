---
title: Bereitstellen von front-End-Paarpools für die Notfallwiederherstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Sie können sich dafür entscheiden, gepaarte Front-End-Pools für den Notfallwiederherstellungsschutz zu verwenden, dies ist jedoch keine Voraussetzung.
ms.openlocfilehash: 9aec106905b2d8628e30461dce130f301aef1b25
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741331"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Bereitstellen von front-End-Paarpools für die Notfallwiederherstellung in Skype for Business Server
 
Sie können sich dafür entscheiden, gepaarte Front-End-Pools für den Notfallwiederherstellungsschutz zu verwenden, dies ist jedoch keine Voraussetzung.
  
Sie können die Notfallwiederherstellungstopologie von gepaarten Front-End-Pools ganz einfach mithilfe des Topologie-Generators bereitstellen. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>So stellen Sie ein Paar von Front-End-Pools bereit

1. Wenn die Pools neu und noch nicht definiert sind, verwenden Sie den Topologie-Generator, um die Pools zu erstellen.
    
2. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **"Eigenschaften bearbeiten".**
    
3. Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich **Zugeordneter Sicherungspool** aus.
    
4. Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.
    
5. Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.
    
    Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**. 
    
6. Verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen.
    
7. Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Sie können die letzten Schritte in diesem Verfahren überspringen.
    
    Wenn die Pools jedoch bereits bereitgestellt wurden, bevor Sie die paarweise Beziehung definiert haben, müssen Sie die folgenden abschließenden Schritte ausführen.
    
8. Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.
    
9. Nachdem Bootstrapper die Installation der erforderlichen Komponenten für die Sicherungspaarung auf jedem Front-End-Server in beiden Pools abgeschlossen hat, müssen Sie alle vorhandenen kumulativen Updates erneut anwenden, die zuvor auf diese Front-End-Server in beiden Pools angewendet wurden, und fahren Sie dann mit dem nächsten Schritt fort.

10. Führen Sie an einer Skype for Business Server Verwaltungsshell-Eingabeaufforderung Folgendes aus: 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Erzwingen Sie, dass die Benutzer- und Konferenzdaten beider Pools mit den folgenden Cmdlets miteinander synchronisiert werden:
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    Das Synchronisieren der Daten kann einige Zeit in Anspruch nehmen. Sie können die folgenden Cmdlets verwenden, um den Status zu prüfen. Stellen Sie sicher, dass der Status in beide Richtungen stabil ist.
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> Die Option **"Automatisches Failover und Failback für VoIP"** und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die In Lync Server-Funktionen zur Ausfallsicherheit von VoIP. Wenn Sie diese Option auswählen, bedeutet dies nicht, dass das in diesem Dokument beschriebene Poolfailover automatisch erfolgt. Poolfailover und Failback erfordern immer, dass ein Administrator die Failover- bzw. Failback-Cmdlets manuell aufruft.
  
## <a name="see-also"></a>Weitere Informationen

[Notfallwiederherstellung von Front-End-Pools in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
