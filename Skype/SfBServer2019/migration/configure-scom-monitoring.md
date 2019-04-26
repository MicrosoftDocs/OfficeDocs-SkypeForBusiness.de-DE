---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Migration zu Microsoft Skype für Business Server 2019, müssen Sie einige Aufgaben zum Konfigurieren von Skype für Business Server 2019 arbeiten mit System Center Operations Manager ausführen.
ms.openlocfilehash: 80ef737c57006550111331db7f46fd607f7cf1ed
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238723"
---
# <a name="configure-scom-monitoring"></a>Konfigurieren der SCOM-Überwachung

Nach der Migration zu Skype für Business Server 2019, müssen Sie einige Aufgaben zum Konfigurieren von Skype für Business Server 2019 arbeiten mit System Center Operations Manager ausführen.
  
- Anwenden von Updates auf einem Server festgelegt, dass die zentrale Erkennung Logik zu verwalten.
    
- Aktualisieren Sie die zentrale Erkennung Serverregistrierungsschlüssel.
    
- Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so die Knoten des Kandidaten zentrale Erkennung überschrieben.
    
Anweisungen zum Ausführen aller dieser Aufgaben finden Sie weiter unten.
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>Anwenden von Updates auf einem Server festgelegt, dass die zentrale Erkennung Logik zu verwalten.

1. Wählen Sie einen Server, der die System Center Operations Manager-Agentdateien installiert und wird als kandidatenermittlungsknoten konfiguriert wurde. 
    
2. Anwenden von Updates auf diesem Server. Finden Sie im Thema [Anwenden von Updates](apply-updates.md).
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>Aktualisieren Sie die zentrale Erkennung Serverregistrierungsschlüssel.

1. Öffnen Sie auf dem Server festgelegt, dass die zentrale Erkennung Logik zu verwalten ein Windows PowerShell-Befehlsfenster. 
    
2. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Wenn Sie die Registrierung bearbeiten, können Fehler auftreten, den der Befehl nicht ordnungsgemäß, wenn der Registrierungsschlüssel bereits vorhanden ist. Wenn dies auftritt, können Sie den Fehler ignorieren. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so Watcher-Knoten des Kandidaten zentrale Erkennung überschrieben.

1. Auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, erweitern Sie die **Management Pack-Objekte** , und wählen Sie **Objektermittlungen**aus.
    
2. Klicken Sie auf **Bereich ändern**
    
3. Wählen Sie auf der Seite **Bereich Management Pack-Objekte** **LS-Ermittlungskandidat**aus.
    
4. Überschreiben der **LS Discovery Candidate Effektivwert** auf den Namen des Servers Candidate zuvor im Verfahren festgelegt. 
    
Um Ihre Änderungen abzuschließen, starten Sie den Healthdienst auf dem System Center Operations Manager-Stammverwaltungsserver neu.
  

