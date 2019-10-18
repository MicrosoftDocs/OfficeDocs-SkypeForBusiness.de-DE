---
title: Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Sehen Sie sich die Probleme mit Sonderzeichen in den Namen der Richtlinien an, und was Sie tun können, um Sie zu beheben.
ms.openlocfilehash: 169f427cc0efc444adfbc7e0f8056337e615f733
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568656"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="d936c-103">Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?</span><span class="sxs-lookup"><span data-stu-id="d936c-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="d936c-104">**Sie können keine Richtlinien (für Nachrichten, Besprechungen usw.) erstellen oder bearbeiten, die im Namen des Microsoft Teams admin Centers ein Sonderzeichen enthalten**.</span><span class="sxs-lookup"><span data-stu-id="d936c-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="d936c-105">Wenn ein Richtlinienname Sonderzeichen enthält, sind Sie im Microsoft Teams Admin Center auf die Verwaltung dieser Richtlinien limitiert.</span><span class="sxs-lookup"><span data-stu-id="d936c-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d936c-106">Daher **wird nachdrücklich empfohlen, dass Richtliniennamen keine Sonderzeichen enthalten**.</span><span class="sxs-lookup"><span data-stu-id="d936c-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="d936c-107">Richtliniennamen, die mit PowerShell für Besprechungen und Nachrichten in Teams erstellt wurden, können Sonderzeichen wie @, #, $ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d936c-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="d936c-108">Wenn Sie jedoch Änderungen an der Richtlinie im Microsoft Teams Admin Center vornehmen möchten, ist dies nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d936c-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="d936c-109">Wenn Sie über eine Richtlinie mit Sonderzeichen verfügen, müssen Sie entweder die Richtlinie mit Windows PowerShell (für immer) bearbeiten oder eine neue Richtlinie im Microsoft Teams Admin Center mit den gleichen Einstellungen wie die alte Richtlinie erstellen und der gleichen Benutzergruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d936c-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="d936c-110">So entfernen Sie Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="d936c-110">To remove special characters</span></span>

<span data-ttu-id="d936c-111">**Schritt 1: Erstellen einer Remoteverbindung mit PowerShell** 
 [Richten Sie Ihren Computer für Windows PowerShell ein](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , wenn Sie dies noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="d936c-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="d936c-112">**Schritt 2: Abrufen der Einstellungen für die alte Richtlinie und Aufzeichnen der Ausgabe.**</span><span class="sxs-lookup"><span data-stu-id="d936c-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="d936c-113">In diesem Beispiel handelt es sich um eine [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="d936c-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="d936c-114">Die Schritte wären für andere Richtlinientypen identisch, aber Sie müssen das richtige Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="d936c-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="d936c-115">**Schritt 3 – Erstellen einer neuen Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="d936c-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="d936c-116">Sie können entweder die neue Richtlinie mit der gleichen Einstellung erstellen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="d936c-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="d936c-117">Wenn Sie dies ausführen, wird eine neue Richtlinie für Sie erstellt, aber Sie müssen die richtigen Einstellungen hinzufügen, indem Sie [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) anzeigen und dann ausführen:</span><span class="sxs-lookup"><span data-stu-id="d936c-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="d936c-118">**Schritt 4: Zuweisen der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="d936c-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="d936c-119">Weitere Informationen zu diesem Cmdlet finden Sie unter [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d936c-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="d936c-120">**Schritt 5: Löschen der alten Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="d936c-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="d936c-121">Dadurch wird die alte Richtlinie mit den Sonderzeichen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d936c-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="d936c-122">Weitere Informationen zu diesem Cmdlet finden Sie unter [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d936c-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="d936c-123">Wenn dieser Befehl erfolgreich ausgeführt wird, sind Sie fertig.</span><span class="sxs-lookup"><span data-stu-id="d936c-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="d936c-124">Wenn der obige Befehl einen Fehler zurückgibt, liegt dies daran, dass die alte Richtlinie Benutzern zugewiesen ist, damit Sie alle zugewiesenen Benutzer aus der Richtlinie entfernen müssen:</span><span class="sxs-lookup"><span data-stu-id="d936c-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d936c-125">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="d936c-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="d936c-p105">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d936c-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d936c-129">Warum müssen Sie Office 365 PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="d936c-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="d936c-130">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d936c-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="d936c-131">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d936c-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="d936c-132">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d936c-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="d936c-133">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d936c-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="d936c-134">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d936c-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="d936c-135">Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="d936c-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="d936c-136">Mit dem Windows PowerShell-Modul für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, die eine Verbindung mit Skype for Business Online und Microsoft Teams herstellt.</span><span class="sxs-lookup"><span data-stu-id="d936c-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="d936c-137">Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="d936c-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

