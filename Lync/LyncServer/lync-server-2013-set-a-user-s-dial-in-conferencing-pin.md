---
title: 'Lync Server 2013: Einrichten der PIN für Einwahlkonferenzen eines Benutzers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258c6e5da1dc5b78d53bbc3779d50890935d7b58
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a><span data-ttu-id="b0a43-102">Einrichten der PIN für Einwahlkonferenzen eines Benutzers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0a43-102">Set a user's dial-in conferencing PIN in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0a43-103">_**Letztes Änderungsdatum des Themas:** 2014-06-10_</span><span class="sxs-lookup"><span data-stu-id="b0a43-103">_**Topic Last Modified:** 2014-06-10_</span></span>

<span data-ttu-id="b0a43-104">Um an einer Einwahlkonferenz als authentifizierter Benutzer teilzunehmen, erfordert ein lync Server 2013-Benutzer mit den Active Directory-Domänendiensten (AD DS) eine persönliche Identifikationsnummer (PIN).</span><span class="sxs-lookup"><span data-stu-id="b0a43-104">To join a dial-in conference as an authenticated user, a Lync Server 2013 user with Active Directory Domain Services (AD DS) credentials requires a personal identification number (PIN).</span></span> <span data-ttu-id="b0a43-105">Wenn ein Benutzer die PIN für Einwahlkonferenzen vergisst oder die PIN nicht mithilfe von lync Server festgesetzt hat, können Sie die PIN des Benutzers über die lync Server-Systemsteuerung festlegen.</span><span class="sxs-lookup"><span data-stu-id="b0a43-105">If a user forgets the dial-in conferencing PIN or has not set the PIN by using Lync Server, you can set the user’s PIN from Lync Server Control Panel.</span></span> <span data-ttu-id="b0a43-106">Die PIN kann entweder automatisch generiert oder manuell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b0a43-106">You can automatically generate the PIN or create one manually.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b0a43-107">Bestimmte Eigenschaften der PIN, beispielsweise die Mindestlänge, können als Richtlinie konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b0a43-107">Specific characteristics of the PIN, such as its minimum length, can be configured as a policy.</span></span> <span data-ttu-id="b0a43-108">Zusätzlich zur globalen Richtlinie können Sie eine PIN-Richtlinie für einzelne Standorte oder Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b0a43-108">In addition to the global policy, you can configure a PIN policy for individual sites or users.</span></span> <span data-ttu-id="b0a43-109">Details zum Konfigurieren einer PIN-Richtlinie finden Sie unter <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Konfigurieren von PIN-Regeln für Einwahlkonferenzen in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b0a43-109">For details about configuring a PIN policy, see <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-set-a-users-pin"></a><span data-ttu-id="b0a43-110">So legen Sie die PIN für einen Benutzer fest</span><span class="sxs-lookup"><span data-stu-id="b0a43-110">To set a user’s PIN</span></span>

1.  <span data-ttu-id="b0a43-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="b0a43-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b0a43-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b0a43-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b0a43-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b0a43-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b0a43-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="b0a43-115">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="b0a43-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="b0a43-116">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="b0a43-117">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="b0a43-118">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="b0a43-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="b0a43-119">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="b0a43-120">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b0a43-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="b0a43-121">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="b0a43-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="b0a43-122">Je nachdem, welche Benutzereigenschaft Sie ausgewählt haben, geben Sie nun die Kriterien ein, mit denen Sie die Suchergebnisse filtern möchten, oder treffen eine entsprechende Auswahl in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="b0a43-122">Depending on the user property you selected, enter the criteria that you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="b0a43-123">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="b0a43-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="b0a43-124">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-124">Click **Find**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b0a43-p104">Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf <STRONG>Aktion</STRONG> und auf <STRONG>PIN entsperren</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b0a43-p104">If the PIN is locked, you must unlock the PIN before you can set it. To unlock the PIN, click the user, click <STRONG>Action</STRONG>, and then click <STRONG>Unlock PIN</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="b0a43-127">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **PIN festlegen**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-127">Click a user in the search results, click **Action**, and then click **Set PIN**.</span></span>

7.  <span data-ttu-id="b0a43-128">Führen Sie im Dialogfeld **PIN festlegen** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="b0a43-128">In the **Set PIN** dialog box, do one of the following:</span></span>
    
      - <span data-ttu-id="b0a43-129">Wenn Sie zulassen möchten, dass lync Server 2013 die PIN des Benutzers generiert, wählen Sie **automatisch eine gültige Pin generieren** aus (die Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="b0a43-129">To allow Lync Server 2013 to generate the user’s PIN, select **Automatically generate a valid PIN** (the default).</span></span>
    
      - <span data-ttu-id="b0a43-130">Zum Erstellen einer eigenen PIN klicken Sie auf **Bestimmte PIN von Hand eingeben**, klicken Sie auf das Textfeld und geben Sie anschließend eine PIN ein, welche die in Ihren PIN-Richtlinieneinstellungen angegebenen PIN-Anforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="b0a43-130">To create your own PIN, click **Manually enter a specific PIN**, click the text box, and then type a PIN that meets the PIN requirements specified in your PIN policy settings.</span></span>

8.  <span data-ttu-id="b0a43-131">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-131">Click **OK**.</span></span>

9.  <span data-ttu-id="b0a43-132">Führen Sie im Abschnitt **PIN festlegen** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="b0a43-132">In **Set PIN**, do one of the following:</span></span>
    
      - <span data-ttu-id="b0a43-133">Aktivieren Sie das Kontrollkästchen **PIN anzeigen**, um die PIN anzuzeigen, kopieren Sie die PIN und teilen Sie sie dem Benutzer über die bevorzugte Methode Ihrer Organisation mit.</span><span class="sxs-lookup"><span data-stu-id="b0a43-133">Select the **Show PIN** check box to see the PIN, and then copy the PIN and communicate it to the user using your organization's preferred method.</span></span>
    
      - <span data-ttu-id="b0a43-p105">Klicken Sie auf **E-Mail-Client öffnen, um die neue PIN an den Benutzer zu senden**, um die PIN per E-Mail zu senden. Wenn Sie Microsoft Office Outlook als E-Mail-Client verwenden, wird die PIN automatisch in die neue E-Mail-Nachricht kopiert. Wenn Sie einen anderen E-Mail-Client einsetzen, aktivieren Sie das Kontrollkästchen **PIN anzeigen** und kopieren Sie die PIN anschließend in die E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b0a43-p105">Click **Open my email application to send the new PIN to the user** to send the PIN by email. If Microsoft Office Outlook is your email client, the PIN is automatically copied into a new email message. If you use a different email client, select the **Show PIN** check box to see the PIN and then copy it into your email message.</span></span>

10. <span data-ttu-id="b0a43-137">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="b0a43-137">Click **Close**.</span></span>

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b0a43-138">Zuweisen einer Benutzer-PIN mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b0a43-138">Assigning a User PIN by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b0a43-139">Sie können Benutzern mithilfe des Cmdlets „Lock-Set-CsClientPin“ PINs zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b0a43-139">You can assign PIN numbers can also be assigned by using the Set-CsClientPin cmdlet.</span></span> <span data-ttu-id="b0a43-140">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="b0a43-140">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b0a43-141">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="b0a43-141">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a><span data-ttu-id="b0a43-142">So weisen Sie Benutzern automatisch PINs zu</span><span class="sxs-lookup"><span data-stu-id="b0a43-142">To auto-assign a PIN number to a user</span></span>

  - <span data-ttu-id="b0a43-143">Der folgende Befehl weist dem Benutzer Ken Myer eine PIN zu.</span><span class="sxs-lookup"><span data-stu-id="b0a43-143">The following command assigns a PIN number to the user Ken Myer.</span></span> <span data-ttu-id="b0a43-144">Da der PIN-Parameter nicht enthalten ist, generiert lync Server automatisch die PIN-Nummer und weist diese zu.</span><span class="sxs-lookup"><span data-stu-id="b0a43-144">Because the Pin parameter is not included, Lync Server will automatically generate and assign the PIN number.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a><span data-ttu-id="b0a43-145">So weisen Sie einem Benutzer eine bestimmte PIN zu</span><span class="sxs-lookup"><span data-stu-id="b0a43-145">To assign a specific PIN number to a user</span></span>

  - <span data-ttu-id="b0a43-146">Der folgende Befehl verwendet den Parameter „Pin“, um dem Benutzer Ken Myer die PIN 121989 zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b0a43-146">This command uses the Pin parameter to assign the PIN number 121989 to the user Ken Myer.</span></span>
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

<span data-ttu-id="b0a43-147">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) ".</span><span class="sxs-lookup"><span data-stu-id="b0a43-147">For more information, see the help topic for the [Set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b0a43-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0a43-148">See Also</span></span>


<span data-ttu-id="b0a43-149">[Zugriffsnummer für Einwahlkonferenz](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="b0a43-149">[Dial-in Access Number](https://technet.microsoft.com/en-us/library/gg133674\(v=ocs.15\))</span></span>  


[<span data-ttu-id="b0a43-150">Konfigurieren von Einwahlkonferenz-Regeln (Personal Identification Number, PIN) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0a43-150">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

