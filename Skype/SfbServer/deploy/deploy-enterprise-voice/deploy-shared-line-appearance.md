---
title: Bereitstellen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lesen Sie dieses Thema und finden Sie heraus, wie die Funktion „Gemeinsame Leitungen“ (SLA) in Skype for Business Server 2015, kumulatives Update vom November 2015, bereitzustellen ist. Bei SLA handelt es sich um eine Funktion zum Verarbeiten mehrerer Anrufe an eine bestimmte Nummer, die als gemeinsam genutzte Nummer bezeichnet wird.
ms.openlocfilehash: 040801c08490edb103fa195098ef8aa3483fc2e0
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924856"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a><span data-ttu-id="56c32-104">Bereitstellen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="56c32-104">Deploy Shared Line Appearance in Skype for Business Server 2015</span></span>

<span data-ttu-id="56c32-p102">Lesen Sie dieses Thema und finden Sie heraus, wie die Funktion „Gemeinsame Leitungen“ (SLA) in Skype for Business Server 2015, kumulatives Update vom November 2015, bereitzustellen ist. Bei SLA handelt es sich um eine Funktion zum Verarbeiten mehrerer Anrufe an eine bestimmte Nummer, die als gemeinsam genutzte Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="56c32-p102">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Skype for Business Server 2015, November 2015 Cumulative Update. SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="56c32-107">Mehr über diese Funktion erfahren Sie unter [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="56c32-107">For more information about this feature, see [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).</span></span>

<span data-ttu-id="56c32-108">Die gemeinsame Leitungsdarstellung (SLA) ist ein neues Feature in Skype for Business Server, 2015, Kumulatives Update vom November.</span><span class="sxs-lookup"><span data-stu-id="56c32-108">Shared Line Appearance (SLA) is a new feature in Skype for Business Server, November 2015 Cumulative Update.</span></span> <span data-ttu-id="56c32-109">Um dieses Feature zu aktivieren, müssen Sie zuerst dieses kumulative Update bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="56c32-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

### <a name="install-shared-line-appearance"></a><span data-ttu-id="56c32-110">Installieren der Funktion „Gemeinsame Leitungen“</span><span class="sxs-lookup"><span data-stu-id="56c32-110">Install Shared Line Appearance</span></span>

1. <span data-ttu-id="56c32-111">Führen Sie nach dem Skype for Business-Server, dem kumulativen Update vom `SkypeServerUpdateInstaller.exe` November 2015, den Patch auf jedem Front-End-Server im Pool aus.</span><span class="sxs-lookup"><span data-stu-id="56c32-111">After Skype for Business Server, November 2015 Cumulative Update is deployed, run the  `SkypeServerUpdateInstaller.exe` patch on each Front End Server in the pool.</span></span>

2. <span data-ttu-id="56c32-p104">Der Installer stellt die aktuelle Version der SLA-Anwendung bereit, allerdings ist diese Anwendung nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die folgenden Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="56c32-p104">The installer will deploy the latest version of the SLA application, however, the application is not enabled by default. It is enabled by following the steps outlined below:</span></span>

    <span data-ttu-id="56c32-114">a.</span><span class="sxs-lookup"><span data-stu-id="56c32-114">a.</span></span> <span data-ttu-id="56c32-115">Registrieren Sie SLA als Serveranwendung, indem Sie für jeden Pool den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="56c32-115">Register SLA as a server application by running the following command for each pool:</span></span>

   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   <span data-ttu-id="56c32-116">Dabei ist %FQDN% der vollqualifizierte Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="56c32-116">where %FQDN% is the fully qualified domain name of the pool.</span></span>

    <span data-ttu-id="56c32-117">b.</span><span class="sxs-lookup"><span data-stu-id="56c32-117">b.</span></span> <span data-ttu-id="56c32-118">Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="56c32-118">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>

   ```
   Update-CsAdminRole
   ```

    <span data-ttu-id="56c32-119">c.</span><span class="sxs-lookup"><span data-stu-id="56c32-119">c.</span></span> <span data-ttu-id="56c32-120">Starten Sie alle Front-End-Server (RTCSRV-Dienst) in sämtlichen Pools neu, in denen SLA installiert und aktiviert worden ist:</span><span class="sxs-lookup"><span data-stu-id="56c32-120">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>

   ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="56c32-121">Erstellen Sie eine SLA-Gruppe und fügen Sie ihr Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="56c32-121">Create an SLA group and add users to it</span></span>

1. <span data-ttu-id="56c32-122">Erstellen Sie die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="56c32-122">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    <span data-ttu-id="56c32-p108">Das Cmdlet „Set-CsSlaConfiguration“ markiert das Enterprise-VoIP-Konto SLAGroup1 als SLA-Entität und die Nummer von SLAGroup1 wird zur Nummer der SLA-Gruppe. Alle Anrufe für SLAGroup1 lassen es in der gesamten SLA-Gruppe läuten.</span><span class="sxs-lookup"><span data-stu-id="56c32-p108">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>

    <span data-ttu-id="56c32-125">Im folgenden Beispiel wird eine SLA-Gruppe SLAGroup1 für einen vorhandenen Enterprise-VoIP-Benutzer erstellt und die Gruppe nutzt die SLAGroup1 zugewiesene Nummer als SLA-Hauptanschlussnummer.</span><span class="sxs-lookup"><span data-stu-id="56c32-125">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>

    <span data-ttu-id="56c32-126">Der Befehl stellt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 ein und bestimmt, dass für alle weiteren Anrufe das „Besetzt“-Signal zu hören sein soll:</span><span class="sxs-lookup"><span data-stu-id="56c32-126">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    <span data-ttu-id="56c32-127">Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene Gruppe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="56c32-127">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="56c32-128">Beachten Sie, dass Sie für `-Identity` ein gültiges vorhandenes Enterprise-VoIP-Benutzerkonto angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="56c32-128">Note that what you specify for  `-Identity` must be a valid existing Enterprise Voice-enabled user account.</span></span>

2. <span data-ttu-id="56c32-129">Fügen Sie der Gruppe mithilfe des Cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) Stellvertretungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="56c32-129">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) cmdlet:</span></span>

   ```
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    <span data-ttu-id="56c32-130">Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="56c32-130">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="56c32-131">Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Enterprise Voice-fähiger Benutzer sein:</span><span class="sxs-lookup"><span data-stu-id="56c32-131">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>

   ```
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    <span data-ttu-id="56c32-p110">Wiederholen Sie das Cmdlet für jeden Nutzer, den Sie der Gruppe hinzufügen möchten. Nutzer können nur zu einer einzelnen SLA-Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="56c32-p110">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

### <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="56c32-134">Konfigurieren der „Besetzt“-Option für die SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="56c32-134">Configure the SLA group Busy Option</span></span>

- <span data-ttu-id="56c32-135">Konfigurieren Sie die „Besetzt“-Option für die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="56c32-135">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    <span data-ttu-id="56c32-136">Im folgenden Beispiel werden Anrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="56c32-136">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="56c32-137">Das Ziel kann ein Benutzer in Ihrer Organisation und nicht eine Telefonnummer sein. in diesem Fall ist die Syntax für die Person, für die weitergeleitete Anrufe zu empfangen sind, identisch mit der `sip:<NameofDelegate@domain>`Angabe einer Stellvertretung:.</span><span class="sxs-lookup"><span data-stu-id="56c32-137">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate:  `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="56c32-138">Der andere mögliche Parameter für `BusyOption` ist `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="56c32-138">The other possible parameter for  `BusyOption` is `Voicemail`:</span></span>

  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="56c32-139">Konfigurieren der Option „Entgangener Anruf“ für die SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="56c32-139">Configure the SLA group Missed Call Option</span></span>

1. <span data-ttu-id="56c32-140">Konfigurieren Sie die Option „Entgangener Anruf“ für die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="56c32-140">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

   ```
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. <span data-ttu-id="56c32-141">Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Namen `sla_forward_number`des Benutzers weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="56c32-141">The following example specifies that missed calls are to be forwarded to the user named  `sla_forward_number`.</span></span> <span data-ttu-id="56c32-142">Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward`, `BusySignal`oder `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="56c32-142">The valid options for the  `-MissedCallOption` parameter are `Forward`,  `BusySignal`, or  `Disconnect`.</span></span> <span data-ttu-id="56c32-143">Wenn Sie auswählen `Forward`, müssen Sie auch den `-MissedCallForwardTarget` Parameter mit einem Benutzer oder einer Telefonnummer als Ziel angeben:</span><span class="sxs-lookup"><span data-stu-id="56c32-143">If you choose  `Forward`, you must also include the  `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>

   ```
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="56c32-144">Entfernen einer Stellvertretung aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="56c32-144">Remove a delegate from a group</span></span>

- <span data-ttu-id="56c32-145">Entfernen Sie eine Stellvertretung mithilfe des Cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) aus einer Gruppe:</span><span class="sxs-lookup"><span data-stu-id="56c32-145">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    <span data-ttu-id="56c32-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="56c32-146">For example:</span></span>

  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a><span data-ttu-id="56c32-147">Löschen einer SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="56c32-147">Delete an SLA group</span></span>

- <span data-ttu-id="56c32-148">Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="56c32-148">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    <span data-ttu-id="56c32-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="56c32-149">For example:</span></span>

  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


