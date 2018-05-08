---
title: Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Zusammenfassung: Informationen Sie zu den Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype für Business Server 2015.'
ms.openlocfilehash: 2ece3aaa99c1e81afd9241e8d435ac0ab3328893
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server-2015"></a>Anforderungen an Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zu den erforderlichen Komponenten Sicherheit und Konfiguration für Enterprise-VoIP in Skype für Business Server 2015.
  
Vor der Bereitstellung von Enterprise-VoIP, stellen Sie sicher, dass Ihre Infrastruktur die folgenden Anforderungen an Sicherheit, Benutzerkonfiguration, und szenariospezifische Hardware erfüllt. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Administrative Rechte und Zertifikatinfrastruktur

Überprüfen Sie vor der Bereitstellung die folgenden Punkte:
  
- Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglied der Gruppe RTCUniversalServerAdmins sein.
    
- Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:
    
  - **CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.
    
  - **CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem benutzerbasierte Richtlinien zuweisen. Hiervon ausgenommen sind die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.
    
  - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit „CsVoiceAdministrator“ und „CsUserAdministrator“ ausgeführt werden können.
    
- Eine Managed Key-Infrastruktur (MKI) wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter bereitgestellt und konfiguriert.
    
    > [!NOTE]
    > Ausführliche Informationen zu zertifikatanforderungen in Skype für Business Server finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). 
  
## <a name="user-configuration"></a>Benutzerkonfiguration

Wenn Sie während der Front-End-Bereitstellung des Vermittlungsservers mit jedem Front-End-Pool oder Standard Edition-Server verbunden, wurden benutzereinstellungen für Enterprise-VoIP automatisch während der Installation der Dateien für diese Serverrollen konfiguriert.
  
Wenn Sie neu die Enterprise-VoIP-Arbeitslast zu diesem Zeitpunkt bereitstellen, bevor Sie mit der Bereitstellung beginnen, legen Sie eine primäre Rufnummer für jeden Benutzer, die Sie für Enterprise-VoIP aktivieren möchten. Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen. Vor der Implementierung alle primären Telefon, dass Zahlen normalisiert werden müssen (ordnungsgemäß formatiert) und auf **Anschluss-URI** -Eigenschaft des Benutzers mithilfe der Skype für Business Server-Systemsteuerung kopiert.
  
> [!NOTE]
> Beispiele für primäre Rufnummern, die für eine Enterprise-VoIP-Bereitstellung erforderlich sind, finden Sie unter [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Anbindung

Nachdem Sie sichergestellt haben, Software und der Umwelt Voraussetzungen für Enterprise-VoIP können Sie entweder:
  
- Installieren Sie der Vermittlungsserver, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015](deploy-a-mediation-server.md), aber nur, wenn Sie einen eigenständigen Vermittlungsserver oder einen Pool bereitstellen, da der Vermittlungsserver installiert sind, als Teil der Vorderseite möchten End-Pool oder Standard Edition-Server-Bereitstellungsprozess beim kombiniert.
    
- Oder: Konfigurieren von Einstellungen für das Anrufrouting für Enterprise-VoIP-Benutzer, wie beschrieben unter [Konfigurieren von Trunks in Skype für Business Server 2015](configure-trunks.md).
    

