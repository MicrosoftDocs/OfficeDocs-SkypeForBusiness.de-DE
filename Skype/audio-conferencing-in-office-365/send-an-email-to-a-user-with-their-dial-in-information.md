---
title: Senden einer e-Mails an einen Benutzer mit ihren Einwahlinformationen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Senden Sie Ihre Benutzer eine e-Mail mit ihren Audiokonferenzinformationen.
ms.openlocfilehash: cb7aaa956b6a679b918603e2aef2ff15ff04a779
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a><span data-ttu-id="ab5de-103">Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ab5de-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="ab5de-104">Manchmal Skype für Business oder Microsoft-Teams, Benutzer benötigen Sie möglicherweise dies ihre Informationen Audiokonferenzen veranlassen.</span><span class="sxs-lookup"><span data-stu-id="ab5de-104">Sometimes Skype for Business or Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="ab5de-105">Sie können diese Schritte durchführen, indem Sie mithilfe der **Skype für Business Administrationscenter** und unter den Eigenschaften für einen Benutzer auf **Konferenz Informationen per e-Mail senden** .</span><span class="sxs-lookup"><span data-stu-id="ab5de-105">You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="ab5de-106">Wenn Sie diese e-Mail senden, enthält sie alle Audiokonferenzinformationen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="ab5de-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="ab5de-107">Die Konferenztelefon- oder Einwahltelefonnummer für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ab5de-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="ab5de-108">Die Konferenz-ID des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ab5de-108">The user's conference ID.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab5de-109">Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist.</span><span class="sxs-lookup"><span data-stu-id="ab5de-109">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="ab5de-110">Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen</span><span class="sxs-lookup"><span data-stu-id="ab5de-110">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="ab5de-111">Wenn Sie zuweisen dynamische statt statische Konferenz-IDs, [Wechseln Sie hier möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ab5de-111">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
<span data-ttu-id="ab5de-112">Es folgt ein Beispiel der e-Mail, die gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="ab5de-112">Here is an example of the email that is sent:</span></span>
  
![E-Mail zu einer Dial-In-Konferenz](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="ab5de-114">Senden Sie eine e-Mail mit Audiokonferenzinformationen an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="ab5de-114">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="ab5de-115">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="ab5de-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ab5de-116">Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen**, und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.</span><span class="sxs-lookup"><span data-stu-id="ab5de-116">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="ab5de-117">Klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="ab5de-117">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="ab5de-118">Klicken Sie im Bereich „Aktion" auf **Konferenzinformationen per E-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="ab5de-118">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="ab5de-119">Sie können e-Mail auch für den Benutzer mit den Einstellungen Audiokonferenzen senden, indem die Eigenschaften des Benutzers bearbeiten und dann auf **Audiokonferenzen** > **Konferenz Informationen per e-Mail senden**.</span><span class="sxs-lookup"><span data-stu-id="ab5de-119">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="ab5de-120">Was sollten Sie sonst über diese E-Mails wissen?</span><span class="sxs-lookup"><span data-stu-id="ab5de-120">What else should you know about this email?</span></span>

- <span data-ttu-id="ab5de-121">Es gibt mehrere e-Mails, die gesendet werden, um Benutzer in Ihrer Organisation, nachdem sie aktiviert sind für Audiokonferenzen:</span><span class="sxs-lookup"><span data-stu-id="ab5de-121">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="ab5de-122">Wenn Ihnen eine **Audiokonferenz** -Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ab5de-122">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="ab5de-123">Wenn Sie manuell des Benutzers Audiokonferenzen PIN zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ab5de-123">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="ab5de-124">Wenn Sie die Konferenz-PIN des Benutzers manuell zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="ab5de-124">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="ab5de-125">Wenn eine **Audiokonferenz** Lizenz daraus entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ab5de-125">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="ab5de-126">Wenn der Anbieter von Audiokonferenzen für einen Benutzer von Microsoft auf einen anderen Anbieter oder **None**geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ab5de-126">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="ab5de-127">Wenn der Anbieter von Audiokonferenzen für einen Benutzer an Microsoft geändert wird.</span><span class="sxs-lookup"><span data-stu-id="ab5de-127">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="ab5de-128">Standardmäßig der Absender der e-Mail-Nachrichten werden von Office 365, aber Sie können die e-Mail-Adresse ändern und den Anzeigenamen mithilfe von Windows PowerShell und das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) .</span><span class="sxs-lookup"><span data-stu-id="ab5de-128">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span></span> <span data-ttu-id="ab5de-129">Um die e-Mail-Adresse ändern, die die e-Mail an Benutzer senden, müssen Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="ab5de-129">To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="ab5de-130">Geben Sie die e-Mail-Adresse in der SendEmailFromAddress-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ab5de-130">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="ab5de-131">Den SendEmailOverride-Parameter auf "true" festlegen.</span><span class="sxs-lookup"><span data-stu-id="ab5de-131">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="ab5de-132">Geben Sie den e-Mail-Anzeigenamen im SendEmailFromDisplayName-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ab5de-132">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="ab5de-133">Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihres Unternehmens für eingehende E-Mails es zulassen, dass E-Mails von der festgelegten benutzerdefinierten Absenderadresse gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab5de-133">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ab5de-134">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="ab5de-134">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ab5de-135">Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.</span><span class="sxs-lookup"><span data-stu-id="ab5de-135">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="ab5de-136">Um eine e-Mail an den Benutzer mit ihren Audiokonferenzinformationen senden möchten, führen Sie folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="ab5de-136">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  <span data-ttu-id="ab5de-p104">In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ab5de-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ab5de-140">Warum müssen Sie mithilfe von Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab5de-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ab5de-141">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab5de-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ab5de-142">Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen.</span><span class="sxs-lookup"><span data-stu-id="ab5de-142">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ab5de-143">Informationen Sie zu dieser Vorteile in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ab5de-143">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ab5de-144">Eine Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ab5de-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="ab5de-145">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ab5de-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ab5de-146">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ab5de-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ab5de-p106">Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="ab5de-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ab5de-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ab5de-149">Related topics</span></span>

[<span data-ttu-id="ab5de-150">Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab5de-150">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
