---
title: Bereitstellen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: Lesen Sie dieses Thema und finden Sie heraus, wie die Funktion „Gemeinsame Leitungen“ (SLA) in Skype for Business Server 2015, kumulatives Update vom November 2015, bereitzustellen ist. Bei SLA handelt es sich um eine Funktion zum Verarbeiten mehrerer Anrufe an eine bestimmte Nummer, die als gemeinsam genutzte Nummer bezeichnet wird.
ms.openlocfilehash: ba7ca76c9ef0c6ed49ba26205df69e7840ec75d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Bereitstellen der Funktion „Gemeinsame Leitungen“ in Skype for Business Server 2015
 
Lesen Sie dieses Thema und finden Sie heraus, wie die Funktion „Gemeinsame Leitungen“ (SLA) in Skype for Business Server 2015, kumulatives Update vom November 2015, bereitzustellen ist. Bei SLA handelt es sich um eine Funktion zum Verarbeiten mehrerer Anrufe an eine bestimmte Nummer, die als gemeinsam genutzte Nummer bezeichnet wird. 
  
Weitere Informationen zu diesem Feature finden Sie unter [Planen der Darstellung einer gemeinsamen Linie in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).
  
Freigegebene Zeile Darstellung (SLA) ist ein neues Feature in Skype für Business Server 2015 November Kumulatives Update. Um dieses Feature aktivieren, müssen Sie zuerst das kumulative Update bereitgestellt.
  
### <a name="install-shared-line-appearance"></a>Installieren der Funktion „Gemeinsame Leitungen“

1. Nach der Skype für Business Server, 2015 November Kumulatives Update bereitgestellt wird, führen Sie die `SkypeServerUpdateInstaller.exe` Patch auf jedem Front-End-Server im Pool.
    
2. Der Installer stellt die aktuelle Version der SLA-Anwendung bereit, allerdings ist diese Anwendung nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die folgenden Schritte durchführen:
    
    a. Registrieren Sie SLA als Serveranwendung, indem Sie für jeden Pool den folgenden Befehl ausführen:
    
   ```
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled                 $true -Priority (Get-CsServerApplication -Identity              'Service:Registrar:%FQDN%/UserServices').Priority 
   ```

   Dabei ist %FQDN% der vollqualifizierte Domänenname des Pools. 
    
    b. Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren: 
    
   ```
   Update-CsAdminRole 
   ```

    c. Starten Sie alle Front-End-Server (RTCSRV-Dienst) in sämtlichen Pools neu, in denen SLA installiert und aktiviert worden ist:
    
  ```
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
                
  ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen Sie eine SLA-Gruppe und fügen Sie ihr Benutzer hinzu.

1. Erstellen Sie die SLA-Gruppe mit dem Cmdlet [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -MaxNumberOfCalls <Number> -BusyOption
          <BusyOnBusy|Voicemail|Forward> [-Target
          <TargetUserOrPhoneNumber>]
  ```

    Das Cmdlet „Set-CsSlaConfiguration“ markiert das Enterprise-VoIP-Konto SLAGroup1 als SLA-Entität und die Nummer von SLAGroup1 wird zur Nummer der SLA-Gruppe. Alle Anrufe für SLAGroup1 lassen es in der gesamten SLA-Gruppe läuten.
    
    Im folgenden Beispiel wird eine SLA-Gruppe SLAGroup1 für einen vorhandenen Enterprise-VoIP-Benutzer erstellt und die Gruppe nutzt die SLAGroup1 zugewiesene Nummer als SLA-Hauptanschlussnummer. 
    
    Der Befehl stellt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 ein und bestimmt, dass für alle weiteren Anrufe das „Besetzt“-Signal zu hören sein soll:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3
          -BusyOption BusyOnBusy
  ```

    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene Gruppe zu ändern.
    
    > [!NOTE]
    > Beachten Sie, dass die Angaben für `-Identity` muss ein gültige vorhandenen Enterprise-VoIP-aktiviertes Benutzerkonto.
  
2. Fügen Sie der Gruppe Stellvertretungen mithilfe des Cmdlets [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) hinzu:
    
  ```
  Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt. Jeder Benutzer der Gruppe hinzugefügt, muss eine gültige Enterprise-VoIP-aktivierten Benutzer:
    
  ```
  Add-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate1@contoso.com
  ```

    Wiederholen Sie das Cmdlet für jeden Nutzer, den Sie der Gruppe hinzufügen möchten. Nutzer können nur zu einer einzelnen SLA-Gruppe gehören.
    
### <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der „Besetzt“-Option für die SLA-Gruppe

- Konfigurieren der Vereinbarung zum SERVICELEVEL gruppieren beschäftigt Option mithilfe des Cmdlets [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup>
          -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Im folgenden Beispiel wird die Anrufe, die überschreitet die maximale Anzahl gleichzeitiger Anrufe an das Telefon 202-555-1234 Nummer weitergeleitet werden. Das Ziel kann ein Benutzer in Ihrer Organisation anstelle einer Telefonnummer sein. In diesem Fall die Syntax für die Person, die die weitergeleitete Anrufe empfangen ist dieselbe wie bei der Angabe von einer stellvertretungs: `sip:<NameofDelegate@domain>`. Die möglichen Parameter für `BusyOption` ist `Voicemail`:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward
          -Target tel:+2025551234]
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option „Entgangener Anruf“ für die SLA-Gruppe

1. Konfigurieren der Vereinbarung zum SERVICELEVEL Gruppe Entgangener Anrufoption mithilfe des Cmdlets [Set-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) :
    
  ```
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> 
          -MissedCallOption <Option> -MissedCallForwardTarget
          <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
  ```

2. Das folgende Beispiel gibt an, dass verpasste Anrufe an die Benutzer mit dem Namen weitergeleitet werden `sla_forward_number`. Die gültigen Optionen für die `-MissedCallOption` Parameter sind `Forward`, `BusySignal`, oder `Disconnect`. Bei Auswahl von `Forward`, müssen Sie auch enthalten die `-MissedCallForwardTarget` Parameter mit einem Benutzer oder Rufnummer weiter als Ziel:
    
  ```
  Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption
          Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com 
    -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com 
  ```

### <a name="remove-a-delegate-from-a-group"></a>Entfernen einer Stellvertretung aus einer Gruppe

- Entfernen Sie eine Stellvertretung aus einer Gruppe mithilfe des Cmdlets [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :
    
  ```
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
  ```

    Beispiel:
    
  ```
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate
          sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

- Löschen Sie eine SLA-Gruppe mit dem Cmdlet [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :
    
  ```
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
          
  ```

    Beispiel: 
    
  ```
  Remove-CsSlaConfiguration -Identity SLAGroup1 
  ```


