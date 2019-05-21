---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Migration zu Microsoft Skype for Business Server 2019 müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284501"
---
# <a name="configure-scom-monitoring"></a>Konfigurieren der SCOM-Überwachung

Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie einige Aufgaben ausführen, um Skype for Business Server 2019 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.
  
- Wenden Sie Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.
    
- Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.
    
- Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für die zentrale Ermittlung außer Kraft setzt.
    
Nachfolgend finden Sie Anweisungen zur Durchführung der einzelnen Aufgaben.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Wenden Sie Updates auf einen Server an, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde.

1. Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und als Knoten für die Kandidaten Ermittlung konfiguriert sind. 
    
2. Wenden Sie Updates auf diesen Server an. Lesen Sie das Thema [Anwenden von Updates](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aktualisieren Sie den Registrierungsschlüssel des zentralen Discovery Candidate-Servers.

1. Öffnen Sie auf dem Server, der zum Verwalten der zentralen Ermittlungslogik gewählt wurde, ein Windows PowerShell-Befehlsfenster. 
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Wenn Sie die Registrierung bearbeiten, tritt möglicherweise ein Fehler auf, dass der Befehl fehlgeschlagen ist, wenn der Registrierungsschlüssel bereits vorhanden ist. Wenn Sie dies erleben, können Sie den Fehler bedenkenlos ignorieren. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass er den Kandidaten für den Central Discovery Watcher-Knoten außer Kraft setzt.

1. Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte** , und wählen Sie dann **Objektermittlungen**aus.
    
2. Klicken Sie auf **Bereich ändern** .
    
3. Wählen Sie auf der Seite **Objekte des Bereichs Management Packs** die Option **ls Discovery Candidate**aus.
    
4. Überschreiben Sie den Wert für den **effektiven ls-Ermittlungs Kandidaten** auf den Namen des Kandidaten Servers, der im vorherigen Verfahren gewählt wurde. 
    
Um Ihre Änderungen abzuschließen, starten Sie den Integritätsdienst auf dem System Center Operations Manager-Stamm Verwaltungs Server neu.
  

