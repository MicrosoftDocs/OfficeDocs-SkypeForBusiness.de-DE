---
title: 'Lync Server 2013: lync precall Diagnostics Tool'
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
ms.openlocfilehash: 79009ce890e37e7238e3fef18f719fb3da411889
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Tool für die lync-voranruf Diagnose in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-11-04_

Das lync precall Diagnostics Tool (PCD) ist eine clientbasierte Anwendung, mit der Sie sehen können, wie sich der aktuelle Status Ihres Netzwerks auf die Audioqualität in einem bevorstehenden Enterprise-VoIP-Anruf auswirkt.

PCD ist besonders nützlich in Situationen, in denen der letzte Hop eines Netzwerks am schwächsten ist (beispielsweise mit Laptops in einem öffentlichen WLAN-Netzwerk oder mit privaten Benutzern). PCD erstellt einen kleinen Paketdaten Strom, der diese letzte Etappe des Netzwerks durchläuft. Das Tool analysiert dann den Paketdaten Strom, um abzuschätzen, wie sich Jitter und Verlust entlang dieses Beins möglicherweise auf die Anrufqualität auswirken und dann einen Bericht bereitstellen. Sie können PCD kontinuierlich auf dem Client ausführen, auch wenn Anrufe getätigt werden. Der Paketdaten Strom hat keinen wesentlichen Einfluss auf die Bandbreite.

**Die neueste Version der PCD, Version 1,1, umfasst die folgenden Verbesserungen:**

  - Unterstützung für längere Kennwörter, die jetzt bis zu 127 Zeichen lang sein können

  - Zusätzliche Diagnose für Authentifizierungs Anmeldeprobleme

  - Bessere Unterstützung für lync-hybridbereitstellungen

  - Aktualisierungen der Anmelde Informationsauswahl

  - Stabilitätsverbesserungen

Wir freuen uns über Feedback. Senden Sie alle Support Fragen oder Probleme an den [PCD-Feedback](mailto:pcdfb@microsoft.com) - <pcdfb@microsoft.com>Alias unter.

Dieses Thema enthält die folgenden Abschnitte:

  - Lync PCD-Versionen

  - Lync PCD-System Anforderungen

  - Lync PCD-Features

  - Ausführung von lync PCD

  - Deinstallieren von lync PCD

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Lync PCD-Versionen

In diesem Thema werden die folgenden Versionen des Tools beschrieben, die zum kostenlosen Download zur Verfügung stehen:

  - Windows-Desktop-[https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)app ()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Lync PCD-System Anforderungen

<div>


> [!NOTE]  
> Für PCD ist es erforderlich, dass Unified Communications Web API (UCWA) installiert und konfiguriert werden, um Mobile Clients in der lync Server-Bereitstellung zu unterstützen. UCWA wird mit lync Server installiert.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Windows-Desktop-App-Anforderungen

  - Eine beliebige Edition des Windows 7 oder Windows 8 Betriebssystems

  - Microsoft .NET Framework 4.5 verfügbar unter[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Lync PCD-Features

Lync PCD umfasst die folgenden Features:

  - Bei Bedarf in Standardausführung ausführen (2 Minuten Bursts)

  - Ausführen von Always on (bis zu 24 Stunden im Modus "Angedockte Ansicht")

  - Verlaufsansicht der Test Läufe

  - Diagnostizieren von Anmeldefehlern (nur lync PCD für Windows 8)

![Anmeldebildschirm Schuss für lync PCD-Features](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Anmeldebildschirm Schuss für lync PCD-Features")

  - Grafische Ansicht der Netzwerk Metriken – Netzwerk-MOS, Paketverlust und interarrival-Jitter im Vollbildmodus und angedockte Ansicht.

**Vollbildansicht**

![Testergebnis Diagramme für das precall-Diagnose Tool](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Testergebnis Diagramme für das precall-Diagnose Tool")

**Angedockte Ansicht**

![Testergebnisse für die Verwendung des precall-Diagnosetools](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Testergebnisse für die Verwendung des precall-Diagnosetools")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Ausführung von lync PCD

<div>

## <a name="running-windows-desktop-app"></a>Windows-Desktop-App wird gestartet

1.  Um die PCD auf einem Windows 7 System zu starten, wählen Sie im **Startmenü** die Option " **Diagnose precall** " aus.
    
    Um die PCD auf einem Windows 8 System zu starten, wählen Sie das Symbol auf dem Startbildschirm aus, oder suchen Sie nach "Diagnose mit vorrufen".
    
    ![Symbol für das precall-Diagnosetool](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Symbol für das precall-Diagnosetool")

2.  Wenn das Tool gestartet wird, wählen Sie Ihre bevorzugte Methode zum Bereitstellen von Anmeldeinformationen aus, und wählen Sie im Dialogfeldoptionen für das Tool für die **Anruf Diagnose** den Netzwerkbetriebs Modus aus, und wählen Sie dann **OK**aus:

3.  Wählen Sie die Schaltfläche **Test starten** aus, um die Diagnose zu starten.
    
    Wenn Sie die Option **Netzwerkanmeldeinformationen verwenden** ausgewählt haben, wird der Test sofort gestartet.
    
    Wenn Sie die Option **Meine Anmeldeinformationen eingeben** aktiviert haben, wird das Dialogfeld **Windows-Sicherheit** geöffnet. Nachdem Sie Ihre Anmeldeinformationen eingegeben haben, wird der Test gestartet.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Deinstallieren von lync PCD

Um lync PCD zu entfernen, führen Sie das Verfahren für Ihr Betriebssystem aus:

  - Öffnen Sie auf einem Windows 7 **System die Systemsteuerung,** wählen Sie **Programme und Funktionen**aus, und doppelklicken Sie auf **lync 2013 Diagnose**für die vorab Verbindung.

  - Klicken Sie auf einem Windows 8 System mit der rechten Maustaste auf die PCD-Kachel, und klicken Sie auf der APP-Leiste am unteren Rand des Startbildschirms auf **deinstallieren** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

