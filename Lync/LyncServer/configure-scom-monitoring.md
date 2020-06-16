---
title: Konfigurieren der SCOM-Überwachung
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>Konfigurieren der SCOM-Überwachung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Nach der Migration zu Microsoft lync Server 2013 müssen Sie einige Aufgaben ausführen, um lync Server 2013 für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren.

  - Wenden Sie lync Server 2010 Updates auf einen Server an, der zur Verwaltung der zentralen Ermittlungslogik gewählt wurde.

  - Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.

  - Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Kandidaten-zentral Suche außer Kraft gesetzt wird.

Anweisungen für diese Aufgaben finden Sie unten.

**Wenden Sie lync Server 2010 Updates auf einen Server an, der zur Verwaltung der zentralen Ermittlungslogik gewählt wurde.**

1.  Wählen Sie einen Server aus, auf dem die System Center Operations Manager-Agentdateien installiert sind und der als Kandidatenermittlungsknoten konfiguriert ist.

2.  Wenden Sie lync Server 2010 Updates auf diesen Server an. Siehe das Thema [Apply lync Server 2010 Updates](apply-lync-server-2010-updates.md).

**Aktualisieren Sie den Serverregistrierungsschlüssel des Kandidaten für die zentrale Erkennung.**

1.  Öffnen Sie auf dem Server, der für die Verwaltung der zentralen Ermittlungslogik ausgewählt wurde, ein Windows PowerShell Befehlsfenster.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.

    
    </div>

**Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver so, dass der Knoten Candidate Central Discovery Watcher außer Kraft gesetzt wird.**

1.  Erweitern Sie auf einem Computer, auf dem die System Center Operations Manager-Konsole installiert wurde, **Management Pack-Objekte**, und wählen Sie **Objektermittlungen** aus.

2.  Klicken Sie auf **Bereich ändern**.

3.  Wählen Sie auf der Seite **Management Pack-Objekte in Bereiche einteilen** den Eintrag **LS-Ermittlungskandidat** aus.

4.  Überschreiben Sie den **Effektivwert für den LS-Ermittlungskandidaten** mit dem Namen des zuvor ausgewählten Kandidatenservers.

Starten Sie zuletzt den Integritätsdienst auf dem System Center Operations Manager-Stammverwaltungsserver neu, um Ihre Änderungen abzuschließen.

</div>

<span> </span>

</div>

</div>

</div>

