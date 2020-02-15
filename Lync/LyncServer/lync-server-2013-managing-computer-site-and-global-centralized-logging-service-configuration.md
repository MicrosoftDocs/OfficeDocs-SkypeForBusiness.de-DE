---
title: Verwalten der Konfiguration von Computer-, Standort-und globalen zentralisierten Protokollierungs Diensten
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing computer, site and global Centralized Logging Service configuration
ms:assetid: 93b9a354-9aea-4b3a-a4fe-68a89f436196
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688138(v=OCS.15)
ms:contentKeyID: 49733738
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b405cef9efd63956b6d676d751027318897f5e98
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-computer-site-and-global-centralized-logging-service-configuration-in-lync-server-2013"></a><span data-ttu-id="df2cb-102">Verwalten der Konfiguration von Computer-, Standort-und globalen zentralisierten Protokollierungs Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df2cb-102">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df2cb-103">_**Letztes Änderungsstand des Themas:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="df2cb-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="df2cb-104">Der zentralisierte Protokollierungsdienst kann in einem Bereich ausgeführt werden, der einen einzelnen Computer, einen Pool von Computern, einen Standortbereich (also einen definierten Standort wie den Standort "Redmond", der eine Sammlung von Computern und Pools in Ihrer Bereitstellung enthält) oder auf globaler Ebene (also , alle Computer und Pools in Ihrer Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="df2cb-104">The Centralized Logging Service can be run at a scope that includes a single computer, a pool of computers, at a site scope (that is, a defined site such as the site Redmond that contains a collection of computer and pools in your deployment), or at a global scope (that is, all computers and pools in your deployment).</span></span>

<span data-ttu-id="df2cb-105">Um den Bereich für den zentralisierten Protokollierungsdienst mithilfe der lync Server-Verwaltungsshell zu konfigurieren, müssen Sie Mitglied der rollenbasierten Sicherheitsgruppen "CsAdministrator" oder "CsServerAdministrator" oder einer benutzerdefinierten RBAC-Rolle sein, die Folgendes enthält: eine dieser beiden Gruppen.</span><span class="sxs-lookup"><span data-stu-id="df2cb-105">To configure the Centralized Logging Service scope by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="df2cb-106">Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl in der lync Server-Verwaltungsshell oder der Windows PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="df2cb-106">To return a list of all the RBAC roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "<Lync Server 2013 cmdlet>"}

<span data-ttu-id="df2cb-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df2cb-107">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>


> [!NOTE]
> <span data-ttu-id="df2cb-108">Windows PowerShell bietet Ihnen weitere Optionen und zusätzliche Konfigurationsoptionen, die mit CLSController. exe nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="df2cb-108">Windows PowerShell provides you more options and additional configuration options that are not available by using CLSController.exe.</span></span> <span data-ttu-id="df2cb-109">CLSController bietet ein schnelles, präzises Verfahren zum Ausführen von Befehlen, ist aber auf den für den CLSController verfügbaren Befehlssatz beschränkt.</span><span class="sxs-lookup"><span data-stu-id="df2cb-109">CLSController offers a quick, concise method to run commands, but is limited to the set of commands available for the CLSController.</span></span> <span data-ttu-id="df2cb-110">Windows PowerShell ist nicht auf den Befehl limitiert, der für den Befehlsprozessor des CLSController verfügbar ist, und bietet eine breitere Palette von Befehlen und eine Vielzahl von Optionen.</span><span class="sxs-lookup"><span data-stu-id="df2cb-110">Windows PowerShell is not limited to just the command available to the command processor of the CLSController, and provides a wider set of commands and a richer set of options.</span></span> <span data-ttu-id="df2cb-111">Beispiel: CLSController.exe bietet Ihnen Optionen für "–computers" und "–pools".</span><span class="sxs-lookup"><span data-stu-id="df2cb-111">For example, CLSController.exe does provide you with a scope options for –computers and –pools.</span></span> <span data-ttu-id="df2cb-112">Mit Windows PowerShell können Sie in den meisten Befehlen Computer oder Pools angeben, und wenn Sie neue Szenarien definieren (CLSController verfügt über eine begrenzte Anzahl von Szenarien, die nicht vom Benutzer geändert werden können), können Sie eine Website oder einen globalen Bereich definieren.</span><span class="sxs-lookup"><span data-stu-id="df2cb-112">With Windows PowerShell, you can indicate computers or pools in most commands, and when you define new scenarios (CLSController has a finite number of scenarios that are not user modifiable) you can define a site or global scope.</span></span> <span data-ttu-id="df2cb-113">Dieses leistungsstarke Feature von Windows PowerShell ermöglicht Ihnen, ein Szenario als Standort oder globaler Bereich zu definieren, die tatsächliche Protokollierung jedoch auf einen Computer oder einen Pool zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="df2cb-113">This powerful feature of Windows PowerShell enables you to define a scenario a site or global scope, but limit the actual logging to a computer or pool.</span></span><BR><span data-ttu-id="df2cb-114">Es gibt grundlegende Unterschiede zwischen den Befehlszeilenbefehlen, die Sie in Windows PowerShell oder CLSController ausführen können.</span><span class="sxs-lookup"><span data-stu-id="df2cb-114">There are fundamental differences between the command-line commands that you can run in Windows PowerShell or CLSController.</span></span> <span data-ttu-id="df2cb-115">Windows PowerShell bietet eine umfassende Methode zum Konfigurieren und Definieren von Szenarien sowie zur sinnvollen Wiederverwendung dieser Szenarien für Ihre Problembehandlungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="df2cb-115">Windows PowerShell provides a rich method to configure and define scenarios, and to reuse those scenarios in a meaningful way for your troubleshooting scenarios.</span></span> <span data-ttu-id="df2cb-116">Während der CLSController eine schnelle und effiziente Möglichkeit bietet, Befehle einzugeben und Ergebnisse zu erhalten, ist der Befehlssatz für den CLSController auf die begrenzte Anzahl der über die Befehlszeile verfügbaren Befehle beschränkt.</span><span class="sxs-lookup"><span data-stu-id="df2cb-116">While CLSController does provide a fast and efficient way to issue commands and get results, the command set for CLSController is limited by the finite commands that you have available from the command line.</span></span> <span data-ttu-id="df2cb-117">Im Gegensatz zu den Windows PowerShell-Cmdlets können CLSController keine neuen Szenarien definieren, den Bereich an einer Website oder auf globaler Ebene verwalten und viele andere Einschränkungen eines begrenzten Befehlssatzes, der nicht dynamisch konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="df2cb-117">Unlike the Windows PowerShell cmdlets, CLSController cannot define new scenarios, manage scope at a site or global level, and many other limitations of a finite command set that cannot be dynamically configured.</span></span> <span data-ttu-id="df2cb-118">Während CLSController eine Möglichkeit zur schnellen Ausführung bietet, bietet Windows PowerShell eine Möglichkeit, die Funktionalität des zentralisierten Protokollierungsdiensts über das hinaus zu erweitern, was mit CLSController möglich ist.</span><span class="sxs-lookup"><span data-stu-id="df2cb-118">While CLSController provides a means for fast execution, Windows PowerShell provides a means to extend the Centralized Logging Service functionality beyond what is possible with CLSController.</span></span>



</div>

<span data-ttu-id="df2cb-119">Ein einzelner Computerbereich kann während der Ausführung eines [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15))-, [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15))-, [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15))-, [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15))-, [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) -und [Update-CsClsLogging-](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) Befehls mithilfe des Parameters – Computers definiert werden.</span><span class="sxs-lookup"><span data-stu-id="df2cb-119">A single computer scope can be defined during the execution of a [Search-CsClsLogging](https://technet.microsoft.com/library/JJ619189(v=OCS.15)), [Show-CsClsLogging](https://technet.microsoft.com/library/JJ619173(v=OCS.15)), [Start-CsClsLogging](https://technet.microsoft.com/library/JJ619190(v=OCS.15)), [Stop-CsClsLogging](https://technet.microsoft.com/library/JJ619180(v=OCS.15)), [Sync-CsClsLogging](https://technet.microsoft.com/library/JJ619169(v=OCS.15)) and [Update-CsClsLogging](https://technet.microsoft.com/library/JJ619170(v=OCS.15)) command using the –Computers parameter.</span></span> <span data-ttu-id="df2cb-120">Der Parameter "–Computers" akzeptiert eine kommagetrennte Liste vollqualifizierter Domänennamen (FQDNs) für den Zielcomputer.</span><span class="sxs-lookup"><span data-stu-id="df2cb-120">The –Computers parameter accepts a comma separated list of fully qualified domain names (FQDNs) for the target computer.</span></span>

<div>


> [!TIP]
> <span data-ttu-id="df2cb-121">Sie können ebenso "–Pools" angeben und eine kommagetrennte Liste mit Pools übergeben, in denen die Protokollierungsbefehle ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="df2cb-121">You can also define –Pools and a comma separated list of pools that you want to run the logging commands on.</span></span>



</div>

<span data-ttu-id="df2cb-122">Website-und globale Bereiche werden in den Cmdlets **New-**, **Sets-** und **Remove-** zentralisierter Protokollierungsdienst definiert.</span><span class="sxs-lookup"><span data-stu-id="df2cb-122">Site and Global scopes are defined in the **New-**, **Set-**, and **Remove-** Centralized Logging Service cmdlets.</span></span> <span data-ttu-id="df2cb-123">Die folgenden Beispiele zeigen, wie ein Standortbereich und ein globaler Bereich festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="df2cb-123">The following examples demonstrate how to set a site and a global scope.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="df2cb-124">Die angezeigten Befehle enthalten möglicherweise Parameter und Konzepte, die in anderen Abschnitten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="df2cb-124">The commands shown may contain parameters and concepts that are covered in other sections.</span></span> <span data-ttu-id="df2cb-125">Die Beispielbefehle sollen die Verwendung des Parameters <STRONG>– Identity</STRONG> veranschaulichen, um den Bereich zu definieren, und die anderen Parameter werden zur Vollständigkeit und zur Angabe des Bereichs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="df2cb-125">The example commands are intended to demonstrate the use of the <STRONG>–Identity</STRONG> parameter to define scope, and the other parameters are included for completeness and to specify the scope.</span></span> <span data-ttu-id="df2cb-126">Ausführliche Informationen zu den Cmdlets für das Cmdlet " <STRONG>csclsconfiguration"</STRONG> "finden Sie unter <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Festlegen von csclsconfiguration"</A> in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="df2cb-126">For details about the <STRONG>Set-CsClsConfiguration</STRONG> cmdlets, see <A href="https://technet.microsoft.com/library/JJ619182(v=OCS.15)">Set-CsClsConfiguration</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="df2cb-127">So rufen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts ab</span><span class="sxs-lookup"><span data-stu-id="df2cb-127">To retrieve the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="df2cb-128">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-129">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-129">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration

<span data-ttu-id="df2cb-130">Verwenden Sie die Cmdlets **New-CsClsConfiguration** und **Set-CsClsConfiguration**, um eine neue Konfiguration zu erstellen oder eine vorhandene Konfiguration zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="df2cb-130">Use the **New-CsClsConfiguration** and **Set-CsClsConfiguration** cmdlets to create a new configuration or to update an existing configuration.</span></span>

<span data-ttu-id="df2cb-131">Wenn Sie **Get-csclsconfiguration "** ausführen, werden Informationen angezeigt, die dem folgenden Screenshot ähneln, in dem die Bereitstellung derzeit die standardmäßige globale Konfiguration aufweist, jedoch keine Websitekonfigurationen definiert sind:</span><span class="sxs-lookup"><span data-stu-id="df2cb-131">When you run **Get-CsClsConfiguration**, it displays information similar to the following screen shot, where the deployment currently has the default Global configuration, but no site configurations defined:</span></span>

<span data-ttu-id="df2cb-132">![Beispielausgabe von Get-csclsconfiguration ".](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Beispielausgabe von Get-csclsconfiguration ".")</span><span class="sxs-lookup"><span data-stu-id="df2cb-132">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>

</div>

<div>

## <a name="to-retrieve-the-current-centralized-logging-service-configuration-from-the-computer-local-store"></a><span data-ttu-id="df2cb-133">So rufen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts aus dem lokalen Computerspeicher ab</span><span class="sxs-lookup"><span data-stu-id="df2cb-133">To retrieve the current Centralized Logging Service configuration from the computer local store</span></span>

1.  <span data-ttu-id="df2cb-134">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-135">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-135">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -LocalStore

<span data-ttu-id="df2cb-136">Wenn Sie das erste Beispiel verwenden, in dem **Get-csclsconfiguration "** keine Parameter angibt, verweist der Befehl auf den zentralen Verwaltungsspeicher für die Daten.</span><span class="sxs-lookup"><span data-stu-id="df2cb-136">When you use the first example where **Get-CsClsConfiguration** does not specify any parameters, the command references the Central Management store for the data.</span></span> <span data-ttu-id="df2cb-137">Wenn Sie den Parameter-localstore angeben, verweist der Befehl auf den Computer localstore anstelle des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="df2cb-137">If you specify the parameter –LocalStore, the command references the computer LocalStore instead of the Central Management store.</span></span>

</div>

<div>

## <a name="to-retrieve-a-listing-of-scenarios-currently-defined"></a><span data-ttu-id="df2cb-138">So rufen Sie eine Liste der aktuell definierten Szenarien ab</span><span class="sxs-lookup"><span data-stu-id="df2cb-138">To retrieve a listing of scenarios currently defined</span></span>

1.  <span data-ttu-id="df2cb-139">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-140">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-140">Type the following at the command-line prompt:</span></span>
    
        Get-CsClsConfiguration -Identity <scope and name> | Select-Object -ExpandProperty Scenarios
    
    <span data-ttu-id="df2cb-141">Um z. B. die für den globalen Bereich definierten Szenarien abzurufen:</span><span class="sxs-lookup"><span data-stu-id="df2cb-141">For example, to retrieve the scenarios that is defined at the global scope:</span></span>
    
        Get-CsClsConfiguration -Identity "global" | Select-Object -ExpandProperty Scenarios

<span data-ttu-id="df2cb-142">Das Cmdlet **Get-CsClsConfiguration** zeigt immer die Szenarien an, die Teil der Konfiguration eines vorgegebenen Bereichs sind.</span><span class="sxs-lookup"><span data-stu-id="df2cb-142">The cmdlet **Get-CsClsConfiguration** always displays the scenarios that are a part of a given scope’s configuration.</span></span> <span data-ttu-id="df2cb-143">In den meisten Fällen werden nicht alle Szenarien angezeigt, und es wird gekürzt.</span><span class="sxs-lookup"><span data-stu-id="df2cb-143">In most cases, all scenarios are not displayed, and are truncated.</span></span> <span data-ttu-id="df2cb-144">Der hier verwendete Befehl erstellt eine Liste aller Szenarien mit Teilinformationen darüber, welche Anbieter, Einstellungen und Flags verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df2cb-144">The command used here lists all of the scenarios and partial information about what providers, settings, and flags are used.</span></span>

</div>

<div>

## <a name="to-update-a-global-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="df2cb-145">So aktualisieren Sie einen globalen Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df2cb-145">To update a global scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="df2cb-146">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-147">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-147">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope> -EtlFileRolloverSizeMB <size for logging file in megabytes>
    
    <span data-ttu-id="df2cb-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df2cb-148">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "global" -EtlFileRolloverSizeMB 40

<span data-ttu-id="df2cb-p109">Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools der Bereitstellung mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Dieser Befehl wirkt sich auf alle Computer und Pools an allen Standorten aus und ändert deren konfigurierten Rollover-Wert in 40 MB.</span><span class="sxs-lookup"><span data-stu-id="df2cb-p109">The command tells the CLSAgent on each computer and pool in the deployment to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in all sites are affected by the command, and will set their configured trace log rollover value to 40 megabytes.</span></span>

</div>

<div>

## <a name="to-update-a-site-scope-for-the-centralized-logging-service-by-using-windows-powershell"></a><span data-ttu-id="df2cb-151">So aktualisieren Sie einen Website Bereich für den zentralisierten Protokollierungsdienst mithilfe von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="df2cb-151">To update a site scope for the Centralized Logging Service by using Windows PowerShell</span></span>

1.  <span data-ttu-id="df2cb-152">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-152">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-153">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-153">Type the following at the command-line prompt:</span></span>
    
        Set-CsClsConfiguration -Identity <scope/site name> -EtlFileRolloverSizeMB <size for logging file in megabytes> -EtlFileFolder <default location %TEMP%\Tracing>
    
    <span data-ttu-id="df2cb-154">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="df2cb-154">For example:</span></span>
    
        Set-CsClsConfiguration -Identity "site/Redmond" -EtlFileRolloverSizeMB 40 -EtlFileFolder "C:\LogFiles\Tracing" 
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="df2cb-p110">Wie im Beispiel gezeigt, ist der Standardspeicherort der Protokolldateien "%TEMP%\Tracing". Da es jedoch der CLSAgent ist, der die Datei tatsächlich schreibt, und da der CSLAgent als Netzwerkdienst ausgeführt wird, wird die Variable %TEMP% zu "%WINDIR%\ServiceProfiles\NetworkService\AppData\Local" erweitert.</span><span class="sxs-lookup"><span data-stu-id="df2cb-p110">As noted in the example, the default location of the log files is %TEMP%\Tracing. However, because it is actually CLSAgent that is writing the file and CSLAgent runs as Network Service, the %TEMP% variable expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local.</span></span>

    
    </div>

<span data-ttu-id="df2cb-p111">Der Befehl teilt dem CLSAgent auf allen Computern und in allen Pools am Standort Redmond mit, die Größe des Rollover-Werts für die Tracing-Datei auf 40 MB festzulegen. Computer und Pools an anderen Standorten sind von dem Befehl nicht betroffen und verwenden weiterhin den aktuell konfigurierten Rollover-Wert für die Tracing-Datei - der entweder durch den Standardwert (20 MB) oder bei der Anmeldung definiert wird.</span><span class="sxs-lookup"><span data-stu-id="df2cb-p111">The command tells the CLSAgent on each computer and pool in the site Redmond to set the size of the rollover value on the tracing file to 40 megabytes. Computers and pools in other sites will not be affected by the command, and will continue to use the currently configured trace log rollover value defined either by default (20 megabytes) or during the start of the logging session.</span></span>

</div>

<div>

## <a name="to-create-a-new-centralized-logging-service-configuration"></a><span data-ttu-id="df2cb-159">So erstellen Sie eine neue Konfiguration für den zentralisierten Protokollierungsdienst</span><span class="sxs-lookup"><span data-stu-id="df2cb-159">To create a new Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="df2cb-160">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-161">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-161">Type the following at the command-line prompt:</span></span>
    
        New-CsClsConfiguration -Identity <scope and name> [CsClsConfiguration options for this site]
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="df2cb-162">"New-CsClsConfiguration" bietet Zugriff auf eine Vielzahl optionaler Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="df2cb-162">New-CsClsConfiguration provides access to a large number of optional configuration settings.</span></span> <span data-ttu-id="df2cb-163">Ausführliche Informationen zu den Konfigurationsoptionen finden Sie unter <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-csclsconfiguration "</A> und <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Grundlegendes zu den Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="df2cb-163">For details about the configuration options, see <A href="https://technet.microsoft.com/library/JJ619179(v=OCS.15)">Get-CsClsConfiguration</A> and <A href="lync-server-2013-understanding-centralized-logging-service-configuration-settings.md">Understanding Centralized Logging Service configuration settings in Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="df2cb-164">Wenn Sie z. B. eine neue Konfiguration erstellen möchten, die einen Netzwerkordner für Cachedateien, den Rollover-Zeitraum für die Protokolldateien und die Rollover-Größe für die Protokolldateien definiert, können Sie folgenden Befehl eingeben:</span><span class="sxs-lookup"><span data-stu-id="df2cb-164">For example, to create a new configuration that defines a network folder for cache files, rollover time period for the log files and rollover size for the log files, you would type:</span></span>
    
        New-CsClsConfiguration -Identity "site:Redmond" -CacheFileNetworkFolder "\\fs01.contoso.net\filestore\logfiles" -EtlFileRolloverMinutes 120 -EtlFileRolloverSizeMB 40

<span data-ttu-id="df2cb-165">Sie sollten die Erstellung neuer Konfigurationen und die Definition neuer Eigenschaften für den zentralisierten Protokollierungsdienst sorgfältig planen.</span><span class="sxs-lookup"><span data-stu-id="df2cb-165">You should carefully plan the creation of new configurations and how you define new properties for the Centralized Logging Service.</span></span> <span data-ttu-id="df2cb-166">Gehen Sie vorsichtig vor, wenn Sie Änderungen durchführen, und stellen Sie sicher, dass Ihnen die Auswirkungen auf die Möglichkeit, Problemszenarien richtig zu protokollieren, bewusst sind.</span><span class="sxs-lookup"><span data-stu-id="df2cb-166">You should be cautious about making changes and make sure you understand the impact on your ability to properly log problem scenarios.</span></span> <span data-ttu-id="df2cb-167">Änderungen an der Konfiguration sollten Sie durchführen, um Ihre Möglichkeiten zur Verwaltung der Protokolle mit einer Größe und einem Rollover-Zeitraum so zu verbessern, dass Sie Probleme bei ihrem Auftreten lösen können.</span><span class="sxs-lookup"><span data-stu-id="df2cb-167">You should make changes to the configuration that will enhance your ability to manage logs to a size and a rollover period that will allow problem solving when it arises.</span></span>

</div>

<div>

## <a name="to-remove-an-existing-centralized-logging-service-configuration"></a><span data-ttu-id="df2cb-168">So entfernen Sie eine vorhandene Konfiguration für den zentralisierten Protokollierungsdienst</span><span class="sxs-lookup"><span data-stu-id="df2cb-168">To remove an existing Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="df2cb-169">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="df2cb-169">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="df2cb-170">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="df2cb-170">Type the following at the command-line prompt:</span></span>
    
        Remove-CsClsConfiguration -Identity <scope and name>
    
    <span data-ttu-id="df2cb-171">Wenn Sie beispielsweise eine von Ihnen erstellte Konfiguration für den zentralisierten Protokollierungsdienst entfernen möchten, um die rolloverzeit der Protokolldatei zu verbessern, vergrößern Sie die Größe der Rollover-Protokolldatei, und legen Sie den Speicherort des Protokolldatei Caches wie folgt auf eine Netzwerkfreigabe fest:</span><span class="sxs-lookup"><span data-stu-id="df2cb-171">For example, to remove a Centralized Logging Service configuration that you created to increase the log file rollover time, increase the rollover log file size, and set the log file cache location to a network share as follows:</span></span>
    
        Remove-CsClsConfiguration -Identity "site:Redmond"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="df2cb-172">Dies ist die neue Konfiguration, die im Verfahren "So erstellen Sie eine neue Konfiguration für den zentralisierten Protokollierungsdienst" erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="df2cb-172">This is the new configuration that was created in the procedure "To create a new Centralized Logging Service configuration."</span></span>

    
    </div>

<span data-ttu-id="df2cb-173">Wenn Sie eine Konfiguration auf Standortebene löschen, verwendet der Standort anschließend die globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="df2cb-173">If you choose to remove a site-level configuration, the site will use the global settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df2cb-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df2cb-174">See Also</span></span>


[<span data-ttu-id="df2cb-175">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df2cb-175">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[<span data-ttu-id="df2cb-176">Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df2cb-176">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)  
<span data-ttu-id="df2cb-177">[Gruppe-csclsconfiguration "](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="df2cb-177">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="df2cb-178">[Get-csclsconfiguration "](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="df2cb-178">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
<span data-ttu-id="df2cb-179">[New-csclsconfiguration "](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="df2cb-179">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="df2cb-180">[Remove-csclsconfiguration "](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="df2cb-180">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

