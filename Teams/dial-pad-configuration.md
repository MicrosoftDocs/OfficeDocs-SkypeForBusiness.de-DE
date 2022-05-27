---
title: Teams Wähltastaturkonfiguration
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Wähltastatur im Teams-Client so konfigurieren, dass Benutzer auf PSTN-Funktionen (Public Switched Telephone Network) zugreifen können.
ms.openlocfilehash: 6aa5edf8f57574fa08a224541772c1f9e662f9ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676153"
---
# <a name="dial-pad-configuration"></a>Konfiguration der Wähltastatur

Im Teams-Client ermöglicht die Wähltastatur Benutzern den Zugriff auf PSTN-Funktionen (Public Switched Telephone Network). Die Wähltastatur ist für Benutzer mit einer Telefonsystem Lizenz verfügbar, sofern sie ordnungsgemäß konfiguriert sind. Die folgenden Kriterien sind alle erforderlich, damit die Wähltastatur angezeigt werden kann:

- Der Benutzer verfügt über eine aktivierte Telefonsystem ("MCOEV")-Lizenz
- Der Benutzer verfügt über Microsoft-Anrufplan, Telefonieanbieter oder ist für Direct Routing aktiviert.
- Benutzer hat Enterprise-VoIP aktiviert
- Der Benutzer wird online verwaltet und nicht in Skype for Business lokal
- Benutzer hat Teams Anrufrichtlinie aktiviert

In den folgenden Abschnitten wird beschrieben, wie PowerShell zum Überprüfen der Kriterien verwendet wird. In den meisten Fällen müssen Sie verschiedene Eigenschaften in der Ausgabe des Get-CsOnlineUser-Cmdlets betrachten. Beispiele gehen davon aus$user entweder die UPN- oder SIP-Adresse des Benutzers ist.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>Der Benutzer verfügt über eine aktivierte Telefonsystem ("MCOEV")-Lizenz

Stellen Sie sicher, dass der zugewiesene Plan für den Benutzer das **CapabilityStatus-Attribut auf "Enabled**" und das **Capability-Set auf MCOEV** (Telefonsystem License) anzeigt. Möglicherweise sehen Sie MCOEV, MCOEV1 usw. Alle sind akzeptabel – solange die Funktion mit MCOEV beginnt.

Verwenden Sie den folgenden Befehl, um zu überprüfen, ob die Attribute richtig festgelegt sind:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

Die Ausgabe sieht wie folgt aus. Sie müssen nur den **CapabilityStatus** und die **Capability-Attribute** überprüfen:

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>Der Benutzer verfügt über einen Microsoft-Anrufplan, Telefonieanbieter ODER für Direct Routing aktiviert ist

**Wenn der Benutzer über einen Microsoft-Anrufplan** verfügt, stellen Sie sicher, dass das **CapabilityStatus-Attribut auf "Enabled" und** die **Funktion auf MCOPSTN festgelegt ist**. Möglicherweise werden MCOPSTN1, MCOPSTN2 usw. angezeigt. Alle sind akzeptabel – solange die Funktion mit MCOPSTN beginnt.

Verwenden Sie den folgenden Befehl, um die Attribute zu überprüfen:

```PowerShell
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

Die Ausgabe sieht wie folgt aus. Sie müssen nur den **CapabilityStatus** und die **Capability-Attribute** überprüfen:

```PowerShell
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-...
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-...
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-...
```

**Wenn der Benutzer für Telefonieanbieter aktiviert ist**, muss der Benutzer einen Nicht-Null-Wert für TeamsCarrierEmergencyCallRoutingPolicy haben. Verwenden Sie zum Überprüfen des Attributs den folgenden Befehl:

```PowerShell
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

Die Ausgabe sollte einen Nicht-Null-Wert aufweisen, z. B.:

```PowerShell
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**Wenn der Benutzer für Direct Routing aktiviert ist**, muss dem Benutzer ein Nicht-Null-Wert für "OnlineVoiceRoutingPolicy" zugewiesen werden. Verwenden Sie zum Überprüfen des Attributs den folgenden Befehl:

```PowerShell
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy
```

Die Ausgabe sollte einen Nicht-Null-Wert aufweisen, z. B.:

```PowerShell
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>Benutzer hat Enterprise-VoIP aktiviert

Verwenden Sie den folgenden Befehl, um zu überprüfen, ob der Benutzer Enterprise-VoIP aktiviert hat:

```PowerShell
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

Die Ausgabe sollte wie folgt aussehen:

```PowerShell
EnterpriseVoiceEnabled
----------------------
                  True
```

## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Der Benutzer wird online verwaltet und nicht in Skype for Business lokal

Um sicherzustellen, dass der Benutzer online und nicht in Skype for Business lokal verwaltet wird, darf der RegistrarPool nicht null sein, und der HostingProvider muss einen Wert enthalten, der mit "sipfed.online" beginnt.  Verwenden Sie den folgenden Befehl, um die Werte zu überprüfen:

```PowerShell
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Die Ausgabe sollte folgendermaßen lauten:

```PowerShell
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>Benutzer hat Teams Anrufrichtlinie aktiviert

Für die effektive TeamsCallingPolicy des Benutzers muss AllowPrivateCalling auf "true" festgelegt sein.  Standardmäßig erben Benutzer die globale Richtlinie, bei der AllowPrivateCallingPolicy standardmäßig auf "true" festgelegt ist.

Verwenden Sie den folgenden Befehl, um die TeamsCallingPolicy für einen Benutzer abzurufen und zu überprüfen, ob AllowPrivateCalling auf "true" festgelegt ist:

```PowerShell
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

Die Ausgabe sollte wie folgt aussehen:

```PowerShell
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
```

## <a name="additional-notes"></a>Zusätzliche Hinweise

- Möglicherweise müssen Sie den Teams-Client neu starten, nachdem Sie eine dieser Konfigurationsänderungen vorgenommen haben.

- Wenn Sie kürzlich eines der oben genannten Kriterien aktualisiert haben, müssen Sie möglicherweise einige Stunden warten, bis der Client die neuen Einstellungen erhält.

- Wenn die Wähltastatur immer noch nicht angezeigt wird, überprüfen Sie mit dem folgenden Befehl, ob ein Bereitstellungsfehler vorliegt:

  ```PowerShell
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

- Wenn es länger als 24 Stunden war und weiterhin Probleme auftreten, wenden Sie sich an den Support.
