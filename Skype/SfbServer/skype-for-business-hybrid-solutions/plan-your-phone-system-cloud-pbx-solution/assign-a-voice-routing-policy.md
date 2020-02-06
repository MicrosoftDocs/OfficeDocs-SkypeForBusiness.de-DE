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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: c7f78f23-b74f-402f-bedb-4cc308718f5b
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie eine VoIP-Richtlinie für Benutzer zuweisen, die das Telefon System in Office 365 mit einer lokalen PSTN-Verbindung verwenden.'
ms.openlocfilehash: 0e9a39fba8d1db7b70f0422e71223d49917716ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803995"
---
# <a name="assign-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routingrichtlinie
 
**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie eine VoIP-Richtlinie für Benutzer zuweisen, die das Telefon System in Office 365 mit lokalen PSTN-Verbindungen verwenden. 
  
Sobald sich ein Benutzer in Skype for Business Online befindet und die Telefonanlage in Office 365 mit lokalen PSTN-Konnektivität verwendet, gelten zwei VoIP-Richtlinien für Sie. Eine ist eine lokale VoIP-Routing Richtlinie, die Sie lokal zuweisen können. Diese Richtlinie kann global oder benutzerspezifisch sein und definiert, welche PSTN-Verwendungsdaten Sätze dem Benutzer zugeordnet sind. In diesem Thema wird erläutert, wie die Richtlinie zugewiesen wird.
  
Die andere VoIP-Richtlinie definiert, welche Anruffeatures für den Benutzer verfügbar sind. Diese VoIP-Richtlinie wird von Microsoft definiert und ist für das gesamte Telefon System in Office 365 mit lokalen PSTN-Konnektivitäts-Benutzern identisch. Sie wird automatisch dem Telefon System in Office 365-Benutzern zugewiesen.
  
||**Lokale Benutzer**|**Telefon System in Office 365 mit lokalem PSTN-Konnektivitäts-Benutzer**|
|:-----|:-----|:-----|
|Anruffunktionen definiert in  <br/> |VoIP-Richtlinie  <br/> |Vordefinierte VoIP-Richtlinie, die automatisch zugewiesen wird, wenn der Benutzer für das Telefon System in Office 365 lizenziert ist.  <br/> |
|PSTN-Verwendungsdatensätze in Verbindung mit  <br/> |VoIP-Richtlinie  <br/> |VoIP-Routingrichtlinie, wird zugeordnet, während der Benutzer noch lokal verwaltet wird.  <br/> |
   
Mit der lokalen Bereitstellung führen Sie die folgenden Schritte aus, während der Benutzer weiterhin in der lokalen Bereitstellung verwaltet wird.
  
## <a name="using-a-global-voice-routing-policy"></a>Verwenden einer globalen VoIP-Richtlinie

Bevor Sie eine globale VoIP-Routing Richtlinie für Ihr Telefon System in Office 365 mit lokalen PSTN-Konnektivitäts-Benutzern verwenden, müssen Sie der Richtlinie PSTN-Verwendungsdaten Sätze hinzufügen.
  
### <a name="to-assign-pstn-usage-records-to-the-global-voice-routing-policy"></a>So werden der globalen VoIP-Routingrichtlinie PSTN-Verwendungsdatensätze zugeordnet

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Fügen Sie der Richtlinie die PSTN-Verwendungseinträge hinzu:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages <PSTNUsagesId> 
   ```

    Beispiel:
    
   ```powershell
   Set-CSVoiceRoutingPolicy -Identity Global -PSTNUsages "Local", "Long Distance" 
   ```

## <a name="creating-a-new-voice-routing-policy"></a>Erstellen einer neuen VoIP-Routingrichtlinie

### <a name="to-create-a-new-voice-routing-policy"></a>So erstellen Sie eine neue VoIP-Routingrichtlinie

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Erstellen Sie eine neuen VoIP-Routingrichtlinie:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity <String> -Name <String> -PSTNUsages <PSTNUsagesId>
   ```

    Beispiel:
    
   ```powershell
   New-CSVoiceRoutingPolicy -Identity HybridVoice -Name Hybrid -PSTNUsages "Local", "Long Distance"
   ```

In diesem Beispiel wird eine neue VoIP-Routingrichtlinie namens HybridVoice erstellt, der zwei PSTN-Verwendungen zugeordnet sind.
  
## <a name="assigning-a-voice-routing-policy"></a>Zuweisen einer VoIP-Routingrichtlinie

Unabhängig davon, ob Sie eine globale oder eine benutzerorientierte VoIP-Routingrichtlinie verwenden, durchlaufen Sie die folgenden Schritte, um einem Benutzer die Richtlinie zuzuordnen.
  
### <a name="to-assign-the-voice-routing-policy"></a>So ordnen Sie eine VoIP-Routingrichtlinie zu

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Weisen Sie einem Benutzer eine vorhandene VoIP-Richtlinie zu:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    Beispiel:
    
   ```powershell
   Grant-CsVoiceRoutingPolicy -Identity "Bob Kelly" -PolicyName HybridVoice
   ```

In diesem Beispiel wird der Benutzer mit dem Anzeigenamen „Bob Kelly“ einer zuvor erstellten VoIP-Richtlinie mit dem Namen „HybridVoice“ zugewiesen.
  
Weitere Informationen zu VoIP-Routing Richtlinien finden Sie unter [erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business 2015](../../deploy/deploy-enterprise-voice/voice-policy-and-pstn-usage-records.md), [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps)und [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoicepolicy?view=skype-ps).
  

