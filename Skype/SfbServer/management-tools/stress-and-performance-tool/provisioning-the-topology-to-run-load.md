---
title: Bereitstellen der Topologie zum Ausführen der Auslastung in Stress-und Leistungs Szenarien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Änderungen oder Bereitstellung von Skype for Business Server 2015-Topologie, um Benutzern das erfolgreiche Ausführen des Stress-und Leistungstools zu ermöglichen.
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816164"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Bereitstellen der Topologie zum Ausführen der Auslastung in Stress-und Leistungs Szenarien
 
Änderungen oder Bereitstellung von Skype for Business Server 2015-Topologie, um Benutzern das erfolgreiche Ausführen des Stress-und Leistungstools zu ermöglichen.
  
Je nach Ihren vorhandenen Einstellungen und der Konfiguration für Ihre Bereitstellung von Skype for Business Server 2015 müssen Sie möglicherweise einige Änderungen in Ihrer Umgebung vornehmen. Die folgende Liste enthält die folgenden Änderungen:
  
1. Setzen Sie die Windows PowerShell-Ausführungsrichtlinie auf Unrestricted. Wenn Sie nicht genau wissen, auf was Sie derzeit eingestellt ist, können Sie die Skype for Business Server-Verwaltungsshell öffnen und diesen Befehl ausführen:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Wenn der Wert Unrestricted nicht zurückgegeben wird, müssen Sie Folgendes ausführen:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Um Skype for Business Server effektiv zu konfigurieren, müssen Sie Folgendes tun:
    
    - Machen Sie sich mit Ihrer Skype for Business Server 2015-Topologie vertraut (wie Computernamen, Dienstinstanzen, Websitenamen und Richtlinien).
    
    - Weisen Sie einige der Benutzer zu, die Gruppen zugeordnet sind, wie etwa Gruppen-Sammelanschlüsse (beispielsweise SIP-URIs).
    
3. Wenn Sie ein Skript über die Befehlszeile ausführen möchten, können Sie Folgendes verwenden:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Nachdem Sie ein Skript aus diesem Paket ausgeführt haben, werden die resultierenden Ablaufverfolgungen in der Regel in einer Datei im gleichen Pfad gespeichert, von dem aus das Skript ausgeführt wurde. Außerdem gibt es ein Benennungsformat \<: Skript\>Name $h $ m $ s. txt. Wenn Sie also ArchivingPolicy. ps1 auf 12:15 Uhr ausgeführt haben, erhalten Sie eine Protokolldatei mit dem Namen ArchivingPolicy121500. txt.
    
5. Obwohl wir diese Beispiele für Ihre Serverkonfiguration bereitgestellt haben, liegt es an Ihnen, sowohl Ihre Konfiguration zu ändern als auch nach Abschluss der Auslastungstests wiederherzustellen oder zurückzusetzen.
    

