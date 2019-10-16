---
title: Erstellen und Verwalten von Wählplänen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Hier erfahren Sie, wie Sie Anruf Wählpläne (PSTN-Wählpläne) in Office 365 erstellen und verwalten können. '
ms.openlocfilehash: 3b96c2f504096b3f77c7080feda1dac982f46e9c
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516672"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="d7aaf-103">Erstellen und Verwalten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="d7aaf-103">Create and manage dial plans</span></span>

<span data-ttu-id="d7aaf-104">Nachdem Sie die Wählpläne für Ihre Organisation geplant und alle Normalisierungsregeln ermittelt haben, die für das Anrufrouting erstellt werden müssen, müssen Sie Windows PowerShell verwenden, um die Wählpläne zu erstellen und Änderungen an den Einstellungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-104">After you have planned the dial plans for your organization and figured out all of the normalization rules that need to be created for call routing, you will need to use Windows PowerShell to create the dial plans and make any setting changes.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d7aaf-105">Das Skype for Business Admin Center kann nicht zum Erstellen und Verwalten von Wählplänen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-105">The Skype for Business admin center can't be used for creating and managing dial plans.</span></span> 
  
## <a name="verifying-and-starting-remote-powershell"></a><span data-ttu-id="d7aaf-106">Überprüfen und starten von Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7aaf-106">Verifying and starting Remote PowerShell</span></span>

 <span data-ttu-id="d7aaf-107">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="d7aaf-107">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="d7aaf-108">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-108">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d7aaf-109">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-109">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="d7aaf-110">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-110">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="d7aaf-111">Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="d7aaf-111">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="d7aaf-112">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-112">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="d7aaf-p102">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-p102">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="d7aaf-116">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-116">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="d7aaf-117">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="d7aaf-117">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="d7aaf-118">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-118">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="d7aaf-119">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-119">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d7aaf-120">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-120">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
>   ```
>     Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
>     $credential = Get-Credential
>     $session = New-CsOnlineSession -Credential $credential
>     Import-PSSession $session
>   ```

<span data-ttu-id="d7aaf-121">Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype for Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-121">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="creating-and-managing-your-dial-plans"></a><span data-ttu-id="d7aaf-122">Erstellen und Verwalten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="d7aaf-122">Creating and managing your dial plans</span></span>

<span data-ttu-id="d7aaf-123">Sie können entweder ein einzelnes Cmdlet oder ein PowerShell-Skript verwenden, um Mandanten-Wählpläne zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-123">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
### <a name="using-single-cmdlets"></a><span data-ttu-id="d7aaf-124">Verwenden einzelner Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d7aaf-124">Using single cmdlets</span></span>

- <span data-ttu-id="d7aaf-125">Wenn Sie einen neuen Wählplan erstellen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-125">To create a new dial plan, run:</span></span>
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d7aaf-126">Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-126">For other examples and parameters, see [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).</span></span>
    
- <span data-ttu-id="d7aaf-127">Wenn Sie Änderungen an einem vorhandenen Wählplan vornehmen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-127">To make setting changes to an existing dial plan, run:</span></span>
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="d7aaf-128">Weitere Beispiele und Parameter finden Sie unter [Satz-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-128">For other examples and parameters, see [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).</span></span>
    
- <span data-ttu-id="d7aaf-129">Führen Sie Folgendes aus, um Benutzer zu einem Wählplan hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-129">To add users to a dial plan, run:</span></span>
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="d7aaf-130">Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-130">For other examples and parameters, see [Grant-CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).</span></span>
    
- <span data-ttu-id="d7aaf-131">Führen Sie die folgenden Optionen aus, um die Einstellungen für einen Wählplan anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-131">To view the settings on a dial plan, run:</span></span>
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="d7aaf-132">Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-132">For other examples and parameters, see [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).</span></span>
    
- <span data-ttu-id="d7aaf-133">Um einen Wählplan zu löschen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-133">To delete a dial plan, run:</span></span>
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="d7aaf-134">Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-134">For other examples and parameters, see [Remove-CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).</span></span>
    
- <span data-ttu-id="d7aaf-135">Um die Einstellungen des effektiven Wählplans anzuzeigen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-135">To see the settings of the effective dial plan, run:</span></span>
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d7aaf-136">Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-136">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).</span></span>
    
- <span data-ttu-id="d7aaf-137">Um die effektiven Einstellungen eines Wählplans zu testen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-137">To test the effective settings of a dial plan, run:</span></span>
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="d7aaf-138">Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span><span class="sxs-lookup"><span data-stu-id="d7aaf-138">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).</span></span>
    
### <a name="using-a-powershell-script"></a><span data-ttu-id="d7aaf-139">Verwenden eines PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="d7aaf-139">Using a PowerShell script</span></span>

<span data-ttu-id="d7aaf-140">Führen Sie diese Aktion aus, um eine Normalisierungsregel zu löschen, die einem Mandanten Wählplan zugeordnet ist, ohne zuerst den Mandanten Wähl Plan löschen zu müssen:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-140">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to deleting the tenant dial plan first:</span></span>
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="d7aaf-141">Führen Sie diese Schritte aus, um die folgende Normalisierungsregel zum vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-141">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="d7aaf-142">Führen Sie diese Option aus, um die folgende Normalisierungsregel aus dem vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-142">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d7aaf-143">Führen Sie die folgenden Schritte aus, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, ermitteln möchten, welche Sie löschen möchten, und dann deren Index verwenden, um Sie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-143">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="d7aaf-144">Das Array von Normalisierungsregeln beginnt mit Index 0.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-144">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="d7aaf-145">Wir möchten die dreistellige Normalisierungsregel entfernen, also Index 1.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-145">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="d7aaf-146">Führen Sie diese Aktion aus, um alle Benutzer zu finden, denen der redmonddialplan "-Mandanten Wählplan gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-146">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="d7aaf-147">Führen Sie diese Aktion aus, um PolicyName für alle Benutzer zu löschen, die Hostinganbieter-sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-147">Run this to delete policyname for all users who have HostingProvider sipfed.online.lync.com.</span></span>
```
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="d7aaf-148">Führen Sie diese aus, um den vorhandenen lokalen Wählplan mit dem Namen OPDP1 als Mandanten Wähl Plan für Ihre Organisation hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-148">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="d7aaf-149">Sie müssen den lokalen Wählplan zunächst in einer XML-Datei speichern und dann zum Erstellen des neuen Mandanten Wähl Plans verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-149">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="d7aaf-150">Führen Sie diese Aktion aus, um den lokalen Wählplan in der XML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-150">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="d7aaf-151">Führen Sie diese Aktion aus, um den neuen Mandanten Wählplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-151">Run this to create the new tenant dial plan.</span></span>
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d7aaf-152">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="d7aaf-152">Want to know more about Windows Powershell?</span></span>

- <span data-ttu-id="d7aaf-153">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d7aaf-154">Mit Windows PowerShell können Sie Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-154">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="d7aaf-155">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d7aaf-156">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d7aaf-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="d7aaf-157">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="d7aaf-157">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="d7aaf-158">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d7aaf-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d7aaf-159">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d7aaf-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d7aaf-160">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7aaf-160">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="d7aaf-161">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d7aaf-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d7aaf-162">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d7aaf-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="d7aaf-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d7aaf-163">Related topics</span></span>
[<span data-ttu-id="d7aaf-164">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="d7aaf-164">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="d7aaf-165">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="d7aaf-165">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="d7aaf-166">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d7aaf-166">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="d7aaf-167">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="d7aaf-167">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

<span data-ttu-id="d7aaf-168">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="d7aaf-168">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
