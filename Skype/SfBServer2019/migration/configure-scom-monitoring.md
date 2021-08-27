---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Nach der Migration zu Microsoft Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Arbeit mit System Center Operations Manager zu konfigurieren.
ms.openlocfilehash: 756e83ad0a8c964954f43518dc8603802d45c40d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590659"
---
# <a name="configure-scom-monitoring"></a>Konfigurieren der SCOM-Überwachung

Nach der Migration zu Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für System Center Operations Manager zu konfigurieren.
  
- Anwenden von Updates auf einen Server, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde.
    
- Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.
    
- Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver, um den zentralen Suchknoten des Kandidaten außer Kraft zu setzen.
    
Anweisungen für diese Aufgaben finden Sie unten.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Anwenden von Updates auf einen Server, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde.

1. Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und der als Kandidatenermittlungsknoten konfiguriert ist. 
    
2. Wenden Sie Updates auf diesen Server an. Weitere Informationen finden Sie im Thema ["Updates anwenden".](apply-updates.md)
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.

1. Öffnen Sie auf dem Server, der sich für die Verwaltung der zentralen Ermittlungslogik entschieden hat, ein Windows PowerShell Befehlsfenster. 
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Bei jeder Bearbeitung der Registrierung kann eine Fehlermeldung angezeigt werden, dass der Befehl nicht ausgeführt wurde, wenn der Registrierungsschlüssel bereits vorhanden ist. Falls dies der Fall ist, können Sie die Fehlermeldung getrost ignorieren. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver, um den Knoten des zentralen Ermittlungsüberwachungsknotens außer Kraft zu setzen.

1. Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte**, und wählen Sie **Objektermittlungen** aus.
    
2. Klicken Sie auf **"Bereich ändern".**
    
3. Wählen Sie auf der Seite **Management Pack-Objekte in Bereiche einteilen** den Eintrag **LS-Ermittlungskandidat** aus.
    
4. Überschreiben Sie den **Effektivwert für den LS-Ermittlungskandidaten** mit dem Namen des zuvor ausgewählten Kandidatenservers. 
    
Starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stammverwaltungsserver neu, um die Änderungen abzuschließen.
  

