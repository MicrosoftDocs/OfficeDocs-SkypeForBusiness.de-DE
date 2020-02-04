---
title: 'Lync Server 2013: lync-Tool zur voranruf Diagnose'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 004d3b30dc2c2886eb7a2d8977f1da062277cc92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Lync-Tool für die voranruf Diagnose in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-11-04_

Das lync precall Diagnostics Tool (PCD) ist eine clientbasierte Anwendung, mit der Sie sehen können, wie sich der aktuelle Zustand Ihres Netzwerks in einem bevorstehenden Enterprise-VoIP-Anruf auf die Audioqualität auswirken kann.

PCD eignet sich besonders für Situationen, in denen der letzte Hop eines Netzwerks wahrscheinlich am schwächsten ist (beispielsweise bei Laptops mit einem öffentlichen WLAN-Netzwerk oder privaten Benutzern). PCD erstellt einen kleinen Paketdaten Strom, der diese letzte Etappe des Netzwerks durchläuft. Das Tool analysiert dann den Paketdaten Strom, um zu schätzen, wie sich der Jitter und der Verlust an diesem Bein auf die Anrufqualität auswirken können, und stellt dann einen Bericht bereit. Sie können PCD kontinuierlich auf dem Client ausführen, auch wenn Anrufe getätigt werden. Der Paketdaten Strom hat keinen signifikanten Einfluss auf die Bandbreite.

**Die neueste Version der PCD, Version 1,1, umfasst die folgenden Verbesserungen:**

  - Unterstützung für längere Kennwörter, die nun bis zu 127 Zeichen lang sein können

  - Zusätzliche Diagnose für Anmeldeprobleme bei der Authentifizierung

  - Bessere Unterstützung für lync-hybridbereitstellungen

  - Aktualisierungen der Anmelde Informationsauswahl

  - Verbesserungen bei der Stabilität

Wir freuen uns über Ihr Feedback. Senden Sie bitte alle Support <pcdfb@microsoft.com>-Fragen oder Probleme an den PCD- [Feedback](mailto:pcdfb@microsoft.com) -Alias unter.

Dieses Thema enthält die folgenden Abschnitte:

  - Lync-PCD-Versionen

  - System Anforderungen für lync-PCD

  - Funktionen von lync PCD

  - Ausführen von lync PCD

  - Deinstallieren von lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync-PCD-Versionen

In diesem Thema werden die folgenden Versionen des Tools beschrieben, die zum kostenlosen Download zur Verfügung stehen:

  - Windows-Desktop-[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)app ()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>System Anforderungen für lync-PCD

<div>


> [!NOTE]  
> Für PCD muss die Unified Communications Web API (UCWA) installiert und für die Unterstützung mobiler Clients in der lync Server-Bereitstellung konfiguriert sein. UCWA wird mit lync Server installiert.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows-Desktop-App-Anforderungen

  - Eine beliebige Edition des Betriebssystems Windows 7 oder Windows 8

  - Microsoft .NET Framework 4,5 verfügbar unter[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Funktionen von lync PCD

Lync PCD umfasst die folgenden Features:

  - Standardmäßige Ausführung bei Bedarf (2 Minuten Bursts)

  - Ausführen von "immer aktiviert" (bis zu 24 Stunden in der angedockten Ansicht)

  - Verlaufsansicht ihrer Testläufe

  - Diagnostizieren von Anmeldefehlern (nur lync PCD für Windows 8)

![Bildschirmfoto der lync PCD-Features für den Anmeldestatus](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Bildschirmfoto der lync PCD-Features für den Anmeldestatus")

  - Grafische Ansicht von Netzwerk Metriken – Netzwerk-MOS, Paketverlust und interarrival-Jitter im Vollbildmodus und angedockten Ansicht.

**Vollbildansicht**

![Testergebnis Diagramme für precall-Diagnosetools](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Testergebnis Diagramme für precall-Diagnosetools")

**Angedockte Ansicht**

![Testergebnisse für die Nutzung des precall-Diagnosetools](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Testergebnisse für die Nutzung des precall-Diagnosetools")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Ausführen von lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Ausführen der Windows-Desktop-App

1.  Wenn Sie die PCD auf einem Windows 7-System starten möchten, wählen Sie im **Startmenü** die Option **precall Diagnostics** aus.
    
    Wenn Sie die PCD unter einem Windows 8-System starten möchten, wählen Sie das Symbol auf dem Startbildschirm aus, oder suchen Sie nach "Diagnose für Vorgespräche".
    
    ![Symbol für das precall-Diagnosetool](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Symbol für das precall-Diagnosetool")

2.  Wenn das Tool gestartet wird, wählen Sie die bevorzugte Methode zum Bereitstellen von Anmeldeinformationen aus, und wählen Sie im Dialogfeldoptionen für das Tool für die **voranruf-Diagnose** den Netzwerkmodus aus, und wählen Sie dann **OK**aus:

3.  Wählen Sie die Schaltfläche **Test starten** aus, um mit der Ausführung der Diagnose zu beginnen.
    
    Wenn Sie die Option **Netzwerkanmeldeinformationen verwenden** ausgewählt haben, wird der Test sofort gestartet.
    
    Wenn Sie die Option **Ich möchte meine Anmeldeinformationen eingeben** aktiviert haben, wird das Dialogfeld **Windows-Sicherheit** geöffnet. Nachdem Sie Ihre Anmeldeinformationen eingegeben haben, wird der Test gestartet.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Deinstallieren von lync PCD

Um lync PCD zu entfernen, führen Sie das Verfahren für Ihr Betriebssystem aus:

  - Öffnen Sie auf einem Windows 7-System **die Systemsteuerung,** wählen Sie **Programme und Funktionen**aus, und doppelklicken Sie auf **lync 2013-Diagnose**.

  - Klicken Sie unter Windows 8 mit der rechten Maustaste auf die PCD-Kachel, und klicken Sie auf der APP-Leiste am unteren Rand des Startbildschirms auf **deinstallieren** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

