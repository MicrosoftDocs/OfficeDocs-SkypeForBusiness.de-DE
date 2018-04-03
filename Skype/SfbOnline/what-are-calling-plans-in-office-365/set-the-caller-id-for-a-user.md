---
title: Festlegen der Anrufer-ID für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: Das Telefonsystem in Office 365 bietet eine Standard Anrufer-ID, die dem Benutzer zugewiesene Telefonnummer ist. Sie können die Anrufer-ID (die auch als Anruferleitungs-ID bezeichnet wird) für einen Benutzer ändern oder blockieren. Erfahren Sie mehr dazu, wie Sie die Anrufer-ID in Ihrer Organisation mithilfe der Wechsel zu verwenden, wie die Anrufer-ID in Ihrer Organisation verwendet werden kann.
ms.openlocfilehash: 07fc6db1a161f8eca83ea601e1a8f5d70e1f1d5e
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="ec476-105">Festlegen der Anrufer-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec476-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="ec476-106">Das Telefonsystem in Office 365 bietet eine Standard Anrufer-ID, die dem Benutzer zugewiesene Telefonnummer ist.</span><span class="sxs-lookup"><span data-stu-id="ec476-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="ec476-107">Sie können die Anrufer-ID (die auch als Anruferleitungs-ID bezeichnet wird) für einen Benutzer ändern oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="ec476-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="ec476-108">Erfahren Sie mehr über die Anrufer-ID in Ihrer Organisation verwenden, [wie kann Anrufer-ID werden in Ihrer Organisation verwendeten](how-can-caller-id-be-used-in-your-organization.md)zugreifen, indem.</span><span class="sxs-lookup"><span data-stu-id="ec476-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="ec476-109">Sie können nicht für Business Online eingehende Anrufe, die derzeit in Skype blockieren.</span><span class="sxs-lookup"><span data-stu-id="ec476-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="ec476-110">Es gibt Einstellungen, die Sie ändern können:</span><span class="sxs-lookup"><span data-stu-id="ec476-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec476-111">Dies **gilt nicht** für lokale Organisationen mit Lync oder Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ec476-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="ec476-p103">**Ändern der ausgehenden Anrufer-ID**: Sie können die Anrufer-ID eines Benutzers - standardmäßig die Telefonnummer des Benutzers - durch eine andere Telefonnummer ersetzen. Sie können beispielsweise die Anrufer-ID des Benutzers von der Telefonnummer des Benutzers in eine Haupttelefonnummer für Ihr Unternehmen ändern, oder Sie können die Anruferleitungs-ID von der Telefonnummer des Benutzers in eine Haupttelefonnummer für die Rechtsabteilung ändern. Sie können die Anruf-ID-Nummer in jede Online- **Service** nummer (gebührenpflichtig oder gebührenfrei) ändern.</span><span class="sxs-lookup"><span data-stu-id="ec476-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec476-115">Wenn Sie den Parameter  _Service_ verwenden möchten, müssen Sie eine gültige Dienstnummer festlegen.</span><span class="sxs-lookup"><span data-stu-id="ec476-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="ec476-116">**Block ihren ausgehenden Anrufer-ID** Sie können die ausgehende Anrufer-ID auf ausgehende PSTN-Anrufe des Benutzers gesendet werden blockieren.</span><span class="sxs-lookup"><span data-stu-id="ec476-116">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="ec476-117">Dadurch wird die Anzeige der Telefonnummer am Telefon der angerufenen Person blockiert.</span><span class="sxs-lookup"><span data-stu-id="ec476-117">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="ec476-118">**Blockieren Sie ihre eingehenden Anrufer-ID** Sie können einen Benutzer aus der Anrufer-ID auf eine beliebige eingehende PSTN-Anrufe empfangen blockieren.</span><span class="sxs-lookup"><span data-stu-id="ec476-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="ec476-119">Bei Notrufen wird immer die Telefonnummer des Benutzers (Anrufer-ID) gesendet.</span><span class="sxs-lookup"><span data-stu-id="ec476-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="ec476-p105">Standardmäßig sind alle diese Anrufer-ID-Einstellungen **deaktiviert**. Dies bedeutet, dass die Telefonnummer des Skype for Business Online-Benutzers zu sehen ist, wenn der Benutzer einen Anruf bei einem PSTN-Telefon tätigt.</span><span class="sxs-lookup"><span data-stu-id="ec476-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="ec476-122">Weitere Informationen zu diesen Einstellungen und zu ihrer Verwendung finden Sie [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ec476-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="ec476-123">Festlegen Ihrer Anrufer-ID-Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="ec476-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="ec476-124">Für alle Einstellungen für die Anrufer-ID in Skype für Business Online müssen Sie Windows PowerShell, und Sie **kann nicht verwendet werden** , der **Skype für Business Administrationscenter**verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec476-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="ec476-125">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec476-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="ec476-126">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="ec476-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="ec476-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ec476-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ec476-128">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="ec476-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="ec476-p106">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="ec476-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="ec476-p107">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="ec476-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="ec476-135">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="ec476-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="ec476-136">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="ec476-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="ec476-137">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ec476-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="ec476-138">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="ec476-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ec476-139">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="ec476-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

<span data-ttu-id="ec476-140">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ec476-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="ec476-141">Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="ec476-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="ec476-142">Um alle Richtlinie für die Anrufer-ID in Ihrer Organisation anzuzeigen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ec476-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="ec476-143">[Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)finden Sie weitere Beispiele und Details.</span><span class="sxs-lookup"><span data-stu-id="ec476-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="ec476-144">Erstellen einer neuen Anrufer-ID-Richtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ec476-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="ec476-145">Zum Erstellen einer neuen Anrufer-ID-Richtlinie, die die Anrufer-ID auf anonymen festgelegt wird, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ec476-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```

  > [!NOTE]  
  > <span data-ttu-id="ec476-146">In allen Fällen das Feld "Dienst" sollte nicht enthalten einen anfänglichen "+".</span><span class="sxs-lookup"><span data-stu-id="ec476-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="ec476-147">[New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)finden Sie weitere Beispiele und Details.</span><span class="sxs-lookup"><span data-stu-id="ec476-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="ec476-148">Um die neue Richtlinie erstellten auf Amos Marmor anwenden möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ec476-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="ec476-149">Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec476-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="ec476-150">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie verwenden Sie das Cmdlet [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) , die vorhandene Richtlinie zu ändern, und klicken Sie dann mit dem Cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) verwenden, um die Einstellungen für die Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ec476-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="ec476-151">Festlegen, dass die eingehende Anrufer-ID blockiert wird</span><span class="sxs-lookup"><span data-stu-id="ec476-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="ec476-152">Um die eingehenden Anrufer-ID zu blockieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ec476-152">To block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="ec476-153">[Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)finden Sie weitere Beispiele und Details.</span><span class="sxs-lookup"><span data-stu-id="ec476-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="ec476-154">Zum Anwenden von einem Benutzer in Ihrer Organisation der richtlinieneinstellung, die Sie erstellt haben, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="ec476-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="ec476-155">Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec476-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="ec476-156">Entfernen einer Anrufer-ID-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ec476-156">Remove a caller ID policy</span></span>

<span data-ttu-id="ec476-157">Führen Sie Folgendes aus, um eine Richtlinie für Ihre Organisation zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ec476-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="ec476-158">Führen Sie Folgendes aus, um eine Richtlinie für einen Benutzer zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ec476-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ec476-159">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="ec476-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ec476-p108">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ec476-p108">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ec476-163">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ec476-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ec476-164">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365</span><span class="sxs-lookup"><span data-stu-id="ec476-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ec476-p109">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ec476-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ec476-167">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec476-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ec476-168">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ec476-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ec476-169">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ec476-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ec476-170">See Also</span><span class="sxs-lookup"><span data-stu-id="ec476-170">Related topics</span></span>
[<span data-ttu-id="ec476-171">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="ec476-171">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="ec476-172">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="ec476-172">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="ec476-173">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="ec476-173">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="ec476-174">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="ec476-174">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="ec476-175">Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe</span><span class="sxs-lookup"><span data-stu-id="ec476-175">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
  
  
 
