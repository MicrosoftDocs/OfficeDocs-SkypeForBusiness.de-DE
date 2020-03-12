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
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Bereitstellen der Darstellung freigegebener Leitungen in Skype for Business Server 2015

Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in Skype for Business Server 2015, November 2015, Kumulatives Update, bereitstellen. SLA ist ein Feature für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.

Weitere Informationen zu dieser Funktion finden Sie unter [Planen der Darstellung freigegebener Leitungen in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Die Darstellung freigegebener Leitungen (SLA) ist ein neues Feature in Skype for Business Server, November 2015 Kumulatives Update. Zum Aktivieren dieses Features müssen Sie zunächst dieses kumulative Update bereitgestellt haben.

### <a name="install-shared-line-appearance"></a>Installieren der Darstellung freigegebener Leitungen

1. Nachdem Skype for Business Server November 2015 Kumulatives Update bereitgestellt wurde, führen `SkypeServerUpdateInstaller.exe` Sie den Patch auf jeder Front-End-Server im Pool aus.

2. Das Installationsprogramm stellt die neueste Version der SLA-Anwendung bereit, die Anwendung ist jedoch standardmäßig nicht aktiviert. Sie wird mithilfe der unten aufgeführten Schritte aktiviert:

    a. Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   Dabei ist% FQDN% der vollqualifizierte Domänenname des Pools.

    b. Führen Sie den folgenden Befehl aus, um die RBAC-Rollen für die SLA-Cmdlets zu aktualisieren:

   ```powershell
   Update-CsAdminRole
   ```

    c. Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern zu ihr

1. Erstellen Sie die SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) ":

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Das Cmdlet "CsSlaConfiguration" kennzeichnet das SLAGroup1 des Enterprise-VoIP-Kontos als SLA-Entität, und die Anzahl der SLAGroup1 wird zur Nummer für die SLA-Gruppe. Alle Anrufe an SLAGroup1 rufen die gesamte SLA-Gruppe ab.

    Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP-Benutzer SLAGroup1 erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptnummer verwendet.

    Mit dem Befehl wird die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 festgelegt, und für Anrufe, die darüber hinausgehen, um ein Besetztzeichen zu hören:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Mithilfe von "CsSlaConfiguration" können Sie eine neue SLA-Gruppe erstellen oder eine vorhandene ändern.

    > [!NOTE]
    > Beachten Sie, dass für `-Identity` ein gültiges vorhandenes Enterprise-VoIP-aktiviertes Benutzerkonto angegeben werden muss.

2. Fügen Sie der Gruppe Stellvertretungen mithilfe des Cmdlets [Add-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/add-cssladelegates?view=skype-ps) hinzu:

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzugefügt. Jeder Benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Benutzer mit Enterprise-VoIP sein:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten. Benutzer können nur zu einer einzelnen SLA-Gruppe gehören.

### <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der Option "besetzt" der SLA-Gruppe

- Konfigurieren Sie die Option "besetzt" der SLA [-](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) Gruppe mithilfe des Cmdlets "CsSlaConfiguration":

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Im folgenden Beispiel werden Aufrufe festgelegt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden sollen. Bei dem Ziel kann es sich um einen Benutzer in Ihrer Organisation anstelle einer Telefonnummer handeln. in diesem Fall ist die Syntax für die Person, die weitergeleitete Anrufe erhalten soll, identisch mit der Angabe eines `sip:<NameofDelegate@domain>`Delegaten:. Der andere mögliche Parameter für `BusyOption` ist `Voicemail`:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option "verpasste Anrufe bei SLA-Gruppen"

1. Konfigurieren Sie die Option für den verpassten Anruf der SLA-Gruppe mithilfe des Cmdlets " [CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csslaconfiguration?view=skype-ps) ":

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit `sla_forward_number`dem Namen weitergeleitet werden sollen. Die gültigen Optionen für den `-MissedCallOption` Parameter sind `Forward`, `BusySignal`oder `Disconnect`. Wenn Sie sich `Forward`entscheiden, müssen Sie auch den `-MissedCallForwardTarget` Parameter mit einer Benutzer-oder Telefonnummer als Ziel einschließen:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Entfernen eines Stellvertreters aus einer Gruppe

- Entfernen Sie eine Stellvertretung aus einer Gruppe mithilfe des Cmdlets [Remove-CsSlaDelegates](https://docs.microsoft.com/powershell/module/skype/remove-cssladelegates?view=skype-ps) :

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

- Löschen Sie eine SLA-Gruppe mithilfe des Cmdlets [Remove-CsSlaConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csslaconfiguration?view=skype-ps) :

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```


