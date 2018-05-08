---
title: Bereitstellen der Funktion „Anruf über Arbeit“ in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 10/31/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4802d733-14ef-4509-92b9-07173614e45f
description: 'Zusammenfassung: Informationen Sie zum Bereitstellen von Anrufen über Arbeitsplatz in Skype für Business Server 2015 für einige oder alle Benutzer.'
ms.openlocfilehash: e101cf39daedb8d94879b6cf99cd0c7b4ae00e8d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-via-work-in-skype-for-business-server-2015"></a>Bereitstellen der Funktion „Anruf über Arbeit“ in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Bereitstellen von Anrufen über Arbeitsplatz in Skype für Business Server 2015 für einige oder alle Benutzer.
  
Verwenden Sie folgende Schritte aus, um über Arbeitsplatz anrufen für Benutzer bereitzustellen. In [Planen von Anrufen über Arbeitsplatz in Skype für Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)werden Planungsaspekte erläutert. In früheren Versionen von Lync Server Remoteaufruf war Steuerelement ein Feature, das Benutzer ihre Nebenstellentelefone über mit Lync Server steuern aktiviert. Dieses Feature wurde in Skype für Business Server mit über Arbeitsplatz anrufen ersetzt. 
  
## <a name="prerequisites-for-call-via-work"></a>Erforderliche Komponenten für Anruf über den Arbeitsplatz

Über Arbeitsplatz anrufen verwendet Unified Communications Web API (UCWA), die automatisch auf alle Skype für Business Server-Front-End-Server installiert ist. Damit Benutzer für über Arbeitsplatz anrufen können, müssen Sie auch die folgenden erforderlichen Komponenten verfügen: 
  
- Sie müssen einen Vermittlungsserver bereitgestellt haben, entweder als Teil eines Front-End-Servers oder als eigenständige Rolle verfügen. Weiterhin müssen Sie ein IP-PBX-Gateway bereitstellen.
    
- Alle Benutzer, die für über Arbeitsplatz anrufen aktiviert, benötigen ein (Direct Inward Dialing DIALING) auf die Telefonanlage. 
    
- Sie müssen alle über Arbeitsplatz anrufen Benutzer für Enterprise-VoIP aktivieren. Wenn Sie dies tun, müssen Sie die Skype für Business haben Anzahl für jeden Benutzer auf die entsprechende DID-Nummer für das entsprechende PBX-Telefon-System konfigurieren. 
    
- Alle Benutzer, die über Arbeitsplatz anrufen verwenden sollen müssen **Automatische Konfiguration** in die Option **Erweiterte Verbindungen** in ihren Skype für Business Client ausgewählt haben. Dies ermöglicht dem Client die UCWA-URLs zu erkennen. **Automatische Konfiguration** ist die Standardauswahl.
    
- Aktivieren Sie für jeden Benutzer über Arbeitsplatz anrufen die anrufweiterleitung und Gleichzeitiges Klingeln. 
    
- Für jeden Benutzer über Arbeitsplatz anrufen stellen Sie sicher, dass einwahlkonferenzen und Konferenzen Dial-Out-aktiviert sind. Dadurch können diese Benutzer an- und wieder abmelden Skype für Business Konferenzen zu erhalten.
    
- Stellen Sie sicher, dass Delegierung, teamanrufe und reaktionsgruppen für jeden Benutzer über Arbeitsplatz anrufen deaktiviert sind.
    
## <a name="deploy-call-via-work"></a>Bereitstellen der Funktion „Anruf über Arbeit“

Wenn alle Voraussetzungen erfüllt sind, gehen Sie wie folgt vor:
  
- Erstellen Sie eine globale Rufnummer für Ihre Bereitstellung Skype für Unternehmen auf der Nebenstellenanlage Anrufer-ID der Benutzer anzeigt, die über Arbeitsplatz anrufen erachtet werden. 
    
- Erstellen Sie eine oder mehrere über Arbeitsplatz anrufen Richtlinien
    
- Zuweisen einer Richtlinie auf über Arbeitsplatz anrufen an jeden Benutzer, die für über Arbeitsplatz anrufen aktiviert wird
    
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
  New-CsCallViaWorkPolicy [-Identity] <XdsIdentity> [-Tenant <guid>] [-Enabled <bool>] [-UseAdminCallbackNumber
    <bool>] [-AdminCallbackNumber <string>] [-InMemory] [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

  ```

    Das folgende Cmdlet beispielsweise über Arbeitsplatz anrufen-Richtlinie namens ContosoUser1CvWP erstellt, bewirkt, dass den Benutzer eine Rückrufnummer Admin verwenden und diese Rückrufnummer auf 1-555-789-1234 festgelegt.
    
  ```
  New-CsCallViaWorkPolicy -Identity Tag:ContosoUser1CvWP -Enabled $true -UseAdminCallbackNumber $true -AdminCallbackNumber +15557891234
  ```

### <a name="assign-a-call-via-work-policy-to-a-user"></a>Zuweisen einer Richtlinie auf über Arbeitsplatz anrufen, die einem Benutzer

- Geben Sie das folgende Cmdlet ein
    
  ```
  Grant-CsCallViaWorkPolicy -Identity <UserName> -PolicyName Tag:<PolicyName>
  ```

    Beispielsweise weist das folgende Cmdlet die Richtlinie über Arbeitsplatz anrufen "ContosoUser1CvWP" dem Benutzer mit dem Namen **ContosoUser1**.
    
  ```
  Grant-CsCallViaWorkPolicy -Identity ContosoUser1 -PolicyName Tag:ContosoUser1CvWP
  ```

## <a name="see-also"></a>Siehe auch

#### 

[Planen der Anruf über den Arbeitsplatz in Skype für Business Server 2015](../plan-your-deployment/enterprise-voice-solution/call-via-work.md)

