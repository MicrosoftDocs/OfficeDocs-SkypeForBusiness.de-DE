---
title: Windows PowerShell Cmdlets, Parameters und Parameterwerte in Skype for Business Online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ad45c9deecf364c273ff64e939c4379d169f3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499962"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Windows PowerShell Cmdlets, Parameters und Parameterwerte in Skype for Business Online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-05_

Wenn Sie mit dem Befehlsfenster vertraut sind, das in allen Versionen von Windows gefunden wurde (oder wenn Sie mit MS-DOS vertraut sind), haben Sie einen ersten Vorsprung, wenn es darum geht, die Verwendung von Windows PowerShell zu erlernen. Geben Sie im Befehlsfenster einen Befehl ein, und drücken Sie die EINGABETASTE. Als Antwort führt der Computer einen Befehl oder eine ausführbare Datei aus. Wenn Sie beispielsweise Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis zurückgeben möchten, geben Sie diesen Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:

```console
dir
```

Sie erhalten wiederum Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis zurück:

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Das ist ein Beispiel für ein Ergebnis, wenn Sie nur den Namen eines Befehls oder einer ausführbaren Datei eingeben. Viele der Befehle, die im Befehlsfenster ausgeführt werden, akzeptieren jedoch auch *Argumente*. Argumente sind zusätzliche Informationselemente, die an den Befehl übergeben werden, wodurch das Verhalten des Befehls geändert wird. Wenn Sie beispielsweise nur die Namen der Dateien und des Ordners im aktuellen Verzeichnis anzeigen möchten – keine weiteren Informationen, wie die Größe der Datei oder des Ordners oder das Datum und die Uhrzeit, zu der der Ordner oder Ordner erstellt wurde. In diesem Fall würden Sie das Argument **/b** anfügen, wenn Sie den Befehl dir ausführen:

```console
dir /b
```

Wenn Sie das Argument **/b** einbeziehen, meldet der **dir** -Befehl nur die Namen der Ordner und Dateien, die im aktuellen Verzeichnis gefunden werden, zurück:

```console
Deploy
Intel
PerfLogs
Program Files
Program Files (x86)
Users
Windows
pldok.log
RHDSetup.exe
setup.doc
```

Im vorherigen Befehl ist das Argument **/b** die einzige erforderliche Information, um die zurückgegebenen Daten auf Datei-und Ordnernamen zu begrenzen. Dies ist häufig bei Befehlszeilenbefehlen der Fall: das bloße vorhanden sein eines Arguments ist alles, was erforderlich ist, um das Verhalten des Befehls zu ändern. (Das heißt, Sie schließen das Argument **/b** ein, um zusätzliche Informationen auszublenden, oder Sie schließen das Argument **/b** aus, um die zusätzlichen Informationen anzuzeigen.) Zu anderen Zeiten müssen Sie jedoch einen *Argumentwert*angeben. Ein Argumentwert sind zusätzliche Informationen, die an das Argument selbst übergeben werden. Beispielsweise können Sie mit dem Argument **/o** angeben, wie der Befehl dir die zurückgegebenen Daten sortieren soll. Unter anderen Optionen können Sie den Argumentwert **e** verwenden, um nach der Dateierweiterung zu sortieren, oder den Argumentwert **s** , um nach der Dateigröße zu sortieren. Mit diesem Befehl werden beispielsweise die zurückgegebenen Daten nach der Dateierweiterung sortiert. Beachten Sie, wie der Argumentwert **e** unmittelbar nach dem Argument **/o** eingeschlossen wird:

```console
dir /oe
```

Mithilfe unseres Beispielordners werden die zurückgegebenen Daten wie folgt aussehen, wobei die Dateien in alphabetischer Reihenfolge nach der Dateierweiterung sortiert werden:

```console
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Oder, um Ihnen dabei zu helfen, genau das zu ermitteln, worüber wir sprechen:

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Obwohl Windows PowerShell unterschiedliche Terminologie verwendet, ist der grundlegende Ansatz beim Arbeiten mit Windows PowerShell mit dem Arbeiten mit dem Befehlsfenster identisch: Sie geben Befehle ein, fügen bei Bedarf Argumente und Argumentwerte ein und drücken dann die EINGABETASTE, um diese Befehle auszuführen. Wie bereits erwähnt, verwendet Windows PowerShell jedoch eine andere Terminologie als die Befehlsshell verwendet. In Windows PowerShell werden die Befehle, die Sie ausführen, als *Cmdlets*bezeichnet. Die an ein Cmdlet übergebenen Argumente werden wiederum als *Parameter*bezeichnet, und die an einen Parameter übergebenen Werte werden als *Parameterwerte*bezeichnet.

Die obigen Definitionen sind etwas vereinfacht. Cmdlets sind im wesentlichen Minianwendungen, die nur in der Windows PowerShell Umgebung ausgeführt werden können. Sie können jedoch auch andere Befehle und Anwendungen in Windows PowerShell ausführen, einschließlich der meisten Befehle und Anwendungen, die in einem Befehlsfenster ausgeführt werden können. Wenn Sie beispielsweise Notepad in Windows PowerShell starten möchten, müssen Sie lediglich Folgendes eingeben und die EINGABETASTE drücken:

```console
notepad.exe
```

Im Hinblick auf die Verwaltung von Skype for Business Online müssen sich die meisten Administratoren jedoch auf Windows PowerShell-Cmdlets verlassen, um administrative Aufgaben auszuführen. Zum Zeitpunkt gibt es nur sehr wenige andere Arten von Befehlen oder Anwendungen, die zum Verwalten von Skype for Business Online verwendet werden können. Manchmal können die Skype for Business Online-Cmdlets ohne zusätzliche Argumente verwendet werden (wie bereits erwähnt, werden Argumente in Windows PowerShell als Parameter bezeichnet). Mit dem folgenden Befehl wird beispielsweise das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) ohne zusätzliche Parameter aufgerufen. Der Befehl gibt von sich aus Informationen zu allen Skype for Business Online-Benutzern zurück:

```powershell
Get-CsOnlineUser
```

Die meisten Skype for Business Online-Cmdlets akzeptieren jedoch auch Parameter (und Parameterwerte). Halten Sie sich an den folgenden Befehl:

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Dieser Befehl besteht aus drei Teilen:

  - Das Cmdlet **Get-CsOnlineUser**.

  - Der Parameter Identity. Beachten Sie, dass Parameter in Windows PowerShell immer mit einem Bindestrich (-) konfrontiert werden. Das bedeutet, dass für das gleiche Cmdlet der Parameter UnassignedUser mit dieser Syntax angezeigt wird:
    
    ```powershell
    -UnassignedUser
    ```
    
    Dies ist hilfreich zu wissen, nicht nur, weil Parameter mit einem Bindestrich vorangestellt werden müssen, sondern auch, da dies sich vom Befehlsfenster unterscheidet, wobei Argumente mit einem Schrägstrich (/) vorstehen:
    
    ```console
    /b
    ```

  - Der Parameterwert **kenmyer@litwareinc.com**.

Der Befehl gibt übrigens Informationen zu einem bestimmten Benutzer zurück: der Benutzer mit der Identität kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Siehe auch


[Eine Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

