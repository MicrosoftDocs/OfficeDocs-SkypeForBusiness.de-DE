---
title: Einschränkungen für Sonderzeichen in Teams-Richtlinien
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Sehen Sie sich die Probleme mit Sonderzeichen in den Namen der Richtlinien an, und was Sie tun können, um Sie zu beheben.
ms.openlocfilehash: 899cffa45bc5ec7a36339e89e3cb97e35e6e4507
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814714"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="f044f-103">Welche Beschränkungen gelten für Sonderzeichen in den Microsoft Teams-Richtlinien?</span><span class="sxs-lookup"><span data-stu-id="f044f-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="f044f-104">**Sie können keine Richtlinien (für Nachrichten, Besprechungen usw.) erstellen oder bearbeiten, die im Namen des Microsoft Teams admin Centers ein Sonderzeichen enthalten**.</span><span class="sxs-lookup"><span data-stu-id="f044f-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="f044f-105">Wenn ein Richtlinienname Sonderzeichen enthält, sind Sie im Microsoft Teams Admin Center auf die Verwaltung dieser Richtlinien limitiert.</span><span class="sxs-lookup"><span data-stu-id="f044f-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f044f-106">Daher **wird nachdrücklich empfohlen, dass Richtliniennamen keine Sonderzeichen enthalten**.</span><span class="sxs-lookup"><span data-stu-id="f044f-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="f044f-107">Richtliniennamen, die mit PowerShell für Besprechungen und Nachrichten in Teams erstellt wurden, können Sonderzeichen wie @, #, $ aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f044f-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="f044f-108">Wenn Sie jedoch Änderungen an der Richtlinie im Microsoft Teams Admin Center vornehmen möchten, ist dies nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="f044f-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="f044f-109">Wenn Sie über eine Richtlinie mit Sonderzeichen verfügen, müssen Sie entweder die Richtlinie mit Windows PowerShell (für immer) bearbeiten oder eine neue Richtlinie im Microsoft Teams Admin Center mit den gleichen Einstellungen wie die alte Richtlinie erstellen und der gleichen Benutzergruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f044f-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="f044f-110">So entfernen Sie Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="f044f-110">To remove special characters</span></span>

<span data-ttu-id="f044f-111">**Schritt 1: Erstellen einer Remoteverbindung mit PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f044f-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="f044f-112">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="f044f-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="f044f-113">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="f044f-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```PowerShell
 Import-Module -Name MicrosoftTeams
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="f044f-114">**Schritt 2: Abrufen der Einstellungen für die alte Richtlinie und Aufzeichnen der Ausgabe.**</span><span class="sxs-lookup"><span data-stu-id="f044f-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="f044f-115">In diesem Beispiel handelt es sich um eine [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f044f-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="f044f-116">Die Schritte wären für andere Richtlinientypen identisch, aber Sie müssen das richtige Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="f044f-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="f044f-117">**Schritt 3 – Erstellen einer neuen Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="f044f-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="f044f-118">Sie können entweder die neue Richtlinie mit der gleichen Einstellung erstellen, indem Sie das Microsoft Teams Admin Center oder PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="f044f-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="f044f-119">Wenn Sie dies ausführen, wird eine neue Richtlinie für Sie erstellt, aber Sie müssen die richtigen Einstellungen hinzufügen, indem Sie [CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) anzeigen und dann ausführen:</span><span class="sxs-lookup"><span data-stu-id="f044f-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="f044f-120">**Schritt 4: Zuweisen der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="f044f-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="f044f-121">Weitere Informationen zu diesem Cmdlet finden Sie unter [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f044f-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="f044f-122">**Schritt 5: Löschen der alten Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="f044f-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="f044f-123">Dadurch wird die alte Richtlinie mit den Sonderzeichen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f044f-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="f044f-124">Weitere Informationen zu diesem Cmdlet finden Sie unter [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f044f-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="f044f-125">Wenn dieser Befehl erfolgreich ausgeführt wird, sind Sie fertig.</span><span class="sxs-lookup"><span data-stu-id="f044f-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="f044f-126">Wenn der obige Befehl einen Fehler zurückgibt, liegt dies daran, dass die alte Richtlinie Benutzern zugewiesen ist, damit Sie alle zugewiesenen Benutzer aus der Richtlinie entfernen müssen:</span><span class="sxs-lookup"><span data-stu-id="f044f-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f044f-127">Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?</span><span class="sxs-lookup"><span data-stu-id="f044f-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="f044f-128">Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f044f-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f044f-129">Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe einer zentralen Verwaltungsstelle verwalten, die Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f044f-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f044f-130">Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f044f-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f044f-131">Warum müssen Sie Office 365 PowerShell verwenden?</span><span class="sxs-lookup"><span data-stu-id="f044f-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f044f-132">Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f044f-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f044f-133">Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f044f-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="f044f-134">Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="f044f-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="f044f-135">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f044f-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="f044f-136">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f044f-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f044f-137">Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben</span><span class="sxs-lookup"><span data-stu-id="f044f-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f044f-138">Mit dem Windows PowerShell-Modul für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, die eine Verbindung mit Skype for Business Online und Microsoft Teams herstellt.</span><span class="sxs-lookup"><span data-stu-id="f044f-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="f044f-139">Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f044f-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

