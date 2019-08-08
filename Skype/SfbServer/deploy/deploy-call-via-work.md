---
title: Bereitstellen von Anrufen über die Arbeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen Anruf über die Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.'
ms.openlocfilehash: d1c55e44cae944664a51eaddb2ad54e758d4f52c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234254"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Bereitstellen von Anrufen über die Arbeit in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen Anruf über die Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.
  
Führen Sie die folgenden Schritte aus, um Anrufe über Arbeit für Ihre Benutzer bereitzustellen. Planungsüberlegungen werden in [Plan für Anruf über die Arbeit in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)erörtert. In früheren Versionen von lync Server war die Remoteanrufsteuerung ein Feature, mit dem Benutzer Ihre PBX-Telefone mit lync Server steuern konnten. In Skype for Business Server wurde diese Funktion durch Anruf über Arbeit ersetzt. 
  
## <a name="prerequisites-for-call-via-work"></a>Voraussetzungen für Anrufe über die Arbeit

Bei Anrufen über die Arbeit wird die Unified Communications Web API (UCWA) verwendet, die automatisch auf allen Skype for Business Server-Front-End-Servern installiert wird. Damit Benutzer den Anruf über die Arbeit tätigen können, müssen Sie auch die folgenden Voraussetzungen erfüllen: 
  
- Sie müssen über einen Vermittlungsserver verfügen, der entweder als Teil eines Front-End-Servers oder als eigenständige Rolle bereitgestellt wird. Weiterhin müssen Sie ein IP-PBX-Gateway bereitstellen.
    
- Alle Benutzer, die über Arbeit für den Anruf aktiviert werden, müssen über eine direkte nach innen Wahl (DID) auf dem PBX-Telefonsystem verfügen. 
    
- Sie müssen alle Anrufe über geschäftliche Benutzer für Enterprise-VoIP aktivieren. Wenn Sie dies tun, müssen Sie die Skype for Business-Nummer für jeden Benutzer auf die entsprechende DID-Nummer für das entsprechende PBX-Telefonsystem konfigurieren. 
    
- Alle Benutzer, die über Arbeit anrufen, müssen in Ihrem Skype for Business-Client über die Option " **Erweiterte Verbindungen** " eine **Automatische Konfiguration** ausgewählt haben. Auf diese Weise kann der Client die UCWA-URLs ermitteln. **Automatische Konfiguration** ist die Standardauswahl.
    
- Aktivieren Sie für jeden Anruf über den Arbeits Benutzer die Anrufweiterleitung und gleichzeitiges Klingeln. 
    
- Stellen Sie für jeden Anruf über den Arbeits Benutzer sicher, dass Einwahlkonferenzen und Konferenz Auswahl aktiviert sind. Auf diese Weise können diese Benutzer in Skype for Business-Konferenzen einstweilen.
    
- Stellen Sie sicher, dass Delegierung, Team Anruf und Reaktionsgruppe für jeden Anruf über den Arbeits Benutzer deaktiviert sind.
    
## <a name="deploy-call-via-work"></a>Bereitstellen der Funktion „Anruf über Arbeit“

Wenn alle Voraussetzungen erfüllt sind, gehen Sie wie folgt vor:
  
- Erstellen Sie eine globale Telefonnummer für Ihre Bereitstellung, die Skype for Business auf der Rufnummernanzeige von Benutzern anzeigt, die Anrufe über geschäftliche Anrufe tätigen. 
    
- Erstellen eines oder mehrerer Anrufe über Arbeitsrichtlinien
    
- Zuweisen eines Anrufs über die Arbeitsrichtlinie für jeden Benutzer, der über die Arbeit für den Anruf aktiviert wird
    
### <a name="create-the-call-via-work-global-phone-number"></a>Erstellen der globalen „Anruf über Arbeit“-Telefonnummer

- Geben Sie das folgende Cmdlet ein
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Mit dem folgenden Cmdlet wird die globale Telefonnummer beispielsweise auf 1-555-123-4567 festgelegt.
    
  ```
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Erstellen einer Richtlinie für „Anruf über Arbeit“

- Geben Sie das folgende Cmdlet ein
    
  ```
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Das folgende Cmdlet erstellt beispielsweise einen Anruf über die Arbeitsrichtlinie mit dem Namen ContosoUser1CvWP, erfordert, dass der Benutzer eine Administrator Rückrufnummer verwendet, und legt diese Rückrufnummer auf 1-555-789-1234 fest.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Zuweisen eines Anrufs über die Arbeitsrichtlinie an einen Benutzer

- Geben Sie das folgende Cmdlet ein
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Das folgende Cmdlet weist beispielsweise dem Benutzer mit dem Namen **ContosoUser1**den Anruf über die Arbeitsrichtlinie "ContosoUser1CvWP" zu.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Siehe auch

[Planen eines Anrufs über die Arbeit in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

