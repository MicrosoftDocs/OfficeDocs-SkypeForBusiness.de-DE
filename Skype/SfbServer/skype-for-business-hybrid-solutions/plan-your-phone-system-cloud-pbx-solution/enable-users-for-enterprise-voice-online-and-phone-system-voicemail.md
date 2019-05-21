---
title: Aktivieren von Benutzern für Enterprise-VoIP und für Telefonsystem in Office 365 Voicemail
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Erfahren Sie, wie Sie das Telefon System in Office 365 Voice Services für Ihre Skype for Business-Benutzer aktivieren.
ms.openlocfilehash: 1305f4045d4de86a65e0286938d22490f577507c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287503"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="159dc-103">Aktivieren von Benutzern für Enterprise-VoIP und für Telefonsystem in Office 365 Voicemail</span><span class="sxs-lookup"><span data-stu-id="159dc-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="159dc-104">Erfahren Sie, wie Sie das Telefon System in Office 365 Voice Services für Ihre Skype for Business-Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="159dc-105">Der letzte Schritt beim Bereitstellen von Telefonsystem in Office 365 mit lokalen PSTN-Konnektivität besteht darin, Ihre Benutzer für das Telefonsystem in Office 365 und Voicemail zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="159dc-106">Um diese Funktionen aktivieren zu können, muss Ihnen als Benutzer in Office 365 die globale Administratorrolle zugewiesen sein, und Sie müssen in der Lage sein, Remote-PowerShell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="159dc-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="159dc-107">Sie müssen die Schritte in diesem Abschnitt für alle Benutzerkonten ausführen, für die Enterprise-VoIP für Skype for Business Online noch nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="159dc-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="159dc-108">Aktivieren des Telefonsystems in Office 365 Voice Services</span><span class="sxs-lookup"><span data-stu-id="159dc-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="159dc-109">Wenn Sie einen Benutzer für das Telefon System in Office 365 Voice und Voicemail aktivieren möchten, müssen Sie einige erste Schritte ausführen, beispielsweise überprüfen, ob der Skype for Business Online-Connector auf Ihren Servern bereitgestellt wird, und Ihre Benutzer für die gehostete Voicemail aktivieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="159dc-110">So aktivieren Sie Ihre Benutzer für das Telefon System in Office 365 Voice und Voicemail</span><span class="sxs-lookup"><span data-stu-id="159dc-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="159dc-111">Bevor Sie beginnen, überprüfen Sie, ob der Skype for Business Online Connector (Windows PowerShell-Modul) auf Ihren Front-End-Servern bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="159dc-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="159dc-112">Wenn dies nicht der Fall ist, können Sie Sie aus [dem Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="159dc-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="159dc-113">Weitere Informationen zur Verwendung dieses Moduls finden Sie unter [Konfigurieren Ihres Computers für die Skype for Business Online-Verwaltung](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="159dc-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="159dc-114">Starten von Windows PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="159dc-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="159dc-115">Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="159dc-115">Type the following and press Enter:</span></span>
    
   ```
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="159dc-116">Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="159dc-116">Type the following and press Enter:</span></span>
    
   ```
   $cred = Get-Credential
   ```

    <span data-ttu-id="159dc-117">Nachdem Sie die EINGABETASTE gedrückt haben, sollte das Windows PowerShell-Dialogfeld für die Eingabe von Anmeldeinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="159dc-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="159dc-118">Geben Sie Ihren Mandantenadministrator-Benutzernamen und Ihr Kennwort ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="159dc-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="159dc-119">Machen Sie folgende Eingaben im PowerShell-Fenster und drücken Sie anschließend die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="159dc-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="159dc-120">Importieren Sie die Sitzung, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="159dc-120">Import the session by typing the following cmdlet:</span></span>
    
   ```
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="159dc-121">Wenn PowerShell auf einem Skype for Business-Server ausgeführt wird, sind die lokalen Cmdlets für Skype for Business bereits geladen, wenn Sie PowerShell öffnen.</span><span class="sxs-lookup"><span data-stu-id="159dc-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="159dc-122">Sie müssen den-AllowClobber-Parameter angeben, damit die Online-Cmdlets die lokalen Cmdlets mit demselben Namen überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="159dc-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="159dc-123">Verwenden Sie das Cmdlet „Set-CsUser“ wie folgt, um Ihrem Benutzer die Eigenschaften „$EnterpriseVoiceEnabled“ und „$HostedVoiceMail“ zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="159dc-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="159dc-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="159dc-124">For example:</span></span>
    
   ```
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="159dc-125">Sie können einen Benutzer genauso über seine SIP-Adresse, den Benutzerprinzipalnamen (UPN), den Domänennamen (Domäne\Benutzername) und den Displaynamen in Active Directory („Bob Kelly“) kenntlich machen.</span><span class="sxs-lookup"><span data-stu-id="159dc-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="159dc-126">Aktualisieren des Leitungs-URIs und des Wählplans für Benutzer, die für das Telefon System in Office 365 aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="159dc-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="159dc-127">In diesem Abschnitt wird beschrieben, wie Sie den Zeilen-URI und den Wählplan für für Telefonsysteme aktivierte Benutzer in Office 365 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="159dc-128">So aktualisieren Sie die Anschluss-URI</span><span class="sxs-lookup"><span data-stu-id="159dc-128">To update the Line URI</span></span>

1. <span data-ttu-id="159dc-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="159dc-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="159dc-130">Benutzen Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Systemsteuerung von Skype for Business Server zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="159dc-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="159dc-131">Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="159dc-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="159dc-132">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="159dc-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="159dc-133">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="159dc-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="159dc-134">Klicken Sie in der Tabelle auf das Skype for Business-Benutzerkonto, dessen Anschluss-URI Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="159dc-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="159dc-p104">Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. Tel:+14255550200). Klicken Sie dann auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="159dc-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="159dc-137">Aktualisieren des Wählplans mithilfe lokaler Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="159dc-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="159dc-138">Sie können Wählpläne für einzelne Benutzer mit Windows PowerShell und dem Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="159dc-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="159dc-139">Sie können dieses Cmdlet entweder über den Skype for Business Server 2015 oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="159dc-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="159dc-140">So weisen Sie einem einzelnen Benutzer einen benutzerbasierten Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="159dc-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="159dc-141">Verwenden Sie das Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , um dem Benutzer Ken Myers den benutzerseitigen Wähl Plan redmonddialplan "zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="159dc-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="159dc-142">So weisen Sie mehreren Benutzern einen benutzerbasierten Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="159dc-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="159dc-143">Mit dem folgenden Befehl wird der benutzerbasierte Wählplan „RedmondDialPlan“ allen Benutzern zugewiesen, die in Redmond arbeiten.</span><span class="sxs-lookup"><span data-stu-id="159dc-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="159dc-144">Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="159dc-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="159dc-p107">Möglicherweise verwenden Sie entweder globale oder Benutzerwähleinstellungen für Onlinebenutzer. Standortwählpläne können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="159dc-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="159dc-147">So heben Sie die Zuweisung eines benutzerbasierten Wählplans auf</span><span class="sxs-lookup"><span data-stu-id="159dc-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="159dc-148">Verwenden Sie das Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , um die Zuweisung von benutzerseitigen Wählplänen aufzuheben, die Ken Myers zuvor zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="159dc-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="159dc-149">Nachdem die Zuweisung des benutzerbezogenen Wählplans aufgehoben wurde, wird „Ken Myer“ automatisch mithilfe des globalen Wählplans oder des Wählplans auf Dienstebene für seine erweiterte Registrierungsstelle oder sein PSTN-Gateway verwaltet.</span><span class="sxs-lookup"><span data-stu-id="159dc-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="159dc-150">Ein Wählplan auf Dienstebene hat Vorrang vor dem globalen Wählplan.</span><span class="sxs-lookup"><span data-stu-id="159dc-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="159dc-151">Aktualisieren der Richtlinien für das VoIP-Routing mithilfe von lokalen Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="159dc-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="159dc-152">In diesem Abschnitt wird beschrieben, wie Sie die VoIP-Routing Richtlinien für Benutzer, die für das Telefon System aktiviert sind, in Office 365 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="159dc-153">Telefon System in Office 365 Benutzern muss eine VoIP-Routing Richtlinie zugewiesen sein, damit Anrufe erfolgreich weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="159dc-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="159dc-154">Das ist anders als bei lokalen Unternehmens-VoIP-Benutzern, denen eine VoIP-Richtlinie zugewiesen sein muss, damit Anrufe erfolgreich weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="159dc-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="159dc-155">Die VoIP-Routing Richtlinie sollte PSTN-Nutzungen enthalten, die autorisierte Anrufe und Routen für Telefonsysteme in Office 365-Benutzern definieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="159dc-156">Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue Richtlinien für das VoIP-Routing kopieren.</span><span class="sxs-lookup"><span data-stu-id="159dc-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="159dc-157">Weitere Informationen finden Sie unter [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="159dc-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="159dc-158">Alle Telefonsysteme in Office 365 Benutzern wird dieselbe Online-VoIP-Richtlinie mit dem Namen BusinessVoice zugewiesen, in der die zulässigen Anruffunktionen definiert sind. So können Sie beispielsweise Gleichzeitiges Klingeln zulassen.</span><span class="sxs-lookup"><span data-stu-id="159dc-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="159dc-159">So weisen Sie einem einzelnen Benutzer eine Richtlinie für das VoIP-Routing auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="159dc-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="159dc-160">Verwenden Sie das Cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) , um dem Benutzer Ken Myers die benutzerspezifische VoIP-Routing Richtlinien-RedmondVoiceRoutingPolicy zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="159dc-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="159dc-161">So weisen Sie mehreren Benutzern eine Richtlinie für das VoIP-Routing auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="159dc-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="159dc-162">Mit dem nächsten Befehl wird die benutzerbasierte Richtlinie „RedmondVoiceRoutingPolicy“ allen Benutzern in der Stadt Redmond zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="159dc-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="159dc-163">Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="159dc-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="159dc-p111">Möglicherweise verwenden Sie entweder globale Einstellungen oder Einstellungen für das VoIP-Routing für Onlinebenutzer. Standortrichtlinien für das VoIP-Routing können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="159dc-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="159dc-166">So heben Sie die Zuweisung einer Richtlinie für das VoIP-Routing auf Benutzerebene auf</span><span class="sxs-lookup"><span data-stu-id="159dc-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="159dc-167">Verwenden Sie die Grant-CsVoiceRoutingPolicy, um die Zuweisung einer benutzerseitigen VoIP-Routing Richtlinie aufzuheben, die Ken Myers zuvor zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="159dc-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="159dc-168">Nachdem die Zuweisung der benutzerbezogenen VoIP-Routingrichtlinie aufgehoben ist, wird „Ken Myer“ automatisch über die globale VoIP-Routingrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="159dc-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="159dc-169">Weitere Informationen finden Sie unter [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="159dc-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

