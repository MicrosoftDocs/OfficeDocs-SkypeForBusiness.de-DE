---
title: Zuweisen einer VoIP-Routingrichtlinie
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie eine VoIP-Richtlinie für Benutzer zuweisen, die Telefonsystem mit lokaler PSTN-Konnektivität verwenden.'
ms.openlocfilehash: a3524c77cf27dc4fd9ab3a4f74211fc9040aad75
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582539"
---
# <a name="assign-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routingrichtlinie
 
> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, danach ist der Dienst nicht mehr verfügbar.  Darüber hinaus wird die PSTN-Konnektivität zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie eine VoIP-Richtlinie für Benutzer zuweisen, die Telefonsystem mit lokaler PSTN-Konnektivität verwenden. 
  
Sobald ein Benutzer Skype for Business Online ist und Telefonsystem mit lokaler PSTN-Konnektivität verwendet, gelten zwei VoIP-Richtlinien für sie. Eine ist eine lokale VoIP-Routingrichtlinie, die Sie lokal zuweisen. Diese Richtlinie kann global oder benutzerspezifisch sein und definiert, welche PSTN-Verwendungsdatensätze dem Benutzer zugeordnet sind. In diesem Thema wird erläutert, wie Diese Richtlinie zugewiesen wird.
  
Die andere VoIP-Richtlinie definiert, welche Anruffunktionen für den Benutzer verfügbar sind. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für alle Telefonsystem mit lokalen PSTN-Verbindungsbenutzern identisch. Es wird automatisch Telefonsystem Benutzern zugewiesen.
  
||**Lokaler Benutzer**|**Telefonsystem mit lokalen PSTN-Verbindungsbenutzern**|
|:-----|:-----|:-----|
|Anruffunktionen, die in  <br/> |VoIP-Richtlinie  <br/> |Vordefinierte VoIP-Richtlinie, die automatisch zugewiesen wird, wenn der Benutzer für Telefonsystem lizenziert ist.  <br/> |
|PSTN-Verwendungsdatensätze, die mit  <br/> |VoIP-Richtlinie  <br/> |VoIP-Routingrichtlinie, die zugewiesen wird, während der Benutzer weiterhin lokal verwaltet wird.  <br/> |
   
Sie führen die folgenden Schritte mit Ihrer lokalen Bereitstellung aus, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.
  
## <a name="using-a-global-voice-routing-policy"></a>Verwenden einer globalen VoIP-Routingrichtlinie

Bevor Sie eine globale VoIP-Routingrichtlinie für Ihre Telefonsystem mit lokalen PSTN-Verbindungsbenutzern verwenden, müssen Sie der Richtlinie PSTN-Verwendungsdatensätze hinzufügen.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>So weisen Sie der globalen VoIP-Routingrichtlinie PSTN-Verwendungsdatensätze zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Fügen Sie der Richtlinie die PSTN-Verwendungsdatensätze hinzu:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Zum Beispiel:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Erstellen einer neuen VoIP-Routingrichtlinie

### <a name="to-create-a-new-voice-routing-policy"></a>So erstellen Sie eine neue VoIP-Routingrichtlinie

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Erstellen Sie eine neue VoIP-Routingrichtlinie:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Zum Beispiel:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

In diesem Beispiel wird eine neue VoIP-Routingrichtlinie namens "HybridVoice" erstellt, der zwei PSTN-Verwendungen zugeordnet sind.
  
## <a name="assigning-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routingrichtlinie

Unabhängig davon, ob Sie die globale VoIP-Routingrichtlinie oder benutzerspezifische Richtlinien verwenden, führen Sie die folgenden Schritte aus, um die Richtlinie einem Benutzer zuzuweisen.
  
### <a name="to-assign-the-voice-routing-policy"></a>So weisen Sie die VoIP-Routingrichtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Weisen Sie einem Benutzer eine vorhandene VoIP-Richtlinie zu:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Zum Beispiel:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In diesem Beispiel wird der Benutzer mit dem Anzeigenamen Bob Kelly der zuvor erstellten VoIP-Richtlinie mit dem Namen "HybridVoice" zugewiesen.
  
Weitere Informationen zu VoIP-Routingrichtlinien finden Sie unter [Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
