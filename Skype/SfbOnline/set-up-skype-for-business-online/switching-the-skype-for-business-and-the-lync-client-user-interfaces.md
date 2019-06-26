---
title: Wechseln zwischen den Client-Benutzeroberflächen von Skype for Business- und Lync
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 '
ms.openlocfilehash: 2788799f5125aab63938241d737eade25f6cd61a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221509"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a><span data-ttu-id="9d1ec-103">Wechseln zwischen den Client-Benutzeroberflächen von Skype for Business- und Lync</span><span class="sxs-lookup"><span data-stu-id="9d1ec-103">Switching between the Skype for Business and the Lync client user interfaces</span></span>

<span data-ttu-id="9d1ec-104">Für Skype for Business Online-Organisationen können Sie die Remote-PowerShell in Office 365 verwenden, um Skype for Business-Benutzern die Nutzung der Skype for Business-Client-oder der Skype for Business (lync)-Client-Benutzeroberfläche zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-104">For Skype for Business Online organizations, you can use the Remote PowerShell in Office 365 to enable your Skype for Business users to use the Skype for Business client or the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="9d1ec-105">Die Standardeinstellung ist, dass Benutzer die Skype for Business-Client-Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-105">The default setting is for users to use the Skype for Business client user interface.</span></span> <span data-ttu-id="9d1ec-106">Wenn Sie die lync-Clientumgebung lieber verwenden möchten, können Sie das erste Start Clientverhalten verwalten, um die lync-Benutzeroberfläche anzuzeigen, indem Sie die Schritte weiter unten in diesem Thema ausführen.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-106">If you'd prefer to use the Lync client experience, you can manage the first launch client behavior to display the Lync user interface by following the steps later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9d1ec-p102">Die Lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion und stellen Sie sicher, dass sie nicht mit der Zahl 16 beginnt, z. B.: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p102">The Lync 2013 client experience isn't an option for Skype for Business 2016 client versions. Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
> [!TIP]
> <span data-ttu-id="9d1ec-109">Wenn Sie die Benutzeroberfläche problemlos wechseln und die manuellen Schritte nicht ausführen möchten, lesen Sie das [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) für ein PowerShell-Skript, um es einfacher zu machen.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-109">If you want to easily switch the user interface and don't want to do the manual steps, see the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) for a PowerShell script to make it easier.</span></span>
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a><span data-ttu-id="9d1ec-110">Wechseln der Skype for Business-Benutzeroberfläche für Benutzer</span><span class="sxs-lookup"><span data-stu-id="9d1ec-110">Switching the Skype for Business user interface for users</span></span>

<span data-ttu-id="9d1ec-p103">Mit dem Windows PowerShell-Modul für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, die eine Verbindung zu Skype for Business Online herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Weitere Informationen finden Sie unter[Konfigurieren Ihres Computers für die Verwaltung von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=534539).</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p103">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). For other information, see [Configuring your computer for Skype for Business Online management](https://go.microsoft.com/fwlink/?LinkId=534539).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9d1ec-p104">Die  _Global_-Richtlinieneinstellungen für den Wechsel der Benutzeroberfläche, wird bei einem Benutzer, der bereits über eine benutzerdefinierter Richtlinie verfügt, nicht eingerichtet . Sie müssen für den Wechsel der Benutzeroberfläche für jeden Benutzer mit benutzerdefinierter Richtlinie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p104">The  _Global_ policy setting for switching the user interface won't be applied to a user that already has a custom policy applied. To be able to change the user interface, you will need to run the following for each user that has a custom policy applied:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> <span data-ttu-id="9d1ec-116">Die  _ClientPolicyEnableSkypeUI_-Richtlinie ersetzt die vorhandene benutzerdefinierte Richtlinie des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-116">The  _ClientPolicyEnableSkypeUI_ policy will replace the existing custom policy setting for the user.</span></span>
  
<span data-ttu-id="9d1ec-117">Öffnen Sie Remote-PowerShell, um für alle Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-117">To enable all of the users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="9d1ec-118">Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-118">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
<span data-ttu-id="9d1ec-120">Öffnen Sie Remote-PowerShell, um für alle Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-120">To enable all of the users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span> 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="9d1ec-121">Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-121">If you set the policy right, you will see:</span></span>
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
<span data-ttu-id="9d1ec-123">Öffnen Sie Remote-PowerShell, um für einen einzelnen Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-123">To allow a single user in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

<span data-ttu-id="9d1ec-124">Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-124">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - Benutzeroberfläche aktivieren](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
<span data-ttu-id="9d1ec-126">Öffnen Sie Remote-PowerShell, um für einen einzelnen Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-126">To allow a single user in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

<span data-ttu-id="9d1ec-127">Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-127">If you set the policy right, you will see:</span></span>
  
![Skype for Business Online - Benutzeroberfläche deaktiviert](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
<span data-ttu-id="9d1ec-129">Öffnen Sie Remote-PowerShell, um für mehrere Benutzer Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-129">To allow multiple users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  

```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="9d1ec-130">Öffnen Sie Remote-PowerShell, um für mehrere Benutzer Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-130">To allow multiple users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

<span data-ttu-id="9d1ec-131">Öffnen Sie Remote-PowerShell, um für eine Benutzergruppe Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-131">To allow a group of users in your organization to use the Skype for Business client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

<span data-ttu-id="9d1ec-132">Öffnen Sie Remote-PowerShell, um für eine Benutzergruppe Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-132">To allow a group of users in your organization to use the Skype for Business (Lync) client, open the Remote PowerShell and type the following:</span></span>
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  <span data-ttu-id="9d1ec-p105">Der Benutzername ist der Name des Benutzerkontos, dem die Richtlinie zugeordnet sein muss. Der Name des Benutzerkontos kann in einem der folgenden Formate eingegeben werden:>  SIP-Adresse des Benutzers>  Benutzerprinzipalname (UPN) des Benutzers>  Domäne\\Benutzername des Benutzers>  Anzeigename des Active Directory des Benutzers</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p105">The user's name is the name of the user's account that the policy should be assigned to. The user's account name can be entered in one of the following formats:>  SIP address of the user>  User Principal name (UPN) of the user>  Domain\\username of the user>  Active Directory display name of the user</span></span>
  
[<span data-ttu-id="9d1ec-135">Verwenden von Windows PowerShell zum Verwalten von Lync Online</span><span class="sxs-lookup"><span data-stu-id="9d1ec-135">Using Windows PowerShell to manage Lync Online</span></span>](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a><span data-ttu-id="9d1ec-136">Richtlinieneinstellungen für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d1ec-136">Skype for Business Online policy settings</span></span>

<span data-ttu-id="9d1ec-137">Diese Tabelle zeigt die Installationsoptionen für Benutzer, denen die Richtlinie zum ersten Mal zugewiesen wird:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-137">This table shows the user experience when the policy is first applied to users:</span></span>
  
|<span data-ttu-id="9d1ec-138">**Administrator-Richtlinieneinstellung**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-138">**Admin policy setting**</span></span>|<span data-ttu-id="9d1ec-139">**Angezeigte Benutzeroberfläche**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-139">**User interface displayed**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d1ec-140">Die Richtlinie ist nicht eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-140">The policy isn't set.</span></span> |<span data-ttu-id="9d1ec-141">Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-141">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|<span data-ttu-id="9d1ec-142">Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-142">The user will continue using the Skype for Business client user interface.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|<span data-ttu-id="9d1ec-143">Der Benutzer wird aufgefordert, zur Client-Benutzeroberfläche von Skype for Business (lync) zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-143">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="9d1ec-144">Sie können den Wechsel später ausführen.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-144">They can switch later.</span></span>|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|<span data-ttu-id="9d1ec-145">Der Benutzer wird die Skype for Business-Client-Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-145">The user will be using the Skype for Business client user interface.</span></span> |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|<span data-ttu-id="9d1ec-146">Der Benutzer wird aufgefordert, zur Client-Benutzeroberfläche von Skype for Business (lync) zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-146">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span> <span data-ttu-id="9d1ec-147">Ein Administrator kann die Einstellung in Zukunft ändern, damit Benutzer auf die Client-Benutzeroberfläche von Skype for Business wechseln können.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-147">An admin can change the setting in the future that will switch them to the Skype for Business client user interface.</span></span> |
   
<span data-ttu-id="9d1ec-148">Diese Tabelle zeigt die Installationsoptionen für Benutzer, bei denen die Richtlinie geändert wird:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-148">This table shows the user experience when the policy is changed:</span></span>
  
|<span data-ttu-id="9d1ec-149">**Administrator-Richtlinieneinstellung**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-149">**Admin policy setting**</span></span>|<span data-ttu-id="9d1ec-150">**Benutzeroberfläche von Skype for Business (Lync)**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-150">**Skype for Business (Lync) user interface**</span></span>|<span data-ttu-id="9d1ec-151">**Skype for Business-Benutzeroberfläche**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-151">**Skype for Business user interface**</span></span>|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|<span data-ttu-id="9d1ec-152">Der Benutzer wird aufgefordert, zur Skype for Business-Client-Benutzeroberfläche zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-152">The user will be asked to switch to the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="9d1ec-153">Der Benutzer wird weiterhin die Skype for Business-Client-Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-153">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|<span data-ttu-id="9d1ec-154">Der Benutzer wird weiterhin die Skype for Business (lync)-Schnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-154">The user will continue to use the Skype for Business (Lync) interface.</span></span>  <br/> |<span data-ttu-id="9d1ec-155">Der Benutzer wird aufgefordert, zur Client-Benutzeroberfläche von Skype for Business (lync) zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-155">The user will be asked to switch to the Skype for Business (Lync) client user interface.</span></span>  <br/> |
|<span data-ttu-id="9d1ec-156">Die Richtlinie ist nicht eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-156">The policy isn't set.</span></span>  <br/> |<span data-ttu-id="9d1ec-157">Benutzer können die Client-Benutzeroberfläche von Skype for Business (lync) nie sehen, wenn die Richtlinie nicht festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-157">Users will never see the Skype for Business (Lync) client user interface if the policy is not set.</span></span> <span data-ttu-id="9d1ec-158">Sie werden immer die Client-Benutzeroberfläche von Skype for Business verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-158">They will always use the Skype for Business client user interface.</span></span>  <br/> |<span data-ttu-id="9d1ec-159">Der Benutzer wird weiterhin die Skype for Business-Client-Benutzeroberfläche verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-159">The user will continue to use the Skype for Business client user interface.</span></span>  <br/> |
   
<span data-ttu-id="9d1ec-p109">Diese Tabelle enthält alle verfügbaren benutzerdefinierten Online-Richtlinien. Es gibt neue Richtlinien, die den Administratoren beim Wechsel zwischen den EnableSkypeUI-Flags mehr Flexibilität bei der Nutzung alter benutzerdefinierter Richtlinien bieten sollen. Mit den obigen Cmdlets können Sie Ihren Benutzern eine der nachstehenden Richtlinien übergeben.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p109">This table shows all the Online custom policies available. There are new policies created to give admins flexibility in retaining the old custom policy while switching between the EnableSkypeUI flags. Please use the cmdlets from above to grant one of the below policies to your users.</span></span>
  
|<span data-ttu-id="9d1ec-163">**Richtlinienname**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-163">**Policy name**</span></span>|<span data-ttu-id="9d1ec-164">**EnableSkypeUI**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-164">**EnableSkypeUI**</span></span>|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |<span data-ttu-id="9d1ec-165">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-165">False</span></span>|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |<span data-ttu-id="9d1ec-166">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-166">False</span></span>|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |<span data-ttu-id="9d1ec-167">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-167">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |<span data-ttu-id="9d1ec-168">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-168">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |<span data-ttu-id="9d1ec-169">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-169">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|<span data-ttu-id="9d1ec-170">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-170">False</span></span>|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |<span data-ttu-id="9d1ec-171">Falsch</span><span class="sxs-lookup"><span data-stu-id="9d1ec-171">False</span></span>|

   
<span data-ttu-id="9d1ec-172">Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-172">To get started with Windows PowerShell, see these topics:</span></span>
  
- [<span data-ttu-id="9d1ec-173">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="9d1ec-173">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [<span data-ttu-id="9d1ec-174">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9d1ec-174">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a><span data-ttu-id="9d1ec-175">Verhalten beim ersten Start des Clients</span><span class="sxs-lookup"><span data-stu-id="9d1ec-175">First launch client behaviors</span></span>

<span data-ttu-id="9d1ec-176">Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie standardmäßig immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie die Clientrichtlinie auf die lync-Clientumgebung (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) festlegen zuvor.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-176">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the client policy to the Lync client experience (`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) as described previously.</span></span> <span data-ttu-id="9d1ec-177">Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-177">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="9d1ec-178">Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-178">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="9d1ec-179">Führen Sie die weiter oben in diesem Thema dargestellten Schritte aus und bestätigen Sie, dass die Clientrichtlinie für die Deaktivierung der Skype for Business-Benutzeroberfläche festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-179">Follow the steps earlier in this topic and confirm that the client policy is set to disable the Skype for Business user interface.</span></span>
    
2. <span data-ttu-id="9d1ec-p111">Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p111">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="9d1ec-183">Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** einen neuen **Binärwert**.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-183">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="9d1ec-184">Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-184">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="9d1ec-185">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-185">The key should look like the following:</span></span>
    
    <span data-ttu-id="9d1ec-186">[HKEY_CURRENT_USER\\-\\Software\\Microsoft\\Office lync]</span><span class="sxs-lookup"><span data-stu-id="9d1ec-186">[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]</span></span>
    
    <span data-ttu-id="9d1ec-187">"CanSharePptInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="9d1ec-187">"CanSharePptInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="9d1ec-188">"CanShareOneNoteInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="9d1ec-188">"CanShareOneNoteInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="9d1ec-189">"CanAppShareInCollab" = DWORD: 00000001</span><span class="sxs-lookup"><span data-stu-id="9d1ec-189">"CanAppShareInCollab"=dword:00000001</span></span>
    
    <span data-ttu-id="9d1ec-190">"EnableSkypeUI" = Hex: 00, 00, 00, 00</span><span class="sxs-lookup"><span data-stu-id="9d1ec-190">"EnableSkypeUI"=hex:00,00,00,00</span></span>
    
<span data-ttu-id="9d1ec-191">Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-191">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="9d1ec-192">Steuern der Anzeige des Lernprogramms auf der Willkommenseite</span><span class="sxs-lookup"><span data-stu-id="9d1ec-192">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="9d1ec-193">Wenn Benutzer den Skype for Business-Client öffnen, besteht das Standardverhalten darin, einen Begrüßungsbildschirm anzuzeigen, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-193">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="9d1ec-194">Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-194">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="9d1ec-p113">Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** einen neuen **DWORD-(32-Bit-)Wert**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p113">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="9d1ec-197">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-197">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="9d1ec-198">Ausschalten des Client-Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="9d1ec-198">Turn off the client tutorial</span></span>

<span data-ttu-id="9d1ec-199">Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-199">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="9d1ec-p114">Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** einen neuen **DWORD-(32-Bit-)Wert**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p114">In the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="9d1ec-202">Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-202">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="9d1ec-203">Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="9d1ec-203">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="9d1ec-p115">Die Aktualisierung der Registrierung zur Anzeige der Lync-Clientumgebung beim ersten Start des Skype for Business-Clients durch einen Benutzer sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>
  
<span data-ttu-id="9d1ec-p116">Das nachstehende Verfahren beschreibt, wie die Registrierung geändert werden kann, damit die Lync-Clientumgebung beim ersten Start von Skype for Business auf dem Computer des Benutzers angezeigt wird. Sie haben damit auch die Möglichkeit, die Registrierung für die Deaktivierung des Lernprogramms auf der Willkommensseite zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
 <span data-ttu-id="9d1ec-209">**So erstellen Sie das Gruppenrichtlinienobjekt**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-209">**To create the GPO**</span></span>
  
1. <span data-ttu-id="9d1ec-210">Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-210">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="9d1ec-211">Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="9d1ec-211">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="9d1ec-212">Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** und wählen Sie im Menü **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-212">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="9d1ec-213">Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das Gruppenrichtlinienobjekt (z. B.MakeLyncDefaultUI) ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-213">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="9d1ec-214">Klicken Sie mit der rechten Maustaste auf das soeben erstellte neue Gruppenrichtlinienobjekt und wählen Sie dann im Menü **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-214">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="9d1ec-215">Im **Gruppenrichtlinienverwaltungs-Editor** erweitern Sie **Benutzerkonfiguration**, dann **Einstellungen** und dann **Windows-Einstellungen** und wählen Sie anschließend den Knoten **Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-215">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="9d1ec-216">Klicken Sie mit der rechten Maustaste auf den Knoten **Registrierung** und wählen Sie dann **Neu** > **Registrierungselement** aus.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-216">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="9d1ec-217">Aktualisieren Sie im Dialogfeld **Neue Registrierungseigenschaften** die folgenden Angaben:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-217">On the **New Registry Properties** dialog, update the following:</span></span>
    
|<span data-ttu-id="9d1ec-218">**Feld**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-218">**Field**</span></span>|<span data-ttu-id="9d1ec-219">**Auszuwählender oder einzugebender Wert**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-219">**Value to select or enter**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9d1ec-220">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-220">**Action**</span></span> <br/> |<span data-ttu-id="9d1ec-221">**Erstellen**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-221">**Create**</span></span> <br/> |
|<span data-ttu-id="9d1ec-222">**Struktur**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-222">**Hive**</span></span> <br/> | <span data-ttu-id="9d1ec-223">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="9d1ec-223">HKEY_CURRENT_USER</span></span> <br/> |
|<span data-ttu-id="9d1ec-224">**Schlüsselpfad**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-224">**Key Path**</span></span> <br/> |<span data-ttu-id="9d1ec-225">Software\\Microsoft\\Office\\lync</span><span class="sxs-lookup"><span data-stu-id="9d1ec-225">Software\\Microsoft\\Office\\Lync</span></span>  <br/> |
|<span data-ttu-id="9d1ec-226">**Wertname**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-226">**Value name**</span></span> <br/> |<span data-ttu-id="9d1ec-227">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="9d1ec-227">EnableSkypeUI</span></span>  <br/> |
|<span data-ttu-id="9d1ec-228">**Werttyp**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-228">**Value type**</span></span> <br/> |<span data-ttu-id="9d1ec-229">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="9d1ec-229">REG_BINARY</span></span>  <br/> |
|<span data-ttu-id="9d1ec-230">**Wertdaten**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-230">**Value data**</span></span> <br/> |<span data-ttu-id="9d1ec-231">00000000</span><span class="sxs-lookup"><span data-stu-id="9d1ec-231">00000000</span></span>  <br/> |
   
<span data-ttu-id="9d1ec-232">Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-232">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="9d1ec-233">Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-233">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
 <span data-ttu-id="9d1ec-234">**So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-234">**To use the GPO to assign the policy**</span></span>
  
1. <span data-ttu-id="9d1ec-235">Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-235">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="9d1ec-236">Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-236">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="9d1ec-237">Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-237">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="9d1ec-238">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-238">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="9d1ec-p117">Die Meldung „Richtlinie wird aktualisiert..." wird angezeigt, während das GPO angewendet wird. Wenn der Vorgang abgeschlossen ist, erscheint die Meldung „Die Aktualisierung der Benutzerrichtlinie wurde abgeschlossen".</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>
    
4. <span data-ttu-id="9d1ec-241">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="9d1ec-241">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="9d1ec-242">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="9d1ec-242">**gpresult /r**</span></span>
    
    <span data-ttu-id="9d1ec-243">Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9d1ec-243">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="9d1ec-p118">Um festzustellen, ob das GPO die Registrierung auf dem Computer des Benutzers erfolgreich aktualisiert hat, überprüfen Sie die Registrierung entsprechend. Öffnen Sie dazu den Registrierungs-Editor und navigieren Sie zum Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Wenn das GPO die Registrierung erfolgreich aktualisiert hat, erscheint unter „EnableSkypeUI" der Wert „0".</span><span class="sxs-lookup"><span data-stu-id="9d1ec-p118">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9d1ec-247">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9d1ec-247">Related topics</span></span>
[<span data-ttu-id="9d1ec-248">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9d1ec-248">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="9d1ec-249">Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="9d1ec-249">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
