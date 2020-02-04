---
title: Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e7d0dd6070eb3c69b23f03e56bf542025c221b15
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="combining-skype-for-business-online-cmdlets-with-other-windows-powershell-cmdlets-in"></a><span data-ttu-id="29772-102">Kombinieren von Skype for Business Online-Cmdlets mit anderen Windows PowerShell-Cmdlets in</span><span class="sxs-lookup"><span data-stu-id="29772-102">Combining Skype for Business Online cmdlets with other Windows PowerShell cmdlets in</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29772-103">_**Letztes Änderungsdatum des Themas:** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="29772-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="29772-104">Wenn Sie mithilfe von Windows PowerShell eine Verbindung mit Skype for Business Online herstellen, stehen Ihnen ungefähr 40-Cmdlets für Skype for Business Online zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="29772-104">When you connect to Skype for Business Online by using Windows PowerShell, approximately 40 Skype for Business Online cmdlets will available for your use.</span></span> <span data-ttu-id="29772-105">Bei der Verwaltung von Skype for Business Online beschränken Sie sich jedoch nicht auf die Verwendung dieser 40-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="29772-105">However, you are not limited to using just those 40 cmdlets when managing Skype for Business Online.</span></span> <span data-ttu-id="29772-106">Zusätzlich zu den Skype for Business Online-Cmdlets können Sie auch alle anderen Windows PowerShell-Cmdlets verwenden, die auf Ihrem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="29772-106">In addition to the Skype for Business Online cmdlets, you can also use any other Windows PowerShell cmdlets that are installed on your computer.</span></span> <span data-ttu-id="29772-107">(Wenn Sie Windows PowerShell 3,0 installieren, werden auch Hunderte von zentralen Windows PowerShell-Cmdlets installiert.) Ihre Befehle können die Skype for Business Online-Cmdlets und alle anderen auf dem Computer verfügbaren Cmdlets kombinieren und anpassen.</span><span class="sxs-lookup"><span data-stu-id="29772-107">(When you install Windows PowerShell 3.0, hundreds of core Windows PowerShell cmdlets are installed, as well.) Your commands can mix and match Skype for Business Online cmdlets and any other cmdlets available on your computer.</span></span>

<span data-ttu-id="29772-108">Obwohl ein vollständiger Kurs in Windows PowerShell 3,0 den Rahmen dieses Artikels sprengt, finden Sie hier einige Beispiele, die zeigen, warum Sie Cmdlets kombinieren und vergleichen können.</span><span class="sxs-lookup"><span data-stu-id="29772-108">Although a complete course in Windows PowerShell 3.0 goes beyond the scope of this article, here are a few examples that show why you might want to mix and match cmdlets.</span></span> <span data-ttu-id="29772-109">Zunächst einmal enthält keines der Skype for Business Online-Cmdlets einen Befehl "Drucken", und in der Windows PowerShell-Konsole kann auch kein solcher Befehl gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="29772-109">First of all, none of the Skype for Business Online cmdlets include a Print command, and no such command can be found in the Windows PowerShell console, either.</span></span> <span data-ttu-id="29772-110">Wie erhalten Sie einen Ausdruck der Informationen, die von einem Cmdlet abgerufen werden?</span><span class="sxs-lookup"><span data-stu-id="29772-110">So how do you get a printout of the information retrieved by a cmdlet?</span></span> <span data-ttu-id="29772-111">Eine Möglichkeit besteht darin, die Informationen abzurufen und diese Informationen dann an das **Out-Printer-** Cmdlet zu senden:</span><span class="sxs-lookup"><span data-stu-id="29772-111">One way is to retrieve the information, and then send that information to the **Out-Printer** cmdlet:</span></span>

    Get-CsTenant | Out-Printer

<span data-ttu-id="29772-112">Da keine zusätzlichen Parameter enthalten sind, werden alle vom **Out-Printer-** Cmdlet zurückgegebenen Informationen auf dem Standarddrucker gedruckt.</span><span class="sxs-lookup"><span data-stu-id="29772-112">Because no additional parameters are included, all the information returned by **the Out-Printer** cmdlet will be printed to the default printer.</span></span>

<span data-ttu-id="29772-113">Ebenso enthalten keine der Skype for Business Online-Cmdlets einen Parameter, mit dem Sie Daten in einer Datei speichern können.</span><span class="sxs-lookup"><span data-stu-id="29772-113">Likewise, none of the Skype for Business Online cmdlets include a parameter that allows you to save data to a file.</span></span> <span data-ttu-id="29772-114">Aber das ist OK: Dieser Befehl verwendet das **Out-File-** Cmdlet, um die zurückgegebenen Informationen in der Textdatei\\C\\: Logs Tenants. txt zu speichern:</span><span class="sxs-lookup"><span data-stu-id="29772-114">But that’s OK: this command uses the **Out-File** cmdlet to save the returned information to the text file C:\\Logs\\Tenants.txt:</span></span>

    Get-Tenant | Out-File -FilePath "C:\Logs\Tenants.txt"

<span data-ttu-id="29772-115">Und dieser Befehl verwendet das Cmdlet **"Select-Object"** , um die Daten zu begrenzen, die zurückgegeben und auf dem Bildschirm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="29772-115">And this command uses the **Select-Object** cmdlet to limit the data that is returned and displayed onscreen.</span></span> <span data-ttu-id="29772-116">In diesem Beispiel ruft das Cmdlet " [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) " Informationen zu allen Skype for Business Online-Benutzern ab, und dann wird das Cmdlet **"Select-Object"** verwendet, um die angezeigten Daten auf den Identitätswert und die Archivierungsrichtlinie des Benutzers zu begrenzen:</span><span class="sxs-lookup"><span data-stu-id="29772-116">In this example, the [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet retrieves information for all of your Skype for Business Online users, and then the **Select-Object** cmdlet is used to limit the displayed data to the user’s Identity value and their archiving policy:</span></span>

    Get-CsOnlineUser | Select-Object Identity, ArchivingPolicy

<span data-ttu-id="29772-117">Da es Hunderte von Cmdlets gibt, die auf Ihrem Computer verwendet werden können, haben Sie möglicherweise Schwierigkeiten, zu ermitteln, welche Cmdlets für Skype for Business Online-Cmdlets gelten und welche nicht.</span><span class="sxs-lookup"><span data-stu-id="29772-117">Because there will be hundreds of cmdlets available for use on your computer, you might have difficulty determining which cmdlets are Skype for Business Online cmdlets and which ones are not.</span></span> <span data-ttu-id="29772-118">Wenn Sie eine Liste der Skype for Business Online-Cmdlets (und nur der Skype for Business Online-Cmdlets) zurückgeben möchten, müssen Sie zuerst den Namen des temporären Windows PowerShell-Moduls ermitteln, das alle Skype for Business Online-Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="29772-118">To return a list of the Skype for Business Online cmdlets (and only Skype for Business Online cmdlets), you must first determine the name of the temporary Windows PowerShell module that contains all the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="29772-119">Führen Sie dazu diesen Befehl in der Windows PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="29772-119">To do that, run this command from the Windows PowerShell prompt:</span></span>

    Get-Module

<span data-ttu-id="29772-120">Auf dem Bildschirm werden Informationen ähnlich der folgenden angezeigt:</span><span class="sxs-lookup"><span data-stu-id="29772-120">Information similar to the following will appear onscreen:</span></span>

    ModuleType Name                 ExportedCommands
    ---------- ----                 ----------------
    Manifest   Microsoft.PowerS...  {Add-Computer, Add-Content, A...}
    Script     tmp_5astd3uh.m5v     {Disable-CsMeetingRoom, Enabl...}

<span data-ttu-id="29772-121">Das Modul mit dem modultype-Skript ist das Modul, das die Skype for Business Online-Cmdlets enthält.</span><span class="sxs-lookup"><span data-stu-id="29772-121">The module with the ModuleType Script is the module that contains the Skype for Business Online cmdlets.</span></span> <span data-ttu-id="29772-122">Wenn Sie eine Liste dieser Cmdlets zurückgeben möchten, führen Sie das Cmdlet " **Get-Command"** aus, indem Sie den Namen des Skriptmoduls als Modulnamen verwenden:</span><span class="sxs-lookup"><span data-stu-id="29772-122">To return a list of those cmdlets, run the **Get-Command** cmdlet, using the name of the Script module as the module name:</span></span>

    Get-Command -Module tmp_5astd3uh.m5v

<span data-ttu-id="29772-123">Es ist möglich, dass Sie mehrere Module mit einem modultype gleich Skript haben könnten.</span><span class="sxs-lookup"><span data-stu-id="29772-123">It’s possible that you could have multiple modules with a ModuleType equal to Script.</span></span> <span data-ttu-id="29772-124">In diesem Fall können Sie den folgenden Befehl ausführen, um herauszufinden, welches Modul das Cmdlet " **Get-CsTenant** " enthält:</span><span class="sxs-lookup"><span data-stu-id="29772-124">In that case, you can run the following command to find out which module includes the **Get-CsTenant** cmdlet:</span></span>

    Get-Command Get-CsTenant

<span data-ttu-id="29772-125">Das Modul, das für das Cmdlet " **Get-CsTenant** " zurückgegeben wird, ist das Modul, das alle Skype for Business Online-Cmdlets enthält:</span><span class="sxs-lookup"><span data-stu-id="29772-125">The module returned for the **Get-CsTenant** cmdlet will be the module containing all the Skype for Business Online cmdlets:</span></span>

    CommandType     Name                                               ModuleName
    -----------     ----                                               ----------
    Function        Get-CsTenant                                       tmp_5astd3uh.m5v

<div>

## <a name="see-also"></a><span data-ttu-id="29772-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29772-126">See Also</span></span>


<span data-ttu-id="29772-127">[Einführung in Windows PowerShell und Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="29772-127">[An introduction to Windows PowerShell and Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

