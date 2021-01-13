---
title: Bereitstellen der Gemeinsamen Leitungs darstellung in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: In diesem Thema erfahren Sie, wie Sie das kumulative Update vom November 2015 in Skype for Business Server 2015 bereitstellen können. SLA ist ein Feature zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.
ms.openlocfilehash: a692768744782f547b57b635a58864c858389d7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812405"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Bereitstellen der Gemeinsamen Leitungs darstellung in Skype for Business Server 2015

In diesem Thema erfahren Sie, wie Sie das kumulative Update vom November 2015 in Skype for Business Server 2015 bereitstellen können. SLA ist ein Feature zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.

Weitere Informationen zu dieser Funktion finden Sie unter [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Die Funktion "Gemeinsame Leitung" (Shared Line Appearance, SLA) ist eine neue Funktion im kumulativen Update für Skype for Business Server vom November 2015. Um dieses Feature zu aktivieren, müssen Sie zuerst dieses kumulative Update bereitgestellt haben.

### <a name="install-shared-line-appearance"></a>Installieren der Darstellung einer freigegebenen Leitung

1. Führen Sie nach der Bereitstellung des kumulativen Updates für Skype for Business Server vom November 2015 den Patch auf jedem  `SkypeServerUpdateInstaller.exe` Front-End-Server im Pool aus.

2. Das Installationsprogramm stellt die neueste Version der SLA-Anwendung, die Anwendung ist jedoch nicht standardmäßig aktiviert. Sie wird aktiviert, indem Sie die unten beschriebenen Schritte ausführen:

    a. Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   Dabei ist %FQDN% der vollqualifizierte Domänenname des Pools.

    b. Führen Sie den folgenden Befehl aus, um die rollen rollenaktivierten Rollen für die SLA-Cmdlets zu aktualisieren:

   ```powershell
   Update-CsAdminRole
   ```

    c. Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern zu dieser Gruppe

1. Erstellen Sie die SLA-Gruppe mithilfe des [Cmdlets "Set-CsSlaConfiguration":](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Das Set-CsSlaConfiguration-Cmdlet markiert das Enterprise-VoIP Konto SLAGroup1 als SLA-Entität, und die Anzahl von SLAGroup1 wird zur Nummer für die SLA-Gruppe. Alle Anrufe an SLAGroup1 klingeln in der gesamten SLA-Gruppe.

    Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP, SLAGroup1, erstellt und die nummer, die SLAGroup1 zugewiesen ist, als die Nummer der SLA-Hauptleitung verwendet.

    Mit dem Befehl wird die maximale Anzahl gleichzeitiger Anrufe für die neue GRUPPE auf 3 und für Anrufe, die darüber hinaus ein Besetztzeichen hören, auf 3 gesetzt:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene gruppe zu ändern.

    > [!NOTE]
    > Beachten Sie, dass es sich bei dem von Ihnen angegebenen Enterprise-VoIP um ein  `-Identity` gültiges, Enterprise-VoIP Benutzerkonto muss.

2. Fügen Sie der Gruppe Stellvertretung mithilfe des [Cmdlets "Add-CsSlaDelegates"](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) hinzu:

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    Im folgenden Beispiel wird der Gruppe "SLA" ein Benutzer hinzufügt. Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger benutzerfähiger Enterprise-VoIP sein:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten. Benutzer können nur zu einer einzelnen SLA-Gruppe gehören.

### <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der Option "Gebucht" für die SLA-Gruppe

- Konfigurieren Sie die Option "Gebucht" für die SLA-Gruppe mithilfe des [Cmdlets "Set-CsSlaConfiguration":](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Im folgenden Beispiel werden Anrufe, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, an die Telefonnummer 202-555-1234 weitergeleitet. Das Ziel kann ein Benutzer in Ihrer Organisation anstelle einer Telefonnummer sein. in diesem Fall ist die Syntax für die Person zum Empfangen der weitergeleiteten Anrufe identisch mit der Syntax, wenn Sie eine Stellvertretung  `sip:<NameofDelegate@domain>` angeben: Der andere mögliche Parameter für  `BusyOption` `Voicemail` ist:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option "Verpasste Anrufe für DIE GRUPPE"

1. Konfigurieren Sie die Option für verpasste Anrufe für die SLA-Gruppe mithilfe des [Cmdlets "Set-CsSlaConfiguration":](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit dem Namen weitergeleitet werden  `sla_forward_number` sollen. Die gültigen Optionen für den  `-MissedCallOption` Parameter sind , oder `Forward`  `BusySignal`  `Disconnect` . Wenn Sie diese Option auswählen, müssen Sie auch den Parameter mit einem Benutzer oder einer Telefonnummer  `Forward`  `-MissedCallForwardTarget` als Ziel angeben:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Entfernen einer Stellvertretung aus einer Gruppe

- Entfernen Eines Delegaten aus einer Gruppe mithilfe des [Cmdlets "Remove-CsSlaDelegates":](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

- Löschen Sie eine SLA-Gruppe mithilfe des [Cmdlets "Remove-CsSlaConfiguration":](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


