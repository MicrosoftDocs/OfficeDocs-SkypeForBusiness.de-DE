---
title: Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Centralized Logging Service configuration settings
ms:assetid: 3c34e600-0b91-43dc-b4cc-90b6a70ee12e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688029(v=OCS.15)
ms:contentKeyID: 49733619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b326f7ee869b060a423696817c21d7cb763bb0a2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c0ce6-102">Grundlegendes zu Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0ce6-102">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0ce6-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c0ce6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c0ce6-104">Der zentralisierte Protokollierungsdienst ist so konfiguriert, dass er definiert, was der Protokollierungsdienst sammeln soll, wie es erfasst, woher es sammelt und welche Protokolleinstellungen verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-104">The Centralized Logging Service is configured to define what the logging service is intended to collect, how it collects, where it will collect from, and what the log settings are.</span></span> <span data-ttu-id="c0ce6-105">Sie definieren diese Einstellungen global (also für die gesamte Bereitstellung) oder für einen Standort (also eine benannte Website in Ihrer Bereitstellung).</span><span class="sxs-lookup"><span data-stu-id="c0ce6-105">You define these settings globally (that is, for the entire deployment) or for a site (that is, a named site in your deployment).</span></span> <span data-ttu-id="c0ce6-106">Für jede Protokollierung, die Sie definieren, werden die Einstellungen verwendet, die jeweils für die von Ihnen für Befehle zum Starten, Beenden, Leeren und Durchsuchen von Protokollen verwendete Identität geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-106">Any logging that you define will use the settings that are appropriate for the identity that you use for commands to start, stop, flush, and search logs.</span></span>

<div>

## <a name="to-display-the-current-centralized-logging-service-configuration"></a><span data-ttu-id="c0ce6-107">So zeigen Sie die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts an</span><span class="sxs-lookup"><span data-stu-id="c0ce6-107">To display the current Centralized Logging Service configuration</span></span>

1.  <span data-ttu-id="c0ce6-108">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c0ce6-109">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein:</span><span class="sxs-lookup"><span data-stu-id="c0ce6-109">Type the following at a command-line prompt:</span></span>
    
        Get-CsClsConfiguration
    
    <div>
    

    > [!TIP]
    > <span data-ttu-id="c0ce6-110">Sie können den Bereich der Konfigurationseinstellungen, die von der Definition <CODE>-Identity</CODE> zurückgegeben werden, oder einen Bereich wie "Site: Redmond" eingrenzen oder erweitern, um nur die csclsconfiguration "für die Website" Redmond "zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-110">You can narrow or expand the scope of the configuration settings that are returned by defining <CODE>-Identity</CODE> and a scope, such as "Site:Redmond" to return only the CsClsConfiguration for the site Redmond.</span></span> <span data-ttu-id="c0ce6-111">Wenn Sie Details zu einem bestimmten Teil der Konfiguration wünschen, können Sie die Ausgabe in ein anderes Windows PowerShell-Cmdlet übertragen.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-111">If you want details about a given portion of the configuration, you can pipe the output into another Windows PowerShell cmdlet.</span></span> <span data-ttu-id="c0ce6-112">Geben Sie beispielsweise Folgendes ein, um Details zu den in der Konfiguration für die Website "Redmond" definierten Szenarien zu erhalten:<CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span><span class="sxs-lookup"><span data-stu-id="c0ce6-112">For example, to get details about the scenarios defined in the configuration for site "Redmond", type: <CODE>Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandPropery Scenarios</CODE></span></span>

    
    </div>
    
    <span data-ttu-id="c0ce6-113">![Beispielausgabe von Get-csclsconfiguration ".](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Beispielausgabe von Get-csclsconfiguration ".")</span><span class="sxs-lookup"><span data-stu-id="c0ce6-113">![Sample output from Get-CsClsConfiguration.](images/JJ688029.23f98ddc-fc48-499a-b6c5-752611f2a0b0(OCS.15).jpg "Sample output from Get-CsClsConfiguration.")</span></span>
    
    <span data-ttu-id="c0ce6-114">Das Ergebnis des Cmdlets zeigt die aktuelle Konfiguration des zentralisierten Protokollierungsdiensts an.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-114">The result from the cmdlet displays the current configuration of the Centralized Logging Service.</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="c0ce6-115">Konfigurationseinstellung</span><span class="sxs-lookup"><span data-stu-id="c0ce6-115">Configuration Setting</span></span></th>
    <th><span data-ttu-id="c0ce6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0ce6-116">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-117"><strong>Identität</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-117"><strong>Identity</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-p103">Identifiziert den Bereich und den Namen dieser Konfiguration. Es gibt nur eine globale Konfiguration sowie eine Konfiguration pro Standort.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-p103">Identifies the scope and name for this configuration. There is only one Global configuration, and one configuration per site.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-120"><strong>Scenarios</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-120"><strong>Scenarios</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-121">Auflistung aller Szenarien, die für diese Konfiguration definiert sind.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-121">Listing of all scenarios that are defined for this configuration.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-122"><strong>SearchTerms</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-122"><strong>SearchTerms</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-123">Definierte Suchbegriffe für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-123">Defined search terms for the configuration.</span></span> <span data-ttu-id="c0ce6-124">Office 365, keine lokalen Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-124">Office 365, not on-premises deployments.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-125"><strong>Zufassen</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-125"><strong>SecurityGroups</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-126">Definierte Sicherheitsgruppen, die steuern, wer (welche Mitglieder der Sicherheitsgruppen) Computer basierend auf dem Standort, an dem sie sich befinden, anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-126">Defined security groups that control who (that is, members of the security groups) can see computers based on the site they are located in.</span></span> <span data-ttu-id="c0ce6-127">Website ist in diesem Kontext die Website, die im Topologie-Generator definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-127">Site, in this context, is the site as defined in Topology Builder.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-128"><strong>Regionen</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-128"><strong>Regions</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-129">Definierte Regionen werden verwendet, um Sicherheitsgruppen zu einer Region zusammenzufassen, beispielsweise EMEA.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-129">Defined regions are used to collect SecurityGroups into a region, for example EMEA.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-130"><strong>EtlFileFolder</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-130"><strong>EtlFileFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-p106">Definierter Pfad zu dem Speicherort, an dem Protokolldateien auf Computer geschrieben werden. CLSAgent schreibt die Protokolldatei und wird im Kontext des Netzwerkdiensts ausgeführt. In diesem Fall wird %TEMP% zu %WINDIR%\ServiceProfiles\NetworkService\AppData\Local erweitert.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-p106">Defined path to the location where log files are written on computers. CLSAgent writes the log files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-134"><strong>EtlFileRolloverSizeMB</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-134"><strong>EtlFileRolloverSizeMB</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-p107">Der Parameter gibt die maximale Größe der Protokolldatei vor der Erstellung einer neuen ETL-Datei (Event Trace Log, Ereignis-Ablaufverfolgungsprotokoll) an. Wenn die definierte Größe erreicht ist, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverMinutes festgelegte maximale Zeit noch nicht erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-p107">The parameter indicates the maximum size of the log file before a new event trace log (.etl) file is created. A new log file is created when the defined size is reached even if the maximum time set in EtlFileRolloverMinutes has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-137"><strong>EtlFileRolloverMinutes</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-137"><strong>EtlFileRolloverMinutes</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-p108">Die definierte maximale Zeitspanne in Minuten, die für ein Protokoll verstreichen kann, bevor eine neue ETL-Datei erstellt wird. Wenn der Timer abläuft, wird eine neue Protokolldatei erstellt, auch wenn die in EtlFileRolloverSizeMB festgelegte maximale Größe noch nicht erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-p108">Defined maximum amount of time, in minutes, that a log can elapse before a new .etl file is created. A new log file is created when the timer expires even if the maximum size set in EtlFileRolloverSizeMB has not yet been reached.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-140"><strong>TmfFileSearchPath</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-140"><strong>TmfFileSearchPath</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-p109">Speicherort, an dem nach den Formatdateien für Ablaufverfolgungsmeldungen gesucht wird. Die Formatdateien für Ablaufverfolgungsmeldungen werden verwendet, um die binären Dateien in ein von Menschen lesbares Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-p109">Location to search for the trace message format files. The trace message format files are used to convert the binary files into a human readable format.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-143"><strong>CacheFileLocalFolders</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-143"><strong>CacheFileLocalFolders</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-p110">Definierter Pfad zu dem Speicherort, an dem Cachedateien auf Computer geschrieben werden. CLSAgent schreibt die Cachedatei und wird im Kontext des Netzwerkdiensts ausgeführt. In diesem Fall wird %TEMP% zu %WINDIR%\ServiceProfiles\NetworkService\AppData\Local erweitert. Standardmäßig werden Cache- und Protokolldateien in dasselbe Verzeichnis geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-p110">Defined path to the location where cache files are written on computers. CLSAgent writes the cache files and runs under the context of the Network Service. In this case, %TEMP% expands to %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. By default, cache files and log files are written to the same directory.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-148"><strong>Para</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-148"><strong>CacheFileNetworkFolder</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-149">Sie können einen UNC-Pfad (Universal Naming Convention) definieren, um die Cachedateien während Protokollierungsvorgängen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-149">You can define a universal naming convention (UNC) path to receive the cache files during logging operations.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-150"><strong>CacheFileLocalRetentionPeriod</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-150"><strong>CacheFileLocalRetentionPeriod</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-151">Definiert als die Höchstdauer in Tagen, für die Cachedateien beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-151">Defined as the maximum time, in days, that cache files are retained.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-152"><strong>CacheFileMaxDiskUsage</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-152"><strong>CacheFileMaxDiskUsage</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-153">Definiert als der prozentuale Anteil des Speicherplatzes, der von den Cachedateien verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-153">Defined as the percentage of disk space that can be used by the cache files.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-154"><strong>ComponentThrottleLimit</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-154"><strong>ComponentThrottleLimit</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-155">Definiert als die Höchstzahl an Ablaufverfolgungen pro Sekunde, die eine Komponente erzeugen kann, bevor der automatische Drosselbegrenzer ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-155">Defined as the maximum number of traces per second that a component can produce before the automatic throttle limiter is triggered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="c0ce6-156"><strong>ComponentThrottleSample</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-156"><strong>ComponentThrottleSample</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-157">Anzahl der möglichen Überschreitungen von ComponentThrottleLimit in 60 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-157">Number of times in 60 seconds that the ComponentThrottleLimit can be exceeded.</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="c0ce6-158"><strong>MinimumClsAgentServiceVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c0ce6-158"><strong>MinimumClsAgentServiceVersion</strong></span></span></p></td>
    <td><p><span data-ttu-id="c0ce6-159">Die mindestens erforderliche Version des CLSAgent, die ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-159">The minimum version of the CLSAgent allowed to run.</span></span> <span data-ttu-id="c0ce6-160">Dieses Element ist für Office 365 vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c0ce6-160">This element is intended for Office 365.</span></span></p></td>
    </tr>
    </tbody>
    </table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c0ce6-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0ce6-161">See Also</span></span>


[<span data-ttu-id="c0ce6-162">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0ce6-162">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  


<span data-ttu-id="c0ce6-163">[Gruppe-csclsconfiguration "](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0ce6-163">[Set-CsClsConfiguration](https://technet.microsoft.com/library/JJ619182(v=OCS.15))</span></span>  
<span data-ttu-id="c0ce6-164">[Remove-csclsconfiguration "](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0ce6-164">[Remove-CsClsConfiguration](https://technet.microsoft.com/library/JJ619191(v=OCS.15))</span></span>  
<span data-ttu-id="c0ce6-165">[New-csclsconfiguration "](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0ce6-165">[New-CsClsConfiguration](https://technet.microsoft.com/library/JJ619177(v=OCS.15))</span></span>  
<span data-ttu-id="c0ce6-166">[Get-csclsconfiguration "](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="c0ce6-166">[Get-CsClsConfiguration](https://technet.microsoft.com/library/JJ619179(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

