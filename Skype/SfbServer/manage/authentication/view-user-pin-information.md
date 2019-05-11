---
title: Benutzer anzeigen PIN-Informationen in Skype Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Zusammenfassung: Benutzer der PIN-Informationen in Skype Business Server anzeigen'
ms.openlocfilehash: a2e9d7d3e2341590a8eb6a4779bbb1a9c5c26227
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919367"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a><span data-ttu-id="a7959-103">Benutzer anzeigen PIN-Informationen in Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="a7959-103">View user PIN information in Skype for Business Server</span></span>
 
<span data-ttu-id="a7959-104">**Zusammenfassung:** Benutzer anzeigen PIN-Informationen in Skype Business Server.</span><span class="sxs-lookup"><span data-stu-id="a7959-104">**Summary:** View user PIN information in Skype for Business Server.</span></span>
  
<span data-ttu-id="a7959-105">Um eine Zugriffsnummer für Einwahl Konferenz als authentifizierter Benutzer teilzunehmen, erfordert einen Skype für Business Server-Benutzer mit Active Directory-Domänendienste (AD DS) Anmeldeinformationen eine persönliche Identifikationsnummer (PIN).</span><span class="sxs-lookup"><span data-stu-id="a7959-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="a7959-106">Sie können einen Benutzer-PIN-Informationen von Skype für Business Server-Systemsteuerung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7959-106">You can view a user's PIN information from Skype for Business Server Control Panel.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7959-107">Sie können Statusinformationen PIN, z. B., ob die PIN-Nummer festgelegt wurde oder wenn die PIN-Nummer der letzten Änderung anzeigen, aber nicht die aktuelle PIN anhand des PIN-Status angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a7959-107">You can view PIN status information such as whether the PIN has been set or when the PIN was last changed, but you cannot see the current PIN by looking at the PIN status.</span></span> <span data-ttu-id="a7959-108">Wenn ein Benutzer seine PIN verloren gegangen ist, können Sie es zurücksetzen, durch die Verfahren in [eines Benutzers einwahlkonferenzen in Skype für Business Server PIN festlegen](set-a-user-s-dial-in-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="a7959-108">If a user has lost their PIN, you can reset it by following the procedures in [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)</span></span>
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="a7959-109">Zum Anzeigen von PIN eines Benutzers in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a7959-109">To view a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a7959-110">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a7959-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a7959-111">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a7959-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="a7959-112">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="a7959-112">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="a7959-113">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="a7959-113">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="a7959-114">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="a7959-114">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="a7959-115">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="a7959-115">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="a7959-116">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="a7959-116">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="a7959-117">a.</span><span class="sxs-lookup"><span data-stu-id="a7959-117">a.</span></span> <span data-ttu-id="a7959-118">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7959-118">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="a7959-119">b.</span><span class="sxs-lookup"><span data-stu-id="a7959-119">b.</span></span> <span data-ttu-id="a7959-120">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a7959-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="a7959-121">c.</span><span class="sxs-lookup"><span data-stu-id="a7959-121">c.</span></span> <span data-ttu-id="a7959-122">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="a7959-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="a7959-123">d.</span><span class="sxs-lookup"><span data-stu-id="a7959-123">d.</span></span> <span data-ttu-id="a7959-124">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="a7959-124">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a7959-125">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="a7959-125">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="a7959-126">e.</span><span class="sxs-lookup"><span data-stu-id="a7959-126">e.</span></span> <span data-ttu-id="a7959-127">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="a7959-127">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a7959-p108">Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf **Aktion** und auf **PIN entsperren**.</span><span class="sxs-lookup"><span data-stu-id="a7959-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="a7959-130">Klicken Sie auf einen Benutzer in den Suchergebnissen und dann auf **Aktion** und auf **PIN-Status anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a7959-130">Click a user in the search results, click **Action**, and then click **View PIN status**.</span></span>
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a7959-131">Anzeigen von PIN-Informationen für Benutzer von mithilfe von Windows PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="a7959-131">Viewing User PIN Information by Using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="a7959-132">Sie können die PIN-Informationen für Benutzer mit dem Cmdlet „Get-CsClientPinInfo“ anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7959-132">You can view user PIN information by using the Get-CsClientPinInfo cmdlet.</span></span> <span data-ttu-id="a7959-133">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a7959-133">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a7959-134">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="a7959-134">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="a7959-135">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="a7959-135">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-view-user-pin-information"></a><span data-ttu-id="a7959-136">So zeigen Sie die PIN-Informationen von Benutzern an</span><span class="sxs-lookup"><span data-stu-id="a7959-136">To view user PIN information</span></span>

<span data-ttu-id="a7959-137">Zum Anzeigen von PIN-Informationen für einen Benutzer geben Sie einen Befehl ähnlich dem folgenden in der Skype für Business Server-Verwaltungsshell, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a7959-137">To view PIN information for a user, type a command similar to the following in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

<span data-ttu-id="a7959-138">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a7959-138">That will return information similar to this:</span></span>

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

<span data-ttu-id="a7959-139">Weitere Informationen finden Sie im Hilfethema zum [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a7959-139">For more information, see the help topic for the [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7959-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7959-140">See also</span></span>

[<span data-ttu-id="a7959-141">Einrichten eines Benutzers einwahlkonferenzen PIN in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a7959-141">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>](set-a-user-s-dial-in-conferencing-pin.md)
  
[<span data-ttu-id="a7959-142">Sperren oder Entsperren einer Benutzer-PIN in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="a7959-142">Lock or unlock a user PIN in Skype for Business Server</span></span>](lock-or-unlock-a-user-pin.md)
