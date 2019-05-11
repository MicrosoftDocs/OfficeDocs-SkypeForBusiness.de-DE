---
title: Skype for Business Server-Verwaltungsshell
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Die Skype für Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für Serveradministration und Verwaltung. Sie basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungsaufgaben -Cmdlets, die speziell für Skype und älterer Lync Server-Produkten.
ms.openlocfilehash: 1daf83ea401501f6607a30aa7710f1d338c47af9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888345"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="79503-104">Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="79503-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="79503-105">Die Skype für Business Server-Verwaltungsshell bietet die Befehlszeilenschnittstelle für Serveradministration und Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="79503-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="79503-106">Sie basiert auf Windows PowerShell und enthält einen umfassenden Satz von Verwaltungsaufgaben -Cmdlets, die speziell für Skype und älterer Lync Server-Produkten.</span><span class="sxs-lookup"><span data-stu-id="79503-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="79503-107">Windows PowerShell können Sie Microsoft-Anwendungen über die Befehlszeile zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="79503-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="79503-108">Enthalten sind eine Befehlszeilenumgebung, produktspezifische Befehle und eine vollständige Skriptsprache.</span><span class="sxs-lookup"><span data-stu-id="79503-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="79503-109">Windows PowerShell wurde als Release zum Herunterladen für Windows-Betriebssystems spät im 2006 eingeführt, und wurde als die Befehlszeilenschnittstelle für die Verwaltung von Microsoft Exchange Server 2007 integriert.</span><span class="sxs-lookup"><span data-stu-id="79503-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="79503-110">Es wurde in die meisten Microsoft Server-Produkte, einschließlich Lync und Skype-Servern, die mit Lync Server 2010 integriert.</span><span class="sxs-lookup"><span data-stu-id="79503-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="79503-111">700 Lync und Skype bestimmte Cmdlets stehen in der Skype für Business Server-Verwaltungsshell zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="79503-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79503-112">Skype für Business-Cmdlet-Referenz verschoben zu docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="79503-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="79503-113">Durch Klicken auf die unten aufgeführten Links gelangen Sie zu der neuen Seite docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="79503-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="79503-114">Der Inhalt ist jetzt open stammenden und bereit zur Community-Beiträge über GitHub.</span><span class="sxs-lookup"><span data-stu-id="79503-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="79503-115">Belohnung interessiert?</span><span class="sxs-lookup"><span data-stu-id="79503-115">Interested in contributing?</span></span> <span data-ttu-id="79503-116">Checken Sie die Infodatei in der Repo hier:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="79503-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="79503-117">Skype für Business Server im Lieferumfang von mehr als 700 Cmdlets, mit die Administratoren Skype für Business Server mithilfe der Skype für Business Server-Verwaltungsshell verwalten können.</span><span class="sxs-lookup"><span data-stu-id="79503-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="79503-118">Sie können Hilfe für ein Cmdlet direkt über die Befehlszeile abrufen, wenn Sie einen Befehl wie den folgenden eingeben:</span><span class="sxs-lookup"><span data-stu-id="79503-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="79503-119">Mit dem oben genannten Befehl rufen Sie alle verfügbaren Hilfeinformationen zum Cmdlet **New-CsVoicePolicy** ab.</span><span class="sxs-lookup"><span data-stu-id="79503-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="79503-120">Wenn Sie Hilfeinformationen zu einem anderen Cmdlet anzeigen möchten, ersetzen Sie den Verweis auf **New-CsVoicePolicy** durch den Namen des Cmdlets, zu dem Sie Hilfeinformationen abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="79503-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="79503-121">Geben Sie den folgenden Befehl an der Eingabeaufforderung ein, um eine vollständige Liste der verfügbaren Cmdlets für Skype for Business Server anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="79503-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="79503-122">Wichtige Informationen zu Windows PowerShell in Skype für Business Server:</span><span class="sxs-lookup"><span data-stu-id="79503-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="79503-123">Öffnen Sie zum Ausführen der Skype für Business Server-Cmdlets die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="79503-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="79503-124">Wenn Sie ein Windows PowerShell-Fenster, statt die Skype für Business Server-Verwaltungsshell öffnen, werden standardmäßig Sie die Skype-Cmdlets ausführen möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="79503-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="79503-125">Um Skype für Business Server-Cmdlets von Windows PowerShell ausgeführt werden soll, geben Sie zuerst Folgendes an der Windows PowerShell-Eingabeaufforderung: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="79503-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="79503-126">Skype für Business Server-Verwaltungsshell wird automatisch auf jedem Skype für Business Server Enterprise Edition-Front-End-Server oder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="79503-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="79503-127">Sie können die Skype für Business Server-Verwaltungsshell-Hilfe-Inhalten durch Ausführen des Cmdlets [Update-Hilfe](https://technet.microsoft.com/en-us/library/hh849720.aspx) aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="79503-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="79503-128">Das Cmdlet Update-Hilfe herunterladen und installieren die neuesten Dateien für alle Module auf Ihrem Computer, einschließlich Updates für Skype für Business-Cmdlets installiert.</span><span class="sxs-lookup"><span data-stu-id="79503-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="79503-129">Standardmäßig wird das Cmdlet **Update-Hilfe** alle Module installiert auf Ihre Skype für Business Server aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="79503-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="79503-130">Wenn Sie nur bestimmte Module aktualisieren möchten, können Sie den Umfang des Cmdlets anhand des Parameters _Module_ einschränken.</span><span class="sxs-lookup"><span data-stu-id="79503-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="79503-131">Im folgende Beispiel wird nur die Skype für Business Modul aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="79503-131">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="79503-132">Wenn Sie die Hilfe auf Servern, die nicht mit dem Internet verbunden sind, aktualisieren müssen, können Sie das Cmdlet [Get-Help speichern](https://technet.microsoft.com/en-us/library/hh849724.aspx) der neuesten Version der Hilfe, und speichern Sie sie an einem Speicherort, den Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="79503-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="79503-133">Sie können das Cmdlet **Update-Hilfe** klicken Sie dann mit dem _SourcePath -_ Parameter auf Servern, die nicht mit dem Internet verbunden verwenden, die aktualisierte Abrufen von Hilfe aus dem Speicherort, den, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="79503-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="79503-134">Das folgende Beispiel veranschaulicht die Hilfedateien auf einer Netzwerkfreigabe speichern, und aktualisieren Sie die Hilfe für die Skype für Business Modul aus der Dateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="79503-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="79503-135">Ausführlichere Informationen finden Sie unter [Aktualisierbare Info](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="79503-135">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79503-136">Wenn Sie Remote PowerShell verwenden, müssen Sie durch eine Firewall hindurch Kommunikation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="79503-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="79503-137">Weitere Informationen zu den Ports PowerShell-Remoting verwendet, finden Sie unter [Was ist PowerShell-Remoting Portverwendung?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span><span class="sxs-lookup"><span data-stu-id="79503-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).</span></span>
    

