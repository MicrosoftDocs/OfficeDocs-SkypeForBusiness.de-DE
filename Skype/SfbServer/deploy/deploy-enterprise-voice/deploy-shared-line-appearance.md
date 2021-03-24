---
title: Bereitstellen einer gemeinsamen Leitung in Skype for Business Server 2015
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
description: In diesem Thema erfahren Sie, wie Sie das kumulative Update für "Shared Line Appearance" (SLA) in Skype for Business Server 2015, November 2015, bereitstellen. SLA ist ein Feature zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.
ms.openlocfilehash: 7758354b7c4be123cb9b5a482af3304b069931a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104911"
---
# <a name="deploy-shared-line-appearance-in-skype-for-business-server-2015"></a>Bereitstellen einer gemeinsamen Leitung in Skype for Business Server 2015

In diesem Thema erfahren Sie, wie Sie das kumulative Update für "Shared Line Appearance" (SLA) in Skype for Business Server 2015, November 2015, bereitstellen. SLA ist ein Feature zum Behandeln mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird.

Weitere Informationen zu diesem Feature finden Sie unter [Plan for Shared Line Appearance in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/shared-line-appearance.md).

Shared Line Appearance (SLA) ist ein neues Feature in Skype for Business Server, kumulatives Update vom November 2015. Um dieses Feature zu aktivieren, müssen Sie dieses kumulative Update zuerst bereitgestellt haben.

### <a name="install-shared-line-appearance"></a>Installieren der Darstellung freigegebener Zeilen

1. Nachdem Skype for Business Server das kumulative Update vom November 2015 bereitgestellt wurde, führen Sie den Patch auf jedem  `SkypeServerUpdateInstaller.exe` Front-End-Server im Pool aus.

2. Das Installationsprogramm stellt die neueste Version der SLA-Anwendung zur Bereitstellung, die Anwendung ist jedoch standardmäßig nicht aktiviert. Sie wird durch die folgenden Schritte aktiviert:

    a. Registrieren Sie SLA als Serveranwendung, indem Sie den folgenden Befehl für jeden Pool ausführen:

   ```powershell
   New-CsServerApplication -Identity 'Service:Registrar:%FQDN%/SharedLineAppearance' -Uri   http://www.microsoft.com/LCS/SharedLineAppearance -Critical $false -Enabled $true -Priority (Get-CsServerApplication -Identity  'Service:Registrar:%FQDN%/UserServices').Priority
   ```

   Dabei ist %FQDN% der vollqualifizierte Domänenname des Pools.

    b. Führen Sie den folgenden Befehl aus, um die ROLLENAC-Rollen für die SLA-Cmdlets zu aktualisieren:

   ```powershell
   Update-CsAdminRole
   ```

    c. Starten Sie alle Front-End-Server (RTCSRV-Dienst) in allen Pools neu, in denen SLA installiert und aktiviert wurde:

   ```powershell
   Stop-CsWindowsService RTCSRV Start-CsWindowsService RTCSRV
   ```

### <a name="create-an-sla-group-and-add-users-to-it"></a>Erstellen einer SLA-Gruppe und Hinzufügen von Benutzern zu dieser Gruppe

1. Erstellen Sie die SLA-Gruppe mithilfe des [Cmdlets Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MaxNumberOfCalls <Number> -BusyOption <BusyOnBusy|Voicemail|Forward> [-Target <TargetUserOrPhoneNumber>]
   ```

    Das Set-CsSlaConfiguration-Cmdlet markiert das Enterprise-VoIP-Konto SLAGroup1 als SLA-Entität, und die Nummer von SLAGroup1 wird zur Nummer für die SLA-Gruppe. Bei allen Anrufen an SLAGroup1 wird die gesamte SLA-Gruppe klingeln.

    Im folgenden Beispiel wird eine SLA-Gruppe für einen vorhandenen Enterprise-VoIP, SLAGroup1, erstellt und die für SLAGroup1 zugewiesene Nummer als SLA-Hauptnetznummer verwendet.

    Der Befehl legt die maximale Anzahl gleichzeitiger Anrufe für die neue SLA-Gruppe auf 3 fest, und für Anrufe, die darüber hinaus ein Besetztsignal hören:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MaxNumberOfCalls 3 -BusyOption BusyOnBusy
   ```

    Sie können Set-CsSlaConfiguration verwenden, um eine neue SLA-Gruppe zu erstellen oder eine vorhandene zu ändern.

    > [!NOTE]
    > Beachten Sie, dass es sich bei den von Ihnen angegebenen Informationen um ein  `-Identity` gültiges vorhandenes Enterprise-VoIP benutzerkonto muss.

2. Fügen Sie der Gruppe delegates mithilfe des [Cmdlets Add-CsSlaDelegates](/powershell/module/skype/add-cssladelegates?view=skype-ps) hinzu:

   ```powershell
   Add-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate
          <NameOfDelegate@domain>
   ```

    Im folgenden Beispiel wird der SLA-Gruppe ein Benutzer hinzufügt. Jeder benutzer, der der Gruppe hinzugefügt wird, muss ein gültiger Enterprise-VoIP benutzerfähig sein:

   ```powershell
   Add-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate1@contoso.com
   ```

    Wiederholen Sie das Cmdlet für jeden Benutzer, den Sie der Gruppe hinzufügen möchten. Benutzer können nur zu einer einzelnen SLA-Gruppe gehören.

### <a name="configure-the-sla-group-busy-option"></a>Konfigurieren der Option "Gebucht" der SLA-Gruppe

- Konfigurieren Sie die Option sla group Busy mit dem [Cmdlet Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

  ```powershell
  Set-CsSlaConfiguration -Identity <IdentityOfGroup> -BusyOption <Option> [-Target <TargetUserOrPhoneNumber>]
  ```

    Im folgenden Beispiel werden Anrufe bestimmt, die die maximale Anzahl gleichzeitiger Anrufe überschreiten, die an die Telefonnummer 202-555-1234 weitergeleitet werden sollen. Das Ziel kann ein Benutzer in Ihrer Organisation anstelle einer Telefonnummer sein. In diesem Fall ist die Syntax für die Person zum Empfangen der weitergeleiteten Anrufe identisch mit der Syntax, wenn Sie eine Stellvertretung angeben:  `sip:<NameofDelegate@domain>` . Der andere mögliche Parameter für  `BusyOption` `Voicemail` ist:

  ```powershell
  Set-CsSlaConfiguration -Identity SLAGroup1 -BusyOption Forward -Target tel:+2025551234
  ```

### <a name="configure-the-sla-group-missed-call-option"></a>Konfigurieren der Option "Verpasster Anruf für die SLA-Gruppe"

1. Konfigurieren Sie die Option für verpasste Anrufe für die SLA-Gruppe mithilfe des [Cmdlets Set-CsSlaConfiguration:](/powershell/module/skype/set-csslaconfiguration?view=skype-ps)

   ```powershell
   Set-CsSlaConfiguration -Identity <IdentityOfGroup> -MissedCallOption <Option> -MissedCallForwardTarget <TargetUserOrPhoneNumber> -BusyOption <Option> -MaxNumberofCalls <#> -Target [Target]
   ```

2. Im folgenden Beispiel wird angegeben, dass verpasste Anrufe an den Benutzer mit dem Namen weitergeleitet werden  `sla_forward_number` sollen. Die gültigen Optionen für  `-MissedCallOption` den Parameter sind , oder `Forward`  `BusySignal`  `Disconnect` . Wenn Sie auswählen, müssen Sie auch den Parameter mit einer Benutzer- oder Telefonnummer als  `Forward`  `-MissedCallForwardTarget` Ziel angeben:

   ```powershell
   Set-CsSlaConfiguration -Identity SLAGroup1 -MissedCallOption Forward -MissedCallForwardTarget sip:sla_forward_number@contoso.com -BusyOption Forward -MaxNumberOfCalls 2 -Target sip:sla_forward_number@contoso.com
   ```

### <a name="remove-a-delegate-from-a-group"></a>Entfernen einer Stellvertretung aus einer Gruppe

- Entfernen Eines Delegaten aus einer Gruppe mithilfe des [Cmdlets Remove-CsSlaDelegates:](/powershell/module/skype/remove-cssladelegates?view=skype-ps)

  ```powershell
  Remove-CsSlaDelegates -Identity <IdentityOfGroup> -Delegate <NameOfDelegate@domain>
  ```

    Zum Beispiel:

  ```powershell
  Remove-CsSlaDelegates -Identity SLAGroup1 -Delegate sip:SLA_Delegate3@contoso.com
  ```

### <a name="delete-an-sla-group"></a>Löschen einer SLA-Gruppe

- Löschen Sie eine SLA-Gruppe mithilfe des [Cmdlets Remove-CsSlaConfiguration:](/powershell/module/skype/remove-csslaconfiguration?view=skype-ps)

  ```powershell
  Remove-CsSlaConfiguration -Identity <IdentityOfGroup>
  ```

    Beispiel:

  ```powershell
  Remove-CsSlaConfiguration -Identity SLAGroup1
  ```