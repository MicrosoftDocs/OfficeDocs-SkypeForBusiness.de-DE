---
title: Aktivieren von Benutzern für Enterprise-VoIP online und für Telefonsystem-Voicemail
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Erfahren Sie, wie Sie VoIP-Dienste für Telefonsysteme für Ihre Skype for Business-Benutzer aktivieren.
ms.openlocfilehash: ed5e571976a032facc70b2e602d4b0ea7fd01afc
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359181"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="78f16-103">Aktivieren von Benutzern für Enterprise-VoIP online und für Telefonsystem-Voicemail</span><span class="sxs-lookup"><span data-stu-id="78f16-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="78f16-104">Skype for Business Online werden am 31. Juli 2021 zurückgezogen, nach dem der Zugriff auf den Dienst nicht mehr möglich ist.</span><span class="sxs-lookup"><span data-stu-id="78f16-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="78f16-105">Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung unabhängig davon, ob über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="78f16-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="78f16-106">Hier erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.</span><span class="sxs-lookup"><span data-stu-id="78f16-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="78f16-107">Erfahren Sie, wie Sie VoIP-Dienste für Telefonsysteme für Ihre Skype for Business-Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="78f16-108">Der letzte Schritt bei der Bereitstellung von Telefonsystem mit lokaler PSTN-Konnektivität besteht darin, Ihre Benutzer für Telefonsystem und Voicemail zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="78f16-109">Um diese Funktionen zu aktivieren, müssen Sie ein Benutzer mit der Rolle "globaler Administrator" sein und Remote-PowerShell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="78f16-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="78f16-110">Sie müssen die Schritte in diesem Thema für alle Benutzerkonten ausführen, für die Enterprise-VoIP für Skype for Business Online noch nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="78f16-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="78f16-111">VoIP-Dienste für Telefonsysteme aktivieren</span><span class="sxs-lookup"><span data-stu-id="78f16-111">Enable Phone System voice services</span></span>

<span data-ttu-id="78f16-112">Wenn Sie einen Benutzer für Telefon System-VoIP und Voicemail aktivieren möchten, müssen Sie einige anfängliche Schritte ausführen, um zu überprüfen, ob der Skype for Business Online-Connector auf Ihren Servern bereitgestellt wurde, und Ihre Benutzer für gehostete Voicemail zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="78f16-113">So aktivieren Sie Ihre Benutzer für Telefon System Sprache und Voicemail</span><span class="sxs-lookup"><span data-stu-id="78f16-113">To enable your users for Phone System voice and voicemail</span></span>

1. <span data-ttu-id="78f16-114">Bevor Sie beginnen, sollten Sie sicherstellen, dass der Skype for Business Online Connector (Windows PowerShell-Modul) auf Ihren Front-End-Servern bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="78f16-114">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="78f16-115">Wenn dies nicht der Fall ist, können Sie es aus [dem Download Center](https://www.microsoft.com/download/details.aspx?id=39366)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="78f16-115">If it's not, you can download it from [the download center](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="78f16-116">Weitere Informationen zur Verwendung dieses Moduls finden Sie unter [Konfigurieren Ihres Computers für Skype for Business Online Verwaltung](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="78f16-116">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="78f16-117">Starten Sie Windows PowerShell als Administrator.</span><span class="sxs-lookup"><span data-stu-id="78f16-117">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="78f16-118">Geben Sie Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="78f16-118">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="78f16-119">Geben Sie Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="78f16-119">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="78f16-120">Nachdem Sie die EINGABETASTE gedrückt haben, sollte das Dialogfeld Windows PowerShell Anmeldeinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="78f16-120">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="78f16-121">Geben Sie den Benutzernamen und das Kennwort Ihres Mandanten Administrators ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78f16-121">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="78f16-122">Geben Sie im PowerShell-Fenster Folgendes ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="78f16-122">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="78f16-123">Importieren Sie die Sitzung, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="78f16-123">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="78f16-124">Beim Ausführen von PowerShell auf einem Skype for Business Server werden die lokalen Skype for Business-Cmdlets bereits geladen, wenn Sie PowerShell öffnen.</span><span class="sxs-lookup"><span data-stu-id="78f16-124">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="78f16-125">Sie müssen den Parameter-AllowClobber angeben, damit die Online-Cmdlets die lokalen Cmdlets mit dem gleichen Namen überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="78f16-125">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="78f16-126">Verwenden Sie das Cmdlet "CsUser", um dem Benutzer die Eigenschaften $EnterpriseVoiceEnabled und $HostedVoiceMail wie folgt zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="78f16-126">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="78f16-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="78f16-127">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="78f16-128">Sie können einen Benutzer auch über seine SIP-Adresse, den Benutzerprinzipalnamen (User Principal Name, UPN), den Domänennamen und den Benutzernamen (Domäne \ Benutzername) und den Anzeigenamen in Active Directory ("Bob Kelly") angeben.</span><span class="sxs-lookup"><span data-stu-id="78f16-128">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="78f16-129">Aktualisieren der Leitungs-URI und des Wählplans für Benutzer, die für das Telefon System aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="78f16-129">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="78f16-130">In diesem Abschnitt wird beschrieben, wie Sie den Anschluss-URI und die Wähleinstellungen für für Telefonsysteme aktivierte Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-130">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="78f16-131">So aktualisieren Sie den Anschluss-URI</span><span class="sxs-lookup"><span data-stu-id="78f16-131">To update the Line URI</span></span>

1. <span data-ttu-id="78f16-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="78f16-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="78f16-133">Verwenden Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="78f16-133">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78f16-134">Sie können auch ein Browserfenster öffnen und die Administrator-URL eingeben, um die Skype for Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="78f16-134">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="78f16-135">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="78f16-135">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="78f16-136">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="78f16-136">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="78f16-137">Klicken Sie in der Tabelle auf das Skype for Business Benutzerkonto, für das Sie den Anschluss-URI ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="78f16-137">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="78f16-138">Klicken Sie auf **Leitungs-URI**, und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="78f16-138">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="78f16-139">Klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="78f16-139">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="78f16-140">Aktualisieren der Wähleinstellungen mithilfe von lokalen Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="78f16-140">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="78f16-141">Sie können benutzerspezifische Wählpläne mit Windows PowerShell und dem Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78f16-141">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="78f16-142">Sie können dieses Cmdlet entweder im Skype for Business Server 2015 oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="78f16-142">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="78f16-143">So weisen Sie einem einzelnen Benutzer einen Wählplan pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="78f16-143">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="78f16-144">Verwenden Sie das [Grant-CsDialPlan-](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet, um den benutzerseitigen Wählplan "redmonddialplan" dem Benutzer Ken Myers zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="78f16-144">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="78f16-145">So weisen Sie mehreren Benutzern einen Wählplan pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="78f16-145">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="78f16-146">Mit dem folgenden Befehl wird der benutzerspezifische Wählplan "redmonddialplan" allen Benutzern zugewiesen, die in der Stadt Redmond arbeiten.</span><span class="sxs-lookup"><span data-stu-id="78f16-146">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="78f16-147">Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="78f16-147">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="78f16-148">Sie können entweder globale oder Benutzer-Wählpläne für Online-Benutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="78f16-148">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="78f16-149">Website Wähl Pläne können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="78f16-149">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="78f16-150">So heben Sie die Zuweisung von benutzerbezogenen Wähleinstellungen auf</span><span class="sxs-lookup"><span data-stu-id="78f16-150">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="78f16-151">Verwenden Sie das [Grant-CsDialPlan-](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Cmdlet, um die Zuweisung aller benutzerbezogenen Wähleinstellungen aufzuheben, die Ken Myers zuvor zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="78f16-151">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="78f16-152">Nachdem der benutzerbezogene Wählplan nicht zugewiesen wurde, wird Ken Myers automatisch mithilfe der globalen Wähleinstellungen oder des Dienstbereichs Wähl Plans verwaltet, der seiner Registrierungsstelle oder dem PSTN-Gateway zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="78f16-152">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="78f16-153">Ein Dienstbereich Wähleinstellungen hat Vorrang vor den globalen Wähleinstellungen:</span><span class="sxs-lookup"><span data-stu-id="78f16-153">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="78f16-154">Aktualisieren der VoIP-Routing Richtlinien mithilfe von lokalen Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="78f16-154">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="78f16-155">In diesem Abschnitt wird beschrieben, wie Sie die VoIP-Routing Richtlinien für für Telefonsysteme aktivierte Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-155">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="78f16-156">Telefon System Benutzern muss eine VoIP-Routing Richtlinie zugewiesen sein, damit Anrufe erfolgreich weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="78f16-156">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="78f16-157">Dies unterscheidet sich von lokalen Business Voice-Benutzern, denen eine VoIP-Richtlinie zugewiesen werden muss, damit Anrufe erfolgreich weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="78f16-157">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="78f16-158">Die VoIP-Routing Richtlinie sollte PSTN-Verwendungen enthalten, die autorisierte Anrufe und Routen für Telefon System Benutzer definieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-158">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="78f16-159">Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue VoIP-Routing Richtlinien kopieren.</span><span class="sxs-lookup"><span data-stu-id="78f16-159">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="78f16-160">Weitere Informationen finden Sie unter [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78f16-160">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="78f16-161">Allen Telefon System Benutzern wird dieselbe Online Sprachrichtlinie namens "BusinessVoice" zugewiesen, die die zulässigen Anruffunktionen definiert. lassen Sie beispielsweise gleichzeitigen Ring zu.</span><span class="sxs-lookup"><span data-stu-id="78f16-161">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="78f16-162">So weisen Sie einem einzelnen Benutzer eine VoIP-Routing Richtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="78f16-162">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="78f16-163">Verwenden Sie das [Grant-csvoiceroutingpolicy "-](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) Cmdlet, um die benutzerbasierte VoIP-Routing Richtlinie" redmondvoiceroutingpolicy "dem Benutzer Ken Myers zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="78f16-163">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="78f16-164">So weisen Sie mehreren Benutzern eine benutzerspezifische VoIP-Routing Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="78f16-164">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="78f16-165">Mit dem folgenden Befehl wird die benutzerspezifische VoIP-Routing Richtlinie "redmondvoiceroutingpolicy" allen Benutzern zugewiesen, die in der Stadt Redmond arbeiten.</span><span class="sxs-lookup"><span data-stu-id="78f16-165">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="78f16-166">Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78f16-166">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="78f16-167">Sie können entweder globale oder Benutzer-VoIP-Routing Richtlinien für Online-Benutzer verwenden.</span><span class="sxs-lookup"><span data-stu-id="78f16-167">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="78f16-168">Website VoIP-Routing Richtlinien können nicht verwendet werden, da diese nur für Benutzer gelten, die lokal gehostet werden und einem lokalen Standort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="78f16-168">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="78f16-169">So heben Sie die Zuweisung einer VoIP-Routing Richtlinie pro Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="78f16-169">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="78f16-170">Verwenden Sie das Grant-csvoiceroutingpolicy ", um die Zuweisung einer benutzerbasierten VoIP-Routing Richtlinie aufzuheben, die Ken Myers zuvor zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="78f16-170">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="78f16-171">Nachdem die Zuweisung der VoIP-Routing Richtlinie pro Benutzer aufgehoben wurde, wird Ken Myers automatisch mithilfe der globalen VoIP-Routing Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="78f16-171">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="78f16-172">Weitere Informationen finden Sie unter [Grant-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78f16-172">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

