---
title: Offline-Nachrichten für Administratoren ein- oder ausschalten
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 84455ad8efceda6af8f7f077ff9968485debed06
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568397"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="4f775-103">Offline-Nachrichten für Administratoren ein- oder ausschalten</span><span class="sxs-lookup"><span data-stu-id="4f775-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="4f775-p101">Sie können Skype for Business-Chatnachrichten an Ihre Kontakte senden, selbst wenn sie nicht angemeldet sind. Mit dieser Funktion informieren Sie Ihre Kontakte, dass Sie versucht haben, sie zu erreichen. Sie müssen nicht warten, bis jemand online ist, um eine Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="4f775-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span> 
  
<span data-ttu-id="4f775-107">Wichtige Informationen zu Offline-Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="4f775-107">For Offline messages, it's important to know:</span></span>
  
- <span data-ttu-id="4f775-108">Offline-Nachrichten werden nicht im Postfach des Benutzers archiviert.</span><span class="sxs-lookup"><span data-stu-id="4f775-108">Offline messages won't be archived in the user's mailbox.</span></span>
    
- <span data-ttu-id="4f775-109">Offlinenachrichten werden an das Postfach des Benutzers gesendet, und der Benutzer wird benachrichtigt, wenn er sich bei Skype for Business anmeldet.</span><span class="sxs-lookup"><span data-stu-id="4f775-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>
    
- <span data-ttu-id="4f775-110">Falls der Status des Nachrichtenempfängers **Nicht stören** oder **Hält Präsentation** lautet, erhält er eine Benachrichtigung über die verpasste Nachricht, die über seinen Skype for Business-Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="4f775-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>
    
<span data-ttu-id="4f775-111">Weitere Informationen finden Sie unter [Offline-Messaging in Skype for Business verwenden](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="4f775-111">For more information, see [Use offline messaging in Skype for Business](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>
  
## <a name="to-get-you-started"></a><span data-ttu-id="4f775-112">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="4f775-112">To get you started</span></span>

### 

 <span data-ttu-id="4f775-113">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="4f775-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="4f775-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4f775-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4f775-115">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="4f775-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="4f775-p102">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4f775-p102">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="4f775-p103">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4f775-p103">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="4f775-122">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f775-122">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
### 

 <span data-ttu-id="4f775-123">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="4f775-123">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="4f775-124">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="4f775-124">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="4f775-125">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="4f775-125">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4f775-126">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="4f775-126">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="4f775-127">Wenn Sie weitere Informationen zu Windows PowerShell starten möchten, finden Sie unter [Connect auf alle Office 365-Dienste in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder [Herstellen einer Verbindung mit Skype für Business Online mithilfe von Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4f775-127">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="4f775-128">Die Offline-Chatfunktion ein- oder ausschalten</span><span class="sxs-lookup"><span data-stu-id="4f775-128">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="4f775-129">Offlinenachrichten sind **nur** in der aktuellen Klick-und-Los-Version des Skype for Business-Clients verfügbar. Sie sind nicht verfügbar, wenn eine ältere Klick-und-Los-Version von Skype for Business verwendet wird oder der Skype for Business-Client über eine MSI-Datei installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4f775-129">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>
  
<span data-ttu-id="4f775-130">Um das Senden von Offlinenachrichten für Benutzer in Ihrer Organisation zu aktivieren oder zu deaktivieren, legen Sie  _EnableIMAutoArchiving_ auf `True` oder `False` fest.</span><span class="sxs-lookup"><span data-stu-id="4f775-130">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="4f775-131">Standardmäßig ist dies auf festgelegt `True`.</span><span class="sxs-lookup"><span data-stu-id="4f775-131">By default, this is set to `True`.</span></span>
  
<span data-ttu-id="4f775-132">Um die Funktion zu deaktivieren, verwenden Sie das **Set-CsClientPolicy** -Cmdlet, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="4f775-132">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="4f775-133">Um das Senden von Offlinenachrichten für einen Benutzer zu aktivieren oder zu deaktivieren, legen Sie  _EnableIMAutoArchiving_ auf `True` oder `False` fest.</span><span class="sxs-lookup"><span data-stu-id="4f775-133">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="4f775-134">Standardmäßig ist diese Option auf `True` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4f775-134">By default, this is set to  `True`.</span></span> <span data-ttu-id="4f775-135">Sie können eine vorhandene Richtlinie verwenden oder erstellen Sie wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="4f775-135">You can use an existing policy or create one like the example below.</span></span>
  
 
  ```
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4f775-136">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="4f775-136">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="4f775-137">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="4f775-137">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="4f775-138">Mit Windows PowerShell können Sie Office 365 und Skype verwalten, für die Business Online verwenden eine zentrale Verwaltung, die Ihrer täglichen Arbeit vereinfachen können, wenn Sie mehrere Aufgaben ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="4f775-138">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="4f775-139">Siehe folgende Themen, um Windows PowerShell zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="4f775-139">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4f775-140">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f775-140">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4f775-141">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365</span><span class="sxs-lookup"><span data-stu-id="4f775-141">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Office 365 </span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4f775-p107">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4f775-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4f775-144">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f775-144">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4f775-145">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f775-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4f775-146">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f775-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4f775-147">See Also</span><span class="sxs-lookup"><span data-stu-id="4f775-147">Related topics</span></span>
[<span data-ttu-id="4f775-148">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4f775-148">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="4f775-149">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="4f775-149">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 