---
title: Bereitstellen der Darstellung freigegebener Leitungen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in Skype for Business Server 2015, November 2015, Kumulatives Update, bereitstellen. SLA ist ein Feature für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.
ms.openlocfilehash: 6ad7d6fca40975990fdd6f6ed01bbb89c185e9e7
ms.sourcegitcommit: a34a827dfdad05b281e2e5ec5a80fc4e67fc89e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604222"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="6cb7c-104">Bereitstellen der Darstellung freigegebener Leitungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6cb7c-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="6cb7c-105">Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in Skype for Business Server 2015, November 2015, Kumulatives Update, bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update.</span></span> <span data-ttu-id="6cb7c-106">SLA ist ein Feature für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="6cb7c-107">Weitere Informationen zu dieser Funktion finden Sie unter [Planen der Darstellung freigegebener Leitungen in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="6cb7c-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="6cb7c-108">Die Darstellung freigegebener Leitungen (SLA) ist ein neues Feature in Skype for Business Server, November 2015 Kumulatives Update.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="6cb7c-109">Zum Aktivieren dieses Features müssen Sie zunächst dieses kumulative Update bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="6cb7c-110">Installieren der Darstellung freigegebener Leitungen</span><span class="sxs-lookup"><span data-stu-id="6cb7c-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="6cb7c-111">Nachdem Skype for Business Server November 2015 Kumulatives Update bereitgestellt wurde, führen `SkypeServerUpdateInstaller.exe` Sie den Patch auf jeder Front-End-Server im Pool aus.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="6cb7c-112">Das Installationsprogramm stellt die neueste Version der SLA-Anwendung bereit, die Anwendung ist jedoch standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-112">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default.</span></span> <span data-ttu-id="6cb7c-113">Sie wird mithilfe der unten aufgeführten Schritte aktiviert:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-113">It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="6cb7c-114">a.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-114">a.</span></span> <span data-ttu-id="6cb7c-115">Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="6cb7c-116">Dabei ist% FQDN% der vollqualifizierte Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="6cb7c-117">b.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-117">b.</span></span> <span data-ttu-id="6cb7c-118">Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```powershell
   Update-CsAdminRole
   ```

    <span data-ttu-id="6cb7c-119">c.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-119">c.</span></span> <span data-ttu-id="6cb7c-120">Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="6cb7c-121">Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern zu ihr</span><span class="sxs-lookup"><span data-stu-id="6cb7c-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="6cb7c-122">Erstellen Sie die SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) ":</span><span class="sxs-lookup"><span data-stu-id="6cb7c-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="6cb7c-123">Das Cmdlet "CsSlaConfiguration" kennzeichnet das SLAGroup1 des Enterprise-VoIP-Kontos als SLA-Entität, und die Anzahl der SLAGroup1 wird zur Nummer für die SLA-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-123">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="6cb7c-124">Alle Anrufe an SLAGroup1 rufen die gesamte SLA-Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-124">All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="6cb7c-125">Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP-Benutzer SLAGroup1 erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptnummer verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="6cb7c-126">Mit dem Befehl wird die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 festgelegt, und für Anrufe, die darüber hinausgehen, um ein Besetztzeichen zu hören:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="6cb7c-127">Mithilfe von "CsSlaConfiguration" können Sie eine neue SLA-Gruppe erstellen oder eine vorhandene ändern.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6cb7c-128">Beachten Sie, dass für `-Identity` ein gültiges vorhandenes Enterprise-VoIP-aktiviertes Benutzerkonto angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="6cb7c-129">Fügen Sie der Gruppe Stellvertretungen mithilfe des Cmdlets [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) hinzu:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="6cb7c-130">Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="6cb7c-131">Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Benutzer mit Enterprise-VoIP sein:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="6cb7c-132">Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-132">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="6cb7c-133">Benutzer können nur zu einer einzelnen SLA-Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-133">Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="6cb7c-134">Konfigurieren der Option "besetzt" der SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="6cb7c-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="6cb7c-135">Konfigurieren Sie die Option "besetzt" der SLA [-](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) Gruppe mithilfe des Cmdlets "CsSlaConfiguration":</span><span class="sxs-lookup"><span data-stu-id="6cb7c-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="6cb7c-136">Im folgenden Beispiel werden Aufrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="6cb7c-137">Bei dem Ziel kann es sich um einen Benutzer in Ihrer Organisation anstelle einer Telefonnummer handeln. in diesem Fall ist die Syntax für die Person, die weitergeleitete Anrufe erhalten soll, identisch mit der Angabe eines `sip:<NameofDelegate@domain>`Delegaten:.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="6cb7c-138">Der andere mögliche Parameter für `BusyOption` ist `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="6cb7c-139">Konfigurieren der Option "verpasste Anrufe bei SLA-Gruppen"</span><span class="sxs-lookup"><span data-stu-id="6cb7c-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="6cb7c-140">Konfigurieren Sie die Option für den verpassten Anruf der SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) ":</span><span class="sxs-lookup"><span data-stu-id="6cb7c-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="6cb7c-141">Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit `sla_forward_number`dem Namen weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="6cb7c-142">Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward`, `BusySignal`oder `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="6cb7c-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="6cb7c-143">Wenn Sie sich `Forward`entscheiden, müssen Sie auch den `-MissedCallForwardTarget` Parameter mit einer Benutzer-oder Telefonnummer als Ziel einschließen:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="6cb7c-144">Entfernen eines Stellvertreters aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="6cb7c-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="6cb7c-145">Entfernen Sie eine Stellvertretung aus einer Gruppe mithilfe des Cmdlets [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="6cb7c-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="6cb7c-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-146">For example:</span></span>

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="6cb7c-147">Löschen einer SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="6cb7c-147">Delete an SLA group</span></span>

- <span data-ttu-id="6cb7c-148">Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="6cb7c-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="6cb7c-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6cb7c-149">For example:</span></span>

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


