---
title: Zuweisen einer Voiceroutingrichtlinie
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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Summary: Read this topic to learn how to assign a voice policy for users using Phone System with on-premises PSTN connectivity.'
ms.openlocfilehash: 43e2b560cc0886bacd6faaec6c113ee1f237eff7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092963"
---
# <a name="assign-a-voice-routing-policy"></a>Zuweisen einer Voiceroutingrichtlinie
 
> [!Important]
> Skype for Business Online wird am 31. Juli 2021 eingestellt, nachdem der Zugriff auf den Dienst nicht mehr möglich ist.  Darüber hinaus wird die PSTN-Verbindung zwischen Ihrer lokalen Umgebung über Skype for Business Server oder Cloud Connector Edition und Skype for Business Online nicht mehr unterstützt.  Erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Benutzern, die das Telefonsystem mit einer lokalen PSTN-Verbindung verwenden, eine Sprachrichtlinie zuweisen. 
  
Sobald sich ein Benutzer in Skype for Business Online befindet und das Telefonsystem mit einer lokalen PSTN-Verbindung verwendet, gelten zwei Sprachrichtlinien für sie. Bei einer handelt es sich um eine lokale Voiceroutingrichtlinie, die Sie lokal zuweisen. Diese Richtlinie kann global oder benutzerspezifisch sein und definiert, welche PSTN-Verwendungsdatensätze dem Benutzer zugeordnet sind. In diesem Thema wird erläutert, wie Diese Richtlinie zugewiesen wird.
  
Die andere #A0 definiert, welche Anruffunktionen dem Benutzer zur Verfügung stehen. Diese Sprachrichtlinie wird von Microsoft definiert und ist für alle Telefonsystembenutzer mit lokalen PSTN-Konnektivitätsbenutzern identisch. Es wird automatisch Benutzern des Telefonsystems zugewiesen.
  
||**Lokale Benutzer**|**Telefonsystem mit lokalem PstN-Konnektivitätsbenutzer**|
|:-----|:-----|:-----|
|In definierten Aufrufen von Features  <br/> |VoIP-Richtlinie  <br/> |Vordefinierte Sprachrichtlinie, die automatisch zugewiesen wird, wenn der Benutzer für das Telefonsystem lizenziert ist.  <br/> |
|Zugeordnete PSTN-Verwendungsdatensätze  <br/> |VoIP-Richtlinie  <br/> |Voice routing policy, assigned while the user is still homed on-premises.  <br/> |
   
Sie führen die folgenden Schritte mithilfe Ihrer lokalen Bereitstellung aus, während der Benutzer weiterhin in der lokalen Bereitstellung zu Hause ist.
  
## <a name="using-a-global-voice-routing-policy"></a>Verwenden einer globalen Voiceroutingrichtlinie

Bevor Sie eine globale Voiceroutingrichtlinie für Ihr Telefonsystem mit lokalen Benutzern der PSTN-Konnektivität verwenden, müssen Sie der Richtlinie PSTN-Verwendungsdatensätze hinzufügen.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>So weisen Sie der globalen Voiceroutingrichtlinie PSTN-Verwendungsdatensätze zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Fügen Sie der Richtlinie die PSTN-Verwendungsdatensätze hinzu:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Zum Beispiel:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Erstellen einer neuen Voiceroutingrichtlinie

### <a name="to-create-a-new-voice-routing-policy"></a>So erstellen Sie eine neue Voiceroutingrichtlinie

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Erstellen einer neuen Voiceroutingrichtlinie:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Zum Beispiel:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

In diesem Beispiel wird eine neue Voiceroutingrichtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.
  
## <a name="assigning-a-voice-routing-policy"></a>Zuweisen einer Voiceroutingrichtlinie

Unabhängig davon, ob Sie die globale Voiceroutingrichtlinie oder benutzerspezifische Verwenden, verwenden Sie die folgenden Schritte, um die Richtlinie einem Benutzer zuzuordnen.
  
### <a name="to-assign-the-voice-routing-policy"></a>So weisen Sie die Voiceroutingrichtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Weisen Sie einem Benutzer eine vorhandene Sprachrichtlinie zu:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Zum Beispiel:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In diesem Beispiel wird der Benutzer mit dem Anzeigenamen Bob Kelly der zuvor erstellten Sprachrichtlinie mit dem Namen HybridVoice zugewiesen.
  
Weitere Informationen zu Voiceroutingrichtlinien finden Sie unter [Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
