---
title: Ausführen von LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29a36be8c6703dad52e6c36d363ae23013643bd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Ausführen von LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Vor dem Ausführen des lync Server 2013-Stress-und-Leistungstools (LyncPerfTool. exe) müssen Sie Benutzer, Kontakte und Szenarien erstellen. Details zum Verwenden der Tools zum Ausführen dieser Aktionen finden Sie unter [Erstellen von Benutzern und Kontakten](create-users-and-contacts.md) und [Konfigurieren des Benutzerprofils](configure-user-profile.md). Wenn Sie diese Tools ausführen, wird auch eine Datei generiert, die LyncPerfTool. exe als Teil einer Batchdatei ausführt, wobei die erforderlichen Parameter enthalten sind.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Ausführen des lync Server 2013-Tools für Stress und Leistung

Das Tool "UserProfileGenerator. exe" erstellt eine Batchdatei, mit der Sie LyncPerfTool. exe ausführen können, indem Sie die LyncPerfTool-Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden. Die Batchdatei führt eine Instanz von LyncPerfTool. exe pro Konfigurationsdatei aus. Gehen Sie wie folgt vor, um die Batchdatei auszuführen:

1.  Kopieren Sie den Ordner, der die Konfigurationsordner und-Dateien enthält, in das Verzeichnis, das LyncStressTool. exe auf jedem Clientcomputer enthält. (Wenn Sie beispielsweise die Konfigurationsdateien in dem Ordner mit dem Namen 1,28\_13.16.16 generiert haben, kopieren Sie diesen Ordner in den Ordner, in dem sich LyncPerfTool. exe auf jedem Client befindet.)

2.  Navigieren Sie zum entsprechend nummerierten Clientordner, und führen Sie das RunClient-Batchskript aus. Sie können einfach im Windows-Explorer auf die Batchdatei doppelklicken, und es werden alle Konfigurationsdateien für diese Client Nummer ausgeführt. Sie können das Skript auch über den entsprechenden Clientordner ausführen, indem Sie die folgende Syntax verwenden:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Wenn Sie LyncPerfTool. exe direkt ausführen möchten, öffnen Sie eine Eingabeaufforderung, und geben Sie dann den folgenden Befehl in der Befehlszeile ein (wenn Sie diese zum ersten Mal ausführen, müssen Sie die Leistungsindikatoren regsvr32/i/n/s LyncPerfToolPerf. dll registrieren, wie in der Notiz weiter unten in diesem Thema angezeigt wird)\<: LyncPerfTool. exe/file: configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Damit das Tool die Werte in der Konfigurationsdatei anzeigt, fügen Sie den/displayfile-Parameter für den vorhergehenden Befehl wie folgt ein:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Drücken Sie STRG + C, um den Vorgang zu beenden.

<div>


> [!NOTE]  
> Bevor Sie LyncPerfTool direkt ausführen können, müssen Sie die Leistungsindikatoren registrieren. Geben Sie den folgenden Befehl ein, um Leistungsindikatoren zu registrieren:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Jede Instanz von LyncPerfTool. exe, die Sie starten, beginnt sofort mit der Anmeldung bei Benutzern, in der Regel mit einer Rate von einem Benutzer pro Sekunde. Die Höchstzahl der Benutzeranmelde Rate für den Pool beträgt ca. 12 pro Sekunde. Das bedeutet, dass Sie nicht mehr als 12 LyncPerfTool-Instanzen gleichzeitig starten sollten, während sich die Benutzer noch anmelden. 1000-Benutzer benötigen ca. 20 Minuten für die vollständige Anmeldung pro Sekunde.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von Benutzern und Kontakten](create-users-and-contacts.md)  
[Benutzerprofil konfigurieren](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

