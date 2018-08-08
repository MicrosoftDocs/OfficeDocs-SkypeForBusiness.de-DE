---
title: Zuweisen einer VoIP-Routingrichtlinie
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie eine VoIP-Richtlinie für Benutzer mit Telefonsystem im Office 365 mit lokalen PSTN-Anbindung zuweisen.'
ms.openlocfilehash: 43d8939e6e0cd49f66234e127f05cb421700a15a
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569498"
---
# <a name="assign-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routingrichtlinie
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie eine VoIP-Richtlinie für Benutzer mit Telefonsystem im Office 365 mit lokalen PSTN-Anbindung zuweisen. 
  
Sobald ein Benutzer auf Skype für Business Online und lokalen PSTN-Anbindung Telefonsystem in Office 365 mit ist, werden zwei VoIP-Richtlinien angewendet werden. Eine ist eine lokale VoIP-Routingrichtlinie, die Sie lokal zuweisen möchten. Diese Richtlinie kann global oder benutzerspezifische und definiert, welche PSTN-verwendungsdatensätzen dem Benutzer zugeordnet sind. In diesem Thema wird erläutert, wie die Richtlinie zugewiesen wird.
  
Die VoIP-Richtlinie definiert, welche Anruffunktionen für den Benutzer verfügbar sind. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für alle Telefonsystem in Office 365 mit lokalen PSTN Connectivity Benutzer identisch. Es wird automatisch Telefonsystem in Office 365-Benutzer zugewiesen.
  
||**Lokale Benutzer**|**Telefonsystem in Office 365 mit lokalen PSTN Connectivity-Benutzer**|
|:-----|:-----|:-----|
|Anruffunktionen definiert in  <br/> |VoIP-Richtlinie  <br/> |Vordefiniert sind VoIP-Richtlinie, die automatisch zugeordnet werden, wenn der Benutzer für Telefonsystem in Office 365 lizenziert ist.  <br/> |
|PSTN-Verwendungsdatensätze in Verbindung mit  <br/> |VoIP-Richtlinie  <br/> |VoIP-Routingrichtlinie, wird zugeordnet, während der Benutzer noch lokal verwaltet wird.  <br/> |
   
Sie führen die folgenden Schritte aus, die mit der lokalen Bereitstellung während der Benutzer noch in der lokalen Bereitstellung verwaltet wird.
  
## <a name="using-a-global-voice-routing-policy"></a>Verwenden einer globalen VoIP-Richtlinie

Bevor Sie eine globale VoIP-Routingrichtlinie für Ihr Telefonsystem in Office 365 mit lokalen PSTN Connectivity Benutzer verwenden, müssen Sie PSTN-Verwendungseinträge für die Richtlinie hinzufügen.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>So werden der globalen VoIP-Routingrichtlinie PSTN-Verwendungsdatensätze zugeordnet

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Fügen Sie die PSTN-verwendungsdatensätzen der Richtlinie:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
  ```

    Beispiel:
    
  ```
  Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
  ```

## <a name="creating-a-new-voice-routing-policy"></a>Erstellen einer neuen VoIP-Routingrichtlinie

### <a name="to-create-a-new-voice-routing-policy"></a>So erstellen Sie eine neue VoIP-Routingrichtlinie

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Erstellen Sie eine neuen VoIP-Routingrichtlinie:
    
  ```
  New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
  ```

    Beispiel:
    
  ```
  New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
  ```

In diesem Beispiel wird eine neue VoIP-Routingrichtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.
  
## <a name="assigning-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routingrichtlinie

Unabhängig davon, ob Sie eine globale oder eine benutzerorientierte VoIP-Routingrichtlinie verwenden, durchlaufen Sie die folgenden Schritte, um einem Benutzer die Richtlinie zuzuordnen.
  
### <a name="to-assign-the-voice-routing-policy"></a>So ordnen Sie eine VoIP-Routingrichtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Weisen Sie einem Benutzer eine vorhandene VoIP-Richtlinie zu:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
  ```

    Beispiel:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
  ```

In diesem Beispiel wird der Benutzer mit dem Anzeigenamen „Bob Kelly“ einer zuvor erstellten VoIP-Richtlinie mit dem Namen „HybridVoice“ zugewiesen.
  
Weitere Informationen zur VoIP-Routingrichtlinien zurückgegeben, finden Sie unter [Erstellen oder ändern eine VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), ["New-csvoiceroutingpolicy"](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

