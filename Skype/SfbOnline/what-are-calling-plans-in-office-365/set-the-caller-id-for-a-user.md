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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Das Telefonsystem in Office 365 stellt eine Standard-Rufnummernanzeige zur Verfügung, die die dem Benutzer zugewiesene Telefonnummer ist. Sie können die Rufnummernanzeige (auch Telefonnummer-ID genannt) für einen Benutzer ändern oder sperren. Weitere Informationen zur Verwendung der Rufnummernanzeige in Ihrer Organisation finden Sie unter "Wie kann die Rufnummernanzeige in Ihrer Organisation verwendet werden?".
ms.openlocfilehash: cf6f1aab6f865a87186b7acb793e5aa7829907aa
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780817"
---
# <a name="set-the-caller-id-for-a-user"></a><span data-ttu-id="6a9f7-105">Festlegen der Anrufer-ID für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="6a9f7-105">Set the Caller ID for a user</span></span>
<span data-ttu-id="6a9f7-p102">Die Telefonanlage in Office 365 stellt eine Standard-Rufnummernanzeige zur Verfügung, die die dem Benutzer zugewiesene Telefonnummer ist. Sie können die Rufnummernanzeige (auch Anrufleitung-ID genannt) für einen Benutzer ändern oder sperren. Weitere Informationen zur Verwendung der Rufnummernanzeige in Ihrer Organisation finden Sie unter [Wie kann die Anrufer-ID in Ihrer Organisation verwendet werden](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-p102">Cloud PBX in Skype for Business Online provides a default caller ID that is the user's assigned telephone number. You can either change or block the caller ID (also called a Calling Line ID) for a user. You learn more about how to use caller ID in your organization by going [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
> [!TIP]
> <span data-ttu-id="6a9f7-109">Sie können eingehende Anrufe derzeit in Skype for Business Online nicht blockieren.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-109">You can't block incoming calls currently in Skype for Business Online.</span></span> 
  
<span data-ttu-id="6a9f7-110">Es gibt Einstellungen, die Sie ändern können:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-110">There are settings that you can change:</span></span>
  
> [!NOTE]
> <span data-ttu-id="6a9f7-111">Dies **gilt nicht** für lokale Organisationen mit Lync oder Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-111">This **is not** for on-premises organizations with Lync or Skype for Business Server.</span></span>
  
- <span data-ttu-id="6a9f7-p103">**Ändern der ausgehenden Anrufer-ID**: Sie können die Anrufer-ID eines Benutzers - standardmäßig die Telefonnummer des Benutzers - durch eine andere Telefonnummer ersetzen. Sie können beispielsweise die Anrufer-ID des Benutzers von der Telefonnummer des Benutzers in eine Haupttelefonnummer für Ihr Unternehmen ändern, oder Sie können die Anruferleitungs-ID von der Telefonnummer des Benutzers in eine Haupttelefonnummer für die Rechtsabteilung ändern. Sie können die Anruf-ID-Nummer in jede Online- **Service** nummer (gebührenpflichtig oder gebührenfrei) ändern.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-p103">**Change their outgoing caller ID** You can replace a user's Caller ID, which by default is their telephone number, with another phone number. For example, you could change the user's Caller ID from their phone number to a main phone number for your business or change the user's Calling Line ID from their phone number to a main phone number for the legal department. You can change the Calling ID number to any Online **service** number (toll or toll-free).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6a9f7-115">Wenn Sie den Parameter  _Service_ verwenden möchten, müssen Sie eine gültige Dienstnummer festlegen.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-115">If you want to use the  _Service_ parameter, you must specify a valid service number.</span></span>
  
- <span data-ttu-id="6a9f7-116">**Blockieren der ausgehenden Rufnummernanzeige** Sie können die ausgehende Rufnummernanzeige so blockieren, dass sie bei ausgehenden PSTN-Anrufen eines Benutzers nicht gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-116">**Block their outbound caller ID** You can block their outgoing Caller ID from being sent on a user's outgoing PSTN calls.</span></span> <span data-ttu-id="6a9f7-117">Dadurch wird die Anzeige der Telefonnummer am Telefon der angerufenen Person blockiert.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-117">Doing this will block their phone number from being displayed on the phone of a person being called.</span></span>
    
- <span data-ttu-id="6a9f7-118">**Blockieren der eingehenden Rufnummernanzeige**: Sie können blockieren, dass der Benutzer die Rufnummernanzeige bei eingehenden PSTN-Anrufen empfängt.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-118">**Block their incoming caller ID** You can block the user from receiving Caller ID on any incoming PSTN calls.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="6a9f7-119">Bei Notrufen wird immer die Telefonnummer des Benutzers (Rufnummernanzeige) gesendet.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-119">Emergency calls will always send the user's telephone number (caller ID).</span></span> 
  
<span data-ttu-id="6a9f7-p105">Standardmäßig sind alle diese Anrufer-ID-Einstellungen **deaktiviert**. Dies bedeutet, dass die Telefonnummer des Skype for Business Online-Benutzers zu sehen ist, wenn der Benutzer einen Anruf bei einem PSTN-Telefon tätigt.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-p105">By default, all of these caller ID settings are **turned off**. This means that the Skype for Business Online user's phone number can be seen when that user makes a call to a PSTN phone.</span></span>
  
<span data-ttu-id="6a9f7-122">Weitere Informationen zu diesen Einstellungen und zu ihrer Verwendung finden Sie [Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation](how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-122">To learn more about these settings and how you can use them, go [How can caller ID be used in your organization](how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="set-your-caller-id-policy-settings"></a><span data-ttu-id="6a9f7-123">Festlegen Ihrer Rufnummernanzeigen-Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="6a9f7-123">Set your caller ID policy settings</span></span>

> [!NOTE]
> <span data-ttu-id="6a9f7-124">Für alle Rufnummernanzeigen-Einstellungen in Skype for Business Online müssen Sie Windows PowerShell verwenden, **nicht** das **Skype for Business Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-124">For all of the callerID settings in Skype for Business Online you must use Windows PowerShell and you **can't use** the **Skype for Business admin center**.</span></span> 
  
### <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="6a9f7-125">Überprüfen und Starten von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a9f7-125">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="6a9f7-126">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="6a9f7-126">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="6a9f7-127">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-127">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6a9f7-128">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-128">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6a9f7-p106">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-p106">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6a9f7-p107">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-p107">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="6a9f7-135">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-135">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="6a9f7-136">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="6a9f7-136">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="6a9f7-137">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-137">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6a9f7-138">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-138">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6a9f7-139">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-139">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
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

<span data-ttu-id="6a9f7-140">Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-140">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a><span data-ttu-id="6a9f7-141">Anzeigen aller Rufnummernanzeigen-Richtlinieneinstellungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="6a9f7-141">See all of the caller ID policy settings in your organization</span></span>

- <span data-ttu-id="6a9f7-142">Zeigen Sie alle Rufnummernanzeigen-Richtlinieneinstellungen in Ihrer Organisation an, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-142">View all of the caller ID policy settings in your organization, run:</span></span>

  ```
  Get-CsCallingLineIdentity |fl
  ```
<span data-ttu-id="6a9f7-143">Weitere Beispiele und Details finden Sie im Artikel zu [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-143">See more examples and details for [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx)</span></span>
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a><span data-ttu-id="6a9f7-144">Erstellen einer neuen Rufnummernanzeigen-Richtlinie für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6a9f7-144">Create a new caller ID policy for your organization</span></span>


- <span data-ttu-id="6a9f7-145">Erstellen Sie eine neue Rufnummernanzeigen-Richtlinie, mit der die Rufnummernanzeige auf Anonym festlegt wird, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-145">Create a new caller ID policy that sets the caller ID to anonymous, run:</span></span>
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > <span data-ttu-id="6a9f7-146">In allen Fällen sollte das Feld "Servicenummer" kein "+" enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-146">In all cases, the "Service Number" field should not include an initial "+".</span></span>

  <span data-ttu-id="6a9f7-147">Weitere Beispiele und Details finden Sie im Artikel zu [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-147">See more examples and details for [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx)</span></span>
    
- <span data-ttu-id="6a9f7-148">Um die erstellte neue Richtlinie Amos Marble zuzuweisen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-148">To grant the new policy you created to Amos Marble, run:</span></span>
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  <span data-ttu-id="6a9f7-149">Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-149">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
<span data-ttu-id="6a9f7-150">Wenn Sie bereits eine Richtlinie erstellt haben, können Sie mit dem [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt793854.aspx)-Cmdlet Änderungen an der vorhandenen Richtlinie vornehmen und dann mit dem [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet die Einstellungen auf die Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-150">If you have already created a policy, you can use the [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt793854.aspx) cmdlet to make changes to the existing policy, and then use the[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet to apply the settings to your users.</span></span>
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a><span data-ttu-id="6a9f7-151">Festlegen, dass die eingehende Anrufer-ID blockiert wird</span><span class="sxs-lookup"><span data-stu-id="6a9f7-151">Set it so the incoming caller ID is blocked</span></span>

- <span data-ttu-id="6a9f7-152">Blockieren Sie die eingehende Rufnummernanzeige, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-152">Block the incoming caller ID, run:</span></span>
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  <span data-ttu-id="6a9f7-153">Weitere Beispiele und Details finden Sie im Artikel zu [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).</span><span class="sxs-lookup"><span data-stu-id="6a9f7-153">See more examples and details for [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx)</span></span>
    
- <span data-ttu-id="6a9f7-154">Wenden Sie die erstellte Richtlinieneinstellung auf einen Benutzer in der Organisation an, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-154">Apply the policy setting you created to a user in your organization, run:</span></span>
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    <span data-ttu-id="6a9f7-155">Weitere Informationen finden Sie im Artikel zum [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx)-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-155">See more on the [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) cmdlet.</span></span>
    
### <a name="remove-a-caller-id-policy"></a><span data-ttu-id="6a9f7-156">Entfernen einer Anrufer-ID-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6a9f7-156">Remove a caller ID policy</span></span>

<span data-ttu-id="6a9f7-157">Führen Sie Folgendes aus, um eine Richtlinie für Ihre Organisation zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-157">To remove a policy from your organization, run:</span></span>
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
<span data-ttu-id="6a9f7-158">Führen Sie Folgendes aus, um eine Richtlinie für einen Benutzer zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-158">To remove a policy from a user, run:</span></span>
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6a9f7-159">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="6a9f7-159">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6a9f7-160">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-160">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6a9f7-161">Mit Windows PowerShell können Sie Office 365 und Skype for Business Online über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen, wenn Sie viele Dinge zu tun haben.</span><span class="sxs-lookup"><span data-stu-id="6a9f7-161">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="6a9f7-162">Siehe folgende Themen, um Windows PowerShell zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-162">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6a9f7-163">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6a9f7-163">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6a9f7-164">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365 </span><span class="sxs-lookup"><span data-stu-id="6a9f7-164">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6a9f7-p109">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6a9f7-p109">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6a9f7-167">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a9f7-167">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6a9f7-168">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6a9f7-168">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6a9f7-169">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6a9f7-169">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a><span data-ttu-id="6a9f7-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6a9f7-170">Related topics</span></span>
[<span data-ttu-id="6a9f7-171">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="6a9f7-171">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="6a9f7-172">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="6a9f7-172">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="6a9f7-173">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="6a9f7-173">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="6a9f7-174">Mehr über Telefonnummer-ID und Name des Anrufers</span><span class="sxs-lookup"><span data-stu-id="6a9f7-174">More about Calling Line ID and Calling Party Name</span></span>](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[<span data-ttu-id="6a9f7-175">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="6a9f7-175">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="6a9f7-176">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="6a9f7-176">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
 
