---
title: Benutzerkonten in Hybridumgebung mit PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über die verschiedenen Kombinationen von Benutzererstellung und welche Kombinationen unterstützt oder nicht unterstützt werden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 34a531c19ba0b7aebc16b09b360c363eff4a1198
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634849"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität

## <a name="about-the-environment"></a>Informationen zur Umgebung

Dieser Artikel bezieht sich auf Umgebungen, in denen die folgenden Punkte zur Verfügung 2010 verfügbar sind: 
 
- Skype for Business Server oder Lync Server 2013 
- Eine Microsoft 365 oder Office 365 Organisation 
- Hybridkonnektivität, die zwischen dem Skype for Business Server und Skype for Business Online oder Microsoft Teams konfiguriert ist 
- Benutzer, die für Anrufe im öffentlichen Telefonnetz (PUBLIC Switched Telephone Network, PSTN) aktiviert sind und diese vom Client aus anrufen

 
Wenn Sie in einer anderen Umgebung arbeiten (z. B. Skype for Business Cloud Connector Edition), wenn keine Hybridlösung konfiguriert ist oder wenn Ihre Benutzer nicht für PSTN-Anrufe aktiviert sind, ist die Unterstützungsmatrix anders.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informationen zu den Kombinationen und der Erklärung zur Unterstützung  

Eine Skype for Business mit PSTN-Anbindung bietet Flexibilität in Bezug auf die Bereitstellung von Benutzerdiensten und die Art und Weise, wie Benutzerkonten bereitgestellt und verwaltet werden. Das Ändern von Optionen kann jedoch zu einigen nicht unterstützten Kombinationen werden. In diesem Abschnitt werden verschiedene Kombinationen von Benutzererstellung erläutert, gefolgt von einer Erklärung zur Unterstützung.


**Definitionen:**   
- **Enterprise-VoIP:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit einem lokalen Skype for Business Benutzerkonto. Der lokale Skype for Business Vermittlungsserver bietet Eine Verbindung mit dem PSTN.  
- **Hybrid-Sprachkonnektivität:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit Skype for Business Online-Konto. Der lokale Skype for Business Vermittlungsserver bietet Eine Verbindung mit dem PSTN. 
- **Direktes Routing:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit Online-Skype for Business-Konto, Microsoft Teams über den Microsoft Teams Client. Der SBC ist in Microsoft 365 oder Office 365 mit dem SIP-Proxy verbunden, ohne dass eine lokale Software von Microsoft benötigt wird.

  
**Die Umgebung unterstützt die folgenden Kombinationen:**
- **Szenario 1:** Das Benutzerkonto in Skype for Business lokal und verwendet den Skype for Business-Client mit Enterprise-VoIP
- **Szenario 2:** Benutzerkonto in Skype for Business Online und verwendet den Skype for Business mit Hybrid Voice Connectivity
- **Szenario 3:** Benutzerkonto in Skype for Business Online mit Microsoft Teams-Lizenz und verwendet den Teams Client
 
### <a name="supportability-matrix"></a>Unterstützungsmatrix


|**In erstellten Benutzerobjekten**  |**Dienstanbieter des Skype for Business Benutzers**|**Benutzerclient**|**Sprachoption**|**Unterstützt**|
| ------------ | --------- | --------- | --------- | -------- |
|Lokales Ad| Lokal |Skype for Business   | Enterprise Voice   |Ja|
|Lokales Ad|Online| Skype for Business  | Hybrid Voice Connectivity   |Ja |
|Lokales Ad|Online |Microsoft Teams |Direktes Routing  |Ja |
|**Nicht unterstützte Kombinationen**    | |         |         |      |
|Azure AD| Lokal/online | Skype for Business/Microsoft Teams|Enterprise-VoIP/Hybrid Voice Connectivity/Direct Routing  |Nein, Benutzerobjekt MUSS zuerst in lokalem AD erstellt werden. |
|Lokales Ad  |Lokal| Microsoft Teams| Enterprise-VoIP/Hybrid Voice Connectivity/Direct Routing   |Nein, Microsoft Teams Client wird von lokalen Clients nicht Skype for Business |     
|Lokales Ad  |Online |Skype for Business  | Direktes Routing  |Nein, Direktes Routing wird vom Client Skype for Business unterstützt.  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Erklärung zur Unterstützung der Hybridumgebung mit PSTN

Für alle Benutzer muss  das Benutzerobjekt im lokalen AD erstellt und mit Azure AD mithilfe des Azure AD-Verbinden synchronisiert werden. Das Aktivieren von Teams/Skype for Business wird  nicht unterstützt, wenn das Benutzerobjekt direkt in Azure AD in einer Hybridkonfiguration erstellt wird. Für neue Benutzer, z. B. einen neuen Mitarbeiter, der direkt für Teams aktiviert wird, muss der Benutzer für die Skype for Business mithilfe der lokalen Skype for Business aktiviert werden. Das Erstellen von Benutzern in online Skype for Business oder Teams, ohne sie zuerst in einem lokalen Pool mit einem Enterprise-VoIP **zu aktivieren, wird nicht unterstützt.** Weitere Informationen hierzu finden Sie unter Planen Telefonsystem mit der lokalen [PSTN-Anbindung in Skype for Business Server.](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)