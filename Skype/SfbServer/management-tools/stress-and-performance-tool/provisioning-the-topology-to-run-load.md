---
title: Bereitstellen der Topologie zum Ausführen von Last in Stress- und Leistungsszenarien
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015-Topologie ändert oder bereitstellung, damit Benutzer das Stress and Performance Tool erfolgreich ausführen können.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814935"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Bereitstellen der Topologie zum Ausführen von Last in Stress- und Leistungsszenarien
 
Skype for Business Server 2015-Topologie ändert oder bereitstellung, damit Benutzer das Stress and Performance Tool erfolgreich ausführen können.
  
Abhängig von Ihren vorhandenen Einstellungen und der Konfiguration für Ihre Bereitstellung von Skype for Business Server 2015 müssen Sie möglicherweise einige Änderungen in Ihrer Umgebung vornehmen. Im Folgenden finden Sie eine Liste dieser Änderungen:
  
1. Legen Sie die Windows PowerShell auf "Unrestricted" (unbeschränkt) festgelegt. Wenn Sie nicht sicher sind, auf was sie aktuell festgelegt ist, können Sie die Skype for Business Server-Verwaltungsshell öffnen und diesen Befehl ausführen:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Wenn der Wert Unrestricted nicht zurückgegeben wird, müssen Sie den folgenden Schritt ausführen:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Um Skype for Business Server effektiv zu konfigurieren, müssen Sie:
    
    - Machen Sie sich mit Ihrer Skype for Business Server 2015-Topologie vertraut (z. B. Computernamen, Dienstinstanzen, Standortnamen und Richtlinien).
    
    - Weisen Sie einige der erstellten Benutzer Gruppen zu, z. B. Reaktionsgruppen-Sammel sammelgruppen (z. B. SIP-URIs).
    
3. Verwenden Sie zum Ausführen eines Skripts über die Befehlszeile:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Nachdem Sie ein Skript aus diesem Paket ausgeführt haben, werden die resultierenden Ablaufverfolgungen in der Regel in einer Datei im selben Pfad gespeichert, von wo aus das Skript ausgeführt wurde. Es gibt auch ein Namensformat, \<scriptname\> $h$m$s.txt. Wenn Sie den ArchivingPolicy.ps1 um 12:15 Uhr erstellt haben, erhalten Sie eine Protokolldatei mit dem Namen ArchivingPolicy121500.txt.
    
5. Obwohl wir diese Beispiele für Ihre Serverkonfiguration bereitgestellt haben, müssen Sie ihre Konfiguration ändern und wiederherstellen oder ein Rollback ausführen, nachdem Sie die Auslastungstests abgeschlossen haben.
    

