---
title: Installieren der lync Server 2013-Hauptdateien und der RTCLocal-Datenbank
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41eefd8316e0e33ab8c4418a6ce72ea9eb05fc84
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="996a5-102">Installieren der lync Server 2013-Hauptdateien und der RTCLocal-Datenbank</span><span class="sxs-lookup"><span data-stu-id="996a5-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="996a5-103">_**Letztes Änderungsstand des Themas:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="996a5-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="996a5-104">Um die lync Server 2013 Kerndateien auf einem Computer zu installieren, führen Sie das folgende Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="996a5-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="996a5-105">Die RTCLocal-Datenbank wird automatisch bei der Installation der Hauptdateien installiert.</span><span class="sxs-lookup"><span data-stu-id="996a5-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="996a5-106">Beachten Sie, dass Sie SQL Server nicht auf den Watcher-Knoten installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="996a5-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="996a5-107">Stattdessen wird SQL Server Express automatisch für Sie installiert.</span><span class="sxs-lookup"><span data-stu-id="996a5-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="996a5-108">So installieren Sie die lync Server 2013 Kerndateien und die RTCLocal-Datenbank:</span><span class="sxs-lookup"><span data-stu-id="996a5-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="996a5-109">Klicken Sie auf dem Computer mit den Watcher-Knoten auf **Start**, **Alle Programme**, **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="996a5-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="996a5-110">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE, und verwenden Sie den entsprechenden Pfad zu ihren lync Server-Setupdateien:</span><span class="sxs-lookup"><span data-stu-id="996a5-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="996a5-111">Um sicherzustellen, dass die Kern lync Server Komponenten erfolgreich installiert wurden, klicken Sie auf **Start**, auf **Alle Programme**, auf **lync Server 2013**und dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="996a5-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="996a5-112">Geben Sie in der lync Server 2013 Verwaltungsshell den folgenden Windows PowerShell Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="996a5-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="996a5-113">Bei der ersten Ausführung dieses Befehls werden keine Daten zurückgegeben, da noch keine Computer mit Watcher-Knoten konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="996a5-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="996a5-114">Solange der Befehl ausgeführt wird, ohne dass ein Fehler zurückgegeben wird, können Sie davon ausgehen, dass das lync Server-Setup erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="996a5-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="996a5-115">Wenn sich der Monitor Knoten Computer in Ihrem Umkreisnetzwerk befindet, können Sie den folgenden Befehl ausführen, um die Installation von lync Server 2013 zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="996a5-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="996a5-116">Sie erhalten in etwa folgende Informationen, abhängig von der Anzahl der zur Verwendung in Ihrer Organisation konfigurierten PIN-Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="996a5-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="996a5-117">Werden Informationen zu Ihren PIN-Richtlinien angezeigt, weist das darauf hin, dass die Hauptkomponenten erfolgreich installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="996a5-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

