---
title: Aktivieren von Benutzern für Enterprise-VoIP online und Telefonsystem in Office 365-Voicemail
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
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
description: Erfahren Sie, wie in Office 365-VoIP-Dienste für Ihre Skype für Unternehmensbenutzer Telefonsystem aktivieren.
ms.openlocfilehash: ef1e7b98ad4a6080d07dc4abca717aef49a725ed
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887904"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="5a148-103">Aktivieren von Benutzern für Enterprise-VoIP online und Telefonsystem in Office 365-Voicemail</span><span class="sxs-lookup"><span data-stu-id="5a148-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="5a148-104">Erfahren Sie, wie in Office 365-VoIP-Dienste für Ihre Skype für Unternehmensbenutzer Telefonsystem aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a148-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="5a148-105">Der letzte Schritt bei der Bereitstellung von Telefonsystem in Office 365 mit lokalen PSTN-Anbindung ist Ihre Benutzer für Telefonsystem in Office 365 und Voicemail aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a148-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="5a148-106">Um diese Funktionen aktivieren zu können, muss Ihnen als Benutzer in Office 365 die globale Administratorrolle zugewiesen sein, und Sie müssen in der Lage sein, Remote-PowerShell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5a148-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="5a148-107">Sie müssen die Schritte in diesem Abschnitt für alle Benutzerkonten ausführen, für die Enterprise-VoIP für Skype for Business Online noch nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5a148-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="5a148-108">Aktivieren Sie Telefonsystem in Office 365-VoIP-Dienste</span><span class="sxs-lookup"><span data-stu-id="5a148-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="5a148-109">Um einen Benutzer für Telefonsystem in Office 365-VoIP und Voicemail aktivieren, müssen Sie erste Schritte, wie das Prüfen von der Skype für Business Online Connector auf Ihren Servern bereitgestellt wird und Sie Ihre Benutzer für gehostete Voicemail aktivieren ausführen.</span><span class="sxs-lookup"><span data-stu-id="5a148-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see of the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="5a148-110">So aktivieren Sie Ihre Benutzer für Telefonsystem in Office 365 Sprach- und voicemail</span><span class="sxs-lookup"><span data-stu-id="5a148-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="5a148-111">Bevor Sie beginnen, überprüfen Sie, dass die Skype für Business Online Connector (Windows PowerShell-Modul) auf Front-End-Servern bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5a148-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="5a148-112">Wenn sie nicht der Fall ist, können Sie es aus [dem Downloadcenter](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="5a148-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="5a148-113">Sie finden weitere Informationen zur Verwendung in diesem Modul zur [Konfiguration des Computers für Skype für das Business Online Management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="5a148-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="5a148-114">Starten von Windows PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="5a148-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="5a148-115">Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5a148-115">Type the following and press Enter:</span></span>
    
  ```
  Import-Module skypeonlineconnector
  ```

4. <span data-ttu-id="5a148-116">Machen Sie folgende Eingabe und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5a148-116">Type the following and press Enter:</span></span>
    
  ```
  $cred = Get-Credential
  ```

    <span data-ttu-id="5a148-117">Nachdem Sie die EINGABETASTE gedrückt haben, sollte das Windows PowerShell-Dialogfeld für die Eingabe von Anmeldeinformationen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5a148-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="5a148-118">Geben Sie Ihren Mandantenadministrator-Benutzernamen und Ihr Kennwort ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a148-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="5a148-119">Machen Sie folgende Eingaben im PowerShell-Fenster und drücken Sie anschließend die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="5a148-119">In the PowerShell window, type the following and press Enter:</span></span>
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. <span data-ttu-id="5a148-120">Importieren Sie die Sitzung, indem Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="5a148-120">Import the session by typing the following cmdlet:</span></span>
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    <span data-ttu-id="5a148-121">Bei der Ausführung von PowerShell auf einen Skype für Business Server, die lokalen Skype für Business Cmdlets bereits geladen sind beim Öffnen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5a148-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="5a148-122">Geben Sie den Parameter AllowClobber - damit können die online-Cmdlets, die lokale-Cmdlets mit demselben Namen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5a148-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="5a148-123">Verwenden Sie das Cmdlet „Set-CsUser“ wie folgt, um Ihrem Benutzer die Eigenschaften „$EnterpriseVoiceEnabled“ und „$HostedVoiceMail“ zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="5a148-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    <span data-ttu-id="5a148-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5a148-124">For example:</span></span>
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > <span data-ttu-id="5a148-125">Sie können einen Benutzer genauso über seine SIP-Adresse, den Benutzerprinzipalnamen (UPN), den Domänennamen (Domäne\Benutzername) und den Displaynamen in Active Directory („Bob Kelly“) kenntlich machen.</span><span class="sxs-lookup"><span data-stu-id="5a148-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="5a148-126">Aktualisieren Sie den Anschluss-URI und Wähleinstellungen für Benutzer aktiviert für Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="5a148-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="5a148-127">In diesem Abschnitt wird beschrieben, wie zum Aktualisieren der Anschluss-URI und Wähleinstellungen für Benutzer in Office 365 Telefonsystem.</span><span class="sxs-lookup"><span data-stu-id="5a148-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="5a148-128">So aktualisieren Sie die Anschluss-URI</span><span class="sxs-lookup"><span data-stu-id="5a148-128">To update the Line URI</span></span>

1. <span data-ttu-id="5a148-129">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="5a148-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5a148-130">Benutzen Sie das Startmenü oder die Verknüpfung auf dem Desktop, um die Systemsteuerung von Skype for Business Server zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5a148-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a148-131">Alternativ können Sie ein Browserfenster öffnen und dort die Admin-URL eingeben, um zur Systemsteuerung von Skype for Business Server zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="5a148-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="5a148-132">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="5a148-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="5a148-133">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="5a148-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="5a148-134">Klicken Sie in der Tabelle auf das Skype for Business-Benutzerkonto, dessen Anschluss-URI Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="5a148-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="5a148-p104">Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (z. B. Tel:+14255550200). Klicken Sie dann auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5a148-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="5a148-137">Aktualisieren des Wählplans mithilfe lokaler Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5a148-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5a148-138">Pro Benutzer weisen Sie Wähleinstellungen mit Windows PowerShell und dem [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5a148-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="5a148-139">Sie können dieses Cmdlet entweder von der Skype für Business Server 2015 oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="5a148-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="5a148-140">So weisen Sie einem einzelnen Benutzer einen benutzerbasierten Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="5a148-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="5a148-141">Verwenden Sie das Cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) , dem Benutzer Ken Myer den benutzerspezifischen Wählplan RedmondDialPlan zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="5a148-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="5a148-142">So weisen Sie mehreren Benutzern einen benutzerbasierten Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="5a148-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="5a148-143">Mit dem folgenden Befehl wird der benutzerbasierte Wählplan „RedmondDialPlan“ allen Benutzern zugewiesen, die in Redmond arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a148-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="5a148-144">Weitere Informationen über die Parameter "LdapFilter" in diesem Befehl verwendet finden Sie in der Dokumentation für das Cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="5a148-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="5a148-p107">Möglicherweise verwenden Sie entweder globale oder Benutzerwähleinstellungen für Onlinebenutzer. Standortwählpläne können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5a148-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="5a148-147">So heben Sie die Zuweisung eines benutzerbasierten Wählplans auf</span><span class="sxs-lookup"><span data-stu-id="5a148-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="5a148-148">Verwenden Sie das [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) -Cmdlet zum Aufheben der Zuweisung von alle benutzerspezifischen Wählplan zuvor Ken Myer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5a148-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="5a148-149">Nachdem die Zuweisung des benutzerbezogenen Wählplans aufgehoben wurde, wird „Ken Myer“ automatisch mithilfe des globalen Wählplans oder des Wählplans auf Dienstebene für seine erweiterte Registrierungsstelle oder sein PSTN-Gateway verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5a148-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="5a148-150">Ein Wählplan auf Dienstebene hat Vorrang vor dem globalen Wählplan.</span><span class="sxs-lookup"><span data-stu-id="5a148-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="5a148-151">Aktualisieren der Richtlinien für das VoIP-Routing mithilfe von lokalen Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5a148-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="5a148-152">In diesem Abschnitt wird beschrieben, wie die VoIP-Routingrichtlinien zurückgegeben Telefonsystem in Office 365-fähigen Benutzer aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="5a148-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="5a148-153">Telefonsystem in Office 365-Benutzer benötigen eine VoIP-Routing-Richtlinie zugewiesen für Anrufe erfolgreich weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5a148-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="5a148-154">Das ist anders als bei lokalen Unternehmens-VoIP-Benutzern, denen eine VoIP-Richtlinie zugewiesen sein muss, damit Anrufe erfolgreich weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="5a148-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="5a148-155">Die VoIP-Routing-Richtlinie sollte PSTN-Verwendungen enthalten, die autorisierten Anrufe und Routen für Telefonsystem in Office 365-Benutzer zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5a148-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="5a148-156">Sie können diese PSTN-Verwendungen aus vorhandenen VoIP-Richtlinien in neue Richtlinien für das VoIP-Routing kopieren.</span><span class="sxs-lookup"><span data-stu-id="5a148-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="5a148-157">Weitere Informationen finden Sie unter ["New-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a148-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a148-158">Alle Telefonsystem in Office 365-Benutzer werden die gleichen online VoIP-Richtlinie mit dem Namen BusinessVoice definiert die zulässige Anruffunktion zugewiesen. Beispielsweise können Sie Gleichzeitiges Klingeln.</span><span class="sxs-lookup"><span data-stu-id="5a148-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="5a148-159">So weisen Sie einem einzelnen Benutzer eine Richtlinie für das VoIP-Routing auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="5a148-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="5a148-160">Verwenden Sie das Cmdlet ["Grant-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) , die pro Benutzer bei der VoIP-Routingrichtlinie "redmondvoiceroutingpolicy" dem Benutzer Ken Myer zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="5a148-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="5a148-161">So weisen Sie mehreren Benutzern eine Richtlinie für das VoIP-Routing auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="5a148-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="5a148-162">Mit dem nächsten Befehl wird die benutzerbasierte Richtlinie „RedmondVoiceRoutingPolicy“ allen Benutzern in der Stadt Redmond zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5a148-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="5a148-163">Weitere Informationen über die Parameter "LdapFilter" in diesem Befehl verwendet finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a148-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="5a148-p111">Möglicherweise verwenden Sie entweder globale Einstellungen oder Einstellungen für das VoIP-Routing für Onlinebenutzer. Standortrichtlinien für das VoIP-Routing können nicht verwendet werden, weil sie nur für Benutzer gelten, die lokal verwaltet werden und einem lokalen Standort zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5a148-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="5a148-166">So heben Sie die Zuweisung einer Richtlinie für das VoIP-Routing auf Benutzerebene auf</span><span class="sxs-lookup"><span data-stu-id="5a148-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="5a148-167">Verwenden Sie das Grant-CsVoiceRoutingPolicy zum Aufheben der Zuweisung von alle VoIP-Routingrichtlinie pro Benutzer zuvor Ken Myer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5a148-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="5a148-168">Nachdem die Zuweisung der benutzerbezogenen VoIP-Routingrichtlinie aufgehoben ist, wird „Ken Myer“ automatisch über die globale VoIP-Routingrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5a148-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="5a148-169">Weitere Informationen finden Sie unter ["Grant-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5a148-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

