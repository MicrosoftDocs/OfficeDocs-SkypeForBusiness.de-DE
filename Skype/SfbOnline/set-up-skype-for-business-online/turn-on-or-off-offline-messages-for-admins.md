---
title: Offline-Nachrichten für Administratoren ein- oder ausschalten
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Sie erfahren, wie Sie Skype for Business-Sofortnachrichten senden können, auch wenn Ihre Kontakte nicht mit PowerShell angemeldet sind.
ms.openlocfilehash: 12d5a6c736616cb9448dc1f75a6f67424d940d7f
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814604"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a><span data-ttu-id="56dd2-103">Offline-Nachrichten für Administratoren ein- oder ausschalten</span><span class="sxs-lookup"><span data-stu-id="56dd2-103">Turn on or off Offline Messages for admins</span></span>

<span data-ttu-id="56dd2-p101">Sie können Skype for Business-Chatnachrichten an Ihre Kontakte senden, selbst wenn sie nicht angemeldet sind. Mit dieser Funktion informieren Sie Ihre Kontakte, dass Sie versucht haben, sie zu erreichen. Sie müssen nicht warten, bis jemand online ist, um eine Nachricht zu senden.</span><span class="sxs-lookup"><span data-stu-id="56dd2-p101">You can send Skype for Business IMs to your contacts even if they aren't signed in. This feature lets your contacts know that you have been trying to reach them. You don't have to wait until someone is online before sending them a message.</span></span>

<span data-ttu-id="56dd2-107">Wichtige Informationen zu Offline-Nachrichten:</span><span class="sxs-lookup"><span data-stu-id="56dd2-107">For Offline messages, it's important to know:</span></span>

- <span data-ttu-id="56dd2-108">Offline-Nachrichten werden nicht im Postfach des Benutzers archiviert.</span><span class="sxs-lookup"><span data-stu-id="56dd2-108">Offline messages won't be archived in the user's mailbox.</span></span>

- <span data-ttu-id="56dd2-109">Offlinenachrichten werden an das Postfach des Benutzers gesendet, und der Benutzer wird benachrichtigt, wenn er sich bei Skype for Business anmeldet.</span><span class="sxs-lookup"><span data-stu-id="56dd2-109">Offline messages will be sent to the user's mailbox, and the user will be notified when they log in to Skype for Business.</span></span>

- <span data-ttu-id="56dd2-110">Falls der Status des Nachrichtenempfängers **Nicht stören** oder **Hält Präsentation** lautet, erhält er eine Benachrichtigung über die verpasste Nachricht, die über seinen Skype for Business-Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="56dd2-110">If the message recipient's status is set to **Do Not Disturb** or **Presenting**, they will receive a missed message that is sent from the recipient's Skype for Business client.</span></span>

<span data-ttu-id="56dd2-111">Weitere Informationen finden Sie unter [Offline-Messaging in Skype for Business verwenden](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span><span class="sxs-lookup"><span data-stu-id="56dd2-111">For more information, see [Use offline messaging in Skype for Business](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).</span></span>

## <a name="to-get-you-started"></a><span data-ttu-id="56dd2-112">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="56dd2-112">To get you started</span></span>

## #

 <span data-ttu-id="56dd2-113">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="56dd2-113">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>

1. <span data-ttu-id="56dd2-114">Zur Überprüfung ob Sie Version 3.0 oder höher verwenden: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="56dd2-114">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="56dd2-115">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="56dd2-115">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>

3. <span data-ttu-id="56dd2-116">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="56dd2-116">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="56dd2-117">Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="56dd2-117">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="56dd2-118">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="56dd2-118">Restart your computer when you are prompted.</span></span>

4. <span data-ttu-id="56dd2-119">Außerdem müssen Sie das Windows PowerShell-Modul für Teams installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="56dd2-119">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>

<span data-ttu-id="56dd2-120">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="56dd2-120">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>

## #

 <span data-ttu-id="56dd2-121">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="56dd2-121">**Start a Windows PowerShell session**</span></span>

1. <span data-ttu-id="56dd2-122">Vom **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="56dd2-122">From the **Start Menu** > **Windows PowerShell**.</span></span>

2. <span data-ttu-id="56dd2-123">Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Ihrem Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="56dd2-123">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>

   > [!NOTE]
   > <span data-ttu-id="56dd2-124">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="56dd2-124">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="56dd2-125">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="56dd2-125">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

  ```PowerShell
  Import-Module -Name MicrosoftTeams
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

<span data-ttu-id="56dd2-126">Wenn Sie weitere Informationen zum Starten von Windows PowerShell benötigen, lesen Sie [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://technet.microsoft.com/library/dn568015.aspx) oder [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="56dd2-126">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>

## <a name="turning-on-or-off-offline-im"></a><span data-ttu-id="56dd2-127">Die Offline-Chatfunktion ein- oder ausschalten</span><span class="sxs-lookup"><span data-stu-id="56dd2-127">Turning on or off Offline IM</span></span>

> [!NOTE]
> <span data-ttu-id="56dd2-128">Offlinenachrichten sind **nur** in der aktuellen Klick-und-Los-Version des Skype for Business-Clients verfügbar. Sie sind nicht verfügbar, wenn eine ältere Klick-und-Los-Version von Skype for Business verwendet wird oder der Skype for Business-Client über eine MSI-Datei installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="56dd2-128">Offline Messages are **only** available in the latest version of the Click-to-Run Skype for Business client and aren't available when an older Click-to-Run Skype for Business is used or an \*.msi file was used to install the Skype for Business client.</span></span>

<span data-ttu-id="56dd2-129">Um das Senden von Offlinenachrichten für Benutzer in Ihrer Organisation zu aktivieren oder zu deaktivieren, legen Sie  _EnableIMAutoArchiving_ auf `True` oder `False` fest.</span><span class="sxs-lookup"><span data-stu-id="56dd2-129">To enable or disable Offline Messages send Offline Messages for users in your organization, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="56dd2-130">Standardmäßig ist diese Einstellung auf `True` .</span><span class="sxs-lookup"><span data-stu-id="56dd2-130">By default, this is set to `True`.</span></span>

<span data-ttu-id="56dd2-131">Um die Funktion zu deaktivieren, verwenden Sie das **Set-CsClientPolicy** -Cmdlet, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="56dd2-131">To turn it off, use the **Set-CsClientPolicy** cmdlet and run:</span></span>

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

<span data-ttu-id="56dd2-132">Um das Senden von Offlinenachrichten für einen Benutzer zu aktivieren oder zu deaktivieren, legen Sie  _EnableIMAutoArchiving_ auf `True` oder `False` fest.</span><span class="sxs-lookup"><span data-stu-id="56dd2-132">To enable or disable Offline Messages send Offline Messages for a user, set  _EnableIMAutoArchiving_ to `True` or `False`.</span></span> <span data-ttu-id="56dd2-133">Standardmäßig ist diese Option auf `True` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56dd2-133">By default, this is set to  `True`.</span></span> <span data-ttu-id="56dd2-134">Sie können eine vorhandene Richtlinie verwenden oder eine erstellen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="56dd2-134">You can use an existing policy or create one like the example below.</span></span>


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="56dd2-135">Möchten Sie mehr über Windows PowerShell erfahren?</span><span class="sxs-lookup"><span data-stu-id="56dd2-135">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="56dd2-136">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="56dd2-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="56dd2-137">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="56dd2-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="56dd2-138">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="56dd2-138">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="56dd2-139">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="56dd2-139">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="56dd2-140">Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="56dd2-140">Six Reasons Why You Might Want to Use Windows PowerShell to Manage Microsoft 365 or Office 365</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="56dd2-141">Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="56dd2-141">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="56dd2-142">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="56dd2-142">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="56dd2-143">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56dd2-143">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="56dd2-144">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="56dd2-144">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="56dd2-145">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="56dd2-145">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="56dd2-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="56dd2-146">Related topics</span></span>
[<span data-ttu-id="56dd2-147">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="56dd2-147">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="56dd2-148">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="56dd2-148">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)


