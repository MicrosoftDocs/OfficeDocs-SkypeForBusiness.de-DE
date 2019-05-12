---
title: Bereitstellung der Topologie zum Laden in Stress and Performance Szenarien ausführen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype für Business Server 2015 topologieänderungen oder Bereitstellung für Benutzer zu das Stress and Performance-Tool erfolgreich ausgeführt.
ms.openlocfilehash: 446c8d8154992540ffd8bfe18b07af7c54e864fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906641"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Bereitstellung der Topologie zum Laden in Stress and Performance Szenarien ausführen
 
Skype für Business Server 2015 topologieänderungen oder Bereitstellung für Benutzer zu das Stress and Performance-Tool erfolgreich ausgeführt.
  
Je nach der vorhandenen Einstellungen und die Konfiguration für die Bereitstellung von Skype für Business Server 2015 müssen Sie möglicherweise einige Änderungen in Ihrer Umgebung vornehmen. Es folgt eine Liste mit diesen Änderungen:
  
1. Legen Sie die Windows PowerShell-Ausführungsrichtlinie nicht eingeschränkt. Wenn Sie nicht sicher sind, was ist können festlegen auf aktuell, Sie die Skype für Business Server-Verwaltungsshell öffnen und führen Sie diesen Befehl:
    
   ```
   Get-ExecutionPolicy
   ```

   Wenn der Wert Unrestricted nicht zurückgegeben wird, müssen Sie diesem als Nächstes ausführen:
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. Um effektiv Skype für Business Server konfigurieren, müssen Sie Folgendes ausführen:
    
    - Mit Ihrer Skype für Business Server 2015 Topologie (beispielsweise Computernamen, Dienstinstanzen, Websitenamen und Richtlinien) vertraut sein.
    
    - Weisen Sie einige Benutzer, die Gruppen erstellt werden, wie Response Group Sammelanschlüssen (beispielsweise SIP-URIs).
    
3. Wenn Sie ein Skript über die Befehlszeile ausführen, können Sie Folgendes verwenden:
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. Nach dem Ausführen eines Skripts aus diesem Paket werden in der Regel, die sich ergebende Spuren gespeichert werden in einer Datei in demselben Pfad in dem das Skript ausgeführt wurde. Es ist auch ein Namensformat \<Skriptname\>$h$m$s.txt. Also, wenn Sie die ArchivingPolicy.ps1 12:15 Uhr ausgeführt haben, Abrufen eine Protokolldatei namens ArchivingPolicy121500.txt.
    
5. Während es in diesen Beispielen für die Serverkonfiguration bereitgestellt haben, ist es Ihnen Ändern der Konfigurations und Wiederherstellen oder ein Rollback durchführen, Sichern Sie nach Abschluss der Auslastungstests ausgeführt.
    

