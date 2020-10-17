---
title: Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in
description: Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets
ms:assetid: 8bb8800a-f966-4570-8c8b-db87a91ad783
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362816(v=OCS.15)
ms:contentKeyID: 56558835
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd18f60891d48a54eb2f77f189ea8417e0b5e93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548001"
---
# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="8b24f-103">Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in</span><span class="sxs-lookup"><span data-stu-id="8b24f-103">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b24f-104">_**Letztes Änderungsstand des Themas:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="8b24f-104">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="8b24f-105">Wenn Sie über Windows PowerShell eine Verbindung mit Skype for Business Online herstellen, stehen Ihnen ungefähr 40 Skype for Business Online-Cmdlets zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8b24f-105">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="8b24f-106">Sie sind jedoch nicht auf die Verwendung von nur den 40-Cmdlets beim Verwalten von Skype for Business Online beschränkte.</span><span class="sxs-lookup"><span data-stu-id="8b24f-106">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="8b24f-107">Zusätzlich zu den Skype for Business Online-Cmdlets können Sie auch alle anderen Windows PowerShell-Cmdlets verwenden, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8b24f-107">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="8b24f-108">(Bei der Installation von Windows PowerShell 3,0 werden auch Hunderte von Kern Windows PowerShell-Cmdlets installiert.) Ihre Befehle können Skype for Business Online-Cmdlets und anderen auf Ihrem Computer verfügbaren Cmdlets mischen und abgleichen.</span><span class="sxs-lookup"><span data-stu-id="8b24f-108">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="8b24f-109">Obwohl ein vollständiger Kurs in Windows PowerShell 3,0 über den Rahmen dieses Artikels hinausgeht, finden Sie hier einige Beispiele, die zeigen, warum Sie Cmdlets möglicherweise kombinieren und anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="8b24f-109">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="8b24f-110">Zunächst enthält keines der Skype for Business Online-Cmdlets einen Print-Befehl, und in der Windows PowerShell Konsole ist auch kein solcher Befehl zu finden.</span><span class="sxs-lookup"><span data-stu-id="8b24f-110">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="8b24f-111">Wie erhalten Sie also einen Ausdruck der von einem Cmdlet abgerufenen Informationen?</span><span class="sxs-lookup"><span data-stu-id="8b24f-111">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="8b24f-112">Eine Möglichkeit besteht darin, die Informationen abzurufen und diese Informationen dann an das **Out-Printer-** Cmdlet zu senden:</span><span class="sxs-lookup"><span data-stu-id="8b24f-112">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="8b24f-113">Da keine zusätzlichen Parameter enthalten sind, werden alle vom **Out-Printer-** Cmdlet zurückgegebenen Informationen auf den Standarddrucker gedruckt.</span><span class="sxs-lookup"><span data-stu-id="8b24f-113">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="8b24f-114">Ebenso enthält keines der Skype for Business Online-Cmdlets einen Parameter, mit dem Sie Daten in einer Datei speichern können.</span><span class="sxs-lookup"><span data-stu-id="8b24f-114">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="8b24f-115">Aber das ist in Ordnung: Dieser Befehl verwendet das **Out-File-** Cmdlet, um die zurückgegebenen Informationen in der Textdatei C: \\ LogsTenants.txt zu speichern \\ :</span><span class="sxs-lookup"><span data-stu-id="8b24f-115">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="8b24f-116">Und dieser Befehl verwendet das Cmdlet **Select-Object** , um die zurückgegebenen und auf dem Bildschirm angezeigten Daten zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="8b24f-116">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="8b24f-117">In diesem Beispiel ruft das Cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) Informationen für alle Skype for Business Online Benutzer ab, und dann wird das Cmdlet **Select-Object** verwendet, um die angezeigten Daten auf den Identitätswert des Benutzers und die dazugehörige Archivierungsrichtlinie zu begrenzen:</span><span class="sxs-lookup"><span data-stu-id="8b24f-117">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="8b24f-118">Da Hunderte von Cmdlets für die Verwendung auf Ihrem Computer verfügbar sein werden, haben Sie möglicherweise Schwierigkeiten festzustellen, welche Cmdlets Skype for Business Online-Cmdlets sind und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="8b24f-118">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="8b24f-119">Um eine Liste der Skype for Business Online-Cmdlets (und nur Skype for Business Online-Cmdlets) zurückzugeben, müssen Sie zuerst den Namen des temporären Windows PowerShell-Moduls ermitteln, das alle Skype for Business Online-Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="8b24f-119">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="8b24f-120">Führen Sie dazu in der Windows PowerShell-Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8b24f-120">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="8b24f-121">Ähnliche Informationen wie die folgenden werden auf dem Bildschirm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8b24f-121">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="8b24f-122">Das Modul mit dem modultype-Skript ist das Modul, das die Skype for Business Online-Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="8b24f-122">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="8b24f-123">Führen Sie das Cmdlet **Get-Command** aus, um eine Liste dieser Cmdlets zurückzugeben, und verwenden Sie dabei den Namen des Skriptmoduls als Modulnamen:</span><span class="sxs-lookup"><span data-stu-id="8b24f-123">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="8b24f-124">Möglicherweise verfügen Sie über mehrere Module mit einem ModuleType-Wert, der dem Skript entspricht.</span><span class="sxs-lookup"><span data-stu-id="8b24f-124">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="8b24f-125">In diesem Fall können Sie den folgenden Befehl ausführen, um herauszufinden, welches Modul das **Get-CsTenant-** Cmdlet enthält:</span><span class="sxs-lookup"><span data-stu-id="8b24f-125">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="8b24f-126">Das Modul, das für das Cmdlet **Get-CsTenant** zurückgegeben wird, ist das Modul, das alle Skype for Business Online-Cmdlets enthält:</span><span class="sxs-lookup"><span data-stu-id="8b24f-126">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="8b24f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b24f-127">See Also</span></span>


<span data-ttu-id="8b24f-128">[Eine Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8b24f-128">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

