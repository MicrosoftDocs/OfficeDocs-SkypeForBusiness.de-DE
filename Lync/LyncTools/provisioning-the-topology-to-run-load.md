---
title: Proversionierung der Topologie zum Ausführen der Last
description: Proversionierung der Topologie zum Ausführen des Ladevorganges
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da482fde949675acc1722305433b95b7a6a6b523
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578411"
---
# <a name="provisioning-the-topology-to-run-load"></a>Proversionierung der Topologie zum Ausführen der Last

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-04_

<div>

Je nach den vorhandenen Einstellungen und der Konfiguration von lync Server 2013 müssen Sie möglicherweise die folgenden Änderungen in Ihrer Umgebung vornehmen:

1.  Legen Sie die Ausführungsrichtlinie für Windows PowerShell auf Unrestricted fest. Um die Einstellungen für die Ausführungsrichtlinie zu überprüfen, öffnen Sie die lync Server-Verwaltungsshell und führen Sie den folgenden Befehl aus:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Wenn dieser Befehl nicht den Wert Unrestricted zurückgibt, führen Sie den folgenden Befehl aus:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Um lync Server 2013 effektiv konfigurieren zu können, müssen Sie Folgendes tun:
    
      - Sie sollten mit lync Server 2013 Topologie (beispielsweise Computernamen, Dienstinstanzen, Websitenamen und Richtlinien) vertraut sein.
    
      - Weisen Sie einige der erstellten Benutzergruppen zu, beispielsweise Reaktionsgruppen-Sammelanschlüsse (beispielsweise SIP-URIs).

3.  Um das Skript über die Befehlszeile auszuführen, können Sie Folgendes verwenden:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Nach dem Ausführen eines Skripts in diesem Paket werden die daraus resultierenden Ablaufverfolgungen in der Regel in einer Datei im gleichen Pfad gespeichert, von dem das Skript aufgerufen wurde, mit dem Namen \<scriptname\> $h $ m $s.txt. Beispiel: Running ArchivingPolicy.ps1 um 12:15 Uhr generiert eine Protokolldatei wie ArchivingPolicy121500.txt.

5.  Beachten Sie außerdem, dass Sie zwar Beispiele für die Konfiguration des Servers bereitgestellt haben, dass Sie jedoch für das ändern oder Löschen der Konfiguration verantwortlich sind, nachdem Sie die Ausführung der Last abgeschlossen haben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

