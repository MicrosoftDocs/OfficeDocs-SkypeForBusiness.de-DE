---
title: Bereitstellen von "Anruf über Arbeit" in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Zusammenfassung: Erfahren Sie, wie Sie Anruf über Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.'
ms.openlocfilehash: 41a0ae8462b12cabf735a2501e5b22eac64abe42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825005"
---
# <a name="deploy-call-via-work-in-skype-for-business-server"></a>Bereitstellen von "Anruf über Arbeit" in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Anruf über Arbeit in Skype for Business Server für einige oder alle Benutzer bereitstellen.
  
Verwenden Sie diese Schritte, um "Anruf über Arbeit" für Ihre Benutzer bereitstellen. Planungsüberlegungen werden in [Plan for Call Via Work in Skype for Business Server behandelt.](../plan-your-deployment/enterprise-voice-solution/call-via-work.md) In früheren Versionen der Lync Server-Remoteanrufsteuerung konnten Benutzer ihre Nebenstellentelefone mit Lync Server steuern. In Skype for Business Server wurde diese Funktion durch "Geschäft arbeitsplatz" ersetzt. 
  
## <a name="prerequisites-for-call-via-work"></a>Voraussetzungen für "Anruf über Arbeit"

Call Via Work verwendet Unified Communications Web API (UCWA), die automatisch auf allen Skype for Business Server-Front-End-Servern installiert wird. Um Benutzer für die Funktion "Über Arbeit anrufen" zu aktivieren, müssen außerdem die folgenden Voraussetzungen erfüllt sein: 
  
- Sie müssen einen Vermittlungsserver bereitstellen, entweder als Teil eines Front-End-Servers oder als eigenständige Rolle. Sie müssen auch ein IP-PBX-Gateway bereitstellen.
    
- Alle Benutzer, die für die Funktion "Anruf über Arbeit" aktiviert werden, müssen über ein DID (Direct Inward Dialing) im Nebenstellensystem verfügen. 
    
- Sie müssen alle Benutzer von "Anruf über Arbeit" für Enterprise-VoIP. Wenn Sie dies tun, müssen Sie die Skype for Business -DID-Nummer für jeden Benutzer auf die entsprechende DID-Nummer für das entsprechende Nebenstellensystem konfigurieren. 
    
- Für alle Benutzer, die "Geschäftisch anrufen"  verwenden, muss in der Option "Erweiterte Verbindungen" in ihrem Skype for Business-Client die Option "Automatische Konfiguration" ausgewählt sein.  Dadurch kann der Client die UCWA-URLs ermitteln. **Die automatische Konfiguration** ist die Standardauswahl.
    
- Aktivieren Sie für jeden Benutzer von "Anruf über Arbeit" die Anruf weiterleitung und gleichzeitiges Klingeln. 
    
- Stellen Sie für jeden Benutzer von "Anruf über Arbeit" sicher, dass Einwahlkonferenzen und Einwahlkonferenzen aktiviert sind. Auf diese Weise können diese Benutzer skype for Business-Konferenzen ein- und aus- und wieder herausrufen.
    
- Stellen Sie sicher, dass Delegierung, Teamanruf und Reaktionsgruppe für jeden Benutzer von "Anruf über Arbeit" deaktiviert sind.
    
## <a name="deploy-call-via-work"></a>Bereitstellen der Funktion „Anruf über Arbeit“

Nachdem die Voraussetzungen erfüllt sind, gehen Sie wie folgt vor:
  
- Erstellen Sie eine globale Telefonnummer für Ihre Bereitstellung, die von Skype for Business auf der PBX-Anrufer-ID der Benutzer angezeigt wird, die Anrufe über die Geschäftliche Telefonanrufe tätigt. 
    
- Erstellen einer oder mehreren "Anruf über Arbeit"-Richtlinien
    
- Zuweisen einer Anruf-über-Arbeit-Richtlinie zu jedem Benutzer, der für "Anruf über Arbeit" aktiviert wird
    
### <a name="create-the-call-via-work-global-phone-number"></a>Erstellen der globalen Telefonnummer "Anruf über Arbeit"

- Geben Sie das folgende Cmdlet ein:
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +<PhoneNumber>
  ```

    Das folgende Cmdlet legt beispielsweise die globale Telefonnummer auf 1-555-123-4567 fest.
    
  ```powershell
  Set-CsRoutingConfiguration -CallViaWorkCallerId +15551234567
  ```

### <a name="create-a-call-via-work-policy"></a>Erstellen einer Richtlinie für "Anruf über Arbeit"

- Geben Sie das folgende Cmdlet ein:
    
  ```powershell
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber  <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]
  ```

    Das folgende Cmdlet erstellt beispielsweise die Richtlinie "ContosoUser1CvWP" für "Anruf über Arbeit", erfordert, dass der Benutzer eine Administratorrückrufnummer verwendet, und legt diese Rückrufnummer auf 1-555-789-1234 fest.
    
  ```powershell
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Zuweisen einer Richtlinie "Anruf über Arbeit" zu einem Benutzer

- Geben Sie das folgende Cmdlet ein:
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Das folgende Cmdlet weist beispielsweise dem Benutzer **"ContosoUser1"** die Richtlinie "ContosoUser1CvWP" für "Anruf über Arbeit" zu.
    
  ```powershell
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Weitere Informationen

[Planen der Anruf-über-Arbeit in Skype for Business Server](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

