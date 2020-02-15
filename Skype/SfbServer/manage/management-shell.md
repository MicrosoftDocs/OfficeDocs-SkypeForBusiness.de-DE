---
title: Skype for Business Server-Verwaltungsshell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype for Business Server Management-Shell stellt die Befehlszeilenschnittstelle für die Server Verwaltung und-Verwaltung bereit. Es basiert auf Windows PowerShell und umfasst eine umfassende Reihe von Verwaltungs-und Verwaltungs-Cmdlets, die für Skype-und Legacy-lync Server-Produkte spezifisch sind.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044257"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="657f0-104">Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="657f0-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="657f0-105">Die Skype for Business Server Management-Shell stellt die Befehlszeilenschnittstelle für die Server Verwaltung und-Verwaltung bereit.</span><span class="sxs-lookup"><span data-stu-id="657f0-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="657f0-106">Es basiert auf Windows PowerShell und umfasst eine umfassende Reihe von Verwaltungs-und Verwaltungs-Cmdlets, die für Skype-und Legacy-lync Server-Produkte spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="657f0-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="657f0-107">Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile verwalten.</span><span class="sxs-lookup"><span data-stu-id="657f0-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="657f0-108">Windows PowerShell umfasst eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="657f0-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="657f0-109">Windows PowerShell wurde erst spät in 2006 als herunterladbare Version für das Windows-Betriebssystem eingeführt und als Befehlszeilenschnittstelle für die Verwaltbarkeit von Microsoft Exchange Server 2007 integriert.</span><span class="sxs-lookup"><span data-stu-id="657f0-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="657f0-110">Es wurde in die meisten Microsoft-Serverprodukte integriert, einschließlich lync-und Skype-Servern, die mit lync Server 2010 beginnen.</span><span class="sxs-lookup"><span data-stu-id="657f0-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="657f0-111">In der Skype for Business Server-Verwaltungsshell stehen über 700 lync-und Skype-spezifische Cmdlets zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="657f0-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="657f0-112">Die Skype for Business-Cmdlet-Referenz wurde zu docs.Microsoft.com verschoben.</span><span class="sxs-lookup"><span data-stu-id="657f0-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="657f0-113">Durch Klicken auf die unten aufgeführten Links gelangen Sie zur neuen docs.Microsoft.com-Seite.</span><span class="sxs-lookup"><span data-stu-id="657f0-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="657f0-114">Der Inhalt ist nun Open sourced und für Community-Beiträge über GitHub verfügbar.</span><span class="sxs-lookup"><span data-stu-id="657f0-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="657f0-115">Möchten Sie einen Beitrag leisten?</span><span class="sxs-lookup"><span data-stu-id="657f0-115">Interested in contributing?</span></span> <span data-ttu-id="657f0-116">Lesen Sie die Readme-Datei im Repo hier:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="657f0-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="657f0-117">Skype for Business Server ist mit mehr als 700 Cmdlets ausgeliefert, mit denen Administratoren Skype for Business Server mithilfe der Skype for Business Server Verwaltungsshell verwalten können.</span><span class="sxs-lookup"><span data-stu-id="657f0-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="657f0-118">Sie können die Hilfe für ein Cmdlet direkt von der Befehlszeile aus abrufen, indem Sie einen Befehl wie den folgenden eingeben:</span><span class="sxs-lookup"><span data-stu-id="657f0-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="657f0-119">Der obige Befehl ruft die vollständige Hilfe ab, die für das Cmdlet **New-CsVoicePolicy** zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="657f0-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="657f0-120">Wenn Sie Hilfe zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie **New-CsVoicePolicy** durch den Namen des Cmdlets, für das Sie die Hilfe abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="657f0-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="657f0-121">Geben Sie an der Shell-Eingabeaufforderung Folgendes ein, um eine vollständige Liste der für die Verwaltung von Skype for Business Server verfügbaren Cmdlets abzurufen:</span><span class="sxs-lookup"><span data-stu-id="657f0-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="657f0-122">Wissenswerte über Windows PowerShell in Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="657f0-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="657f0-123">Öffnen Sie zum Ausführen der Skype for Business Server-Cmdlets die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="657f0-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="657f0-124">Wenn Sie ein Windows PowerShell Fenster anstelle der Skype for Business Server-Verwaltungsshell öffnen, können Sie die Skype-Cmdlets möglicherweise nicht ausführen.</span><span class="sxs-lookup"><span data-stu-id="657f0-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="657f0-125">Wenn Sie Skype for Business Server-Cmdlets in Windows PowerShell ausführen möchten, geben Sie an der Windows PowerShell-Eingabeaufforderung Folgendes ein: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="657f0-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="657f0-126">Skype for Business Server Verwaltungsshell wird automatisch auf allen Skype for Business Server Enterprise Edition-Front-End-Server oder-Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="657f0-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="657f0-127">Sie können die Hilfeinhalte für die Skype for Business Server Verwaltungsshell aktualisieren, indem Sie das Cmdlet [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) ausführen.</span><span class="sxs-lookup"><span data-stu-id="657f0-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="657f0-128">Mit dem Cmdlet Update-Help werden die neuesten Hilfedateien heruntergeladen und installiert, die für alle auf Ihrem Computer installierten Module verfügbar sind, einschließlich Updates für Skype for Business-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="657f0-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="657f0-129">Standardmäßig aktualisiert das Cmdlet **Update-Help** alle Module, die auf Ihrem Skype for Business Server installiert sind.</span><span class="sxs-lookup"><span data-stu-id="657f0-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="657f0-130">Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Bereich des Cmdlets mit dem Parameter _Module_ einschränken.</span><span class="sxs-lookup"><span data-stu-id="657f0-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="657f0-131">Im folgenden Beispiel wird nur das Skype for Business Modul aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="657f0-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="657f0-132">Wenn Sie die Hilfe auf Servern aktualisieren müssen, die nicht mit dem Internet verbunden sind, können Sie das [Save-Help-](https://technet.microsoft.com/library/hh849724.aspx) Cmdlet verwenden, um die neueste Version der Hilfe abzurufen und an einem von Ihnen angegebenen Speicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="657f0-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="657f0-133">Anschließend können Sie das Cmdlet **Update-Help** mit dem Parameter _-SourcePath_ auf Servern verwenden, die nicht mit dem Internet verbunden sind, um die aktualisierte Hilfe von dem ausgewählten Speicherort abzurufen.</span><span class="sxs-lookup"><span data-stu-id="657f0-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="657f0-134">Im folgenden Beispiel wird gezeigt, wie Sie die Hilfedateien in einer Netzwerkdateifreigabe speichern und dann die Hilfe für das Skype for Business Modul aus der Dateifreigabe aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="657f0-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="657f0-135">Ausführlichere Informationen finden Sie unter Informationen [zur aktualisierbaren Hilfe](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="657f0-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="657f0-136">Wenn Sie PowerShell Remote verwenden, müssen Sie möglicherweise die Kommunikation über eine Firewall zulassen.</span><span class="sxs-lookup"><span data-stu-id="657f0-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="657f0-137">Weitere Informationen zu den von PowerShell-Remoting verwendeten Ports finden Sie unter [welchen Port verwendet PowerShell-Remoting?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="657f0-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

