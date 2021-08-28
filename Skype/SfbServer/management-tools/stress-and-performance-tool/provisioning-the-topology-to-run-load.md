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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server 2015:Topologieänderungen oder Bereitstellung, damit Benutzer das Stress and Performance-Tool erfolgreich ausführen können.
ms.openlocfilehash: 224a2c1afde71ce94b69826ee0222dce729d22d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611914"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Bereitstellen der Topologie zum Ausführen von Last in Stress- und Leistungsszenarien
 
Skype for Business Server 2015:Topologieänderungen oder Bereitstellung, damit Benutzer das Stress and Performance-Tool erfolgreich ausführen können.
  
Je nach den vorhandenen Einstellungen und der Konfiguration für die Bereitstellung von Skype for Business Server 2015 müssen Sie möglicherweise einige Änderungen in Ihrer Umgebung vornehmen. Es folgt eine Liste dieser Änderungen:
  
1. Legen Sie die Windows PowerShell Ausführungsrichtlinie auf "Uneingeschränkt" fest. Wenn Sie sich nicht sicher sind, auf was sie derzeit festgelegt ist, können Sie die Skype for Business Server Verwaltungsshell öffnen und den folgenden Befehl ausführen:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Wenn der Wert "Uneingeschränkt" nicht zurückgegeben wird, müssen Sie als Nächstes Folgendes ausführen:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Um Skype for Business Server effektiv zu konfigurieren, müssen Sie:
    
    - Machen Sie sich mit Ihrer Skype for Business Server 2015-Topologie vertraut (z. B. Computernamen, Dienstinstanzen, Standortnamen und Richtlinien).
    
    - Weisen Sie einige der erstellten Benutzer Gruppen zu, z. B. Sammelanschlüsse für Reaktionsgruppen (z. B. SIP-URIs).
    
3. Zum Ausführen eines Skripts über die Befehlszeile können Sie Folgendes verwenden:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. In der Regel werden die resultierenden Ablaufverfolgungen nach dem Ausführen eines Skripts aus diesem Paket in einer Datei im selben Pfad gespeichert, von dem aus das Skript ausgeführt wurde. Es gibt auch ein Namensformat, \<scriptname\> $h$m$s.txt. Wenn Sie also die ArchivingPolicy.ps1 um 12:15 Uhr ausgeführt haben, erhalten Sie eine Protokolldatei mit dem Namen ArchivingPolicy121500.txt.
    
5. Obwohl wir diese Beispiele für Ihre Serverkonfiguration bereitgestellt haben, liegt es an Ihnen, ihre Konfiguration zu ändern und sie wiederherzustellen oder zurückzustellen, nachdem Sie die Auslastungstests abgeschlossen haben.
    

