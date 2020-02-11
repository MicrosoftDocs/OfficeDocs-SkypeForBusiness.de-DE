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

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a><span data-ttu-id="4635f-102">Windows PowerShell-Cmdlets,-Parameter und-Parameterwerte in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4635f-102">Windows PowerShell cmdlets, parameters, and parameter values in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4635f-103">_**Letztes Änderungsdatum des Themas:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="4635f-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="4635f-104">Wenn Sie mit dem in allen Versionen von Windows gefundenen Befehlsfenster vertraut sind (oder wenn Sie mit MS-DOS vertraut sind), haben Sie einen Vorsprung, wenn es um die Verwendung von Windows PowerShell geht.</span><span class="sxs-lookup"><span data-stu-id="4635f-104">If you are familiar with the command window found in all versions of Windows (or if you are familiar with MS-DOS), then you’ll have a head start when it comes to learning how to use Windows PowerShell.</span></span> <span data-ttu-id="4635f-105">Geben Sie im Befehlsfenster einen Befehl ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="4635f-105">In the command window, you type a command and press ENTER.</span></span> <span data-ttu-id="4635f-106">Als Antwort führt der Computer einen Befehl oder eine ausführbare Datei aus.</span><span class="sxs-lookup"><span data-stu-id="4635f-106">In response, the computer runs a command or an executable file.</span></span> <span data-ttu-id="4635f-107">Wenn Sie beispielsweise Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis zurückgeben möchten, geben Sie diesen Befehl an der Eingabeaufforderung ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="4635f-107">For example, to return information about all the files and folders in the current directory, you’d type this command at the command prompt and then press ENTER:</span></span>

```console
dir
```

<span data-ttu-id="4635f-108">Sie erhalten wiederum Informationen zu allen Dateien und Ordnern im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="4635f-108">In turn, you get back information about all the files and folders in the current directory:</span></span>

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

<span data-ttu-id="4635f-109">Dies ist ein Beispiel für ein Ergebnis, wenn Sie nur den Namen eines Befehls oder einer ausführbaren Datei eingeben.</span><span class="sxs-lookup"><span data-stu-id="4635f-109">That’s one example of a result when you do type only the name of a command or an executable file.</span></span> <span data-ttu-id="4635f-110">Viele der Befehle, die im Befehlsfenster ausgeführt werden, akzeptieren aber auch *Argumente*.</span><span class="sxs-lookup"><span data-stu-id="4635f-110">However, many of the commands that are run from within the command window also accept *arguments*.</span></span> <span data-ttu-id="4635f-111">Argumente sind zusätzliche Informationselemente, die an den Befehl übergeben werden, wodurch das Verhalten des Befehls geändert wird.</span><span class="sxs-lookup"><span data-stu-id="4635f-111">Arguments are additional pieces of information that are passed to the command, which modify the behavior of the command.</span></span> <span data-ttu-id="4635f-112">Wenn Sie beispielsweise nur die Namen der Dateien und Ordner im aktuellen Verzeichnis anzeigen möchten, gibt es keine anderen Informationen, beispielsweise die Größe der Datei oder des Ordners, oder das Datum und die Uhrzeit, zu dem der Ordner oder Ordner erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4635f-112">For example, if you only wanted to see the names of the files and folder in the current directory—no other information, such as the size of the file or folder, or the date and time that the folder or folder was created.</span></span> <span data-ttu-id="4635f-113">In diesem Fall fügen Sie das Argument **/b** ein, wenn Sie den Befehl dir ausführen:</span><span class="sxs-lookup"><span data-stu-id="4635f-113">In this case, you’d append the **/b** argument when running the dir command:</span></span>

```console
dir /b
```

<span data-ttu-id="4635f-114">Wenn Sie das Argument **/b** einbeziehen, gibt der Befehl **dir** nur die Namen der Ordner und Dateien zurück, die im aktuellen Verzeichnis zu finden sind:</span><span class="sxs-lookup"><span data-stu-id="4635f-114">When you include the **/b** argument, the **dir** command reports back only the names of the folders and files found in the current directory:</span></span>

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

<span data-ttu-id="4635f-115">Im vorhergehenden Befehl ist das Argument **/b** die einzige Information, die erforderlich ist, um die zurückgegebenen Daten auf Datei-und Ordnernamen zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="4635f-115">In the preceding command, the **/b** argument is the only information required to limit the returned data to file and folder names.</span></span> <span data-ttu-id="4635f-116">Dies ist häufig bei Befehlszeilenbefehlen der Fall: das bloße vorhanden sein eines Arguments ist alles, was erforderlich ist, um das Verhalten des Befehls zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4635f-116">This is often the case with command-line commands: the mere presence of an argument is all that’s needed to change the command’s behavior.</span></span> <span data-ttu-id="4635f-117">(Sie fügen also das Argument **/b** hinzu, um zusätzliche Informationen auszublenden, oder Sie schließen das Argument **/b** aus, um die zusätzlichen Informationen anzuzeigen.) Zu anderen Zeiten müssen Sie jedoch einen *Argumentwert*angeben.</span><span class="sxs-lookup"><span data-stu-id="4635f-117">(That is, you include the **/b** argument to hide additional information, or you exclude the **/b** argument to show the extra information.) At other times, however, you must specify an *argument value*.</span></span> <span data-ttu-id="4635f-118">Ein Argumentwert ist zusätzliche Informationen, die an das Argument selbst übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="4635f-118">An argument value is additional information passed to the argument itself.</span></span> <span data-ttu-id="4635f-119">So können Sie beispielsweise mit dem Argument **/o** angeben, wie der Befehl dir die zurückgegebenen Daten sortieren soll.</span><span class="sxs-lookup"><span data-stu-id="4635f-119">For instance, the **/o** argument enables you to specify how you would like the dir command to sort the returned data.</span></span> <span data-ttu-id="4635f-120">Neben anderen Optionen können Sie den Argumentwert **e** verwenden, um nach Dateierweiterung oder dem Argumentwert **s** zu sortieren, um nach Dateigröße zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="4635f-120">Among other options, you can use the argument value **e** to sort by file extension or the argument value **s** to sort by file size.</span></span> <span data-ttu-id="4635f-121">Dieser Befehl sortiert beispielsweise die zurückgegebenen Daten nach Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="4635f-121">For example, this command sorts the returned data by file extension.</span></span> <span data-ttu-id="4635f-122">Beachten Sie, dass der Argumentwert **e** unmittelbar nach dem **/o** -Argument enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="4635f-122">Note how the argument value **e** is included immediately after the **/o** argument:</span></span>

```console
dir /oe
```

<span data-ttu-id="4635f-123">Bei Verwendung unseres Beispielordners sehen die zurückgegebenen Daten wie folgt aus, wobei die Dateien alphabetisch nach Dateierweiterung sortiert werden:</span><span class="sxs-lookup"><span data-stu-id="4635f-123">Using our sample folder, the returned data will look like this, with the files sorted alphabetically by file extension:</span></span>

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

<span data-ttu-id="4635f-124">Oder, um Ihnen zu helfen, genau zu bestimmen, worüber wir sprechen:</span><span class="sxs-lookup"><span data-stu-id="4635f-124">Or, to help you pinpoint exactly what we are talking about:</span></span>

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

<span data-ttu-id="4635f-125">Obwohl Windows PowerShell unterschiedliche Terminologie verwendet, ist der grundlegende Ansatz für die Arbeit mit Windows PowerShell identisch mit der Arbeit mit dem Befehlsfenster: Sie geben Befehle ein, fügen Argumente und Argumentwerte nach Bedarf ein und drücken dann die EINGABETASTE, um Sie auszuführen. Diese Befehle.</span><span class="sxs-lookup"><span data-stu-id="4635f-125">Although Windows PowerShell uses different terminology, the basic approach to working with Windows PowerShell is the same as working with the command window: you type commands, you include arguments and argument values as needed, and then you press ENTER to execute those commands.</span></span> <span data-ttu-id="4635f-126">Wie bereits erwähnt, verwendet Windows PowerShell jedoch eine andere Terminologie als die Befehlsshell verwendet.</span><span class="sxs-lookup"><span data-stu-id="4635f-126">As noted, however, Windows PowerShell does use a different terminology than the command shell uses.</span></span> <span data-ttu-id="4635f-127">In Windows PowerShell werden die ausgeführten Befehle als *Cmdlets*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4635f-127">In Windows PowerShell, the commands you execute are known as *cmdlets*.</span></span> <span data-ttu-id="4635f-128">Die an ein Cmdlet übergebenen Argumente werden wiederum als *Parameter*bezeichnet, und die an einen Parameter übergebenen Werte werden als *Parameterwerte*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4635f-128">In turn, the arguments passed to a cmdlet are known as *parameters*, and the values passed to a parameter are known as *parameter values*.</span></span>

<span data-ttu-id="4635f-129">Die vorhergehenden Definitionen sind etwas vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="4635f-129">The preceding definitions are somewhat simplified.</span></span> <span data-ttu-id="4635f-130">Cmdlets sind im wesentlichen Minianwendungen, die nur in der Windows PowerShell-Umgebung ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="4635f-130">Cmdlets are essentially mini-applications that can be run only from within the Windows PowerShell environment.</span></span> <span data-ttu-id="4635f-131">Sie können jedoch auch andere Befehle und Anwendungen in Windows PowerShell ausführen, einschließlich der meisten Befehle und Anwendungen, die über ein Befehlsfenster ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="4635f-131">However, you can also run other commands and applications from within Windows PowerShell, including most of the commands and applications that can be run from a command window.</span></span> <span data-ttu-id="4635f-132">Wenn Sie den Editor beispielsweise in Windows PowerShell starten möchten, müssen Sie nur Folgendes eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="4635f-132">For example, if you want to start Notepad from within Windows PowerShell, all you need to do is type the following and press ENTER:</span></span>

```console
notepad.exe
```

<span data-ttu-id="4635f-133">Bei der Verwaltung von Skype for Business Online sind die meisten Administratoren jedoch auf Windows PowerShell-Cmdlets angewiesen, um administrative Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4635f-133">When it comes to managing Skype for Business Online, however, most administrators will rely on Windows PowerShell cmdlets to carry out administrative tasks.</span></span> <span data-ttu-id="4635f-134">Zur Zeit gibt es nur sehr wenige andere Arten von Befehlen oder Anwendungen, die für die Verwaltung von Skype for Business Online verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4635f-134">At time, there are very few other types of commands or applications that can be used to manage Skype for Business Online.</span></span> <span data-ttu-id="4635f-135">Manchmal können die Skype for Business Online-Cmdlets ohne zusätzliche Argumente verwendet werden (wie bereits erwähnt, werden Argumente in Windows PowerShell als Parameter bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="4635f-135">Sometimes the Skype for Business Online cmdlets can be used without any additional arguments (, as noted, arguments are known as parameters in Windows PowerShell).</span></span> <span data-ttu-id="4635f-136">Mit dem folgenden Befehl wird beispielsweise das Cmdlet " [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) " ohne zusätzliche Parameter aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4635f-136">For example, the following command calls the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet without any additional parameters.</span></span> <span data-ttu-id="4635f-137">Der Befehl gibt für sich selbst Informationen zu allen Skype for Business Online-Benutzern zurück:</span><span class="sxs-lookup"><span data-stu-id="4635f-137">By itself, the command returns information about all of your Skype for Business Online users:</span></span>

```powershell
Get-CsOnlineUser
```

<span data-ttu-id="4635f-138">Die meisten der Skype for Business Online-Cmdlets akzeptieren aber auch Parameter (und Parameterwerte).</span><span class="sxs-lookup"><span data-stu-id="4635f-138">However, most of the Skype for Business Online cmdlets also accept parameters (and parameter values).</span></span> <span data-ttu-id="4635f-139">Nehmen Sie den folgenden Befehl in Frage:</span><span class="sxs-lookup"><span data-stu-id="4635f-139">Consider the following command:</span></span>

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

<span data-ttu-id="4635f-140">Dieser Befehl besteht aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="4635f-140">This command consists of three parts:</span></span>

  - <span data-ttu-id="4635f-141">Das Cmdlet **Get-CsOnlineUser**.</span><span class="sxs-lookup"><span data-stu-id="4635f-141">The cmdlet **Get-CsOnlineUser**.</span></span>

  - <span data-ttu-id="4635f-142">Der Parameter Identity.</span><span class="sxs-lookup"><span data-stu-id="4635f-142">The Identity parameter.</span></span> <span data-ttu-id="4635f-143">Beachten Sie, dass in Windows PowerShell den Parametern immer ein Bindestrich (-) vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4635f-143">Note that, in Windows PowerShell, parameters are always prefaced with a dash (-).</span></span> <span data-ttu-id="4635f-144">Das bedeutet, dass für dieses Cmdlet der UnassignedUser-Parameter mit der folgenden Syntax angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="4635f-144">That means that, for this same cmdlet, the UnassignedUser parameter would be indicated by using this syntax:</span></span>
    
    ```powershell
    -UnassignedUser
    ```
    
    <span data-ttu-id="4635f-145">Dies ist hilfreich, um nicht nur zu wissen, dass den Parametern ein Bindestrich vorangestellt werden muss, sondern auch, weil sich dies vom Befehlsfenster unterscheidet, in dem Argumente mit einem Schrägstrich (/) vorangestellt werden:</span><span class="sxs-lookup"><span data-stu-id="4635f-145">This is useful to know, not only because parameters must be prefaced with a dash, but also because this differs from the command window, where arguments are prefaced using a forward slash (/):</span></span>
    
    ```console
    /b
    ```

  - <span data-ttu-id="4635f-146">Der Parameterwert **kenmyer@litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="4635f-146">The parameter value **kenmyer@litwareinc.com**.</span></span>

<span data-ttu-id="4635f-147">Dieser Befehl gibt im übrigen Informationen zu einem bestimmten Benutzer zurück: der Benutzer mit der Identität kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4635f-147">That command, incidentally, returns information about a specific user: the user with the identity, kenmyer@litwareinc.com.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4635f-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4635f-148">See Also</span></span>


<span data-ttu-id="4635f-149">[Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="4635f-149">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

