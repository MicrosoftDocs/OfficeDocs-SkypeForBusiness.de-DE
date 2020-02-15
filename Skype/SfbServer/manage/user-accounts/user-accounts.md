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
description: In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory Benutzer aus Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.
ms.openlocfilehash: aa1ed16c39141cbcd6542f2c7e254a278c345826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009638"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="d482b-103">Verwalten von Benutzerkonten für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d482b-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="d482b-104">In den Abschnitten in diesem Artikel wird beschrieben, wie Sie Active Directory Benutzer aus Skype for Business Server aktivieren, vorübergehend deaktivieren oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="d482b-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="d482b-105">Informationen zum Aktivieren eines Active Directory Benutzers finden Sie unter [Erstellen eines neuen Benutzerkontos](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d482b-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="d482b-106">Informationen zum Löschen eines Active Directory Benutzers finden Sie unter [Löschen eines Benutzerkontos](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="d482b-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="d482b-107">Diese Verfahren sollten während eines Wartungsfensters ausgeführt werden, wenn Skype for Business Verwendung am niedrigsten ist.</span><span class="sxs-lookup"><span data-stu-id="d482b-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="d482b-108">Ob dies für einen täglichen oder wöchentlichen Zeitplan erfolgt, hängt von den Anforderungen Ihrer Organisation ab.</span><span class="sxs-lookup"><span data-stu-id="d482b-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="d482b-109">Dieser Artikel enthält die folgenden Verfahren:</span><span class="sxs-lookup"><span data-stu-id="d482b-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="d482b-110">So suchen Sie nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="d482b-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="d482b-111">Hinzufügen und Aktivieren eines neuen Skype for Business Server Benutzers</span><span class="sxs-lookup"><span data-stu-id="d482b-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="d482b-112">Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="d482b-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="d482b-113">Deaktivieren eines Benutzers für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d482b-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="d482b-114">Entfernen eines Benutzerkontos mit der Skype for Business Server Management-Shell</span><span class="sxs-lookup"><span data-stu-id="d482b-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="d482b-115">So suchen Sie nach einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="d482b-115">To search for one or more users</span></span>
<span data-ttu-id="d482b-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="d482b-116"><a name="Search"> </a></span></span>

<span data-ttu-id="d482b-117">Sie können die Ergebnisse einer Suchabfrage verwenden, um Active Directory Benutzer für Skype for Business Server zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d482b-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="d482b-118">Sie können anhand des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der SIP-Adresse oder des Anschluss-URIs (Uniform Resource Identifier) nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="d482b-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="d482b-119">Sie können mithilfe der Systemsteuerung von Skype for Business Server oder des Snap-Ins Active Directory Benutzer und Computer nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="d482b-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="d482b-120">Im folgenden Verfahren wird beschrieben, wie Sie Skype for Business Server Systemsteuerung verwenden, um nach Benutzern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d482b-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="d482b-121">In einer Umgebung mit einer zentralen Gesamtstrukturtopologie sind Suchergebnisse möglicherweise nicht genau, wenn Sie nach einem Benutzer durch die e-Mail-Adresse des Benutzers suchen.</span><span class="sxs-lookup"><span data-stu-id="d482b-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="d482b-122">Stattdessen können Sie Benutzer durch Angabe eines SIP-Adressenpräfixes suchen, z. B. "sip:name", einen Suchfilter hinzufügen und eine SIP-Adresse auswählen, die einen Teil einer E-Mail-Adresse enthält, oder das Cmdlet **Get-CSUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="d482b-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="d482b-123">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d482b-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="d482b-124">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d482b-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d482b-125">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d482b-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="d482b-126">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen, die SIP-Adresse oder den Anschluss-URI des zu suchenden Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="d482b-127">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="d482b-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="d482b-128">a.</span><span class="sxs-lookup"><span data-stu-id="d482b-128">a.</span></span> <span data-ttu-id="d482b-129">Klicken Sie in der oberen rechten Ecke des Bildschirms oberhalb von **Suchergebnisse** auf die Pfeiltaste zum Erweitern des Fensters, und klicken Sie dann auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="d482b-130">b.</span><span class="sxs-lookup"><span data-stu-id="d482b-130">b.</span></span> <span data-ttu-id="d482b-131">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um eine Benutzereigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d482b-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="d482b-132">c.</span><span class="sxs-lookup"><span data-stu-id="d482b-132">c.</span></span> <span data-ttu-id="d482b-133">Klicken Sie in der Dropdownliste **Gleich** auf **Gleich** oder **Ungleich**.</span><span class="sxs-lookup"><span data-stu-id="d482b-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="d482b-134">d.</span><span class="sxs-lookup"><span data-stu-id="d482b-134">d.</span></span> <span data-ttu-id="d482b-135">Geben Sie im Textfeld die Suchkriterien ein, die Sie zum Filtern der Suchergebnisse verwenden möchten, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="d482b-p110">Die Suchergebnisse werden unter **Suchergebnisse** angezeigt. Sie können bestimmte oder alle Benutzer in der Liste auswählen und für die ausgewählten Benutzer Konfigurationsaufgaben durchführen.</span><span class="sxs-lookup"><span data-stu-id="d482b-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="d482b-138">Hinzufügen und Aktivieren eines neuen Skype for Business Server Benutzers</span><span class="sxs-lookup"><span data-stu-id="d482b-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="d482b-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="d482b-139"><a name="Add"> </a></span></span>

<span data-ttu-id="d482b-140">Nachdem Sie ein Benutzerkonto in Active Directory Benutzer und Computer aktiviert haben, können Sie Skype for Business Server Systemsteuerung verwenden, um neue Skype for Business Server Benutzerkonten zu erstellen und zu aktivieren, indem Sie Skype for Business Server einen Active Directory Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d482b-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="d482b-141">Sie können auch ein Cmdlet verwenden, insbesondere [enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d482b-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="d482b-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d482b-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="d482b-143">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d482b-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d482b-144">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d482b-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="d482b-145">Klicken Sie auf **Benutzer aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d482b-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="d482b-146">Klicken Sie im Dialogfeld **neue lync Server Benutzer** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="d482b-147">Geben Sie im Feld **Benutzer suchen** den vollständigen oder ersten Teil des Namens, des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontonamens (Security Accounts Manager), der e-Mail-Adresse, des Benutzerprinzipalnamens (User Principal Name, UPN) oder der Telefonnummer des gewünschten Active Directory Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="d482b-148">Wählen Sie in der Tabelle das Konto aus, das Sie Skype for Business Server hinzufügen möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d482b-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="d482b-149">Weisen Sie den Benutzer einem Pool zu, geben Sie weitere Details an, und weisen Sie die Richtlinien dem gewünschten Benutzer zu, und klicken Sie dann auf **aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d482b-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="d482b-150">Deaktivieren oder erneutes Aktivieren eines zuvor für Skype for Business Server aktivierten Benutzerkontos</span><span class="sxs-lookup"><span data-stu-id="d482b-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="d482b-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="d482b-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="d482b-152">Mit dem folgenden Verfahren können Sie ein zuvor aktiviertes Benutzerkonto in Skype for Business Server deaktivieren, ohne die Skype for Business Server Einstellungen zu verlieren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="d482b-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="d482b-153">Da die Skype for Business Server Benutzerkontoeinstellungen nicht verloren gehen, können Sie ein zuvor aktiviertes Benutzerkonto erneut aktivieren, ohne das Benutzerkonto neu konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d482b-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="d482b-154">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d482b-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="d482b-155">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d482b-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d482b-156">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d482b-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="d482b-157">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="d482b-158">Klicken Sie in der Tabelle auf das Benutzerkonto, das deaktiviert oder erneut aktiviert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d482b-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="d482b-159">Führen Sie im Menü **Aktion** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d482b-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="d482b-160">Wenn Sie das Benutzerkonto für Skype for Business Server vorübergehend deaktivieren möchten, klicken Sie auf **vorübergehend für lync Server deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d482b-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="d482b-161">Klicken Sie zum Aktivieren des Benutzerkontos für Skype for Business Server auf **für lync Server erneut aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d482b-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="d482b-162">Verwenden von Windows PowerShell zum Deaktivieren oder erneuten Aktivieren von Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="d482b-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="d482b-163">Benutzerkonten können vorübergehend deaktiviert und später erneut aktiviert werden, indem das Cmdlet " **CsUser** " verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d482b-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="d482b-164">Sie können dieses Cmdlet entweder über die Skype for Business Server Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="d482b-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d482b-165">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d482b-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d482b-166">Der Prozess ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="d482b-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="d482b-167">So deaktivieren Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="d482b-167">To disable a user account</span></span>

- <span data-ttu-id="d482b-168">Zum vorübergehenden Deaktivieren eines Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "False" ($False).</span><span class="sxs-lookup"><span data-stu-id="d482b-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="d482b-169">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d482b-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="d482b-170">So aktivieren Sie ein Benutzerkonto erneut</span><span class="sxs-lookup"><span data-stu-id="d482b-170">To re-enable a user account</span></span>

- <span data-ttu-id="d482b-171">Zum erneuten Aktivieren eines deaktivierten Benutzerkontos setzen Sie den Wert der Eigenschaft "Enabled" auf "True" ($True).</span><span class="sxs-lookup"><span data-stu-id="d482b-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="d482b-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d482b-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="d482b-173">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="d482b-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="d482b-174">Deaktivieren eines Benutzers für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d482b-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="d482b-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="d482b-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="d482b-176">Verwenden Sie das folgende Verfahren, um Enterprise-VoIP für ein Benutzerkonto zu deaktivieren, das für Skype for Business Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d482b-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="d482b-177">So deaktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d482b-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="d482b-178">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d482b-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="d482b-179">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d482b-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d482b-180">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d482b-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="d482b-181">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="d482b-182">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d482b-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="d482b-183">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="d482b-184">Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf eine beliebige Option außer **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="d482b-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d482b-185">Klicken Sie unter **Telefonie**auf **Audio/Video deaktiviert**, um zu verhindern, dass ein Benutzer über lync Audio-oder Videoanrufe tätigen kann.</span><span class="sxs-lookup"><span data-stu-id="d482b-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="d482b-186">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-186">Click **Commit**.</span></span>

<span data-ttu-id="d482b-187">Der Benutzer kann nun das Enterprise-VoIP-Feature nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="d482b-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="d482b-188">Verwandte Informationen:</span><span class="sxs-lookup"><span data-stu-id="d482b-188">Related information:</span></span> <br/>[<span data-ttu-id="d482b-189">Enterprise-VoIP und Mobilität</span><span class="sxs-lookup"><span data-stu-id="d482b-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="d482b-190">Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d482b-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="d482b-191">Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="d482b-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="d482b-192">Entfernen eines Benutzerkontos mit der Skype for Business Server Management-Shell</span><span class="sxs-lookup"><span data-stu-id="d482b-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="d482b-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="d482b-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="d482b-194">Mit dem folgenden Verfahren können Sie ein zuvor hinzugefügtes Benutzerkonto in Skype for Business Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="d482b-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="d482b-195">Wenn Sie einen Benutzer entfernen, gehen alle Einstellungen verloren, die Sie für das Benutzerkonto konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="d482b-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="d482b-196">Wenn Sie stattdessen ein Benutzerkonto vorübergehend deaktivieren möchten, finden Sie weitere Informationen unter [deaktivieren oder erneutes Aktivieren eines Benutzerkontos, das zuvor für Skype for Business Server aktiviert](user-accounts.md#Disable)wurde.</span><span class="sxs-lookup"><span data-stu-id="d482b-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="d482b-197">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d482b-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="d482b-198">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d482b-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="d482b-199">Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d482b-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="d482b-200">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager, Sicherheitskonto-Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das deaktiviert oder erneut aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d482b-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="d482b-201">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="d482b-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="d482b-202">Klicken Sie im Menü **Aktion** auf **Aus Lync Server entfernen**. Daraufhin wird ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d482b-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="d482b-203">Wählen Sie im Dialogfeld**OK** aus, um den Benutzer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d482b-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="d482b-204">Entfernen von Benutzerkonten mit Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d482b-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="d482b-205">Sie können Benutzerkonten mithilfe des Cmdlets Disable-CsUser entfernen.</span><span class="sxs-lookup"><span data-stu-id="d482b-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="d482b-206">Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d482b-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="d482b-207">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="d482b-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="d482b-208">Der Prozess ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="d482b-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="d482b-209">So entfernen Sie ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="d482b-209">To remove a user account</span></span>
<span data-ttu-id="d482b-210">Sie können das Cmdlet Disable-CsUser verwenden, um ein Benutzerkonto zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d482b-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="d482b-211">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d482b-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="d482b-212">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d482b-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d482b-213">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d482b-213">See also</span></span>
<span data-ttu-id="d482b-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="d482b-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="d482b-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="d482b-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="d482b-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="d482b-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
