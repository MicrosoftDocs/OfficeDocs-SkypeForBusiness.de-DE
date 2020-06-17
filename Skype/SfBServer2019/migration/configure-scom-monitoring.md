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
localization_priority: Normal
description: Nach der Migration zu Microsoft Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754045"
---
# <a name="configure-scom-monitoring"></a>Konfigurieren der SCOM-Überwachung

Nach der Migration zu Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.
  
- Wenden Sie Updates auf einen Server an, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde.
    
- Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.
    
- Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Kandidaten-zentral Suche außer Kraft gesetzt wird.
    
Anweisungen für diese Aufgaben finden Sie unten.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Wenden Sie Updates auf einen Server an, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde.

1. Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und der als Kandidatenermittlungsknoten konfiguriert ist. 
    
2. Wenden Sie Updates auf diesen Server an. Siehe das Thema [Apply Updates](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.

1. Öffnen Sie auf dem Server, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde, ein Windows PowerShell Befehlsfenster. 
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Candidate Central Discovery Watcher außer Kraft gesetzt wird.

1. Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte**, und wählen Sie **Objektermittlungen** aus.
    
2. Klicken Sie auf **Bereich ändern** .
    
3. Wählen Sie auf der Seite **Management Pack-Objekte in Bereiche einteilen** den Eintrag **LS-Ermittlungskandidat** aus.
    
4. Überschreiben Sie den **Effektivwert für den LS-Ermittlungskandidaten** mit dem Namen des zuvor ausgewählten Kandidatenservers. 
    
Starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stamm Verwaltungs Server neu, um die Änderungen abzuschließen.
  

