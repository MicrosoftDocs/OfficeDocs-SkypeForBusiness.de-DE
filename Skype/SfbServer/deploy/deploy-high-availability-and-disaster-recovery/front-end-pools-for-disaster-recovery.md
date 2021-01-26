---
title: Bereitstellen gepaarter Front-End-Pools für die Notfallwiederherstellung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: Möglicherweise entscheiden Sie sich für die Verwendung von Front-End-Poolpaaren, um Notfallwiederherstellungsschutz zu bieten, dies ist jedoch nicht erforderlich.
ms.openlocfilehash: 7d066de60bf3ab98d73d8aeee08044803fad983c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830605"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>Bereitstellen gepaarter Front-End-Pools für die Notfallwiederherstellung in Skype for Business Server
 
Möglicherweise entscheiden Sie sich für die Verwendung von Front-End-Poolpaaren, um Notfallwiederherstellungsschutz zu bieten, dies ist jedoch nicht erforderlich.
  
Sie können die Notfallwiederherstellungstopologie von gekoppelten Front-End-Pools ganz einfach mithilfe des Topologie-Generators bereitstellen. 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>So stellen Sie ein Paar von Front-End-Pools bereit

1. Wenn die Pools neu sind und noch nicht definiert sind, verwenden Sie den Topologie-Generator, um die Pools zu erstellen.
    
2. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf einen der beiden Pools, und klicken Sie dann auf **Eigenschaften bearbeiten.**
    
3. Klicken Sie im linken Bereich auf **Flexibilität**, und wählen Sie dann im rechten Bereich **Zugeordneter Sicherungspool** aus.
    
4. Wählen Sie im Feld unter **Zugeordneter Sicherungspool** den Pool aus, mit dem dieser Pool ein Paar bilden soll. Zur Auswahl stehen nur vorhandene Pools, die noch nicht mit einem anderen Pool ein Paar bilden.
    
5. Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.
    
    Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**. 
    
6. Verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen.
    
7. Wenn die beiden Pools noch nicht bereitgestellt wurden, führen Sie die Bereitstellung jetzt durch, um die Konfiguration abzuschließen. Sie können die letzten Schritte in diesem Verfahren überspringen.
    
    Wenn die Pools jedoch bereits bereitgestellt wurden, bevor Sie die Paarbeziehung definiert haben, müssen Sie die folgenden abschließenden Schritte ausführen.
    
8. Führen Sie auf jedem Front-End-Server in beiden Pools Folgendes aus:
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    Hierdurch werden die anderen Dienste konfiguriert, die erforderlich sind, damit die Sicherung des Poolpaars korrekt funktioniert.
    
9. Sobald Bootstrapper die Installation der erforderlichen Komponenten für die Sicherungspaarung auf jedem Front-End-Server in beiden Pools abgeschlossen hat, müssen Sie alle vorhandenen kumulativen Updates, die zuvor auf diesen Front-End-Servern in beiden Pools angewendet wurden, erneut anwenden und dann mit dem nächsten Schritt fortfahren.

10. Führen Sie an einer Skype for Business Server-Verwaltungsshell-Eingabeaufforderung Folgendes aus: 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. Erzwingen Sie die Synchronisierung der Benutzer- und Konferenzdaten beider Pools miteinander mit den folgenden Cmdlets:
    
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
> Die **Option "Automatisches Failover** und Failback für Voice" und die zugehörigen Zeitintervalle im Topologie-Generator gelten nur für die Funktionen zur Ausfallsicherheit von Sprachfunktionen, die in Lync Server eingeführt wurden. Wenn Sie diese Option auswählen, bedeutet dies nicht, dass das in diesem Dokument erläuterte Poolfailover automatisch erfolgt. Für Das Failover und Failback eines Pools muss ein Administrator die Failover- bzw. Failback-Cmdlets immer manuell aufrufen.
  
## <a name="see-also"></a>Siehe auch

[Notfallwiederherstellung für Front-End-Pools in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
