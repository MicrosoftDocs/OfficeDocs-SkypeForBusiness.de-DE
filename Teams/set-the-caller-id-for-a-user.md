---
title: Festlegen der Anrufer-ID für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You can learn more about how to use caller ID in your organization by going How can caller ID be used in your organization.
ms.openlocfilehash: 9b31e761ee59626482b0cd98991ae1ab886af7b6
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838095"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="4a5e6-105">Festlegen der Anrufer-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="4a5e6-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="4a5e6-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-106">The Phone System in Office 365 provides a default caller ID that is the user's assigned telephone number.</span></span> <span data-ttu-id="4a5e6-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-107">You can either change or block the caller ID (also called a Calling Line ID) for a user.</span></span> <span data-ttu-id="4a5e6-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-108">You can learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="4a5e6-109">Sie können eingehende Anrufe derzeit in Skype for Business Online nicht blockieren.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="4a5e6-110">Es gibt Einstellungen, die Sie ändern können:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a5e6-111">Dies **gilt nicht** für lokale Organisationen mit Lync oder Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="4a5e6-p103">**Ändern der ausgehenden Anrufer-ID**: Sie können die Anrufer-ID eines Benutzers - standardmäßig die Telefonnummer des Benutzers - durch eine andere Telefonnummer ersetzen. Sie können beispielsweise die Anrufer-ID des Benutzers von der Telefonnummer des Benutzers in eine Haupttelefonnummer für Ihr Unternehmen ändern, oder Sie können die Anruferleitungs-ID von der Telefonnummer des Benutzers in eine Haupttelefonnummer für die Rechtsabteilung ändern. Sie können die Anruf-ID-Nummer in jede Online- **Service** nummer (gebührenpflichtig oder gebührenfrei) ändern.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4a5e6-115">Wenn Sie den Parameter  _Service_ verwenden möchten, müssen Sie eine gültige Dienstnummer festlegen.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="4a5e6-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p104">**Block their outbound caller ID** You can block the outgoing Caller ID from being sent on a user's outgoing PSTN calls. Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="4a5e6-118">**Blockieren der eingehenden Anrufer-ID** Sie können verhindern, dass ein Benutzer die Rufnummernanzeige bei eingehenden PSTN-anrufen empfängt.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-118">**Block their incoming caller ID** You can block a user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="4a5e6-119">Bei Notrufen wird immer die Telefonnummer des Benutzers (Anrufer-ID) gesendet.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="4a5e6-p105">Standardmäßig sind alle diese Anrufer-ID-Einstellungen **deaktiviert**. Dies bedeutet, dass die Telefonnummer des Skype for Business Online-Benutzers zu sehen ist, wenn der Benutzer einen Anruf bei einem PSTN-Telefon tätigt.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="4a5e6-122">Weitere Informationen zu diesen Einstellungen und zu ihrer Verwendung finden Sie [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="4a5e6-123">Festlegen Ihrer Anrufer-ID-Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="4a5e6-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="4a5e6-124">Für alle Anrufer-ID-Einstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, und Sie können das **Skype for Business Admin Center** **nicht verwenden** .</span><span class="sxs-lookup"><span data-stu-id="4a5e6-124">For all of the Caller ID settings in Skype for Business Online, you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="4a5e6-125">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a5e6-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="4a5e6-126">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="4a5e6-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="4a5e6-127">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4a5e6-128">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4a5e6-p106">Wenn Sie nicht über Version 3,0 oder höher verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4a5e6-p107">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="4a5e6-135">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="4a5e6-136">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="4a5e6-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="4a5e6-137">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4a5e6-138">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="4a5e6-139">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

<span data-ttu-id="4a5e6-140">Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="4a5e6-141">Anzeigen aller Anrufer-ID-Richtlinieneinstellungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4a5e6-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="4a5e6-142">Wenn Sie alle Einstellungen für die Rufnummernanzeige in Ihrer Organisation anzeigen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-142">To view all of the caller ID policy settings in your organization, run:</span></span>

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  <span data-ttu-id="4a5e6-143">Weitere Beispiele und Details finden Sie unter [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="4a5e6-144">Erstellen einer neuen Anrufer-ID-Richtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4a5e6-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="4a5e6-145">Führen Sie Folgendes aus, um eine neue Richtlinie für die Rufnummernanzeige zu erstellen, die die Rufnummernanzeige auf Anonymous festlegt:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-145">To create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="4a5e6-146">In allen Fällen sollte das Feld "Servicenummer" kein "+" enthalten.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="4a5e6-147">Weitere Beispiele und Details finden Sie unter [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793855.aspx).</span></span>
    
- <span data-ttu-id="4a5e6-148">Um die von Ihnen erstellte neue Richtlinie auf Amos Marble anzuwenden, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-148">To apply the new policy you created to Amos Marble, run:</span></span>
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="4a5e6-149">Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="4a5e6-150">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie das Cmdlet " [festlegen-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) " verwenden, um Änderungen an der vorhandenen Richtlinie vorzunehmen, und verwenden Sie dann das Cmdlet [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) , um die Einstellungen auf die Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-150">If you have already created a policy, you can use the [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="4a5e6-151">Festlegen, dass die eingehende Anrufer-ID blockiert wird</span><span class="sxs-lookup"><span data-stu-id="4a5e6-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="4a5e6-152">Um die eingehende Rufnummernanzeige zu blockieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-152">To block the incoming caller ID, run:</span></span>
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="4a5e6-153">Weitere Beispiele und Details finden Sie unter [Satz-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="4a5e6-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).</span></span>
    
- <span data-ttu-id="4a5e6-154">Um die von Ihnen erstellte Richtlinieneinstellung auf einen Benutzer in Ihrer Organisation anzuwenden, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-154">To apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="4a5e6-155">Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4a5e6-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="4a5e6-156">Entfernen einer Anrufer-ID-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4a5e6-156">Remove a caller ID policy</span></span>

<span data-ttu-id="4a5e6-157">Führen Sie Folgendes aus, um eine Richtlinie für Ihre Organisation zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-157">To remove a policy from your organization, run:</span></span>
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="4a5e6-158">Führen Sie Folgendes aus, um eine Richtlinie für einen Benutzer zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-158">To remove a policy from a user, run:</span></span>
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4a5e6-159">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4a5e6-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4a5e6-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p108">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4a5e6-163">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a5e6-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4a5e6-164">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365</span><span class="sxs-lookup"><span data-stu-id="4a5e6-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4a5e6-p109">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Weitere Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4a5e6-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4a5e6-167">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a5e6-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4a5e6-168">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a5e6-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4a5e6-169">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4a5e6-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="4a5e6-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4a5e6-170">Related topics</span></span>
[<span data-ttu-id="4a5e6-171">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="4a5e6-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="4a5e6-172">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="4a5e6-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="4a5e6-173">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4a5e6-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="4a5e6-174">Mehr über Telefonnummer-ID und Name des Anrufers</span><span class="sxs-lookup"><span data-stu-id="4a5e6-174">More about Calling Line ID and Calling Party Name</span></span>](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[<span data-ttu-id="4a5e6-175">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="4a5e6-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="4a5e6-176">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="4a5e6-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
