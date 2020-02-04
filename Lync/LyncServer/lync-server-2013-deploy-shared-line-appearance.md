---
title: 'Lync Server 2013: Bereitstellen der freigegebenen Leitungsdarstellung'
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
ms.openlocfilehash: 5e0f6aeb7d235ea7691c6878a4f21e6ec98f531e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a><span data-ttu-id="7f229-102">Bereitstellen der Darstellung der freigegebenen Zeile in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f229-102">Deploy Shared Line Appearance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f229-103">_**Letztes Änderungsdatum des Themas:** 2016-06-13_</span><span class="sxs-lookup"><span data-stu-id="7f229-103">_**Topic Last Modified:** 2016-06-13_</span></span>

<span data-ttu-id="7f229-104">Lesen Sie dieses Thema, um zu erfahren, wie Sie in lync Server 2013, Kumulatives Update April 2016, die freigegebene Leitungsdarstellung (SLA) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7f229-104">Read this topic to learn how to deploy Shared Line Appearance (SLA) in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="7f229-105">Bei SLA handelt es sich um eine Funktion zum Verarbeiten mehrerer Anrufe an eine bestimmte Nummer, die als gemeinsam genutzte Nummer bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="7f229-105">SLA is a feature for handling multiple calls on a specific number called a shared number.</span></span>

<span data-ttu-id="7f229-106">Weitere Informationen zu diesem Feature finden Sie unter [Planen der Darstellung der freigegebenen Zeile in lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span><span class="sxs-lookup"><span data-stu-id="7f229-106">For more information about this feature, see [Plan for Shared Line Appearance in Lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).</span></span>

<span data-ttu-id="7f229-107">Die gemeinsame Leitungsdarstellung (SLA) ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.</span><span class="sxs-lookup"><span data-stu-id="7f229-107">Shared Line Appearance (SLA) is a new feature in Lync Server 2013, Cumulative Update April 2016.</span></span> <span data-ttu-id="7f229-108">Um dieses Feature zu aktivieren, müssen Sie zuerst dieses kumulative Update bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="7f229-108">To enable this feature, you must have first deployed this cumulative update.</span></span>

<div>

## <a name="install-shared-line-appearance"></a><span data-ttu-id="7f229-109">Installieren der Funktion „Gemeinsame Leitungen“</span><span class="sxs-lookup"><span data-stu-id="7f229-109">Install Shared Line Appearance</span></span>

1.  <span data-ttu-id="7f229-110">Nach lync Server 2013 wird das kumulative Update April 2016 bereitgestellt, die SLA-Anwendung ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7f229-110">After Lync Server 2013, Cumulative Update April 2016 is deployed, the SLA application is not enabled by default.</span></span> <span data-ttu-id="7f229-111">Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="7f229-111">To enable the application, follow the steps below:</span></span>
    
    1.  <span data-ttu-id="7f229-112">Registrieren Sie SLA als Serveranwendung, indem Sie für jeden Pool den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="7f229-112">Register SLA as a server application by running the following command for each pool:</span></span>
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        <span data-ttu-id="7f229-113">Dabei ist %FQDN% der vollqualifizierte Domänenname des Pools.</span><span class="sxs-lookup"><span data-stu-id="7f229-113">where %FQDN% is the fully qualified domain name of the pool.</span></span>
    
    2.  <span data-ttu-id="7f229-114">Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="7f229-114">Run the following command to update the RBAC roles for the SLA cmdlets:</span></span>
        ```powershell
        Update-CsAdminRole 
        ```
    3.  <span data-ttu-id="7f229-115">Starten Sie alle Front-End-Server (RTCSRV-Dienst) in sämtlichen Pools neu, in denen SLA installiert und aktiviert worden ist:</span><span class="sxs-lookup"><span data-stu-id="7f229-115">Restart all the Front End Servers (RTCSRV service) in all the pools where SLA was installed and enabled:</span></span>
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a><span data-ttu-id="7f229-116">Erstellen Sie eine SLA-Gruppe und fügen Sie ihr Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="7f229-116">Create an SLA group and add users to it</span></span>

1.  <span data-ttu-id="7f229-117">Erstellen Sie die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="7f229-117">Create the SLA group by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="7f229-p104">Das Cmdlet „Set-CsSlaConfiguration“ markiert das Enterprise-VoIP-Konto SLAGroup1 als SLA-Entität und die Nummer von SLAGroup1 wird zur Nummer der SLA-Gruppe. Alle Anrufe für SLAGroup1 lassen es in der gesamten SLA-Gruppe läuten.</span><span class="sxs-lookup"><span data-stu-id="7f229-p104">The Set-CsSlaConfiguration cmdlet marks the Enterprise Voice account SLAGroup1 as an SLA entity, and the number of SLAGroup1 becomes the number for the SLA group. All calls to SLAGroup1 will ring the entire SLA group.</span></span>
    
    <span data-ttu-id="7f229-120">Im folgenden Beispiel wird eine SLA-Gruppe SLAGroup1 für einen vorhandenen Enterprise-VoIP-Benutzer erstellt und die Gruppe nutzt die SLAGroup1 zugewiesene Nummer als SLA-Hauptanschlussnummer.</span><span class="sxs-lookup"><span data-stu-id="7f229-120">The following example creates an SLA group for an existing Enterprise Voice user, SLAGroup1, and uses the number assigned for SLAGroup1 as the SLA mainline number.</span></span>
    
    <span data-ttu-id="7f229-121">Der Befehl stellt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 ein und bestimmt, dass für alle weiteren Anrufe das „Besetzt“-Signal zu hören sein soll:</span><span class="sxs-lookup"><span data-stu-id="7f229-121">The command sets the maximum number of concurrent calls for the new SLA group to 3, and for calls in excess of that to hear a busy signal:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    <span data-ttu-id="7f229-122">Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene Gruppe zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7f229-122">You can use Set-CsSlaConfiguration to create a new SLA group or modify an existing one.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7f229-123">Beachten Sie, dass Sie für <CODE>-Identity</CODE> ein gültiges vorhandenes Enterprise-VoIP-Benutzerkonto angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="7f229-123">Note that what you specify for <CODE>-Identity</CODE> must be a valid existing Enterprise Voice-enabled user account.</span></span>

    
    </div>

2.  <span data-ttu-id="7f229-124">Fügen Sie der Gruppe mithilfe des Cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) Stellvertretungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="7f229-124">Add delegates to the group by using the [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) cmdlet:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="7f229-125">Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7f229-125">The following example adds a user to the SLA group.</span></span> <span data-ttu-id="7f229-126">Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Enterprise Voice-fähiger Benutzer sein:</span><span class="sxs-lookup"><span data-stu-id="7f229-126">Each user added to the group must be a valid Enterprise Voice-enabled user:</span></span>
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    <span data-ttu-id="7f229-p106">Wiederholen Sie das Cmdlet für jeden Nutzer, den Sie der Gruppe hinzufügen möchten. Nutzer können nur zu einer einzelnen SLA-Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="7f229-p106">Repeat the cmdlet for each user you want to add to the group. Users can only belong to a single SLA group.</span></span>

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a><span data-ttu-id="7f229-129">Konfigurieren der „Besetzt“-Option für die SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="7f229-129">Configure the SLA group Busy Option</span></span>

1.  <span data-ttu-id="7f229-130">Konfigurieren Sie die „Besetzt“-Option für die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="7f229-130">Configure the SLA group Busy Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    <span data-ttu-id="7f229-131">Im folgenden Beispiel werden Anrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="7f229-131">The following example sets calls that exceed the maximum number of concurrent calls to be forwarded to the telephone number 202-555-1234.</span></span> <span data-ttu-id="7f229-132">Das Ziel kann ein Benutzer in Ihrer Organisation und nicht eine Telefonnummer sein. in diesem Fall ist die Syntax für die Person, für die weitergeleitete Anrufe zu empfangen sind, identisch mit der `sip:<NameofDelegate@domain>`Angabe einer Stellvertretung:.</span><span class="sxs-lookup"><span data-stu-id="7f229-132">The target could be a user in your organization instead of a phone number; in that case, the syntax for the person to receive the forwarded calls is the same as when you specify a delegate: `sip:<NameofDelegate@domain>`.</span></span> <span data-ttu-id="7f229-133">Der andere mögliche Parameter für `BusyOption` ist `Voicemail`:</span><span class="sxs-lookup"><span data-stu-id="7f229-133">The other possible parameter for `BusyOption` is `Voicemail`:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a><span data-ttu-id="7f229-134">Konfigurieren der Option „Entgangener Anruf“ für die SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="7f229-134">Configure the SLA group Missed Call Option</span></span>

1.  <span data-ttu-id="7f229-135">Konfigurieren Sie die Option „Entgangener Anruf“ für die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):</span><span class="sxs-lookup"><span data-stu-id="7f229-135">Configure the SLA group Missed Call Option by using the [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) cmdlet:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    <span data-ttu-id="7f229-136">Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Namen `sla_forward_number`des Benutzers weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7f229-136">The following example specifies that missed calls are to be forwarded to the user named `sla_forward_number`.</span></span> <span data-ttu-id="7f229-137">Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward`, `BusySignal`oder `Disconnect`.</span><span class="sxs-lookup"><span data-stu-id="7f229-137">The valid options for the `-MissedCallOption` parameter are `Forward`, `BusySignal`, or `Disconnect`.</span></span> <span data-ttu-id="7f229-138">Wenn Sie auswählen `Forward`, müssen Sie auch den `-MissedCallForwardTarget` Parameter mit einem Benutzer oder einer Telefonnummer als Ziel angeben:</span><span class="sxs-lookup"><span data-stu-id="7f229-138">If you choose `Forward`, you must also include the `-MissedCallForwardTarget` parameter, with a user or phone number as the target:</span></span>
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a><span data-ttu-id="7f229-139">Entfernen einer Stellvertretung aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="7f229-139">Remove a delegate from a group</span></span>

1.  <span data-ttu-id="7f229-140">Entfernen Sie eine Stellvertretung mithilfe des Cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) aus einer Gruppe:</span><span class="sxs-lookup"><span data-stu-id="7f229-140">Remove a delegate from a group by using the [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) cmdlet:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    <span data-ttu-id="7f229-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7f229-141">For example:</span></span>
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a><span data-ttu-id="7f229-142">Löschen einer SLA-Gruppe</span><span class="sxs-lookup"><span data-stu-id="7f229-142">Delete an SLA group</span></span>

1.  <span data-ttu-id="7f229-143">Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):</span><span class="sxs-lookup"><span data-stu-id="7f229-143">Delete an SLA group by using the [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) cmdlet:</span></span>
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    <span data-ttu-id="7f229-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7f229-144">For example:</span></span>
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

