---
title: 'Lync Server 2013: Bereitstellen der freigegebenen Leitungsdarstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Shared Line Appearance
ms:assetid: 6666dfef-9ecf-4834-af6a-2d5da227dfa3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712152(v=OCS.15)
ms:contentKeyID: 72522137
ms.date: 06/13/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6893dbda1c8f9ecf61319d19a24b896ff67de20b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-shared-line-appearance-in-lync-server-2013"></a>Bereitstellen der Darstellung der freigegebenen Zeile in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-06-13_

Lesen Sie dieses Thema, um zu erfahren, wie Sie in lync Server 2013, Kumulatives Update April 2016, die freigegebene Leitungsdarstellung (SLA) bereitstellen. Bei SLA handelt es sich um eine Funktion zum Verarbeiten mehrerer Anrufe an eine bestimmte Nummer, die als gemeinsam genutzte Nummer bezeichnet wird.

Weitere Informationen zu diesem Feature finden Sie unter [Planen der Darstellung der freigegebenen Zeile in lync Server 2013](lync-server-2013-plan-for-shared-line-appearance.md).

Die gemeinsame Leitungsdarstellung (SLA) ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016. Um dieses Feature zu aktivieren, müssen Sie zuerst dieses kumulative Update bereitgestellt haben.

<div>

## <a name="install-shared-line-appearance"></a>Installieren der Funktion „Gemeinsame Leitungen“

1.  Nach lync Server 2013 wird das kumulative Update April 2016 bereitgestellt, die SLA-Anwendung ist standardmäßig nicht aktiviert. Führen Sie die folgenden Schritte aus, um die Anwendung zu aktivieren:
    
    1.  Registrieren Sie SLA als Serveranwendung, indem Sie für jeden Pool den folgenden Befehl ausführen:
        
            New-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri
                            http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled
                            $true -Priority (Get-CsServerApplication -Identity
                            'Service:Registrar:%FQDN%/UserServices').Priority 
        
        Dabei ist %FQDN% der vollqualifizierte Domänenname des Pools.
    
    2.  Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:
        
            Update-CsAdminRole 
    
    3.  Starten Sie alle Front-End-Server (RTCSRV-Dienst) in sämtlichen Pools neu, in denen SLA installiert und aktiviert worden ist:
        
        ``` 
         Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                        
        ```

</div>

<div>

## <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen Sie eine SLA-Gruppe und fügen Sie ihr Benutzer hinzu.

1.  Erstellen Sie die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -MaxNumberOfCalls <Number> -BusyOption
                  <BusyOnBusy|Voicemail|Forward> [-Target
                  <TargetUserOrPhoneNumber>]
    
    Das Cmdlet „Set-CsSlaConfiguration“ markiert das Enterprise-VoIP-Konto SLAGroup1 als SLA-Entität und die Nummer von SLAGroup1 wird zur Nummer der SLA-Gruppe. Alle Anrufe für SLAGroup1 lassen es in der gesamten SLA-Gruppe läuten.
    
    Im folgenden Beispiel wird eine SLA-Gruppe SLAGroup1 für einen vorhandenen Enterprise-VoIP-Benutzer erstellt und die Gruppe nutzt die SLAGroup1 zugewiesene Nummer als SLA-Hauptanschlussnummer.
    
    Der Befehl stellt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 ein und bestimmt, dass für alle weiteren Anrufe das „Besetzt“-Signal zu hören sein soll:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
                  -BusyOption BusyOnBusy
    
    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene Gruppe zu ändern.
    
    <div>
    

    > [!NOTE]  
    > Beachten Sie, dass Sie für <CODE>-Identity</CODE> ein gültiges vorhandenes Enterprise-VoIP-Benutzerkonto angeben müssen.

    
    </div>

2.  Fügen Sie der Gruppe mithilfe des Cmdlet [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates) Stellvertretungen hinzu:
    
        Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt. Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Enterprise Voice-fähiger Benutzer sein:
    
        Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate1@contoso.com
    
    Wiederholen Sie das Cmdlet für jeden Nutzer, den Sie der Gruppe hinzufügen möchten. Nutzer können nur zu einer einzelnen SLA-Gruppe gehören.

</div>

<div>

## <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der „Besetzt“-Option für die SLA-Gruppe

1.  Konfigurieren Sie die „Besetzt“-Option für die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup>
                  -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
    
    Im folgenden Beispiel werden Anrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden. Das Ziel kann ein Benutzer in Ihrer Organisation und nicht eine Telefonnummer sein. in diesem Fall ist die Syntax für die Person, für die weitergeleitete Anrufe zu empfangen sind, identisch mit der `sip:<NameofDelegate@domain>`Angabe einer Stellvertretung:. Der andere mögliche Parameter für `BusyOption` ist `Voicemail`:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
                  -Target tel:+2025551234]

</div>

<div>

## <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option „Entgangener Anruf“ für die SLA-Gruppe

1.  Konfigurieren Sie die Option „Entgangener Anruf“ für die SLA-Gruppe mithilfe des Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration):
    
        Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
                  -MissedCallOption <Option> -MissedCallForwardTarget
                  <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
    
    Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Namen `sla_forward_number`des Benutzers weitergeleitet werden sollen. Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward`, `BusySignal`oder `Disconnect`. Wenn Sie auswählen `Forward`, müssen Sie auch den `-MissedCallForwardTarget `Parameter mit einem Benutzer oder einer Telefonnummer als Ziel angeben:
    
        Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
                  Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
            -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 

</div>

<div>

## <a name="remove-a-delegate-from-a-group"></a>Entfernen einer Stellvertretung aus einer Gruppe

1.  Entfernen Sie eine Stellvertretung mithilfe des Cmdlet [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates) aus einer Gruppe:
    
        Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
                  <NameOfDelegate@domain>
    
    Beispiel:
    
        Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
                  sip:SLA_Delegate3@contoso.com

</div>

<div>

## <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

1.  Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps):
    
    ``` 
    Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
              
    ```
    
    Beispiel:
    
        Remove-CsSlaConfiguration -Identity SLAGroup1 

</div>

</div>

<span> </span>

</div>

</div>

</div>

