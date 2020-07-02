---
title: Konfiguration der Wähltastatur für Teams
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die Wähltastatur im Teams-Client so konfigurieren, dass Benutzer auf die PSTN-Funktionalität (Public Switched Telephone Network) zugreifen können.
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012416"
---
# <a name="dial-pad-configuration"></a>Wähltasten Konfiguration

Im Teams-Client ermöglicht die Wähltastatur Benutzern den Zugriff auf die PSTN-Funktionalität (Public Switched Telephone Network). Die Wähltasten sind für Benutzer mit einer Telefon System Lizenz verfügbar, vorausgesetzt, Sie sind ordnungsgemäß konfiguriert. Die folgenden Kriterien sind für die Anzeige der Wähltasten erforderlich:

- Der Benutzer verfügt über eine aktivierte Telefon System Lizenz ("MCOEV").
- Der Benutzer hat einen Microsoft-Anrufplan oder ist für die direkte Weiterleitung aktiviert.
- Benutzer hat Enterprise-VoIP aktiviert
- Der Nutzer ist online und nicht in Skype for Business vor Ort.
- Benutzer hat eine Anrufrichtlinie für Teams aktiviert

In den folgenden Abschnitten wird beschrieben, wie Sie die Kriterien mithilfe von PowerShell überprüfen. In den meisten Fällen müssen Sie sich verschiedene Eigenschaften in der Ausgabe des Cmdlets Get-CsOnlineUser ansehen. Beispiele gehen davon aus, dass $User entweder die UPN-oder die SIP-Adresse des Benutzers ist.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>Der Benutzer verfügt über eine aktivierte Telefon System Lizenz ("MCOEV").

Sie müssen sicherstellen, dass der zugewiesene Plan für den Benutzer das **CapabilityStatus-Attribut auf Enabled** und den **Funktionsplan auf MCOEV** (Phone System License) zeigt. Möglicherweise sehen Sie MCOEV, MCOEV1 usw. Alle sind akzeptabel--solange der Kapazitäts Plan mit MCOEV beginnt.

Um zu überprüfen, ob die Attribute richtig festgesetzt sind, verwenden Sie den folgenden Befehl:

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>Der Benutzer hat einen Microsoft-Anrufplan oder ist für die direkte Weiterleitung aktiviert.

**Wenn der Benutzer Microsoft-Anrufplan hat**, müssen Sie sicherstellen, dass das **CapabilityStatus-Attribut auf Enabled festzulegen ist**und dass der **Kapazitätsplan auf MCOPSTN festgesetzt ist**. Möglicherweise sehen Sie MCOPSTN1, MCOPSTN2 usw. Alle sind akzeptabel--solange der Kapazitäts Plan mit MCOPSTN beginnt.

Verwenden Sie den folgenden Befehl, um die Attribute zu überprüfen:

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

**Wenn der Benutzer für die direkte Weiterleitung aktiviert ist**, muss dem Benutzer ein ungleich NULL-Wert für OnlineVoiceRoutingPolicy zugewiesen werden. Verwenden Sie zum Überprüfen des Attributs den folgenden Befehl:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

Die Ausgabe sollte einen Wert ungleich NULL aufweisen, beispielsweise:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>Benutzer hat Enterprise-VoIP aktiviert

Verwenden Sie den folgenden Befehl, um zu überprüfen, ob der Benutzer Enterprise-VoIP aktiviert hat:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

Die Ausgabe sollte wie folgt aussehen:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Der Nutzer ist online und nicht in Skype for Business vor Ort.

Um sicherzustellen, dass der Benutzer online und nicht in Skype for Business lokal gehostet wird, darf der RegistrarPool nicht NULL sein, und der Hostinganbieter muss einen Wert enthalten, der mit "sipfed. Online" beginnt.  Verwenden Sie den folgenden Befehl, um die Werte zu überprüfen:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Die Ausgabe sollte wie folgt aussehen:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>Benutzer hat eine Anrufrichtlinie für Teams aktiviert

Die effektive TeamsCallingPolicy des Benutzers muss AllowPrivateCalling auf "true" festgelegt haben.  Standardmäßig erben Benutzer die globale Richtlinie, bei der AllowPrivateCallingPolicy standardmäßig auf "true" festgelegt ist.

Verwenden Sie den folgenden Befehl, um die TeamsCallingPolicy für einen Benutzer abzurufen und zu überprüfen, ob AllowPrivateCalling auf "true" festgelegt ist:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

Die Ausgabe sollte wie folgt aussehen:

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

## <a name="additional-notes"></a>Zusätzliche Notizen

-   Möglicherweise müssen Sie den Microsoft Teams-Client neu starten, nachdem Sie eine dieser Konfigurationsänderungen vorgenommen haben.

-   Wenn Sie kürzlich eines der oben aufgeführten Kriterien aktualisiert haben, müssen Sie möglicherweise einige Stunden warten, bis der Client die neuen Einstellungen erhalten hat.

-   Wenn die Wähltastatur weiterhin nicht angezeigt wird, überprüfen Sie, ob ein Bereitstellungsfehler vorliegt, indem Sie den folgenden Befehl verwenden:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Wenn es mehr als 24 Stunden war und Sie immer noch Probleme haben, wenden Sie sich an den Support.


