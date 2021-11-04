---
title: Bereitstellen der Funktion "Gemeinsame Leitungen" in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
description: In diesem Thema erfahren Sie, wie Sie die Funktion "Gemeinsame Leitungen" (Shared Line Appearance, SLA) in Skype for Business Server kumulativen Update vom November 2015 2015 bereitstellen. SLA ist ein Feature für die Behandlung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.
ms.openlocfilehash: edf731976ae9fbf36f99266f0d993c9e4e78fa34
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749444"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Bereitstellen der Funktion "Gemeinsame Leitungen" in Skype for Business Server 2015

In diesem Thema erfahren Sie, wie Sie die Funktion "Gemeinsame Leitungen" (Shared Line Appearance, SLA) in Skype for Business Server kumulativen Update vom November 2015 2015 bereitstellen. SLA ist ein Feature für die Behandlung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.

Weitere Informationen zu diesem Feature finden Sie unter [Plan for Shared Line Appearance in Skype for Business Server 2015.](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md)

SLA (Shared Line Appearance) ist ein neues Feature in Skype for Business Server kumulativen Update vom November 2015. Um dieses Feature zu aktivieren, müssen Sie zuerst dieses kumulative Update bereitgestellt haben.

### <a name="install-shared-line-appearance"></a>Installieren der Funktion "Gemeinsame Leitungen"

1. Führen Sie nach der Bereitstellung des kumulativen Updates vom November 2015 Skype for Business Server den `SkypeServerUpdateInstaller.exe` Patch auf jedem Front-End-Server im Pool aus.

2. Das Installationsprogramm stellt die neueste Version der SLA-Anwendung bereit, die Anwendung ist jedoch nicht standardmäßig aktiviert. Sie wird durch Ausführen der unten beschriebenen Schritte aktiviert:

    a. Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
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

### <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern

1. Erstellen Sie die SLA-Gruppe mithilfe des [Cmdlets "Set-CsSlaConfiguration":](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Das cmdlet Set-CsSlaConfiguration kennzeichnet das Enterprise-VoIP Konto SLAGroup1 als SLA-Entität, und die Anzahl von SLAGroup1 wird zur Nummer für die SLA-Gruppe. Alle Aufrufe von SLAGroup1 klingeln für die gesamte SLA-Gruppe.

    Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP Benutzer, SLAGroup1, erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptliniennummer verwendet.

    Der Befehl legt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 fest, und für anrufe, die darüber hinausgehen, um ein besetztes Signal zu hören:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene gruppe zu ändern.

    > [!NOTE]
    > Beachten Sie, dass es sich bei ihrer Angabe `-Identity` um ein gültiges vorhandenes Enterprise-VoIP aktiviertes Benutzerkonto handelt.

2. Fügen Sie der Gruppe mithilfe des Cmdlets ["Add-CsSlaDelegates"](/powershell/module/skype/add-cssladelegates?view=skype-ps) Stellvertretungen hinzu:

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt. Jeder Benutzer, der der Gruppe hinzugefügt wurde, muss ein gültiger Enterprise-VoIP aktivierter Benutzer sein:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten. Benutzer können nur einer einzigen SLA-Gruppe angehören.

### <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der Beschäftigt-Option für SLA-Gruppe

- Konfigurieren Sie die Beschäftigt-Option der SLA-Gruppe mithilfe des [Cmdlets "Set-CsSlaConfiguration":](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Im folgenden Beispiel werden Anrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden sollen. Das Ziel kann ein Benutzer in Ihrer Organisation anstelle einer Telefonnummer sein. In diesem Fall ist die Syntax für die Person, die die weitergeleiteten Anrufe entgegennehmen soll, identisch mit der Syntax, wenn Sie einen Delegaten angeben:  `sip:<NameofDelegate@domain>` . Der andere mögliche Parameter  `BusyOption` `Voicemail` ist:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option "Verpasster Anruf" für die SLA-Gruppe

1. Konfigurieren Sie die Option für verpasste Anrufe der SLA-Gruppe mithilfe des [Cmdlets "Set-CsSlaConfiguration":](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer namens weitergeleitet werden  `sla_forward_number` sollen. Die gültigen Optionen für den  `-MissedCallOption` Parameter sind , oder `Forward`  `BusySignal`  `Disconnect` . Wenn Sie dies  `Forward` auswählen, müssen Sie auch den  `-MissedCallForwardTarget` Parameter mit einem Benutzer oder einer Telefonnummer als Ziel angeben:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Entfernen eines Delegaten aus einer Gruppe

- Entfernen Eines Delegaten aus einer Gruppe mithilfe des [Cmdlets "Remove-CsSlaDelegates":](/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

- Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets ["Remove-CsSlaConfiguration":](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```