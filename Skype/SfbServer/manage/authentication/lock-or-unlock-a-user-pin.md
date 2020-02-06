---
title: Sperren oder Entsperren einer Benutzer-PIN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Zusammenfassung: Sperren oder Entsperren der PIN für Einwahlkonferenzen eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: e9a5e59497a4cb771d0b20cef55b09b26817216d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818787"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a><span data-ttu-id="7e28b-103">Sperren oder Entsperren einer Benutzer-PIN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7e28b-103">Lock or unlock a user PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="7e28b-104">**Zusammenfassung:** Sperren oder Entsperren der PIN für Einwahlkonferenzen eines Benutzers für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7e28b-104">**Summary:** Lock or unlock a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="7e28b-105">Sie können die PIN eines Benutzers über den Abschnitt **Benutzer** der Skype for Business Server-Systemsteuerung sperren oder entsperren.</span><span class="sxs-lookup"><span data-stu-id="7e28b-105">You can lock or unlock a user's PIN from the **Users** section of Skype for Business Server Control Panel.</span></span>
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7e28b-106">So sperren Sie die PIN eines Benutzers in der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="7e28b-106">To lock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7e28b-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e28b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e28b-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e28b-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7e28b-109">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-109">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e28b-110">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="7e28b-110">Use one of the following methods to locate a user:</span></span>
    
    - <span data-ttu-id="7e28b-111">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
    - <span data-ttu-id="7e28b-112">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-112">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="7e28b-113">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="7e28b-113">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="7e28b-114">a.</span><span class="sxs-lookup"><span data-stu-id="7e28b-114">a.</span></span> <span data-ttu-id="7e28b-115">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-115">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="7e28b-116">b.</span><span class="sxs-lookup"><span data-stu-id="7e28b-116">b.</span></span> <span data-ttu-id="7e28b-117">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7e28b-117">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="7e28b-118">c.</span><span class="sxs-lookup"><span data-stu-id="7e28b-118">c.</span></span> <span data-ttu-id="7e28b-119">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="7e28b-119">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="7e28b-120">d.</span><span class="sxs-lookup"><span data-stu-id="7e28b-120">d.</span></span> <span data-ttu-id="7e28b-121">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="7e28b-121">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7e28b-122">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7e28b-122">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="7e28b-123">e.</span><span class="sxs-lookup"><span data-stu-id="7e28b-123">e.</span></span> <span data-ttu-id="7e28b-124">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-124">Click **Find**.</span></span>
    
   <span data-ttu-id="7e28b-125">f.</span><span class="sxs-lookup"><span data-stu-id="7e28b-125">f.</span></span> <span data-ttu-id="7e28b-126">Klicken Sie auf den Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN sperren**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-126">Click the user, click **Action**, and then click **Lock PIN**.</span></span>
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a><span data-ttu-id="7e28b-127">So entsperren Sie die PIN eines Benutzers in der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="7e28b-127">To unlock a user's PIN in Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7e28b-128">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="7e28b-128">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="7e28b-129">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7e28b-129">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="7e28b-130">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-130">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="7e28b-131">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="7e28b-131">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="7e28b-132">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-132">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="7e28b-133">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-133">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="7e28b-134">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="7e28b-134">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="7e28b-135">a.</span><span class="sxs-lookup"><span data-stu-id="7e28b-135">a.</span></span> <span data-ttu-id="7e28b-136">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-136">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="7e28b-137">b.</span><span class="sxs-lookup"><span data-stu-id="7e28b-137">b.</span></span> <span data-ttu-id="7e28b-138">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7e28b-138">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="7e28b-139">c.</span><span class="sxs-lookup"><span data-stu-id="7e28b-139">c.</span></span> <span data-ttu-id="7e28b-140">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="7e28b-140">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="7e28b-141">d.</span><span class="sxs-lookup"><span data-stu-id="7e28b-141">d.</span></span> <span data-ttu-id="7e28b-142">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="7e28b-142">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7e28b-143">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="7e28b-143">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="7e28b-144">e.</span><span class="sxs-lookup"><span data-stu-id="7e28b-144">e.</span></span> <span data-ttu-id="7e28b-145">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-145">Click **Find**.</span></span>
    
   <span data-ttu-id="7e28b-146">f.</span><span class="sxs-lookup"><span data-stu-id="7e28b-146">f.</span></span> <span data-ttu-id="7e28b-147">Klicken Sie auf den Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN entsperren**.</span><span class="sxs-lookup"><span data-stu-id="7e28b-147">Click the user, click **Action**, and then click **Unlock PIN**.</span></span>
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7e28b-148">Sperren und Entsperren von Benutzer Pins mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7e28b-148">Locking and Unlocking User PINs by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7e28b-149">Sie können Benutzer Pins mithilfe von Windows PowerShell und den Cmdlets Lock-CsClientPin und Unlock-CsClientPin Sperren und entsperren.</span><span class="sxs-lookup"><span data-stu-id="7e28b-149">You can lock and unlock user PINs by using Windows PowerShell and the Lock-CsClientPin and Unlock-CsClientPin cmdlets.</span></span> <span data-ttu-id="7e28b-150">Sie können diese Cmdlets entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="7e28b-150">You can run these cmdlets either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7e28b-151">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="7e28b-151">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7e28b-152">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="7e28b-152">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-lock-a-user-pin"></a><span data-ttu-id="7e28b-153">So sperren Sie die PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="7e28b-153">To lock a user PIN</span></span>

- <span data-ttu-id="7e28b-154">Verwenden Sie das Cmdlet Lock-CsClientPin, um die PIN eines Benutzers zu sperren.</span><span class="sxs-lookup"><span data-stu-id="7e28b-154">To lock a user's PIN, use the Lock-CsClientPin cmdlet.</span></span> <span data-ttu-id="7e28b-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e28b-155">For example:</span></span>
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a><span data-ttu-id="7e28b-156">So entsperren Sie die PIN eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="7e28b-156">To unlock a user PIN</span></span>

- <span data-ttu-id="7e28b-157">Wenn Sie die PIN eines Benutzers entsperren möchten, verwenden Sie das Cmdlet Unlock-CsClientPin.</span><span class="sxs-lookup"><span data-stu-id="7e28b-157">To unlock a user's PIN, use the Unlock-CsClientPin cmdlet.</span></span> <span data-ttu-id="7e28b-158">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7e28b-158">For example:</span></span>
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

<span data-ttu-id="7e28b-159">Weitere Informationen finden Sie im Hilfethema zu den Cmdlets [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) und [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="7e28b-159">For more information, see the help topic for the [Lock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) and [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) cmdlets.</span></span>
