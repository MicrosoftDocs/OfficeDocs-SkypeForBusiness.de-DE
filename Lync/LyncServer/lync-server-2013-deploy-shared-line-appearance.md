---
title: 'Lync Server 2013: Bereitstellen der Darstellung freigegebener Leitungen'
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
ms.openlocfilehash: 15d0bffd92c4c2e2448938c467eec73c9bab1a94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531412"
---
# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Bereitstellen der Darstellung freigegebener Leitungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-06-13_

Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in lync Server 2013, Kumulatives Update April 2016, bereitstellen. SLA ist ein Feature für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.

Weitere Informationen zu dieser Funktion finden Sie unter [Planen der Darstellung freigegebener Leitungen in lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

Die Darstellung freigegebener Leitungen (SLA) ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016. Zum Aktivieren dieses Features müssen Sie zunächst dieses kumulative Update bereitgestellt haben.

<div>

## <a name="install-shared-line-appearance"></a>Installieren der Darstellung freigegebener Leitungen

1.  Nachdem lync Server 2013 das kumulative Update April 2016 bereitgestellt wurde, ist die SLA-Anwendung standardmäßig nicht aktiviert. Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:
    
    1.  Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:
        ```powershell
        New-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                        http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                        $true -Priority (Get-CsServerApplication -Identity
                        'Service:Registrar:%FQDN%/UserServices').Priority 
        ```
        Dabei ist% FQDN% der vollqualifizierte Domänenname des Pools.
    
    2.  Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:
        ```powershell
        Update-CsAdminRole 
        ```
    3.  Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:
        
        ```powershell 
        Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern zu ihr

1.  Erstellen Sie die SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) ":
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                -MaxNumberOfCalls <Number> -BusyOption
                <BusyOnBusy|Voicemail|Forward> [-Target
                <TargetUserOrPhoneNumber>]
    ```
    Das Set-CsSlaConfiguration-Cmdlet kennzeichnet das SLAGroup1 des Enterprise-VoIP-Kontos als SLA-Entität, und die Anzahl von SLAGroup1 wird zur Nummer für die SLA-Gruppe. Alle Anrufe an SLAGroup1 rufen die gesamte SLA-Gruppe ab.
    
    Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP-Benutzer SLAGroup1 erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptnummer verwendet.
    
    Mit dem Befehl wird die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 festgelegt, und für Anrufe, die darüber hinausgehen, um ein Besetztzeichen zu hören:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                -BusyOption BusyOnBusy
    ```
    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene zu ändern.
    
    <div>
    

    > [!NOTE]  
    > Beachten Sie, dass für <CODE>-Identity</CODE> ein gültiges vorhandenes Enterprise-VoIP-aktiviertes Benutzerkonto angegeben werden muss.

    
    </div>

2.  Fügen Sie der Gruppe Stellvertretungen mithilfe des Cmdlets [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) hinzu:
    ```powershell
    Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt. Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Benutzer mit Enterprise-VoIP sein:
    ```powershell
    Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate1@contoso.com
    ```
    Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten. Benutzer können nur zu einer einzelnen SLA-Gruppe gehören.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der Option "besetzt" der SLA-Gruppe

1.  Konfigurieren Sie die Option "besetzt" der SLA [-](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) Gruppe mithilfe des Cmdlets "CsSlaConfiguration":
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup>
              -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    ```
    Im folgenden Beispiel werden Aufrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden sollen. Bei dem Ziel kann es sich um einen Benutzer in Ihrer Organisation anstelle einer Telefonnummer handeln. in diesem Fall ist die Syntax für die Person, die weitergeleitete Anrufe erhalten soll, identisch mit der Angabe eines Delegaten: `sip:<NameofDelegate@domain>` . Der andere mögliche Parameter für `BusyOption` ist `Voicemail` :
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
              -Target tel:+2025551234]
    ```
</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option "verpasste Anrufe bei SLA-Gruppen"

1.  Konfigurieren Sie die Option für den verpassten Anruf der SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration) ":
    ```powershell
    Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
              -MissedCallOption <Option> -MissedCallForwardTarget
              <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    ```
    Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit dem Namen weitergeleitet werden sollen `sla_forward_number` . Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward` , `BusySignal` oder `Disconnect` . Wenn Sie `Forward` sich entscheiden, müssen Sie auch den `-MissedCallForwardTarget` Parameter mit einer Benutzer-oder Telefonnummer als Ziel einschließen:
    ```powershell
    Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
              Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
        -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
    ```
</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Entfernen eines Stellvertreters aus einer Gruppe

1.  Entfernen Sie eine Stellvertretung aus einer Gruppe mithilfe des Cmdlets [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) :
    ```powershell
    Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
              <NameOfDelegate@domain>
    ```
    Zum Beispiel:
    ```powershell
    Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
              sip:SLA_Delegate3@contoso.com
    ```
</div>

<div>

## <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

1.  Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
    ```powershell
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Beispiel:
    ```powershell
    Remove-CsSlaConfiguration -Identity SLAGroup1 
    ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

