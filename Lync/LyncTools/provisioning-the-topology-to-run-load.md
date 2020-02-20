---
title: Proversionierung der Topologie zum Ausführen der Last
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
ms.openlocfilehash: a9b81708cbd518b43247c4324ecc651a4089c3ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="cb063-102">Proversionierung der Topologie zum Ausführen der Last</span><span class="sxs-lookup"><span data-stu-id="cb063-102">Provisioning the Topology to Run Load</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb063-103">_**Letztes Änderungsstand des Themas:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="cb063-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

## <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="cb063-104">Proversionierung der Topologie zum Ausführen der Last</span><span class="sxs-lookup"><span data-stu-id="cb063-104">Provisioning the Topology to Run Load</span></span>

<span data-ttu-id="cb063-105">Je nach den vorhandenen Einstellungen und der Konfiguration von lync Server 2013 müssen Sie möglicherweise die folgenden Änderungen in Ihrer Umgebung vornehmen:</span><span class="sxs-lookup"><span data-stu-id="cb063-105">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="cb063-106">Legen Sie die Ausführungsrichtlinie für Windows PowerShell auf Unrestricted fest.</span><span class="sxs-lookup"><span data-stu-id="cb063-106">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="cb063-107">Um die Einstellungen für die Ausführungsrichtlinie zu überprüfen, öffnen Sie die lync Server-Verwaltungsshell und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="cb063-107">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="cb063-108">Wenn dieser Befehl nicht den Wert Unrestricted zurückgibt, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="cb063-108">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="cb063-109">Um lync Server 2013 effektiv konfigurieren zu können, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="cb063-109">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="cb063-110">Sie sollten mit lync Server 2013 Topologie (beispielsweise Computernamen, Dienstinstanzen, Websitenamen und Richtlinien) vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="cb063-110">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="cb063-111">Weisen Sie einige der erstellten Benutzergruppen zu, beispielsweise Reaktionsgruppen-Sammelanschlüsse (beispielsweise SIP-URIs).</span><span class="sxs-lookup"><span data-stu-id="cb063-111">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="cb063-112">Um das Skript über die Befehlszeile auszuführen, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="cb063-112">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="cb063-113">Nach dem Ausführen eines Skripts in diesem Paket werden die daraus resultierenden Ablaufverfolgungen in der Regel in einer Datei im gleichen Pfad gespeichert, in dem das Skript aufgerufen wurde, mit dem \<Namen ScriptName\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="cb063-113">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="cb063-114">Beispiel: Running ArchivingPolicy. ps1 um 12:15 Uhr</span><span class="sxs-lookup"><span data-stu-id="cb063-114">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="cb063-115">eine Protokolldatei wie ArchivingPolicy121500. txt wird generiert.</span><span class="sxs-lookup"><span data-stu-id="cb063-115">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="cb063-116">Beachten Sie außerdem, dass Sie zwar Beispiele für die Konfiguration des Servers bereitgestellt haben, dass Sie jedoch für das ändern oder Löschen der Konfiguration verantwortlich sind, nachdem Sie die Ausführung der Last abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="cb063-116">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

