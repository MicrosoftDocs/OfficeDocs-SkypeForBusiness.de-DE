---
title: Einrichten der PIN für Einwahlkonferenzen von Benutzern in Skype for Business Server
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
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Zusammenfassung: Einrichten der PIN für Einwahlkonferenzen eines Benutzers für Skype for Business Server.'
ms.openlocfilehash: eb025f069156dd54ba772dd866c09adc59d078eb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818737"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a><span data-ttu-id="55cb9-103">Einrichten der PIN für Einwahlkonferenzen von Benutzern in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="55cb9-103">Set a user's dial-in conferencing PIN in Skype for Business Server</span></span>
 
<span data-ttu-id="55cb9-104">**Zusammenfassung:** Die PIN für Einwahlkonferenzen eines Benutzers für Skype for Business Server festzulegen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-104">**Summary:** Set a user's dial-in conferencing PIN for Skype for Business Server.</span></span>
  
<span data-ttu-id="55cb9-105">Um an einer Einwahlkonferenz als authentifizierter Benutzer teilzunehmen, erfordert ein Skype for Business Server-Benutzer mit den Anmeldeinformationen für Active Directory-Domänendienste (AD DS) eine persönliche Identifikationsnummer (PIN).</span><span class="sxs-lookup"><span data-stu-id="55cb9-105">To join a dial-in conference as an authenticated user, a Skype for Business Server user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="55cb9-106">Wenn ein Benutzer die PIN für Einwahlkonferenzen vergisst oder die PIN nicht über Skype for Business Server festgesetzt hat, können Sie die PIN des Benutzers über die Skype for Business Server-Systemsteuerung festlegen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-106">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Skype for Business Server, you can set the user's PIN from Skype for Business Server Control Panel.</span></span> <span data-ttu-id="55cb9-107">Die PIN kann entweder automatisch generiert oder manuell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="55cb9-107">You can automatically generate the PIN or create one manually.</span></span>
  
> [!NOTE]
> <span data-ttu-id="55cb9-p102">Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden. Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="55cb9-p102">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy. In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> 
  
### <a name="to-set-a-users-pin"></a><span data-ttu-id="55cb9-110">So richten Sie die PIN eines Benutzers ein</span><span class="sxs-lookup"><span data-stu-id="55cb9-110">To set a user's PIN</span></span>

1. <span data-ttu-id="55cb9-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="55cb9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="55cb9-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="55cb9-113">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-113">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="55cb9-114">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="55cb9-114">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="55cb9-115">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="55cb9-116">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-116">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="55cb9-117">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="55cb9-117">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="55cb9-118">a.</span><span class="sxs-lookup"><span data-stu-id="55cb9-118">a.</span></span> <span data-ttu-id="55cb9-119">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-119">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="55cb9-120">b.</span><span class="sxs-lookup"><span data-stu-id="55cb9-120">b.</span></span> <span data-ttu-id="55cb9-121">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="55cb9-122">c.</span><span class="sxs-lookup"><span data-stu-id="55cb9-122">c.</span></span> <span data-ttu-id="55cb9-123">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="55cb9-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="55cb9-124">d.</span><span class="sxs-lookup"><span data-stu-id="55cb9-124">d.</span></span> <span data-ttu-id="55cb9-125">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="55cb9-125">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="55cb9-126">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="55cb9-126">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="55cb9-127">e.</span><span class="sxs-lookup"><span data-stu-id="55cb9-127">e.</span></span> <span data-ttu-id="55cb9-128">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-128">Click **Find**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="55cb9-p108">Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf **Aktion** und auf **PIN entsperren**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-p108">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click **Action**, and then click **Unlock PIN**.</span></span> 
  
6. <span data-ttu-id="55cb9-131">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-131">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>
    
7. <span data-ttu-id="55cb9-132">Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="55cb9-132">In the **Set PIN** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="55cb9-133">Wenn Sie zulassen möchten, dass Skype for Business Server die PIN des Benutzers generiert, wählen Sie **automatisch eine gültige Pin generieren** (Standardeinstellung) aus.</span><span class="sxs-lookup"><span data-stu-id="55cb9-133">To allow Skype for Business Server to generate the user's PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
   - <span data-ttu-id="55cb9-134">Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN von Hand eingeben**, klicken Sie auf das Textfeld und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="55cb9-134">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>
    
8. <span data-ttu-id="55cb9-135">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-135">Click **OK**.</span></span>
    
9. <span data-ttu-id="55cb9-136">Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="55cb9-136">In **Set PIN**, do one of the following:</span></span> 
    
   - <span data-ttu-id="55cb9-137">Aktivieren Sie das Kontrollkästchen **PIN anzeigen**, um die PIN anzuzeigen, kopieren Sie die PIN und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.</span><span class="sxs-lookup"><span data-stu-id="55cb9-137">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
   - <span data-ttu-id="55cb9-p109">Klicken Sie auf **E-Mail-Client öffnen, um die neue PIN an den Benutzer zu senden**, um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen** und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="55cb9-p109">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>
    
10. <span data-ttu-id="55cb9-141">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="55cb9-141">Click **Close**.</span></span>
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="55cb9-142">Zuweisen einer Benutzer-PIN mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="55cb9-142">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="55cb9-143">Sie können Benutzern mithilfe des Cmdlets „Lock-Set-CsClientPin“ PINs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-143">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="55cb9-144">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-144">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="55cb9-145">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="55cb9-145">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="55cb9-146">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="55cb9-146">The process is the same in Skype for Business Server.</span></span> 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="55cb9-147">So weisen Sie Benutzern automatisch PINs zu</span><span class="sxs-lookup"><span data-stu-id="55cb9-147">To auto-assign a PIN number to a user</span></span>

<span data-ttu-id="55cb9-148">Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu.</span><span class="sxs-lookup"><span data-stu-id="55cb9-148">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="55cb9-149">Da der PIN-Parameter nicht enthalten ist, wird von Skype for Business Server automatisch die PIN-Nummer generiert und zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-149">Because the Pin parameter is not included, Skype for Business Server will automatically generate and assign the PIN number.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="55cb9-150">So weisen Sie einem Benutzer eine bestimmte PIN zu</span><span class="sxs-lookup"><span data-stu-id="55cb9-150">To assign a specific PIN number to a user</span></span>

<span data-ttu-id="55cb9-151">Der folgende Befehl verwendet den Parameter „Pin“, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="55cb9-151">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

<span data-ttu-id="55cb9-152">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="55cb9-152">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) cmdlet.</span></span>
  

