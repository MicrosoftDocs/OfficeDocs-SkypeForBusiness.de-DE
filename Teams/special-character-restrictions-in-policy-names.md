---
title: Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Finden Sie unter welche Probleme mit Sonderzeichen im Namen von Richtlinien und was Sie tun können sind, um es zu beheben.
ms.openlocfilehash: b0ae1458e81bdb6ee527c954ab0f2faf3461e3cf
ms.sourcegitcommit: 33966ebb9ca3d922d47aaa9b9e3a2ddd26c320ca
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "23844813"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="17789-103">Was sind die Sonderzeichen Einschränkungen in Teams Richtlinien?</span><span class="sxs-lookup"><span data-stu-id="17789-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="17789-104">**Erstellen oder Bearbeiten von Richtlinien (für messaging, Besprechungen, usw.), die den Namen in der Microsoft-Teams und Skype für Business Admin Center ein Sonderzeichen aufweisen.**</span><span class="sxs-lookup"><span data-stu-id="17789-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams and Skype for Business Admin Center.**</span></span> 

<span data-ttu-id="17789-105">Wenn Sie ein Richtliniennamen Sonderzeichen enthält, werden Sie bei der Verwaltung diese Richtlinien in der Microsoft-Teams und Skype für Business Admin Center eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="17789-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams and Skype for Business Admin Center.</span></span> <span data-ttu-id="17789-106">**Daher wird dringend empfohlen, Richtliniennamen keine Sonderzeichen enthalten**.</span><span class="sxs-lookup"><span data-stu-id="17789-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="17789-107">Richtliniennamen, die von PowerShell für Besprechungen und messaging in Teams können Sonderzeichen wie haben erstellt wurden @, #, $.</span><span class="sxs-lookup"><span data-stu-id="17789-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="17789-108">Jedoch, wenn Sie die Richtlinie in der Microsoft-Teams und Skype für Business Admin Center ändern möchte, Sie kann nicht zu werden.</span><span class="sxs-lookup"><span data-stu-id="17789-108">However, if you are wanting to make changes to the policy in the Microsoft Teams and Skype for Business Admin Center,you won't be able to.</span></span> 

<span data-ttu-id="17789-109">Wenn Sie eine Richtlinie mit Sonderzeichen haben, müssen Sie die Richtlinie mithilfe von Windows PowerShell (unbegrenzt) bearbeiten oder erstellen eine neue Richtlinie in der Microsoft-Teams und Skype für Business Admin Center mit denselben Einstellungen wie die alte Richtlinie und weisen Sie es der gleichen Grupe p von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="17789-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams and Skype for Business Admin Center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="17789-110">So entfernen Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="17789-110">To remove special characters</span></span>



<span data-ttu-id="17789-111">**Schritt 1: Stellen Sie eine Remoteverbindung mit PowerShell.** 
 [Einrichten des Computers für Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , falls Sie noch nicht getan haben.</span><span class="sxs-lookup"><span data-stu-id="17789-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="17789-112">**Schritt 2 – die Einstellungen für die alte Richtlinie erhalten möchten, und erfassen Sie die Ausgabe.**</span><span class="sxs-lookup"><span data-stu-id="17789-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="17789-113">In diesem Beispiel wird für eine [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) -Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="17789-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="17789-114">Die Schritte wäre für andere Richtlinientypen identisch, aber Sie müssen das richtige-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="17789-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="17789-115">**Schritt 3: Erstellen einer neuen Richtlinie.**</span><span class="sxs-lookup"><span data-stu-id="17789-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="17789-116">Sie können entweder die neue Richtlinie mit der gleichen Einstellung mit dem Microsoft-Teams und Skype für Business-Verwaltungskonsole oder PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="17789-116">You can either create the new policy with the same setting using the Microsoft Teams and Skype for Business Admin Center or PowerShell.</span></span>

<span data-ttu-id="17789-117">Mit dieser wird eine neue Richtlinie für Sie erstellen, aber Sie müssen die richtigen Einstellungen hinzufügen, indem Sie [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) anzeigen, und klicken Sie dann ausführen:</span><span class="sxs-lookup"><span data-stu-id="17789-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="17789-118">**Schritt 4: Zuweisen der Richtlinie.**</span><span class="sxs-lookup"><span data-stu-id="17789-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="17789-119">Finden Sie unter [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) für Weitere Informationen zu diesem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="17789-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="17789-120">**Schritt 5: Löschen Sie die alte Richtlinie.**</span><span class="sxs-lookup"><span data-stu-id="17789-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="17789-121">Dadurch wird die alte Richtlinie mit Sonderzeichen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="17789-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="17789-122">Finden Sie unter [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) für Weitere Informationen zu diesem Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="17789-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="17789-123">Wenn dieser Befehl erfolgreich ist wird, sind Sie fertig.</span><span class="sxs-lookup"><span data-stu-id="17789-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="17789-124">Wenn Sie der oben aufgeführten Befehl einen Fehler zurückgibt, ist es, da die alte Richtlinie Benutzern zugewiesen ist, Sie ausführen, um alle zugewiesenen Benutzer aus der Richtlinie zu entfernen müssen:</span><span class="sxs-lookup"><span data-stu-id="17789-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="17789-125">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="17789-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="17789-p105">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="17789-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="17789-129">Warum müssen Sie Office 365 PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="17789-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="17789-130">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="17789-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="17789-p106">Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:</span><span class="sxs-lookup"><span data-stu-id="17789-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="17789-133">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="17789-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="17789-134">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="17789-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="17789-135">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="17789-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="17789-136">Das Windows PowerShell-Modul für Skype für Business Online können Sie eine remote Windows PowerShell-Sitzung zu erstellen, die mit Skype für Business Online und Microsoft-Teams, eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="17789-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="17789-137">Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="17789-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
### <a name="related-topics"></a><span data-ttu-id="17789-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="17789-138">Related topics</span></span>
