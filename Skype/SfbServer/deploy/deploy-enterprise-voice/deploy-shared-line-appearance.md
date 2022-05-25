---
title: Bereitstellen der Darstellung freigegebener Zeilen in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 474a5e4a-9479-4e86-8607-b9f41a0fa648
description: In diesem Thema erfahren Sie, wie Sie SLA (Shared Line Appearance) im kumulativen Update vom Skype for Business Server 2015 vom November 2015 bereitstellen. SLA ist ein Feature zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.
ms.openlocfilehash: 7f9d904de2b3348bdf8ed75b9f0df38aee252cdd
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671591"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Bereitstellen der Darstellung freigegebener Zeilen in Skype for Business Server 2015

In diesem Thema erfahren Sie, wie Sie SLA (Shared Line Appearance) im kumulativen Update vom Skype for Business Server 2015 vom November 2015 bereitstellen. SLA ist ein Feature zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.

Weitere Informationen zu diesem Feature finden Sie unter [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Shared Line Appearance (SLA) ist ein neues Feature im kumulativen Update Skype for Business Server November 2015. Um dieses Feature zu aktivieren, müssen Sie zuerst dieses kumulative Update bereitgestellt haben.

## <a name="install-shared-line-appearance"></a>Gemeinsame Liniendarstellung installieren

1. Führen Sie nach Skype for Business Server, dem kumulativen Update vom November 2015, den `SkypeServerUpdateInstaller.exe` Patch auf jedem Front-End-Server im Pool aus.

2. Das Installationsprogramm stellt die neueste Version der SLA-Anwendung bereit, die Anwendung ist jedoch nicht standardmäßig aktiviert. Sie wird durch Die folgenden Schritte aktiviert:

    a. Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   dabei ist %FQDN% der vollqualifizierte Domänenname des Pools.

    b. Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:

   ```powershell
   Update-CsAdminRole
   ```

    c. Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

## <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern

1. Erstellen Sie die SLA-Gruppe mithilfe des Cmdlets [Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) :

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Das cmdlet Set-CsSlaConfiguration kennzeichnet das Enterprise-VoIP Konto SLAGroup1 als SLA-Entität, und die Anzahl der SLAGroup1 wird zur Nummer für die SLA-Gruppe. Alle Aufrufe von SLAGroup1 werden die gesamte SLA-Gruppe anrufen.

    Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP Benutzer, SLAGroup1, erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptliniennummer verwendet.

    Der Befehl legt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 fest, und für anrufe, die darüber hinaus gehen, um ein besetztes Signal zu hören:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene gruppe zu ändern.

    > [!NOTE]
    > Beachten Sie, dass es sich bei `-Identity` dem von Ihnen angegebenen Wert um ein gültiges Enterprise-VoIP-aktiviertes Benutzerkonto sein muss.

2. Fügen Sie der Gruppe mithilfe des [Cmdlets "Add-CsSlaDelegates" Stellvertretungen](/powershell/module/skype/add-cssladelegates) hinzu:

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
   ```

    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt. Jeder der Gruppe hinzugefügte Benutzer muss ein gültiger Enterprise-VoIP-aktivierter Benutzer sein:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten. Benutzer können nur einer einzelnen SLA-Gruppe angehören.

## <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der Option "SLA-Gruppe beschäftigt"

- Konfigurieren Sie die Option "Beschäftigt" der SLA-Gruppe mithilfe des Cmdlets ["Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) ":

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Im folgenden Beispiel werden Anrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden. Das Ziel könnte ein Benutzer in Ihrer Organisation anstelle einer Telefonnummer sein. in diesem Fall ist die Syntax für die Person, die die weitergeleiteten Anrufe empfängt, identisch mit der, wenn Sie einen Delegaten angeben:  `sip:<NameofDelegate@domain>`. Der andere mögliche Parameter für  `BusyOption` ist `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

## <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option "Verpasster Anruf" der SLA-Gruppe

1. Konfigurieren Sie die Option für verpasste Anrufe der SLA-Gruppe mithilfe des Cmdlets ["Set-CsSlaConfiguration](/powershell/module/skype/set-csslaconfiguration) ":

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit dem Namen  `sla_forward_number`weitergeleitet werden sollen. Die gültigen Optionen für den  `-MissedCallOption` Parameter sind `Forward`,  `BusySignal`oder  `Disconnect`. Wenn Sie dies auswählen  `Forward`, müssen Sie auch den  `-MissedCallForwardTarget` Parameter mit einem Benutzer oder einer Telefonnummer als Ziel angeben:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

## <a name="remove-a-delegate-from-a-group"></a>Entfernen einer Stellvertretung aus einer Gruppe

- Entfernen sie einen Delegaten aus einer Gruppe mithilfe des Cmdlets [Remove-CsSlaDelegates](/powershell/module/skype/remove-cssladelegates) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

## <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

- Löschen Sie eine SLA-Gruppe mit dem Cmdlet [Remove-CsSlaConfiguration](/powershell/module/skype/remove-csslaconfiguration) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```
