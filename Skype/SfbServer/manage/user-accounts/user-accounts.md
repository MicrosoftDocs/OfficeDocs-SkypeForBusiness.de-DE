---
title: Verwalten von Benutzerkonten für Skype für Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: In den Abschnitten in diesem Artikel wird beschrieben, wie aktivieren, vorübergehend deaktivieren oder Entfernen von Active Directory-Benutzer von Skype für Business Server.
ms.openlocfilehash: ee6a82c5b5def06866379467beddae788d85171b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976737"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="86d83-103">Verwalten von Benutzerkonten für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86d83-103">Manage user accounts for Skype for Business Server</span></span>
 
<span data-ttu-id="86d83-104">In den Abschnitten in diesem Artikel wird beschrieben, wie aktivieren, vorübergehend deaktivieren oder Entfernen von Active Directory-Benutzer von Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="86d83-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>
  
<span data-ttu-id="86d83-105">Informationen zum Aktivieren von Active Directory-Benutzer finden Sie unter [Erstellen eines neuen Benutzerkontos](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="86d83-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="86d83-106">Informationen zum Löschen eines Active Directory-Benutzers finden Sie unter [Löschen eines Benutzerkontos](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="86d83-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>
  
<span data-ttu-id="86d83-107">Diese Verfahren sollten während eines Wartungsfensters durchgeführt werden, wenn für die Verwendung von Business Skype niedrigsten ist.</span><span class="sxs-lookup"><span data-stu-id="86d83-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="86d83-108">Ob dies nach einem Zeitplan täglich oder wöchentlich erfolgt wird durch die Anforderungen Ihrer Organisation bestimmt.</span><span class="sxs-lookup"><span data-stu-id="86d83-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span> 
  
<span data-ttu-id="86d83-109">Dieser Artikel enthält die folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="86d83-109">This article contains the following procedures:</span></span>
  
- [<span data-ttu-id="86d83-110">Suche nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="86d83-110">To search for one or more users</span></span>](user-accounts.md#Search)
    
- [<span data-ttu-id="86d83-111">Fügen Sie hinzu und aktivieren Sie eine neue Skype für Business Server-Benutzer</span><span class="sxs-lookup"><span data-stu-id="86d83-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)
    
- [<span data-ttu-id="86d83-112">Deaktivieren oder Reaktivieren eines Benutzerkontos, die zuvor für die Skype für Business Server aktiviert</span><span class="sxs-lookup"><span data-stu-id="86d83-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)
    
- [<span data-ttu-id="86d83-113">Deaktivieren eines Benutzers für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="86d83-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)
    
- [<span data-ttu-id="86d83-114">Entfernen eines Benutzerkontos mit der Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="86d83-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)
    
## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="86d83-115">Suche nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="86d83-115">To search for one or more users</span></span>
<span data-ttu-id="86d83-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="86d83-116"></span></span>

<span data-ttu-id="86d83-117">Sie können die Ergebnisse einer Suchabfrage verwenden, Active Directory-Benutzer für Skype für Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86d83-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="86d83-118">Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="86d83-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>
  
<span data-ttu-id="86d83-119">Sie können nach Benutzern suchen, unter Verwendung der Skype für Business Server-Systemsteuerung oder Active Directory-Benutzer und Computer-Snap-in.</span><span class="sxs-lookup"><span data-stu-id="86d83-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="86d83-120">Das folgende Verfahren beschreibt, wie Sie Skype Business Server-Systemsteuerung verwenden, um nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="86d83-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86d83-121">In einer Umgebung mit einer Topologie mit zentraler Gesamtstruktur möglicherweise Suchergebnisse nicht genau sein, wenn Sie für einen Benutzer von e-Mail-Adresse des Benutzers suchen.</span><span class="sxs-lookup"><span data-stu-id="86d83-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="86d83-122">Sie können stattdessen durch Angeben einer SIP-Adresspräfix, z. B.: Namen der Sip-Benutzern suchen, fügen Sie einen Filter für die Suche und wählen Sie eine SIP-Adresse, die eine partielle e-Mail-Adresse enthält oder verwenden Sie das Cmdlet **Get-CSUser** .</span><span class="sxs-lookup"><span data-stu-id="86d83-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>
  
1. <span data-ttu-id="86d83-123">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="86d83-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="86d83-124">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86d83-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="86d83-125">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="86d83-125">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="86d83-126">Klicken Sie in das Feld **Suchbenutzer** alle oder den ersten Teil der Anzeigename, Vorname, Nachname, SAM-Kontoname SIP-Adresse oder Anschluss-URI des Benutzerkontos, dem Sie suchen, und klicken Sie dann auf **Suchen**möchten.</span><span class="sxs-lookup"><span data-stu-id="86d83-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>
    
5. <span data-ttu-id="86d83-127">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="86d83-127">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="86d83-128">a.</span><span class="sxs-lookup"><span data-stu-id="86d83-128">a.</span></span> <span data-ttu-id="86d83-129">Klicken Sie auf die Schaltfläche in der oberen rechten Ecke des Bildschirms oberhalb **von Suchergebnisse**Pfeil, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>
    
   <span data-ttu-id="86d83-130">b.</span><span class="sxs-lookup"><span data-stu-id="86d83-130">b.</span></span> <span data-ttu-id="86d83-131">Geben Sie die Benutzereigenschaft durch eingeben oder auf den Pfeil in der Dropdownliste aus, um eine Benutzereigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="86d83-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>
    
   <span data-ttu-id="86d83-132">c.</span><span class="sxs-lookup"><span data-stu-id="86d83-132">c.</span></span> <span data-ttu-id="86d83-133">Klicken Sie in der Liste **gleich** auf **gleich** oder **ungleich**.</span><span class="sxs-lookup"><span data-stu-id="86d83-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>
    
   <span data-ttu-id="86d83-134">d.</span><span class="sxs-lookup"><span data-stu-id="86d83-134">d.</span></span> <span data-ttu-id="86d83-135">Klicken Sie in das Textfeld Geben Sie die Suchkriterien ein, den, die Sie verwenden, um die Suchergebnisse filtern möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>
    
6. <span data-ttu-id="86d83-136">Die Suchergebnisse werden unter **Suchergebnisse**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86d83-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="86d83-137">Sie können einige oder alle Benutzer in der Liste wählen, und führen Konfigurationsaufgaben für die Benutzer, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="86d83-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>
    
## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="86d83-138">Fügen Sie hinzu und aktivieren Sie eine neue Skype für Business Server-Benutzer</span><span class="sxs-lookup"><span data-stu-id="86d83-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="86d83-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="86d83-139"></span></span>

<span data-ttu-id="86d83-140">Nach dem Aktivieren eines Benutzerkontos in Active Directory-Benutzer und-Computer, können Sie Skype Business Server-Systemsteuerung erstellen und Aktivieren von neuen Skype für Benutzerkonten Business Server Skype für Business Server einen Active Directory-Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="86d83-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>
  
<span data-ttu-id="86d83-141">Sie können auch auf einem speziell [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="86d83-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>
  
1. <span data-ttu-id="86d83-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="86d83-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="86d83-143">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86d83-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="86d83-144">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="86d83-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="86d83-145">Klicken Sie auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="86d83-145">Click **Enable users**.</span></span>
    
5. <span data-ttu-id="86d83-146">Klicken Sie auf **Hinzufügen**, klicken Sie im Dialogfeld **Neuer Lync Server-Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="86d83-146">On the **New Lync Server User** dialog, click **Add**.</span></span>
    
6. <span data-ttu-id="86d83-147">Geben Sie im Feld **Suche Benutzer** alle den ersten Teil des Namens anzeigen Sie, Name, Vorname, Nachname, Kontonamen Sicherheitskontenverwaltung (SAM), e-Mail-Adresse, User Principal Name (UPN) oder des Active Directory-Benutzerkontos die gewünschte Telefonnummer , und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>
    
7. <span data-ttu-id="86d83-148">Wählen Sie in der Tabelle das Konto aus, den, das Sie Skype für Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="86d83-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>
    
8. <span data-ttu-id="86d83-149">Weisen Sie dem Benutzer zu einem Pool, geben Sie zusätzliche Details, und weisen Sie die Richtlinien für den gewünschten Benutzer, und klicken Sie dann auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="86d83-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>
    
## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="86d83-150">Deaktivieren oder Reaktivieren eines Benutzerkontos, die zuvor für die Skype für Business Server aktiviert</span><span class="sxs-lookup"><span data-stu-id="86d83-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="86d83-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="86d83-151"></span></span>

<span data-ttu-id="86d83-152">Das folgende Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype für Business Server deaktivieren, ohne zu verlieren die Skype für Business Server-Einstellungen, die Sie für das Benutzerkonto konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="86d83-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="86d83-153">Da Sie nicht die Skype für Business Server Benutzerkonteneinstellungen verlieren, können Sie ein zuvor aktiviertes Benutzerkonto erneut erneut ermöglichen, ohne dass das Benutzerkonto neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86d83-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span> 
  
1. <span data-ttu-id="86d83-154">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="86d83-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="86d83-155">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86d83-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="86d83-156">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="86d83-156">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="86d83-157">Geben Sie im Feld **Suche Benutzer** alle den ersten Teil der Anzeigename, Vorname, Nachname, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () des Benutzerkontos, das Sie deaktivieren oder aktivieren möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="86d83-158">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="86d83-158">In the table, click the user account that you want to disable or re-enable.</span></span>
    
6. <span data-ttu-id="86d83-159">Klicken Sie im Menü **Aktion** auf führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="86d83-159">On the **Action** menu, do one of the following:</span></span>
    
   - <span data-ttu-id="86d83-160">Um das Benutzerkonto vorübergehend für Skype für Business Server deaktivieren, klicken Sie auf **vorübergehend für Lync Server deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="86d83-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>
    
   - <span data-ttu-id="86d83-161">Klicken Sie auf **erneut für Lync Server aktivieren**, um das Benutzerkonto für Skype für Business Server zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="86d83-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>
    
### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="86d83-162">Deaktivieren oder Reaktivieren von Benutzerkonten mithilfe von Windows Powershell</span><span class="sxs-lookup"><span data-stu-id="86d83-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="86d83-163">Benutzerkonten können vorübergehend deaktiviert, und klicken Sie dann später wieder aktiviert, mit dem **Set-CsUser** -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86d83-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="86d83-164">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="86d83-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="86d83-165">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="86d83-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="86d83-166">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="86d83-166">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-disable-a-user-account"></a><span data-ttu-id="86d83-167">So deaktivieren Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="86d83-167">To disable a user account</span></span>

- <span data-ttu-id="86d83-168">Legen Sie den Wert der Eigenschaft Enabled auf "false" ($False), um ein Benutzerkonto vorübergehend zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="86d83-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="86d83-169">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="86d83-169">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="86d83-170">Reaktivieren ein Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="86d83-170">To re-enable a user account</span></span>

- <span data-ttu-id="86d83-171">Um ein deaktiviertes Benutzerkonto wieder zu aktivieren, legen Sie den Wert der Eigenschaft Enabled auf "true" ($True).</span><span class="sxs-lookup"><span data-stu-id="86d83-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="86d83-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="86d83-172">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="86d83-173">Weitere Informationen finden Sie im Hilfethema zum [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="86d83-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="86d83-174">Deaktivieren eines Benutzers für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="86d83-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="86d83-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="86d83-175"></span></span>

<span data-ttu-id="86d83-176">Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto deaktivieren, die für Skype für Business Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="86d83-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>
  
### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="86d83-177">So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="86d83-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="86d83-178">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="86d83-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="86d83-179">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86d83-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="86d83-180">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="86d83-180">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="86d83-181">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="86d83-182">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="86d83-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="86d83-183">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-183">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="86d83-184">Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie**auf eine beliebige Option außer **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="86d83-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="86d83-185">Um einen Benutzer daran zu hindern, Ausführen von Audio-oder Videoanrufe mit Lync, klicken Sie unter **Telefonie**, klicken Sie auf **Audio/Video deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="86d83-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span> 
  
8. <span data-ttu-id="86d83-186">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-186">Click **Commit**.</span></span>
    
<span data-ttu-id="86d83-187">Der Benutzer kann jetzt das Enterprise-VoIP-Feature verwenden.</span><span class="sxs-lookup"><span data-stu-id="86d83-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="86d83-188">Verwandte Informationen:</span><span class="sxs-lookup"><span data-stu-id="86d83-188">Related information:</span></span> <br/>[<span data-ttu-id="86d83-189">Enterprise-VoIP und Mobilität</span><span class="sxs-lookup"><span data-stu-id="86d83-189">Enterprise Voice and mobility</span></span>](http://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="86d83-190">Aktivieren von Benutzern für Enterprise-VoIP in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="86d83-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="86d83-191">Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="86d83-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="86d83-192">Entfernen eines Benutzerkontos mit der Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="86d83-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="86d83-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="86d83-193"></span></span>

<span data-ttu-id="86d83-194">Das folgende Verfahren können Sie um ein zuvor hinzugefügtes Benutzerkonto in Skype für Business Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="86d83-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="86d83-195">Entfernen eines Benutzers führen Sie alle Einstellungen, die Sie für das Benutzerkonto konfiguriert haben, gehen verloren.</span><span class="sxs-lookup"><span data-stu-id="86d83-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="86d83-196">Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, finden Sie unter [deaktivieren oder reaktivieren ein Benutzerkontos, die zuvor für die Skype für Business Server aktiviert](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="86d83-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span> 
  
1. <span data-ttu-id="86d83-197">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="86d83-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="86d83-198">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="86d83-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="86d83-199">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="86d83-199">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="86d83-200">Geben Sie im Feld **Suche Benutzer** alle den ersten Teil der Anzeigename, Vorname, Nachname, Kontonamen Sicherheitskontenverwaltung (SAM), SIP-Adresse oder Zeile URI Uniform Resource Identifier () des Benutzerkontos, das Sie deaktivieren oder aktivieren möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="86d83-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="86d83-201">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="86d83-201">In the table, click the user account that you want to remove.</span></span>
    
6. <span data-ttu-id="86d83-202">Das wird auf **das Aktionsmenü** , select **Entfernen von Lync Server**und ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="86d83-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>
    
7. <span data-ttu-id="86d83-203">Wählen Sie im Dialogfeld **OK** , um den Benutzer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="86d83-203">From the dialog box, select **OK** to remove the user.</span></span>
    
### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="86d83-204">Entfernen von Benutzerkonten mit Windows Powershell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="86d83-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="86d83-205">Sie können Benutzerkonten mit dem Cmdlet Disable-CsUser entfernen.</span><span class="sxs-lookup"><span data-stu-id="86d83-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="86d83-206">Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="86d83-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="86d83-207">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="86d83-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="86d83-208">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="86d83-208">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-user-account"></a><span data-ttu-id="86d83-209">Zum Entfernen eines Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="86d83-209">To remove a user account</span></span>
<span data-ttu-id="86d83-210">Um ein Benutzerkonto zu entfernen, verwenden Sie das Cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="86d83-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="86d83-211">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="86d83-211">For example:</span></span>
    
  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.
    
<span data-ttu-id="86d83-212">Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="86d83-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86d83-213">Waren diese Schritte hilfreich? Wenn ja, teilen Sie uns dies bitte unterhalb des Artikels mit. Wenn nicht, schreiben Sie uns, was für Sie unklar war, und wir verwenden Ihr Feedback, um unsere Schritte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="86d83-213">See also</span></span>
<span data-ttu-id="86d83-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="86d83-214"></span></span>

[<span data-ttu-id="86d83-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="86d83-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)
  
[<span data-ttu-id="86d83-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="86d83-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)