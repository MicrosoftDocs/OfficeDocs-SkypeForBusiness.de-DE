---
title: Direct Routing SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über das direkte Routing, beispielsweise die Konfiguration, die erforderlichen zentralen Bereitstellungsentscheidungen und Überlegungen zu VoIP-Routing.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620726"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="ec55c-103">Überlebensfähige Branch Appliance (SBA) für direktes Routing – öffentliche Vorschau</span><span class="sxs-lookup"><span data-stu-id="ec55c-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="ec55c-104">Hierbei handelt es sich um eine öffentliche Preview-Version.</span><span class="sxs-lookup"><span data-stu-id="ec55c-104">This is a public preview release.</span></span>

<span data-ttu-id="ec55c-105">Gelegentlich kann es vorkommen, dass eine Kunden Website, die Direktes Routing zum Herstellen einer Verbindung mit dem Microsoft Phone System verwendet, einen internetausfall hat.</span><span class="sxs-lookup"><span data-stu-id="ec55c-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="ec55c-106">Davon ausgehen, dass die Kunden Website – so genannte Verzweigung – vorübergehend keine Verbindung mit der Microsoft-Cloud über direktes Routing herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="ec55c-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="ec55c-107">Das Intranet innerhalb der Verzweigung ist jedoch weiterhin voll funktionsfähig, und Benutzer können eine Verbindung mit dem Session Border Controller (SBC) herstellen, der PSTN-Konnektivität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ec55c-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="ec55c-108">In diesem Artikel wird beschrieben, wie Sie eine Survivable Branch Appliance (SBA) verwenden, damit Microsoft Phone System im Fall eines Ausfalls weiterhin PSTN-Anrufe (Public Switched Telephone Network) durchführen und empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="ec55c-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec55c-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ec55c-109">Prerequisites</span></span>

<span data-ttu-id="ec55c-110">Die SBA ist ein Verteilungs Code, der von Microsoft an SBC-Anbieter bereitgestellt wird, die dann Code in Ihre Firmware einbetten oder separat verteilen, damit SBA auf einem separaten VM oder auf einer anderen Hardware ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ec55c-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="ec55c-111">Wenden Sie sich an Ihren SBC-Anbieter, um die neueste Session Border Controller-Firmware mit der eingebetteten Survivable Branch-Appliance zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ec55c-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="ec55c-112">Darüber hinaus ist Folgendes erforderlich:</span><span class="sxs-lookup"><span data-stu-id="ec55c-112">In addition, the following is required:</span></span>

- <span data-ttu-id="ec55c-113">Der SBC muss für die medienumgehung konfiguriert werden, um sicherzustellen, dass der Microsoft Teams-Client auf der Verzweigungs Website Medien direkt mit dem SBC fließen lassen kann.</span><span class="sxs-lookup"><span data-stu-id="ec55c-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="ec55c-114">TLS 1.2 sollte auf dem SBA VM-Betriebssystem aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="ec55c-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="ec55c-115">Unterstützte Teams-Clients</span><span class="sxs-lookup"><span data-stu-id="ec55c-115">Supported Teams clients</span></span>

<span data-ttu-id="ec55c-116">Das SBA-Feature wird für die folgenden Microsoft Teams-Clients unterstützt:</span><span class="sxs-lookup"><span data-stu-id="ec55c-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="ec55c-117">Microsoft Teams Windows-Desktop</span><span class="sxs-lookup"><span data-stu-id="ec55c-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="ec55c-118">Microsoft Teams macOS Desktop</span><span class="sxs-lookup"><span data-stu-id="ec55c-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="ec55c-119">Funktionsweise</span><span class="sxs-lookup"><span data-stu-id="ec55c-119">How it works</span></span>

<span data-ttu-id="ec55c-120">Bei einem internetausfall sollte der Team-Client automatisch zur SBA wechseln, und die laufenden Anrufe sollten ohne Unterbrechungen fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ec55c-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="ec55c-121">Vom Benutzer ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec55c-121">No action is required from the user.</span></span> <span data-ttu-id="ec55c-122">Sobald der Team-Client feststellt, dass das Internet aktiviert ist und alle ausgehenden Anrufe ablaufen, wird der Client wieder in den normalen Betriebsmodus versetzt und mit anderen Teams-Diensten verbunden.</span><span class="sxs-lookup"><span data-stu-id="ec55c-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="ec55c-123">Die SBA wird gesammelte anrufdatensätze in die Cloud hochladen, und der ANRUFVERLAUF wird aktualisiert, damit diese Informationen vom mandantenadministrator zur Überprüfung zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="ec55c-124">Wenn sich der Microsoft Teams-Client im Offlinemodus befindet, stehen die folgenden anrufbezogenen Funktionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ec55c-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="ec55c-125">Durchführen von PSTN-anrufen über lokales SBA/SBC mit Medien, die über den SBC fließen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="ec55c-126">Empfangen von PSTN-anrufen über lokales SBA/SBC mit Medien, die über den SBC fließen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="ec55c-127">Anhalten und Fortsetzen von PSTN-anrufen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="ec55c-128">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ec55c-128">Configuration</span></span>

<span data-ttu-id="ec55c-129">Damit die SBA-Funktion funktioniert, muss der Team-Client wissen, welche SBAS in jeder Verzweigungs Website verfügbar sind und welche SBAS den Benutzern auf dieser Website zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="ec55c-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="ec55c-130">Die Konfigurationsschritte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="ec55c-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="ec55c-131">Erstellen Sie den SBAS.</span><span class="sxs-lookup"><span data-stu-id="ec55c-131">Create the SBAs.</span></span>
2. <span data-ttu-id="ec55c-132">Erstellen Sie die Survival-Richtlinie für Teams.</span><span class="sxs-lookup"><span data-stu-id="ec55c-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="ec55c-133">Weisen Sie die Richtlinie Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="ec55c-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="ec55c-134">Registrieren Sie eine Anwendung für die SBA mit Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ec55c-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="ec55c-135">Die gesamte Konfiguration erfolgt mithilfe der PowerShell-Cmdlets von Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ec55c-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="ec55c-136">(Das Team Admin Center unterstützt noch nicht das Direct Routing SBA-Feature.)</span><span class="sxs-lookup"><span data-stu-id="ec55c-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="ec55c-137">(Informationen zum Konfigurieren des SBC mit Links zur SBC-Lieferantendokumentation finden Sie unter Konfiguration des Sitzungs Grenz Controllers am Ende dieses Artikels.)</span><span class="sxs-lookup"><span data-stu-id="ec55c-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="ec55c-138">Erstellen der SBAS</span><span class="sxs-lookup"><span data-stu-id="ec55c-138">Create the SBAs</span></span>

<span data-ttu-id="ec55c-139">Zum Erstellen des SBAS verwenden Sie das New-CsTeamsSurvivableBranchAppliance-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec55c-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="ec55c-140">Dieses Cmdlet verfügt über die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="ec55c-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="ec55c-141">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec55c-141">Parameter</span></span>| <span data-ttu-id="ec55c-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec55c-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ec55c-143">Identity</span><span class="sxs-lookup"><span data-stu-id="ec55c-143">Identity</span></span>  | <span data-ttu-id="ec55c-144">Die Identität des SBA</span><span class="sxs-lookup"><span data-stu-id="ec55c-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="ec55c-145">FQDN</span><span class="sxs-lookup"><span data-stu-id="ec55c-145">Fqdn</span></span> | <span data-ttu-id="ec55c-146">Der FQDN des SBA</span><span class="sxs-lookup"><span data-stu-id="ec55c-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="ec55c-147">Standort</span><span class="sxs-lookup"><span data-stu-id="ec55c-147">Site</span></span> | <span data-ttu-id="ec55c-148">Der TenantNetworkSite, in dem sich die SBA befindet</span><span class="sxs-lookup"><span data-stu-id="ec55c-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="ec55c-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec55c-149">Description</span></span> | <span data-ttu-id="ec55c-150">Kostenloses Formatieren von Text</span><span class="sxs-lookup"><span data-stu-id="ec55c-150">Free format text</span></span> |
|||

<span data-ttu-id="ec55c-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ec55c-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="ec55c-152">Erstellen der Survivable-Richtlinie für Teams</span><span class="sxs-lookup"><span data-stu-id="ec55c-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="ec55c-153">Zum Erstellen einer Richtlinie verwenden Sie das New-CsTeamsSurvivableBranchAppliancePolicy-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ec55c-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ec55c-154">Dieses Cmdlet verfügt über die folgenden Parameter.</span><span class="sxs-lookup"><span data-stu-id="ec55c-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="ec55c-155">Beachten Sie, dass die Richtlinie mindestens eine SBAS enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="ec55c-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="ec55c-156">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec55c-156">Parameter</span></span>| <span data-ttu-id="ec55c-157">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec55c-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ec55c-158">Identity</span><span class="sxs-lookup"><span data-stu-id="ec55c-158">Identity</span></span> | <span data-ttu-id="ec55c-159">Die Identität der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ec55c-159">The identity of the policy</span></span> |
| <span data-ttu-id="ec55c-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="ec55c-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="ec55c-161">Der FQDN der SBA (s) auf der Website</span><span class="sxs-lookup"><span data-stu-id="ec55c-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="ec55c-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ec55c-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="ec55c-163">Mithilfe des Set-CsTeamsSurvivableBranchAppliancePolicy-Cmdlets können Sie einer Richtlinie SBAS hinzufügen oder daraus entfernen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ec55c-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ec55c-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="ec55c-165">Zuweisen einer Richtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec55c-165">Assign a policy to a user</span></span>

<span data-ttu-id="ec55c-166">Wenn Sie die Richtlinie einzelnen Benutzern zuweisen möchten, verwenden Sie das Cmdlet Grant-CsTeamsSurvivableBranchAppliancePolicy.</span><span class="sxs-lookup"><span data-stu-id="ec55c-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="ec55c-167">Dieses Cmdlet verfügt über die folgenden Parameter:</span><span class="sxs-lookup"><span data-stu-id="ec55c-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="ec55c-168">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec55c-168">Parameter</span></span>| <span data-ttu-id="ec55c-169">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec55c-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="ec55c-170">Identity</span><span class="sxs-lookup"><span data-stu-id="ec55c-170">Identity</span></span> | <span data-ttu-id="ec55c-171">Die Identität des Benutzers</span><span class="sxs-lookup"><span data-stu-id="ec55c-171">The identity of the user</span></span> |
| <span data-ttu-id="ec55c-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="ec55c-172">PolicyName</span></span> | <span data-ttu-id="ec55c-173">Die Identität der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ec55c-173">The identity of the policy</span></span> |
||

<span data-ttu-id="ec55c-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ec55c-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="ec55c-175">Sie können eine Richtlinie von einem Benutzer entfernen, indem Sie die $NULL Richtlinie zuweisen, wie im nächsten Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec55c-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="ec55c-176">Registrieren einer Anwendung für die SBA mit Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ec55c-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="ec55c-177">Damit andere SBAS, die in Ihrem Mandanten verwendet werden, erforderliche Daten von Microsoft 365 lesen können, müssen Sie eine Anwendung für die SBA mit Azure Active Directory registrieren.</span><span class="sxs-lookup"><span data-stu-id="ec55c-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="ec55c-178">Weitere Informationen zur Anwendungsregistrierung finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ec55c-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="ec55c-179">Entwickeln von Branchen-Apps für Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ec55c-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="ec55c-180">[Registrieren Sie eine Anwendung mit der Microsoft Identity-Plattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="ec55c-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="ec55c-181">Sie müssen nur eine Anwendung für die Verwendung durch alle SBAS in Ihrem Mandanten registrieren.</span><span class="sxs-lookup"><span data-stu-id="ec55c-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="ec55c-182">Für die Registrierung von SBA benötigen Sie die folgenden Werte, die durch die Registrierung erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="ec55c-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="ec55c-183">Anwendungs-ID (Client)</span><span class="sxs-lookup"><span data-stu-id="ec55c-183">Application (client) ID</span></span> 
- <span data-ttu-id="ec55c-184">Kundengeheimnis</span><span class="sxs-lookup"><span data-stu-id="ec55c-184">Client secret</span></span> 

<span data-ttu-id="ec55c-185">Beachten Sie bei der SBA-Anwendung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ec55c-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="ec55c-186">Der Name kann sein, was auch immer Sie sich entscheiden.</span><span class="sxs-lookup"><span data-stu-id="ec55c-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="ec55c-187">Unterstützte Kontotypen = Konto nur in diesem Organisations Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ec55c-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="ec55c-188">Das Web Redirect URI = https://login.microsoftonline.com/common/oauth2/nativeclient .</span><span class="sxs-lookup"><span data-stu-id="ec55c-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="ec55c-189">Implizite Grant-Tokens = Zugriffstoken und ID-Token.</span><span class="sxs-lookup"><span data-stu-id="ec55c-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="ec55c-190">API-Berechtigungen = Skype und Teams mandantenadministrator Zugriff – > Anwendungsberechtigungen – > application_access_custom_sba_appliance.</span><span class="sxs-lookup"><span data-stu-id="ec55c-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="ec55c-191">Client-Secret: Sie können jede Beschreibung und Ablaufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec55c-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="ec55c-192">Vergessen Sie nicht, den Client-Schlüssel unmittelbar nach dem erstellen zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="ec55c-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="ec55c-193">Die Anwendungs-ID (Client) wird auf der Registerkarte Übersicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec55c-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="ec55c-194">Führen Sie dann die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ec55c-194">Then follow these steps:</span></span>

1. <span data-ttu-id="ec55c-195">Registrieren Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ec55c-195">Register the application.</span></span>
2. <span data-ttu-id="ec55c-196">Setzen Sie die impliziten Grant-Token.</span><span class="sxs-lookup"><span data-stu-id="ec55c-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="ec55c-197">Setzen Sie die API-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-197">Set the API permissions.</span></span>
4. <span data-ttu-id="ec55c-198">Erstellen Sie den geheimen Client.</span><span class="sxs-lookup"><span data-stu-id="ec55c-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="ec55c-199">Session Border Controller-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ec55c-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="ec55c-200">Eine Schritt-für-Schritt-Anleitung zum Konfigurieren Ihres Session Border Controllers mit der eingebetteten Survivable Branch-Appliance finden Sie in der Dokumentation Ihres SBC-Anbieters:</span><span class="sxs-lookup"><span data-stu-id="ec55c-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="ec55c-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="ec55c-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="ec55c-202">Multifunktionsleiste</span><span class="sxs-lookup"><span data-stu-id="ec55c-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="ec55c-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="ec55c-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="ec55c-204">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="ec55c-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="ec55c-205">Melden von Problemen</span><span class="sxs-lookup"><span data-stu-id="ec55c-205">Reporting issues</span></span>

<span data-ttu-id="ec55c-206">Melden Sie alle Probleme an die Support Organisation Ihres SBC-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="ec55c-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="ec55c-207">Wenn Sie das Problem melden, geben Sie an, dass Sie über eine konfigurierte Survivable Branch-Appliance verfügen.</span><span class="sxs-lookup"><span data-stu-id="ec55c-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="ec55c-208">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="ec55c-208">Known issues</span></span>

- <span data-ttu-id="ec55c-209">Wenn Sie neue überlebensfähige Branch Appliances hinzufügen, kann es einige Zeit dauern, bis Sie Sie in Survivable Branch Appliance-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ec55c-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="ec55c-210">Wenn Sie einem Benutzer eine Survivable Branch Appliance-Richtlinie zuweisen, kann es einige Zeit dauern, bis die SBA in der Ausgabe von Get-CsOnlineUser angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ec55c-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="ec55c-211">Umgekehrte Nummernsuche mit Azure AD-Kontakten wird nicht durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="ec55c-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="ec55c-212">Die SBA unterstützt keine Einstellungen für die Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="ec55c-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="ec55c-213">Das tätigen eines Notrufs an eine Notrufnummer, die für Dynamic Emergency Calling (E911) konfiguriert ist, wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec55c-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="ec55c-214">Die Ausgabe von Get-CsOnlineUser zeigt TeamsBranchSurvivabilityPolicy.</span><span class="sxs-lookup"><span data-stu-id="ec55c-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
