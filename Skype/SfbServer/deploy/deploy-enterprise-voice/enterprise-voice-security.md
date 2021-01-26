---
title: Sicherheits- und Konfigurationsvoraussetzungen für Enterprise-VoIP in Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Zusammenfassung: Erfahren Sie mehr über die Sicherheits- und Konfigurationsvoraussetzungen für Enterprise-VoIP in Skype for Business Server.'
ms.openlocfilehash: 77efbf231f83c6d3c31254c9ab742de7e2b226e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830845"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Sicherheits- und Konfigurationsvoraussetzungen für Enterprise-VoIP in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Sicherheits- und Konfigurationsvoraussetzungen für Enterprise-VoIP in Skype for Business Server.
  
Vergewissern Sie sich vor Enterprise-VoIP, dass Ihre Infrastruktur die folgenden Sicherheits-, Benutzerkonfigurations- und szenariospezifischen Hardwarevoraussetzungen erfüllt. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Administratorrechte und Zertifikatinfrastruktur

Überprüfen Sie vor der Bereitstellung Folgendes:
  
- Administratoren, die Enterprise-VoIP bereitstellen, sollten Mitglied der Gruppe "RTCUniversalServerAdmins" sein.
    
- Administratoren, die die Konfigurationsaufgaben ausführen, müssen über geeignete Rechte verfügen:
    
  - **CsVoiceAdministrator:** Diese Administratorrolle kann VoIP-Konfigurationsaufgaben ausführen, VoIP-Anwendungen verwalten und Endbenutzern VoIP-Richtlinien zuweisen.
    
  - **CsUserAdministrator:** Diese Administratorrolle kann Benutzereigenschaften verwalten, z. B. die Aktivierung von Enterprise-VoIP für einen Benutzer. Diese Administratorrolle kann außerdem Richtlinien auf Benutzerebene zuweisen. Hiervon ausgenommen ist die Archivierungsrichtlinie, das Verschieben von Benutzern, das Verwalten von Telefonen in öffentlichen Bereichen und das Verwalten von analogen Geräten.
    
  - **CsAdministrator:** Diese Administratorrolle kann sämtliche Aufgaben ausführen, die mit "CsVoiceAdministrator" und "CsUserAdministrator" ausgeführt werden können.
    
- Es wurde mithilfe einer Zertifizierungsstelleninfrastruktur von Microsoft oder einem Drittanbieter eine Managed Key-Infrastruktur (MKI) bereitgestellt und konfiguriert.
    
    > [!NOTE]
    > Weitere Informationen zu zertifikatanforderungen in Skype for Business Server finden Sie unter Umgebungsanforderungen für [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Serveranforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Benutzerkonfiguration

Wenn Sie den Vermittlungsserver während der Front-End-Bereitstellung mit jedem Front-End-Pool oder Standard Edition-Server verbinden, wurden die für Enterprise-VoIP erforderlichen Benutzereinstellungen während der Installation der Dateien für diese Serverrollen automatisch konfiguriert.
  
Wenn Sie Enterprise-VoIP neu bereitstellen, müssen Sie vor Beginn der Bereitstellung eine primäre Rufnummer für jeden Benutzer bereitstellen, der für Enterprise-VoIP aktiviert werden soll. Als Administrator sind Sie dafür verantwortlich, die Eindeutigkeit dieser Nummer sicherzustellen. Vor der Implementierung müssen alle primären Telefonnummern normalisiert (ordnungsgemäß formatiert) und mithilfe der Skype for Business Server-Systemsteuerung in die **Line-URI-Eigenschaft** jedes Benutzers kopiert werden.
  
> [!NOTE]
> Beispiele für primäre Telefonnummern, die für die Enterprise-VoIP erforderlich sind, finden Sie unter ["Beispielnormalisierungsregeln".](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules) 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Nächste Schritte: Installieren von Dateien oder Konfigurieren der PSTN-Konnektivität

Nach der Überprüfung der Software- und Umgebungsvoraussetzungen für Enterprise-VoIP Sie entweder:
  
- Installieren Sie den Vermittlungsserver, wie unter "Bereitstellen eines Vermittlungsservers [im Topologie-Generator in Skype for Business Server"](deploy-a-mediation-server.md)beschrieben, jedoch nur, wenn Sie einen eigenständigen Vermittlungsserver oder -pool bereitstellen möchten, da Vermittlungsserver im Rahmen des Front-End-Pools oder Standard Edition-Serverbereitstellungsprozesses installiert werden, wenn sie zusammen ausgeführt werden.
    
- Oder beginnen Sie mit dem Konfigurieren von Einstellungen zum Routen von Anrufen Enterprise-VoIP Benutzer, wie in "Konfigurieren von [Trunks in Skype for Business Server" beschrieben.](configure-trunks.md)
    

