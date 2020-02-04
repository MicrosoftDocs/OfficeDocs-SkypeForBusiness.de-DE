---
title: Bereitstellen der Topologie zum Ausführen der Auslastung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Bereitstellen der Topologie zum Ausführen der Auslastung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Bereitstellen der Topologie zum Ausführen der Auslastung

Je nach den vorhandenen Einstellungen und der Konfiguration von lync Server 2013 müssen Sie möglicherweise die folgenden Änderungen in Ihrer Umgebung vornehmen:

1.  Setzen Sie die Windows PowerShell-Ausführungsrichtlinie auf Unrestricted. Um die Einstellungen für die Ausführungsrichtlinie zu überprüfen, öffnen Sie die lync Server-Verwaltungsshell, und führen Sie den folgenden Befehl aus:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Wenn dieser Befehl nicht den Wert Unrestricted zurückgibt, führen Sie diesen Befehl aus:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Um lync Server 2013 effektiv zu konfigurieren, müssen Sie Folgendes tun:
    
      - Mit der lync Server 2013-Topologie vertraut sein (beispielsweise Computernamen, Dienstinstanzen, Websitenamen und Richtlinien).
    
      - Weisen Sie einige der Benutzer zu, die Gruppen erstellt wurden, wie etwa Gruppen-Sammelanschlüsse (beispielsweise SIP-URIs).

3.  Wenn Sie das Skript über die Befehlszeile ausführen möchten, können Sie Folgendes verwenden:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  In der Regel wird nach einem der Skripts in diesem Paket die resultierenden Ablaufverfolgungen aus dem Skript in einer Datei im gleichen Pfad gespeichert, von dem aus das Skript aufgerufen wurde, \<mit dem\>Namen ScriptName $h $ m $ s. txt. Beispiel: Ausführen von ArchivingPolicy. ps1 um 12:15 Uhr generiert eine Protokolldatei wie ArchivingPolicy121500. txt.

5.  Beachten Sie abschließend, dass Sie zwar Beispiele für die Konfiguration des Servers bereitgestellt haben, Sie aber für das ändern oder Löschen der Konfiguration verantwortlich sind, nachdem Sie die Auslastung ausgeführt haben.

</div>

</div>

<span> </span>

</div>

</div>

</div>

