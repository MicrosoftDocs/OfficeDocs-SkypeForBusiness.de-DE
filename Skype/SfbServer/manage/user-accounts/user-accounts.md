---
title: Verwalten von Benutzerkonten für Skype for Business Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory-Benutzer in Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.
ms.openlocfilehash: 33af0305fe25b9d7a272e89ae196923e97c4cfd3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817055"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="04385-103">Verwalten von Benutzerkonten für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="04385-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="04385-104">In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory-Benutzer in Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="04385-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="04385-105">Informationen zum Aktivieren eines Active Directory-Benutzers finden Sie unter [Erstellen eines neuen Benutzerkontos](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="04385-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="04385-106">Informationen zum Löschen eines Active Directory-Benutzers finden Sie unter [Löschen eines Benutzerkontos](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="04385-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="04385-107">Diese Verfahren sollten während eines Wartungsfensters durchgeführt werden, wenn die Nutzung von Skype for Business am niedrigsten ist.</span><span class="sxs-lookup"><span data-stu-id="04385-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="04385-108">Ob dies für einen Tages-oder Wochenplan erfolgt, hängt von den Anforderungen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="04385-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="04385-109">Dieser Artikel enthält die folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="04385-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="04385-110">So suchen Sie nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="04385-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="04385-111">Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers</span><span class="sxs-lookup"><span data-stu-id="04385-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="04385-112">Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="04385-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="04385-113">Deaktivieren eines Benutzers für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="04385-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="04385-114">Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="04385-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="04385-115">So suchen Sie nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="04385-115">To search for one or more users</span></span>
<span data-ttu-id="04385-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="04385-116"><a name="Search"> </a></span></span>

<span data-ttu-id="04385-117">Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory-Benutzer für Skype for Business Server zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="04385-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="04385-118">Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URI (Uniform Resource Identifier) nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="04385-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="04385-119">Sie können über die Skype for Business Server-Systemsteuerung oder das Snap-in Active Directory-Benutzer und-Computer nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="04385-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="04385-120">Im folgenden Verfahren wird beschrieben, wie Sie mit der Skype for Business Server-Systemsteuerung nach Benutzern suchen können.</span><span class="sxs-lookup"><span data-stu-id="04385-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="04385-121">In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind die Suchergebnisse möglicherweise nicht korrekt, wenn Sie nach einem Benutzer anhand der e-Mail-Adresse des Benutzers suchen.</span><span class="sxs-lookup"><span data-stu-id="04385-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="04385-122">Stattdessen können Sie nach Benutzern suchen, indem Sie ein SIP-Adresspräfix angeben, beispielsweise SIP: Name, einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die eine teilweise e-Mail-Adresse enthält, oder das Cmdlet " **Get-CSUser** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="04385-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="04385-123">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04385-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="04385-124">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04385-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="04385-125">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="04385-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="04385-126">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens, der SIP-Adresse oder des Leitungs-URIs des Benutzerkontos ein, nach dem Sie suchen möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04385-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="04385-127">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="04385-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="04385-128">a.</span><span class="sxs-lookup"><span data-stu-id="04385-128">a.</span></span> <span data-ttu-id="04385-129">Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb der **Suchergebnisse**auf die Schaltfläche zum Erweitern des Pfeils, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="04385-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="04385-130">b.</span><span class="sxs-lookup"><span data-stu-id="04385-130">b.</span></span> <span data-ttu-id="04385-131">Geben Sie die Benutzereigenschaft ein, indem Sie Sie eingeben oder in der Dropdownliste auf den Pfeil klicken, um eine Benutzereigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="04385-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="04385-132">c.</span><span class="sxs-lookup"><span data-stu-id="04385-132">c.</span></span> <span data-ttu-id="04385-133">Klicken Sie in der Liste **gleich** an auf **gleich** oder **ungleich**.</span><span class="sxs-lookup"><span data-stu-id="04385-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="04385-134">d.</span><span class="sxs-lookup"><span data-stu-id="04385-134">d.</span></span> <span data-ttu-id="04385-135">Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04385-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="04385-136">Die Suchergebnisse werden unter **Suchergebnisse**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04385-136">The search results appear under **Search Results**.</span></span> <span data-ttu-id="04385-137">Sie können einen oder alle Benutzer in der Liste auswählen und Konfigurationsaufgaben für die von Ihnen ausgewählten Benutzer durchführen.</span><span class="sxs-lookup"><span data-stu-id="04385-137">You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="04385-138">Hinzufügen und Aktivieren eines neuen Skype for Business Server-Benutzers</span><span class="sxs-lookup"><span data-stu-id="04385-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="04385-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="04385-139"><a name="Add"> </a></span></span>

<span data-ttu-id="04385-140">Nachdem Sie ein Benutzerkonto in Active Directory-Benutzer und-Computer aktiviert haben, können Sie die Skype for Business Server-Systemsteuerung verwenden, um neue Skype for Business Server-Benutzerkonten zu erstellen und zu aktivieren, indem Sie einen Active Directory-Benutzer zu Skype for Business Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="04385-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="04385-141">Sie können auch ein Cmdlet verwenden, insbesondere [enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="04385-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="04385-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04385-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="04385-143">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04385-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="04385-144">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="04385-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="04385-145">Klicken Sie auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="04385-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="04385-146">Klicken Sie im Dialogfeld **neuer lync Server-Benutzer** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="04385-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="04385-147">Geben Sie im Feld Benutzer suchen den gesamten oder den ersten Teil des Namens, den Anzeigenamen, den Vornamen, den **Nachnamen** , den Kontonamen, die e-Mail-Adresse, den Benutzerprinzipalnamen (User Principal Name, UPN) oder die Telefonnummer des gewünschten Active Directory-Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04385-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="04385-148">Wählen Sie in der Tabelle das Konto aus, das Sie zu Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="04385-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="04385-149">Weisen Sie den Benutzer einem Pool zu, geben Sie zusätzliche Details an, und weisen Sie die Richtlinien dem gewünschten Benutzer zu, und klicken Sie dann auf **aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="04385-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="04385-150">Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="04385-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="04385-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="04385-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="04385-152">Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype for Business Server deaktivieren, ohne die Skype for Business-Servereinstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="04385-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="04385-153">Da die Einstellungen für das Skype for Business Server-Benutzerkonto nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="04385-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="04385-154">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04385-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="04385-155">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04385-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="04385-156">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="04385-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="04385-157">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04385-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="04385-158">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie deaktivieren oder erneut aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="04385-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="04385-159">Führen Sie im Menü **Aktion** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="04385-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="04385-160">Wenn Sie das Benutzerkonto für Skype for Business Server vorübergehend deaktivieren möchten, klicken Sie auf **für lync Server vorübergehend deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="04385-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="04385-161">Wenn Sie das Benutzerkonto für Skype for Business Server aktivieren möchten, klicken Sie auf **für lync Server erneut aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="04385-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="04385-162">Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="04385-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="04385-163">Mithilfe des Cmdlets " **Satz-CsUser** " können Benutzerkonten vorübergehend deaktiviert und später erneut aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="04385-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="04385-164">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="04385-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="04385-165">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="04385-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="04385-166">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="04385-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="04385-167">So deaktivieren Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="04385-167">To disable a user account</span></span>

- <span data-ttu-id="04385-168">Wenn Sie ein Benutzerkonto vorübergehend deaktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf false ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="04385-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="04385-169">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04385-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="04385-170">So aktivieren Sie ein Benutzerkonto erneut</span><span class="sxs-lookup"><span data-stu-id="04385-170">To re-enable a user account</span></span>

- <span data-ttu-id="04385-171">Wenn Sie ein deaktiviertes Benutzerkonto erneut aktivieren möchten, legen Sie den Wert der Enabled-Eigenschaft auf true ($true) fest.</span><span class="sxs-lookup"><span data-stu-id="04385-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="04385-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04385-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="04385-173">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="04385-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="04385-174">Deaktivieren eines Benutzers für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="04385-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="04385-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="04385-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="04385-176">Gehen Sie wie folgt vor, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="04385-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="04385-177">So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="04385-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="04385-178">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04385-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="04385-179">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04385-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="04385-180">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="04385-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="04385-181">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04385-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="04385-182">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="04385-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="04385-183">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="04385-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="04385-184">Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie**auf eine beliebige Option mit Ausnahme von **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="04385-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04385-185">Wenn Sie einen Benutzer daran hindern möchten, Audio-oder Videoanrufe mit lync zu führen, klicken Sie unter **Telefonie**auf **Audio/Video deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="04385-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="04385-186">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="04385-186">Click **Commit**.</span></span>

<span data-ttu-id="04385-187">Der Benutzer kann nun die Enterprise-VoIP-Funktion nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="04385-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="04385-188">Verwandte Informationen:</span><span class="sxs-lookup"><span data-stu-id="04385-188">Related information:</span></span> <br/>[<span data-ttu-id="04385-189">Enterprise-VoIP und Mobilität</span><span class="sxs-lookup"><span data-stu-id="04385-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="04385-190">Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="04385-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="04385-191">Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="04385-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="04385-192">Entfernen eines Benutzerkontos mit der Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="04385-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="04385-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="04385-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="04385-194">Sie können das folgende Verfahren verwenden, um ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="04385-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="04385-195">Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="04385-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="04385-196">Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, lesen Sie [deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos](user-accounts.md#Disable).</span><span class="sxs-lookup"><span data-stu-id="04385-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="04385-197">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04385-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="04385-198">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04385-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="04385-199">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="04385-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="04385-200">Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des Benutzerkontos ein, das Sie deaktivieren oder erneut aktivieren möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="04385-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="04385-201">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="04385-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="04385-202">Klicken Sie im Menü **Aktion** auf **aus lync Server entfernen**, und es wird ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04385-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="04385-203">Wählen Sie im Dialogfeld **OK** aus, um den Benutzer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="04385-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="04385-204">Entfernen von Benutzerkonten mit Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04385-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="04385-205">Sie können Benutzerkonten mithilfe des Cmdlets Disable-CsUser entfernen.</span><span class="sxs-lookup"><span data-stu-id="04385-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="04385-206">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="04385-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="04385-207">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="04385-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="04385-208">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="04385-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="04385-209">So entfernen Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="04385-209">To remove a user account</span></span>
<span data-ttu-id="04385-210">Wenn Sie ein Benutzerkonto entfernen möchten, verwenden Sie das Cmdlet Disable-CsUser.</span><span class="sxs-lookup"><span data-stu-id="04385-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="04385-211">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04385-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="04385-212">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="04385-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="04385-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04385-213">See also</span></span>
<span data-ttu-id="04385-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="04385-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="04385-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="04385-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="04385-216">Deaktivieren-CsUser</span><span class="sxs-lookup"><span data-stu-id="04385-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
