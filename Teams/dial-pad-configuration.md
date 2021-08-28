---
title: Teams der Wähltablockkonfiguration
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
description: Erfahren Sie, wie Sie die Wähltat nicht im Teams-Client konfigurieren, damit Benutzer auf die PstN-Funktionalität (Public Switched Telephone Network) zugreifen können.
ms.openlocfilehash: 6f67aeda059505ec5c1e78d117407f0e9703f732
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627617"
---
# <a name="dial-pad-configuration"></a>Wähltablockkonfiguration

Im Teams-Client können Benutzer über die Wählta nicht über das Telefonnetz (PSTN) auf die Funktionen des öffentlichen Telefonnetzwerks zugreifen. Die Wähltapad ist für Benutzer mit einer Telefonsystem verfügbar, sofern sie ordnungsgemäß konfiguriert sind. Die folgenden Kriterien sind alle erforderlich, damit die Wählta nicht auf der Wählta nicht verwendet werden kann:

- Der Benutzer hat eine Telefonsystem ("MCOEV")-Lizenz aktiviert.
- Der Benutzer verfügt über einen Microsoft-Anrufplan oder ist für direktes Routing aktiviert.
- Benutzer hat Enterprise-VoIP aktiviert
- Der Benutzer ist online und nicht lokal Skype for Business homed.
- Benutzer hat Teams Anrufrichtlinie aktiviert

In den folgenden Abschnitten wird beschrieben, wie Sie die Kriterien mithilfe von PowerShell überprüfen. In den meisten Fällen müssen Sie sich verschiedene Eigenschaften in der Ausgabe des cmdlets Get-CsOnlineUser betrachten. Beispiele setzen $user, dass es sich entweder um die UPN- oder SIP-Adresse des Benutzers handelt.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>Der Benutzer hat eine Telefonsystem ("MCOEV")-Lizenz aktiviert.

Sie müssen sicherstellen, dass im zugewiesenen Plan für den Benutzer das **CapabilityStatus-Attribut** auf Aktiviert und der Funktionsplan auf **MCOEV** (Telefonsystem) festgelegt ist. Möglicherweise sehen Sie MCOEV, MCOEV1 und so weiter. Alle sind akzeptabel, solange der Funktionsplan mit MCOEV beginnt.

Um zu überprüfen, ob die Attribute richtig festgelegt sind, verwenden Sie den folgenden Befehl:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Die Ausgabe sieht wie folgt aus: Sie müssen nur die Attribute **CapabilityStatus** und **Capability Plan** überprüfen:

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>Benutzer hat Microsoft-Anrufplan ODER ist für direktes Routing aktiviert

**Wenn der Benutzer über einen Microsoft-Anrufplan** verfügt, müssen Sie sicherstellen, dass das **CapabilityStatus-Attribut** auf Enabled und der Capability Plan auf **MCOPSTN festgelegt ist.** Möglicherweise wird MCOPSTN1, MCOPSTN2 und so weiter sehen. Alle sind akzeptabel, solange der Funktionsplan mit MCOPSTN beginnt.

Verwenden Sie zum Überprüfen der Attribute den folgenden Befehl:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Die Ausgabe sieht wie folgt aus: Sie müssen nur die Attribute **CapabilityStatus** und **Capability Plan** überprüfen:

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**Wenn der Benutzer für Direct-Routing** aktiviert ist, muss dem Benutzer ein Nicht-NULL-Wert für OnlineVoiceRoutingPolicy zugewiesen sein. Verwenden Sie zum Überprüfen des -Attributs den folgenden Befehl:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

Die Ausgabe sollte einen Nicht-NULL-Wert haben, z. B.:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>Benutzer hat Enterprise-VoIP aktiviert

Um zu überprüfen, ob der Enterprise-VoIP aktiviert ist, verwenden Sie den folgenden Befehl:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

Die Ausgabe sollte wie hier aussehen:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Der Benutzer ist online und nicht lokal Skype for Business homed.

Um sicherzustellen, dass der Benutzer online und nicht in Skype for Business lokal hostet, darf "RegistrarPool" nicht NULL sein und "HostingProvider" muss einen Wert enthalten, der mit "sipfed.online" beginnt.  Verwenden Sie zum Überprüfen der Werte den folgenden Befehl:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Die Ausgabe sollte wie hier angezeigt werden:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>Benutzer hat Teams Anrufrichtlinie aktiviert

Für die effektive TeamsCallingPolicy des Benutzers muss AllowPrivateCalling auf true festgelegt sein.  Standardmäßig erben Benutzer die globale Richtlinie, bei der AllowPrivateCallingPolicy standardmäßig auf "true" festgelegt ist.

Verwenden Sie den folgenden Befehl, um TeamsCallingPolicy für einen Benutzer zu erhalten und zu überprüfen, ob AllowPrivateCalling auf "true" festgelegt ist:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

Die Ausgabe sollte wie hier aussehen:

```
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

-   Möglicherweise müssen Sie den Teams neu starten, nachdem Sie eine dieser Konfigurationsänderungen vorgenommen haben.

-   Wenn Sie kürzlich eines der oben genannten Kriterien aktualisiert haben, müssen Sie möglicherweise einige Stunden warten, bis der Client die neuen Einstellungen erhält.

-   Wenn die Wähltastierung immer noch nicht angezeigt wird, überprüfen Sie mithilfe des folgenden Befehls, ob ein Bereitstellungsfehler vor liegt:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Wenn es mehr als 24 Stunden gezeit ist und weiterhin Probleme auftreten, wenden Sie sich an den Support.


