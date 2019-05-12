---
title: Sperren oder Entsperren einer Benutzer-PIN in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Zusammenfassung: Sperren Sie oder Entsperren Sie eines Benutzers einwahlkonferenzen PIN für Skype für Business Server.'
ms.openlocfilehash: 36d25ad681136a88953535a902ef1d3580ff7a1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919900"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="da5dc-103">Sperren oder Entsperren einer Benutzer-PIN in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="da5dc-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="da5dc-104">**Zusammenfassung:** Sperren Sie oder Entsperren Sie eines Benutzers einwahlkonferenzen PIN für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="da5dc-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="da5dc-105">Sie können Sperren oder Entsperren der PIN eines Benutzers aus dem Abschnitt **Benutzer** Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="da5dc-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="da5dc-106">So sperren Sie PIN eines Benutzers in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="da5dc-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="da5dc-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="da5dc-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="da5dc-108">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="da5dc-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="da5dc-109">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="da5dc-110">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="da5dc-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="da5dc-111">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="da5dc-112">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="da5dc-113">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="da5dc-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="da5dc-114">a.</span><span class="sxs-lookup"><span data-stu-id="da5dc-114">a.</span></span> <span data-ttu-id="da5dc-115">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="da5dc-116">b.</span><span class="sxs-lookup"><span data-stu-id="da5dc-116">b.</span></span> <span data-ttu-id="da5dc-117">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="da5dc-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="da5dc-118">c.</span><span class="sxs-lookup"><span data-stu-id="da5dc-118">c.</span></span> <span data-ttu-id="da5dc-119">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="da5dc-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="da5dc-120">d.</span><span class="sxs-lookup"><span data-stu-id="da5dc-120">d.</span></span> <span data-ttu-id="da5dc-121">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="da5dc-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="da5dc-122">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="da5dc-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="da5dc-123">e.</span><span class="sxs-lookup"><span data-stu-id="da5dc-123">e.</span></span> <span data-ttu-id="da5dc-124">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-124">Click **Find**.</span></span>
    
   <span data-ttu-id="da5dc-125">f.</span><span class="sxs-lookup"><span data-stu-id="da5dc-125">f.</span></span> <span data-ttu-id="da5dc-126">Klicken Sie auf den Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN sperren**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="da5dc-127">So entsperren Sie die PIN eines Benutzers in Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="da5dc-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="da5dc-128">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="da5dc-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="da5dc-129">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="da5dc-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="da5dc-130">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="da5dc-131">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="da5dc-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="da5dc-132">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="da5dc-133">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="da5dc-134">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="da5dc-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="da5dc-135">a.</span><span class="sxs-lookup"><span data-stu-id="da5dc-135">a.</span></span> <span data-ttu-id="da5dc-136">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="da5dc-137">b.</span><span class="sxs-lookup"><span data-stu-id="da5dc-137">b.</span></span> <span data-ttu-id="da5dc-138">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="da5dc-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="da5dc-139">c.</span><span class="sxs-lookup"><span data-stu-id="da5dc-139">c.</span></span> <span data-ttu-id="da5dc-140">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="da5dc-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="da5dc-141">d.</span><span class="sxs-lookup"><span data-stu-id="da5dc-141">d.</span></span> <span data-ttu-id="da5dc-142">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="da5dc-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="da5dc-143">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="da5dc-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="da5dc-144">e.</span><span class="sxs-lookup"><span data-stu-id="da5dc-144">e.</span></span> <span data-ttu-id="da5dc-145">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-145">Click **Find**.</span></span>
    
   <span data-ttu-id="da5dc-146">f.</span><span class="sxs-lookup"><span data-stu-id="da5dc-146">f.</span></span> <span data-ttu-id="da5dc-147">Klicken Sie auf den Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN entsperren**.</span><span class="sxs-lookup"><span data-stu-id="da5dc-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="da5dc-148">Sperren und entsperren Benutzer-PINs mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="da5dc-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="da5dc-149">Sie können Sperren und Entsperren von Benutzer-PINs mithilfe von Windows PowerShell und den Cmdlets Lock-CsClientPin und Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="da5dc-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="da5dc-150">Sie können diese Cmdlets entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="da5dc-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="da5dc-151">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="da5dc-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="da5dc-152">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="da5dc-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="da5dc-153">So sperren Sie die PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="da5dc-153">To lock a user PIN</span></span>

- <span data-ttu-id="da5dc-154">Verwenden Sie das Lock-CsClientPin-Cmdlet, um die PIN eines Benutzers zu sperren.</span><span class="sxs-lookup"><span data-stu-id="da5dc-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="da5dc-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="da5dc-155">For example:</span></span>
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="da5dc-156">So entsperren Sie die PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="da5dc-156">To unlock a user PIN</span></span>

- <span data-ttu-id="da5dc-157">Verwenden Sie zum Entsperren der PIN eines Benutzers mit dem Cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="da5dc-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="da5dc-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="da5dc-158">For example:</span></span>
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="da5dc-159">Weitere Informationen finden Sie im Hilfethema für die Cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) und [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="da5dc-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
