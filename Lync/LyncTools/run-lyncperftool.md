---
title: Ausführen von LyncPerfTool
description: Führen Sie LyncPerfTool aus.
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
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560081"
---
# <a name="run-lyncperftool"></a><span data-ttu-id="a595e-103">Ausführen von LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="a595e-103">Run LyncPerfTool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a595e-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a595e-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a595e-105">Vor dem Ausführen des lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) müssen Sie Benutzer, Kontakte und Szenarien erstellen.</span><span class="sxs-lookup"><span data-stu-id="a595e-105">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="a595e-106">Ausführliche Informationen zur Verwendung der Tools zum Ausführen dieser Aktionen finden Sie unter [Erstellen von Benutzern und Kontakten](create-users-and-contacts.md) und [Konfigurieren des Benutzerprofils](configure-user-profile.md).</span><span class="sxs-lookup"><span data-stu-id="a595e-106">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="a595e-107">Durch das Ausführen dieser Tools wird auch eine Datei generiert, die LyncPerfTool.exe als Teil einer Batchdatei mit den erforderlichen Parametern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a595e-107">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="a595e-108">Ausführung des lync Server 2013-Tools für Stress und Leistung</span><span class="sxs-lookup"><span data-stu-id="a595e-108">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="a595e-109">Mit dem UserProfileGenerator.exe-Tool wird eine Batchdatei erstellt, mit der Sie LyncPerfTool.exe ausführen können, indem Sie die LyncPerfTool-Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden.</span><span class="sxs-lookup"><span data-stu-id="a595e-109">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="a595e-110">In der Batchdatei wird eine Instanz von LyncPerfTool.exe pro Konfigurationsdatei ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a595e-110">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="a595e-111">Führen Sie die folgenden Schritte aus, um die Batchdatei auszuführen:</span><span class="sxs-lookup"><span data-stu-id="a595e-111">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="a595e-112">Kopieren Sie den Ordner mit den Konfigurationsordnern und-Dateien in das Verzeichnis, das LyncStressTool.exe auf jedem Clientcomputer enthält.</span><span class="sxs-lookup"><span data-stu-id="a595e-112">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="a595e-113">(Wenn Sie beispielsweise die Konfigurationsdateien im Ordner 1,28 \_ 13.16.16 generiert haben, kopieren Sie diesen Ordner in den Ordner, der LyncPerfTool.exe auf jedem Client enthält.)</span><span class="sxs-lookup"><span data-stu-id="a595e-113">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="a595e-114">Navigieren Sie zum entsprechend nummerierten Clientordner, und führen Sie das RunClient-Batchskript aus.</span><span class="sxs-lookup"><span data-stu-id="a595e-114">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="a595e-115">Sie können einfach im Windows-Explorer auf die Batchdatei doppelklicken, und alle Konfigurationsdateien für diese Client Nummer werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a595e-115">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="a595e-116">Sie können das Skript auch mithilfe der folgenden Syntax aus dem entsprechenden Clientordner ausführen:</span><span class="sxs-lookup"><span data-stu-id="a595e-116">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="a595e-117">Wenn Sie LyncPerfTool.exe direkt ausführen möchten, öffnen Sie eine Eingabeaufforderung, und geben Sie den folgenden Befehl an der Befehlszeile ein (wenn Sie dies zum ersten Mal tun, müssen Sie die Leistungsindikatoren regsvr32/i/n/s LyncPerfToolPerf.dll registrieren, wie im Hinweis weiter unten in diesem Thema gezeigt) :LyncPerfTool.exe/file:\<configXML\></span><span class="sxs-lookup"><span data-stu-id="a595e-117">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="a595e-118">Damit das Tool die Werte in der Konfigurationsdatei anzeigen kann, schließen Sie den/displayfile-Parameter auf dem vorherigen Befehl wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="a595e-118">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="a595e-119">Drücken Sie STRG + C, um den Vorgang zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a595e-119">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a595e-120">Bevor Sie LyncPerfTool direkt ausführen, müssen Sie die Leistungsindikatoren registrieren.</span><span class="sxs-lookup"><span data-stu-id="a595e-120">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="a595e-121">Geben Sie den folgenden Befehl ein, um Leistungsindikatoren zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="a595e-121">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="a595e-122">Jede Instanz von LyncPerfTool.exe, die Sie starten, beginnt sofort mit dem Anmelden von Benutzern, normalerweise mit einer Rate von einem Benutzer pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="a595e-122">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="a595e-123">Die maximale Benutzeranmelde Rate für den Pool beträgt ungefähr 12 pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="a595e-123">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="a595e-124">Dies bedeutet, dass Sie nicht mehr als 12 LyncPerfTool-Instanzen gleichzeitig starten sollten, während sich die Benutzer immer noch anmelden.</span><span class="sxs-lookup"><span data-stu-id="a595e-124">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="a595e-125">1000 Benutzer benötigen ungefähr 20 Minuten, um sich vollständig anzumelden, um eine pro Sekunde.</span><span class="sxs-lookup"><span data-stu-id="a595e-125">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a595e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a595e-126">See Also</span></span>


[<span data-ttu-id="a595e-127">Erstellen von Benutzern und Kontakten</span><span class="sxs-lookup"><span data-stu-id="a595e-127">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="a595e-128">Konfigurieren des Benutzerprofils</span><span class="sxs-lookup"><span data-stu-id="a595e-128">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

