---
title: Windows PowerShell Cmdlets, Parameters und Parameterwerte in Skype for Business Online
description: Windows PowerShell Cmdlets, Parameters und Parameterwerte in Skype for Business Online.
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
ms.openlocfilehash: b1500713a02f85384be5a9cd9a7338b58d3c365f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555451"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="5e0e4-103">Windows PowerShell Cmdlets, Parameters und Parameterwerte in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5e0e4-103">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e0e4-104">_**Letztes Änderungsstand des Themas:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="5e0e4-104">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="5e0e4-105">Wenn Sie mit dem Befehlsfenster vertraut sind, das in allen Versionen von Windows gefunden wurde (oder wenn Sie mit MS-DOS vertraut sind), haben Sie einen ersten Vorsprung, wenn es darum geht, die Verwendung von Windows PowerShell zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-105">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="5e0e4-106">Geben Sie im Befehlsfenster einen Befehl ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-106">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="5e0e4-107">Als Antwort führt der Computer einen Befehl oder eine ausführbare Datei aus.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-107">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="5e0e4-108">Wenn Sie beispielsweise Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis zurückgeben möchten, geben Sie diesen Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-108">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="5e0e4-109">Sie erhalten wiederum Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis zurück:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-109">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="5e0e4-110">Das ist ein Beispiel für ein Ergebnis, wenn Sie nur den Namen eines Befehls oder einer ausführbaren Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-110">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="5e0e4-111">Viele der Befehle, die im Befehlsfenster ausgeführt werden, akzeptieren jedoch auch *Argumente*.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-111">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="5e0e4-112">Argumente sind zusätzliche Informationselemente, die an den Befehl übergeben werden, wodurch das Verhalten des Befehls geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-112">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="5e0e4-113">Wenn Sie beispielsweise nur die Namen der Dateien und des Ordners im aktuellen Verzeichnis anzeigen möchten – keine weiteren Informationen, wie die Größe der Datei oder des Ordners oder das Datum und die Uhrzeit, zu der der Ordner oder Ordner erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-113">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="5e0e4-114">In diesem Fall würden Sie das Argument **/b** anfügen, wenn Sie den Befehl dir ausführen:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-114">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="5e0e4-115">Wenn Sie das Argument **/b** einbeziehen, meldet der **dir** -Befehl nur die Namen der Ordner und Dateien, die im aktuellen Verzeichnis gefunden werden, zurück:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-115">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="5e0e4-116">Im vorherigen Befehl ist das Argument **/b** die einzige erforderliche Information, um die zurückgegebenen Daten auf Datei-und Ordnernamen zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-116">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="5e0e4-117">Dies ist häufig bei Befehlszeilenbefehlen der Fall: das bloße vorhanden sein eines Arguments ist alles, was erforderlich ist, um das Verhalten des Befehls zu ändern.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-117">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="5e0e4-118">(Das heißt, Sie schließen das Argument **/b** ein, um zusätzliche Informationen auszublenden, oder Sie schließen das Argument **/b** aus, um die zusätzlichen Informationen anzuzeigen.) Zu anderen Zeiten müssen Sie jedoch einen *Argumentwert*angeben.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-118">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="5e0e4-119">Ein Argumentwert sind zusätzliche Informationen, die an das Argument selbst übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-119">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="5e0e4-120">Beispielsweise können Sie mit dem Argument **/o** angeben, wie der Befehl dir die zurückgegebenen Daten sortieren soll.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-120">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="5e0e4-121">Unter anderen Optionen können Sie den Argumentwert **e** verwenden, um nach der Dateierweiterung zu sortieren, oder den Argumentwert **s** , um nach der Dateigröße zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-121">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="5e0e4-122">Mit diesem Befehl werden beispielsweise die zurückgegebenen Daten nach der Dateierweiterung sortiert.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-122">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="5e0e4-123">Beachten Sie, wie der Argumentwert **e** unmittelbar nach dem Argument **/o** eingeschlossen wird:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-123">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="5e0e4-124">Mithilfe unseres Beispielordners werden die zurückgegebenen Daten wie folgt aussehen, wobei die Dateien in alphabetischer Reihenfolge nach der Dateierweiterung sortiert werden:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-124">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="5e0e4-125">Oder, um Ihnen dabei zu helfen, genau das zu ermitteln, worüber wir sprechen:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-125">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="5e0e4-126">Obwohl Windows PowerShell unterschiedliche Terminologie verwendet, ist der grundlegende Ansatz beim Arbeiten mit Windows PowerShell mit dem Arbeiten mit dem Befehlsfenster identisch: Sie geben Befehle ein, fügen bei Bedarf Argumente und Argumentwerte ein und drücken dann die EINGABETASTE, um diese Befehle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-126">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="5e0e4-127">Wie bereits erwähnt, verwendet Windows PowerShell jedoch eine andere Terminologie als die Befehlsshell verwendet.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-127">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="5e0e4-128">In Windows PowerShell werden die Befehle, die Sie ausführen, als *Cmdlets*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-128">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="5e0e4-129">Die an ein Cmdlet übergebenen Argumente werden wiederum als *Parameter*bezeichnet, und die an einen Parameter übergebenen Werte werden als *Parameterwerte*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-129">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="5e0e4-130">Die obigen Definitionen sind etwas vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-130">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="5e0e4-131">Cmdlets sind im wesentlichen Minianwendungen, die nur in der Windows PowerShell Umgebung ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-131">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="5e0e4-132">Sie können jedoch auch andere Befehle und Anwendungen in Windows PowerShell ausführen, einschließlich der meisten Befehle und Anwendungen, die in einem Befehlsfenster ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-132">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="5e0e4-133">Wenn Sie beispielsweise Notepad in Windows PowerShell starten möchten, müssen Sie lediglich Folgendes eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-133">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="5e0e4-134">Im Hinblick auf die Verwaltung von Skype for Business Online müssen sich die meisten Administratoren jedoch auf Windows PowerShell-Cmdlets verlassen, um administrative Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-134">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="5e0e4-135">Zum Zeitpunkt gibt es nur sehr wenige andere Arten von Befehlen oder Anwendungen, die zum Verwalten von Skype for Business Online verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-135">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="5e0e4-136">Manchmal können die Skype for Business Online-Cmdlets ohne zusätzliche Argumente verwendet werden (wie bereits erwähnt, werden Argumente in Windows PowerShell als Parameter bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="5e0e4-136">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="5e0e4-137">Mit dem folgenden Befehl wird beispielsweise das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) ohne zusätzliche Parameter aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-137">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="5e0e4-138">Der Befehl gibt von sich aus Informationen zu allen Skype for Business Online-Benutzern zurück:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-138">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="5e0e4-139">Die meisten Skype for Business Online-Cmdlets akzeptieren jedoch auch Parameter (und Parameterwerte).</span><span class="sxs-lookup"><span data-stu-id="5e0e4-139">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="5e0e4-140">Halten Sie sich an den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-140">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="5e0e4-141">Dieser Befehl besteht aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-141">This command consists of three parts:</span></span>

  - <span data-ttu-id="5e0e4-142">Das Cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-142">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="5e0e4-143">Der Parameter Identity.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-143">The Identity parameter.</span></span> <span data-ttu-id="5e0e4-144">Beachten Sie, dass Parameter in Windows PowerShell immer mit einem Bindestrich (-) konfrontiert werden.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-144">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="5e0e4-145">Das bedeutet, dass für das gleiche Cmdlet der Parameter UnassignedUser mit dieser Syntax angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-145">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="5e0e4-146">Dies ist hilfreich zu wissen, nicht nur, weil Parameter mit einem Bindestrich vorangestellt werden müssen, sondern auch, da dies sich vom Befehlsfenster unterscheidet, wobei Argumente mit einem Schrägstrich (/) vorstehen:</span><span class="sxs-lookup"><span data-stu-id="5e0e4-146">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="5e0e4-147">Der Parameterwert **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-147">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="5e0e4-148">Der Befehl gibt übrigens Informationen zu einem bestimmten Benutzer zurück: der Benutzer mit der Identität kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5e0e4-148">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5e0e4-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e0e4-149">See Also</span></span>


<span data-ttu-id="5e0e4-150">[Eine Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="5e0e4-150">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

