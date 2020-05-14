---
title: Zuweisen einer VoIP-Routing Richtlinie
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
description: 'Zusammenfassung: in diesem Thema erfahren Sie, wie Sie eine VoIP-Richtlinie für Benutzer mit Telefon System mit lokaler PSTN-Konnektivität zuweisen.'
ms.openlocfilehash: 141d3cca560201df921fb4195db55ac60103a3d6
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221859"
---
# <a name="assign-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routing Richtlinie
 
**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie eine VoIP-Richtlinie für Benutzer mit Telefon System mit lokaler PSTN-Konnektivität zuweisen. 
  
Sobald ein Benutzer Skype for Business Online und Telefon System mit lokaler PSTN-Konnektivität verwendet, gelten zwei VoIP-Richtlinien für diese. Eine ist eine lokale VoIP-Routing Richtlinie, die Sie lokal zuweisen werden. Diese Richtlinie kann global oder benutzerspezifisch sein und definiert, welche PSTN-Verwendungsdaten Sätze dem Benutzer zugeordnet sind. In diesem Thema wird erläutert, wie diese Richtlinie zugewiesen wird.
  
Die andere VoIP-Richtlinie definiert, welche Anruffunktionen dem Benutzer zur Verfügung stehen. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für alle Telefonsysteme mit lokalen PSTN-Konnektivitäts-Benutzern identisch. Sie wird automatisch den Telefon System Benutzern zugewiesen.
  
||**Lokaler Benutzer**|**Telefon System mit lokaler PSTN-Konnektivität Benutzer**|
|:-----|:-----|:-----|
|In festgelegte Anruffunktionen  <br/> |VoIP-Richtlinie  <br/> |Vordefinierte VoIP-Richtlinie, die automatisch zugewiesen wird, wenn der Benutzer für das Telefon System lizenziert ist.  <br/> |
|Zugeordnete PSTN-Verwendungsdaten Sätze  <br/> |VoIP-Richtlinie  <br/> |VoIP-Routing Richtlinie, die zugewiesen wird, während der Benutzer noch lokal verwaltet wird.  <br/> |
   
Sie führen die folgenden Schritte mithilfe Ihrer lokalen Bereitstellung aus, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.
  
## <a name="using-a-global-voice-routing-policy"></a>Verwenden einer globalen VoIP-Routing Richtlinie

Bevor Sie eine globale VoIP-Routing Richtlinie für Ihr Telefon System mit lokalen PSTN-Konnektivitäts-Benutzern verwenden, müssen Sie der Richtlinie PSTN-Verwendungsdaten Sätze hinzufügen.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>So weisen Sie der globalen VoIP-Routing Richtlinie PSTN-Verwendungsdaten Sätze zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Fügen Sie die PSTN-Verwendungsdaten Sätze zur Richtlinie hinzu:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Zum Beispiel:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Erstellen einer neuen VoIP-Routing Richtlinie

### <a name="to-create-a-new-voice-routing-policy"></a>So erstellen Sie eine neue VoIP-Routing Richtlinie

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Erstellen Sie eine neue VoIP-Routing Richtlinie:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Zum Beispiel:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

In diesem Beispiel wird eine neue VoIP-Routing Richtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.
  
## <a name="assigning-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routing Richtlinie

Unabhängig davon, ob Sie die globale VoIP-Routing Richtlinie oder benutzerspezifische verwenden, führen Sie die folgenden Schritte aus, um die Richtlinie einem Benutzer zuzuweisen.
  
### <a name="to-assign-the-voice-routing-policy"></a>So weisen Sie die VoIP-Routing Richtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business 2015**, und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Zuweisen einer vorhandenen VoIP-Richtlinie zu einem Benutzer:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Zum Beispiel:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In diesem Beispiel wird der Benutzer mit dem Anzeigenamen Bob Kelly der zuvor erstellten VoIP-Richtlinie mit dem Namen HybridVoice zugewiesen.
  
Weitere Informationen zu VoIP-Routing Richtlinien finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

