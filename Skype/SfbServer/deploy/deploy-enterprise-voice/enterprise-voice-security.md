---
title: Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Zusammenfassung: Informationen zu den Sicherheits-und Konfigurationsvoraussetzungen für Enterprise-VoIP in Skype for Business Server.'
ms.openlocfilehash: 314c25429dbf346a5f62705afa4f19a5b518452a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767238"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Voraussetzungen für Sicherheit und Konfiguration für Enterprise-VoIP in Skype for Business Server.
  
Überprüfen Sie vor der Bereitstellung von Enterprise-VoIP, ob Ihre Infrastruktur die folgenden Sicherheits-, Benutzer Konfigurations-und Szenario-spezifischen Hardwarevoraussetzungen erfüllt. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Administrative Rechte und Zertifikatinfrastruktur

Überprüfen Sie vor der Bereitstellung die folgenden Punkte:
  
- Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglieder der RTCUniversalServerAdmins-Gruppe sein.
    
- Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:
    
  - **CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.
    
  - **CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem benutzerbasierte Richtlinien zuweisen. Hiervon ausgenommen sind die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.
    
  - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit „CsVoiceAdministrator“ und „CsUserAdministrator“ ausgeführt werden können.
    
- Eine Managed Key-Infrastruktur (MKI) wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter bereitgestellt und konfiguriert.
    
    > [!NOTE]
    > Details zu den Zertifikatanforderungen in Skype for Business Server finden Sie unter [Umweltanforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Benutzerkonfiguration

Wenn Sie den Vermittlungsserver mit jedem Front-End-Pool oder Standard Edition-Server während der Front-End-Bereitstellung zusammengestellt haben, wurden die für Enterprise-VoIP erforderlichen Benutzereinstellungen während der Installation der Dateien für diese Server Rollen automatisch konfiguriert.
  
Wenn Sie die Enterprise-VoIP-Arbeitsauslastung zu diesem Zeitpunkt neu bereitstellen, bevor Sie mit dem Bereitstellungsprozess beginnen, legen Sie für jeden Benutzer, den Sie für Enterprise-VoIP aktivieren möchten, eine primäre Telefonnummer fest. Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen. Vor der Implementierung müssen alle primären Telefonnummern normalisiert (korrekt formatiert) und mithilfe der Skype for Business Server-Systemsteuerung in die Eigenschaft des jeweiligen Benutzer- **URI** kopiert werden.
  
> [!NOTE]
> Beispiele für primäre Rufnummern, die für eine Enterprise-VoIP-Bereitstellung erforderlich sind, finden Sie unter [Sample Normalization Rules](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules). 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Anbindung

Nach der Überprüfung der Software-und Umgebungsvoraussetzungen für Enterprise-VoIP können Sie entweder:
  
- Installieren Sie den Vermittlungsserver, wie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](deploy-a-mediation-server.md)beschrieben, aber nur, wenn Sie einen eigenständigen Vermittlungsserver oder Pool bereitstellen möchten, weil Vermittlungsserver als Teil des Front-End-Pools oder des Standard Edition-Server Bereitstellungsprozesses bei der Zusammenstellung installiert werden.
    
- Oder beginnen Sie mit der Konfiguration von Einstellungen für die Weiterleitung von Anrufen für Enterprise-VoIP-Benutzer, wie unter [Konfigurieren von Trunks in Skype for Business Server](configure-trunks.md)beschrieben.
    

