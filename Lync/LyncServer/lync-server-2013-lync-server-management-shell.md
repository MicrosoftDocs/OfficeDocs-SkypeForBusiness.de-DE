---
title: 'Lync Server 2013: lync Server-Verwaltungsshell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f367ec9ff3f990c410a95289c159bb021b053cec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a><span data-ttu-id="1e6f1-102">Lync Server 2013 Management-Shell</span><span class="sxs-lookup"><span data-stu-id="1e6f1-102">Lync Server 2013 Management Shell</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e6f1-103">_**Letztes Änderungsstand des Themas:** 2017-09-20_</span><span class="sxs-lookup"><span data-stu-id="1e6f1-103">_**Topic Last Modified:** 2017-09-20_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1e6f1-104">Die Skype for Business-Cmdlet-Referenz wurde zu docs.Microsoft.com verschoben.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-104">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="1e6f1-105">Durch Klicken auf die unten aufgeführten Links gelangen Sie zur neuen docs.Microsoft.com-Seite.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-105">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="1e6f1-106">Der Inhalt ist nun Open sourced und für Community-Beiträge über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-106">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="1e6f1-107">Möchten Sie einen Beitrag leisten?</span><span class="sxs-lookup"><span data-stu-id="1e6f1-107">Interested in contributing?</span></span> <span data-ttu-id="1e6f1-108">Lesen Sie die Readme-Datei im Repo hier:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span><span class="sxs-lookup"><span data-stu-id="1e6f1-108">Check out the README in the repo here: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A></span></span>



</div>

<span data-ttu-id="1e6f1-109">In Microsoft lync Server 2010 wurde eine große Menge neuer und verbesserter Features im Vergleich zu den in Microsoft Office Communications Server 2007 R2 verfügbaren Funktionen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-109">Microsoft Lync Server 2010 introduced a large set of new and improved features compared to what was available in Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="1e6f1-110">Eine Verbesserung ist die Methode zur Verwaltung Ihrer Implementierung.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-110">One improvement is the way in which you manage your implementation.</span></span> <span data-ttu-id="1e6f1-111">Es gibt beispielsweise eine neue Benutzeroberfläche, die als lync Server-Systemsteuerung bezeichnet wird, die eine große Verschiebung von der Verwendung der meisten Personen mit der Microsoft Management Console darstellt.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-111">For example, there’s a new user interface, called the Lync Server Control Panel, which represents a big shift from what most people are used to with the Microsoft Management Console.</span></span> <span data-ttu-id="1e6f1-112">Die andere wesentliche Verbesserung der Verwaltbarkeit ist die Einbeziehung von Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-112">The other major improvement to manageability is the inclusion of Windows PowerShell.</span></span>

<span data-ttu-id="1e6f1-113">Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-113">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="1e6f1-114">Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-114">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="1e6f1-115">Windows PowerShell wurde erst spät in 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-115">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="1e6f1-116">Von diesem Moment an wuchs es weiter an und wurde in die meisten Microsoft-Server Produkte integriert, wobei die neueste Microsoft lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-116">From that point it continued to grow, and it has been incorporated into most of the Microsoft Server products, the most recent of these being Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1e6f1-117">Lync Server 2010 haben fast 550 produktspezifische Cmdlets eingeführt, mit denen Sie jeden Aspekt Ihrer Bereitstellung verwalten können.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-117">Lync Server 2010 introduced close to 550 product-specific cmdlets that you can use to manage every aspect of your deployment.</span></span>

<span data-ttu-id="1e6f1-118">Die folgenden Abschnitte enthalten eine Liste der Cmdlets sowie Beschreibungen der Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-118">The following sections contain a list of cmdlets and their descriptions.</span></span> <span data-ttu-id="1e6f1-119">Diese Informationen stehen auch direkt über die Befehlszeile zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-119">This information is also available directly from the command line.</span></span> <span data-ttu-id="1e6f1-120">Geben Sie einfach an der lync Server-Verwaltungsshell Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1e6f1-120">Simply type the following at the Lync Server Management Shell command prompt:</span></span>

    Get-Help <cmdlet name> -Full

<span data-ttu-id="1e6f1-121">Wenn Sie beispielsweise Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** von der Befehlszeile aus abrufen möchten, geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="1e6f1-121">For example, to retrieve help from the command prompt on the **New-CsVoicePolicy** cmdlet, type the following:</span></span>

    Get-Help New-CsVoicePolicy -Full

<span data-ttu-id="1e6f1-122">Wissenswerte über Windows PowerShell in lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1e6f1-122">Things to know about Windows PowerShell in Lync Server 2013:</span></span>

  - <span data-ttu-id="1e6f1-123">Öffnen Sie zum Ausführen der lync Server-Cmdlets das lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-123">To run the Lync Server cmdlets, open the Lync Server Management Shell.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="1e6f1-124">Wenn Sie ein Windows PowerShell Fenster anstatt des lync Server-Verwaltungsshells öffnen, können Sie die lync Server-Cmdlets standardmäßig nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-124">If you open a Windows PowerShell window rather than the Lync Server Management Shell, by default you will not be able to run the Lync Server cmdlets.</span></span> <span data-ttu-id="1e6f1-125">Geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein, um die lync Server-Cmdlets in Windows PowerShell auszuführen:</span><span class="sxs-lookup"><span data-stu-id="1e6f1-125">To run the Lync Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt:</span></span><BR><span data-ttu-id="1e6f1-126">Import-Module Lync</span><span class="sxs-lookup"><span data-stu-id="1e6f1-126">Import-Module Lync</span></span>

    
    </div>

  - <span data-ttu-id="1e6f1-127">Lync Server-Verwaltungsshell wird automatisch auf allen lync Server Enterprise Edition-Front-End-Server oder-Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-127">Lync Server Management Shell is automatically installed on every Lync Server Enterprise Edition Front End Server or Standard Edition server.</span></span>

  - <span data-ttu-id="1e6f1-128">Auf der lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)finden Sie neue und aktualisierte Informationen, Beispielskripts und Hilfe zum Thema Windows PowerShell und Microsoft lync Server 2013-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="1e6f1-128">New and updated information, sample scripts, and help for getting started and learning more about Windows PowerShell and Microsoft Lync Server 2013 cmdlets is available at the Lync Server Windows PowerShell Blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

