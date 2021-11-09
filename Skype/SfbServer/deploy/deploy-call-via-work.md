---
title: Bereitstellen von "Anruf über Arbeit" in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Zusammenfassung: Erfahren Sie, wie Sie Anruf über Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.'
ms.openlocfilehash: 932d94c13d4ba9ead63504cfba66175db52084d7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851619"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Bereitstellen von "Anruf über Arbeit" in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Anruf über Arbeit in Skype for Business Server für einige oder alle Ihre Benutzer bereitstellen.
  
Führen Sie die folgenden Schritte aus, um Anruf über Arbeit für Ihre Benutzer bereitzustellen. Planungsüberlegungen werden in ["Plan for Call Via Work" in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)erläutert. In früheren Versionen von Lync Server war die Remoteanrufsteuerung ein Feature, mit dem Benutzer ihre Nebenstellenanlagentelefone mit Lync Server steuern konnten. In Skype for Business Server wurde dieses Feature durch "Über Arbeit anrufen" ersetzt. 
  
## <a name="prerequisites-for-call-via-work"></a>Voraussetzungen für anruf per Arbeit

Call Via Work verwendet unified Communications Web API (UCWA), die automatisch auf allen Skype for Business Server Front-End-Servern installiert wird. Um Benutzer für "Anruf über Arbeit" zu aktivieren, müssen auch die folgenden Voraussetzungen erfüllt sein: 
  
- Sie müssen einen Vermittlungsserver bereitstellen, entweder als Teil eines Front-End-Servers oder als eigenständige Rolle. Sie müssen auch ein IP-PBX-Gateway bereitstellen.
    
- Alle Benutzer, die für "Anruf über Arbeit" aktiviert sind, müssen über eine DID (Direct Inward Dialing) auf dem PbX-Telefonsystem verfügen. 
    
- Sie müssen alle Benutzer von "Anruf über Arbeit" für Enterprise-VoIP aktivieren. Wenn Sie dies tun, müssen Sie die Skype for Business DID-Nummer für jeden Benutzer mit der entsprechenden DID-Nummer für das entsprechende PBX-Telefonsystem konfigurieren. 
    
- Alle Benutzer, die "Anruf über Arbeit" verwenden, müssen die **automatische Konfiguration** in ihrer Option **"Erweiterte Verbindungen"** in ihrem Skype for Business-Client ausgewählt haben. Dadurch kann der Client die UCWA-URLs ermitteln. **Die automatische Konfiguration** ist die Standardauswahl.
    
- Aktivieren Sie für jeden Benutzer von "Anruf über Arbeit" die Anrufweiterleitung und das gleichzeitige Klingeln. 
    
- Stellen Sie für jeden Benutzer von "Anruf über Arbeit" sicher, dass Einwahlkonferenzen und Einwahlkonferenzen aktiviert sind. Dadurch können diese Benutzer in Skype for Business Konferenzen ein- und ausgehen.
    
- Stellen Sie sicher, dass Delegierung, Teamanruf und Reaktionsgruppe für jeden Benutzer von "Über Arbeit anrufen" deaktiviert sind.
    
## <a name="deploy-call-via-work"></a>Bereitstellen der Funktion "Anruf über Arbeit"

Nachdem die Voraussetzungen erfüllt sind, führen Sie die folgenden Schritte aus:
  
- Erstellen Sie eine globale Telefonnummer für Ihre Bereitstellung, die Skype for Business auf der PBX-Anrufer-ID von Benutzern anzeigt, die Anrufe über Die Arbeit tätigen. 
    
- Erstellen einer oder mehrerer Anruf-über-Arbeit-Richtlinien
    
- Weisen Sie jedem Benutzer, der für "Anruf über Arbeit" aktiviert ist, eine Richtlinie "Anruf über Arbeit" zu.
    
### <a name="create-the-call-via-work-global-phone-number"></a>Erstellen der globalen Telefonnummer für "Anruf über Arbeit"

- Geben Sie das folgende Cmdlet ein.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Mit dem folgenden Cmdlet wird beispielsweise die globale Telefonnummer auf 1-555-123-4567 festgelegt.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Erstellen einer Anruf-über-Arbeit-Richtlinie

- Geben Sie das folgende Cmdlet ein.
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Das folgende Cmdlet erstellt z. B. eine Richtlinie "Call Via Work" namens "ContosoUser1CvWP", erfordert, dass der Benutzer eine Administratorrückrufnummer verwendet, und legt diese Rückrufnummer auf 1-555-789-1234 fest.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Zuweisen einer Anruf-über-Arbeit-Richtlinie zu einem Benutzer

- Geben Sie das folgende Cmdlet ein.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Mit dem folgenden Cmdlet wird beispielsweise die Richtlinie "ContosoUser1CvWP" für "Call Via Work" dem Benutzer namens **"ContosoUser1"** zugewiesen.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Siehe auch

[Plan for Call Via Work in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

