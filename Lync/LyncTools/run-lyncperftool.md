---
title: Ausführen von LyncPerfTool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82df3ee8cfccb91aec4e284674ace72e23a202c4
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Ausführen von LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Vor dem Ausführen des lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) müssen Sie Benutzer, Kontakte und Szenarien erstellen. Ausführliche Informationen zur Verwendung der Tools zum Ausführen dieser Aktionen finden Sie unter [Erstellen von Benutzern und Kontakten](create-users-and-contacts.md) und [Konfigurieren des Benutzerprofils](configure-user-profile.md). Durch das Ausführen dieser Tools wird auch eine Datei generiert, die LyncPerfTool.exe als Teil einer Batchdatei mit den erforderlichen Parametern ausgeführt wird.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Ausführung des lync Server 2013-Tools für Stress und Leistung

Mit dem UserProfileGenerator.exe-Tool wird eine Batchdatei erstellt, mit der Sie LyncPerfTool.exe ausführen können, indem Sie die LyncPerfTool-Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden. In der Batchdatei wird eine Instanz von LyncPerfTool.exe pro Konfigurationsdatei ausgeführt. Führen Sie die folgenden Schritte aus, um die Batchdatei auszuführen:

1.  Kopieren Sie den Ordner mit den Konfigurationsordnern und-Dateien in das Verzeichnis, das LyncStressTool.exe auf jedem Clientcomputer enthält. (Wenn Sie beispielsweise die Konfigurationsdateien im Ordner 1,28 \_ 13.16.16 generiert haben, kopieren Sie diesen Ordner in den Ordner, der LyncPerfTool.exe auf jedem Client enthält.)

2.  Navigieren Sie zum entsprechend nummerierten Clientordner, und führen Sie das RunClient-Batchskript aus. Sie können einfach im Windows-Explorer auf die Batchdatei doppelklicken, und alle Konfigurationsdateien für diese Client Nummer werden ausgeführt. Sie können das Skript auch mithilfe der folgenden Syntax aus dem entsprechenden Clientordner ausführen:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Wenn Sie LyncPerfTool.exe direkt ausführen möchten, öffnen Sie eine Eingabeaufforderung, und geben Sie den folgenden Befehl an der Befehlszeile ein (wenn Sie dies zum ersten Mal tun, müssen Sie die Leistungsindikatoren regsvr32/i/n/s LyncPerfToolPerf.dll registrieren, wie im Hinweis weiter unten in diesem Thema gezeigt) :LyncPerfTool.exe/file:\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Damit das Tool die Werte in der Konfigurationsdatei anzeigen kann, schließen Sie den/displayfile-Parameter auf dem vorherigen Befehl wie folgt ein:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Drücken Sie STRG + C, um den Vorgang zu beenden.

<div>


> [!NOTE]  
> Bevor Sie LyncPerfTool direkt ausführen, müssen Sie die Leistungsindikatoren registrieren. Geben Sie den folgenden Befehl ein, um Leistungsindikatoren zu registrieren:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Jede Instanz von LyncPerfTool.exe, die Sie starten, beginnt sofort mit dem Anmelden von Benutzern, normalerweise mit einer Rate von einem Benutzer pro Sekunde. Die maximale Benutzeranmelde Rate für den Pool beträgt ungefähr 12 pro Sekunde. Dies bedeutet, dass Sie nicht mehr als 12 LyncPerfTool-Instanzen gleichzeitig starten sollten, während sich die Benutzer immer noch anmelden. 1000 Benutzer benötigen ungefähr 20 Minuten, um sich vollständig anzumelden, um eine pro Sekunde.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen von Benutzern und Kontakten](create-users-and-contacts.md)  
[Konfigurieren des Benutzerprofils](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

