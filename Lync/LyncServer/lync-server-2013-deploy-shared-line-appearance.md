---
title: 'Lync Server 2013: Bereitstellen der Darstellung freigegebener Leitungen'
description: 'Lync Server 2013: Bereitstellen der Darstellung freigegebener Leitungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c83c06bbc9b91e11cabc0abee20de28fc7281205
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558621"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="83f2a-103">Bereitstellen der Darstellung freigegebener Leitungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83f2a-103">Deploy Shared Line Appearance in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83f2a-104">_**Letztes Änderungsstand des Themas:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="83f2a-104">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="83f2a-105">Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in lync Server 2013, Kumulatives Update April 2016, bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="83f2a-105">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="83f2a-106">SLA ist ein Feature für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="83f2a-106">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="83f2a-107">Weitere Informationen zu dieser Funktion finden Sie unter [Planen der Darstellung freigegebener Leitungen in lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="83f2a-107">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="83f2a-108">Die Darstellung freigegebener Leitungen (SLA) ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.</span><span class="sxs-lookup"><span data-stu-id="83f2a-108">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="83f2a-109">Zum Aktivieren dieses Features müssen Sie zunächst dieses kumulative Update bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="83f2a-109">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="83f2a-110">Installieren der Darstellung freigegebener Leitungen</span><span class="sxs-lookup"><span data-stu-id="83f2a-110">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="83f2a-111">Nachdem lync Server 2013 das kumulative Update April 2016 bereitgestellt wurde, ist die SLA-Anwendung standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="83f2a-111">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="83f2a-112">Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="83f2a-112">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="83f2a-113">Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:</span><span class="sxs-lookup"><span data-stu-id="83f2a-113">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="83f2a-114">Dabei ist% FQDN% der vollqualifizierte Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="83f2a-114">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="83f2a-115">Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="83f2a-115">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="83f2a-116">Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="83f2a-116">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="83f2a-117">Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern zu ihr</span><span class="sxs-lookup"><span data-stu-id="83f2a-117">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="83f2a-118">Erstellen Sie die SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) ":</span><span class="sxs-lookup"><span data-stu-id="83f2a-118">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="83f2a-119">Das Set-CsSlaConfiguration-Cmdlet kennzeichnet das SLAGroup1 des Enterprise-VoIP-Kontos als SLA-Entität, und die Anzahl von SLAGroup1 wird zur Nummer für die SLA-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="83f2a-119">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group.</span></span> <span data-ttu-id="83f2a-120">Alle Anrufe an SLAGroup1 rufen die gesamte SLA-Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="83f2a-120">All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="83f2a-121">Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP-Benutzer SLAGroup1 erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptnummer verwendet.</span><span class="sxs-lookup"><span data-stu-id="83f2a-121">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="83f2a-122">Mit dem Befehl wird die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 festgelegt, und für Anrufe, die darüber hinausgehen, um ein Besetztzeichen zu hören:</span><span class="sxs-lookup"><span data-stu-id="83f2a-122">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="83f2a-123">Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="83f2a-123">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="83f2a-124">Beachten Sie, dass für <CODE>-Identity</CODE> ein gültiges vorhandenes Enterprise-VoIP-aktiviertes Benutzerkonto angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="83f2a-124">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="83f2a-125">Fügen Sie der Gruppe Stellvertretungen mithilfe des Cmdlets [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) hinzu:</span><span class="sxs-lookup"><span data-stu-id="83f2a-125">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="83f2a-126">Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="83f2a-126">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="83f2a-127">Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Benutzer mit Enterprise-VoIP sein:</span><span class="sxs-lookup"><span data-stu-id="83f2a-127">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="83f2a-128">Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="83f2a-128">Repeat the cmdlet for each user you want to add to the group.</span></span> <span data-ttu-id="83f2a-129">Benutzer können nur zu einer einzelnen SLA-Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="83f2a-129">Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="83f2a-130">Konfigurieren der Option "besetzt" der SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="83f2a-130">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="83f2a-131">Konfigurieren Sie die Option "besetzt" der SLA [-](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) Gruppe mithilfe des Cmdlets "CsSlaConfiguration":</span><span class="sxs-lookup"><span data-stu-id="83f2a-131">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="83f2a-132">Im folgenden Beispiel werden Aufrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="83f2a-132">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="83f2a-133">Bei dem Ziel kann es sich um einen Benutzer in Ihrer Organisation anstelle einer Telefonnummer handeln. in diesem Fall ist die Syntax für die Person, die weitergeleitete Anrufe erhalten soll, identisch mit der Angabe eines Delegaten: `sip:<NameofDelegate@domain>` .</span><span class="sxs-lookup"><span data-stu-id="83f2a-133">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="83f2a-134">Der andere mögliche Parameter für `BusyOption` ist `Voicemail` :</span><span class="sxs-lookup"><span data-stu-id="83f2a-134">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="83f2a-135">Konfigurieren der Option "verpasste Anrufe bei SLA-Gruppen"</span><span class="sxs-lookup"><span data-stu-id="83f2a-135">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="83f2a-136">Konfigurieren Sie die Option für den verpassten Anruf der SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) ":</span><span class="sxs-lookup"><span data-stu-id="83f2a-136">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="83f2a-137">Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit dem Namen weitergeleitet werden sollen `sla_forward_number` .</span><span class="sxs-lookup"><span data-stu-id="83f2a-137">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="83f2a-138">Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward` , `BusySignal` oder `Disconnect` .</span><span class="sxs-lookup"><span data-stu-id="83f2a-138">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="83f2a-139">Wenn Sie `Forward` sich entscheiden, müssen Sie auch den `-MissedCallForwardTarget` Parameter mit einer Benutzer-oder Telefonnummer als Ziel einschließen:</span><span class="sxs-lookup"><span data-stu-id="83f2a-139">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="83f2a-140">Entfernen eines Stellvertreters aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="83f2a-140">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="83f2a-141">Entfernen Sie eine Stellvertretung aus einer Gruppe mithilfe des Cmdlets [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :</span><span class="sxs-lookup"><span data-stu-id="83f2a-141">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="83f2a-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="83f2a-142">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="83f2a-143">Löschen einer SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="83f2a-143">Delete an SLA group</span></span>

1.  <span data-ttu-id="83f2a-144">Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="83f2a-144">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="83f2a-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="83f2a-145">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

