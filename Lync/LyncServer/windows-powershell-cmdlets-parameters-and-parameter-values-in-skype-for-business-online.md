---
title: Windows PowerShell-Cmdlets,-Parameter und-Parameterwerte in Skype for Business Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9fadf59b353458b2e7c48f597c11b92342e7edc
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Windows PowerShell-Cmdlets,-Parameter und-Parameterwerte in Skype for Business Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-05_

Wenn Sie mit dem in allen Versionen von Windows gefundenen Befehlsfenster vertraut sind (oder wenn Sie mit MS-DOS vertraut sind), haben Sie einen Vorsprung, wenn es um die Verwendung von Windows PowerShell geht. Geben Sie im Befehlsfenster einen Befehl ein, und drücken Sie die EINGABETASTE. Als Antwort führt der Computer einen Befehl oder eine ausführbare Datei aus. Wenn Sie beispielsweise Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis zurückgeben möchten, geben Sie diesen Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:

```console
dir
```

Sie erhalten wiederum Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis:

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

Dies ist ein Beispiel für ein Ergebnis, wenn Sie nur den Namen eines Befehls oder einer ausführbaren Datei eingeben. Viele der Befehle, die im Befehlsfenster ausgeführt werden, akzeptieren aber auch *Argumente*. Argumente sind zusätzliche Informationselemente, die an den Befehl übergeben werden, wodurch das Verhalten des Befehls geändert wird. Wenn Sie beispielsweise nur die Namen der Dateien und Ordner im aktuellen Verzeichnis anzeigen möchten, gibt es keine anderen Informationen, beispielsweise die Größe der Datei oder des Ordners, oder das Datum und die Uhrzeit, zu dem der Ordner oder Ordner erstellt wurde. In diesem Fall fügen Sie das Argument **/b** ein, wenn Sie den Befehl dir ausführen:

```console
dir /b
```

Wenn Sie das Argument **/b** einbeziehen, gibt der Befehl **dir** nur die Namen der Ordner und Dateien zurück, die im aktuellen Verzeichnis zu finden sind:

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

Im vorhergehenden Befehl ist das Argument **/b** die einzige Information, die erforderlich ist, um die zurückgegebenen Daten auf Datei-und Ordnernamen zu begrenzen. Dies ist häufig bei Befehlszeilenbefehlen der Fall: das bloße vorhanden sein eines Arguments ist alles, was erforderlich ist, um das Verhalten des Befehls zu ändern. (Sie fügen also das Argument **/b** hinzu, um zusätzliche Informationen auszublenden, oder Sie schließen das Argument **/b** aus, um die zusätzlichen Informationen anzuzeigen.) Zu anderen Zeiten müssen Sie jedoch einen *Argumentwert*angeben. Ein Argumentwert ist zusätzliche Informationen, die an das Argument selbst übergeben werden. So können Sie beispielsweise mit dem Argument **/o** angeben, wie der Befehl dir die zurückgegebenen Daten sortieren soll. Neben anderen Optionen können Sie den Argumentwert **e** verwenden, um nach Dateierweiterung oder dem Argumentwert **s** zu sortieren, um nach Dateigröße zu sortieren. Dieser Befehl sortiert beispielsweise die zurückgegebenen Daten nach Dateierweiterung. Beachten Sie, dass der Argumentwert **e** unmittelbar nach dem **/o** -Argument enthalten ist:

```console
dir /oe
```

Bei Verwendung unseres Beispielordners sehen die zurückgegebenen Daten wie folgt aus, wobei die Dateien alphabetisch nach Dateierweiterung sortiert werden:

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

Oder, um Ihnen zu helfen, genau zu bestimmen, worüber wir sprechen:

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Obwohl Windows PowerShell unterschiedliche Terminologie verwendet, ist der grundlegende Ansatz für die Arbeit mit Windows PowerShell identisch mit der Arbeit mit dem Befehlsfenster: Sie geben Befehle ein, fügen Argumente und Argumentwerte nach Bedarf ein und drücken dann die EINGABETASTE, um Sie auszuführen. Diese Befehle. Wie bereits erwähnt, verwendet Windows PowerShell jedoch eine andere Terminologie als die Befehlsshell verwendet. In Windows PowerShell werden die ausgeführten Befehle als *Cmdlets*bezeichnet. Die an ein Cmdlet übergebenen Argumente werden wiederum als *Parameter*bezeichnet, und die an einen Parameter übergebenen Werte werden als *Parameterwerte*bezeichnet.

Die vorhergehenden Definitionen sind etwas vereinfacht. Cmdlets sind im wesentlichen Minianwendungen, die nur in der Windows PowerShell-Umgebung ausgeführt werden können. Sie können jedoch auch andere Befehle und Anwendungen in Windows PowerShell ausführen, einschließlich der meisten Befehle und Anwendungen, die über ein Befehlsfenster ausgeführt werden können. Wenn Sie den Editor beispielsweise in Windows PowerShell starten möchten, müssen Sie nur Folgendes eingeben und die EINGABETASTE drücken:

```console
notepad.exe
```

Bei der Verwaltung von Skype for Business Online sind die meisten Administratoren jedoch auf Windows PowerShell-Cmdlets angewiesen, um administrative Aufgaben auszuführen. Zur Zeit gibt es nur sehr wenige andere Arten von Befehlen oder Anwendungen, die für die Verwaltung von Skype for Business Online verwendet werden können. Manchmal können die Skype for Business Online-Cmdlets ohne zusätzliche Argumente verwendet werden (wie bereits erwähnt, werden Argumente in Windows PowerShell als Parameter bezeichnet). Mit dem folgenden Befehl wird beispielsweise das Cmdlet " [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) " ohne zusätzliche Parameter aufgerufen. Der Befehl gibt für sich selbst Informationen zu allen Skype for Business Online-Benutzern zurück:

```powershell
Get-CsOnlineUser
```

Die meisten der Skype for Business Online-Cmdlets akzeptieren aber auch Parameter (und Parameterwerte). Nehmen Sie den folgenden Befehl in Frage:

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Dieser Befehl besteht aus drei Teilen:

  - Das Cmdlet **Get-CsOnlineUser**.

  - Der Parameter Identity. Beachten Sie, dass in Windows PowerShell den Parametern immer ein Bindestrich (-) vorangestellt wird. Das bedeutet, dass für dieses Cmdlet der UnassignedUser-Parameter mit der folgenden Syntax angegeben wird:
    
    ```powershell
    -UnassignedUser
    ```
    
    Dies ist hilfreich, um nicht nur zu wissen, dass den Parametern ein Bindestrich vorangestellt werden muss, sondern auch, weil sich dies vom Befehlsfenster unterscheidet, in dem Argumente mit einem Schrägstrich (/) vorangestellt werden:
    
    ```console
    /b
    ```

  - Der Parameterwert **kenmyer@litwareinc.com**.

Dieser Befehl gibt im übrigen Informationen zu einem bestimmten Benutzer zurück: der Benutzer mit der Identität kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Siehe auch


[Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

