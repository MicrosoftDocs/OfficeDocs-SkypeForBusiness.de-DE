---
title: Benutzerkonten in Hybridumgebung mit PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über verschiedene Kombinationen von Benutzererstellung und welche Kombinationen unterstützt oder nicht unterstützt werden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096325"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität

## <a name="about-the-environment"></a>Informationen zur Umgebung

Dieser Artikel bezieht sich auf Umgebungen, in denen Sie über folgendes verfügen: 
 
- Skype for Business Server oder Lync Server 2013 
- Eine Microsoft 365- oder Office 365-Organisation 
- Hybridkonnektivität, die zwischen dem Skype for Business Server- und Skype for Business Online- oder Microsoft Teams-Mandanten konfiguriert ist 
- Benutzer, die für Anrufe im öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) von und an den Client aktiviert sind

 
Wenn Sie über eine andere Umgebung (z. B. Skype for Business Cloud Connector Edition) verfügen, hybrid nicht konfiguriert ist oder Ihre Benutzer nicht für PSTN-Anrufe aktiviert sind, ist die Unterstützungsmatrix anders.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informationen zu den Kombinationen und der Supportability-Anweisung  

Eine Skype for Business-Hybridumgebung mit PSTN-Konnektivität bietet Flexibilität in Bezug auf die Bereitstellung von Benutzerdiensten und die Art und Weise, wie Benutzerkonten bereitgestellt und verwaltet werden. Die Fülle der Optionen kann jedoch einige nicht unterstützte Kombinationen erzeugen. In diesem Abschnitt werden verschiedene Kombinationen von Benutzererstellung und anschließend eine Supportability-Anweisung erläutert.


**Definitionen:**   
- **Enterprise-VoIP:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit einem lokalen Skype for Business-Benutzerkonto. Der lokale Skype for Business-Vermittlungsserver stellt eine Verbindung mit pstN zur Verfügung.  
- **Hybrid Voice Connectivity:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit einem Skype for Business Online-Konto. Der lokale Skype for Business-Vermittlungsserver stellt eine Verbindung mit pstN zur Verfügung. 
- **Direktes Routing:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit Skype for Business-Onlinekonto, Microsoft Teams-Lizenz, über den Microsoft Teams-Client. Der SBC ist mit dem SIP-Proxy in Microsoft 365 oder Office 365 verbunden, ohne dass lokale Software von Microsoft benötigt wird.

  
**Die Umgebung unterstützt die folgenden Kombinationen:**
- **Szenario 1:** Benutzerkonto in Skype for Business lokal und verwendet den Skype for Business-Client mit Enterprise-VoIP
- **Szenario 2:** Benutzerkonto in Skype for Business online und verwendet den Skype for Business-Client mit Hybrid Voice Connectivity
- **Szenario 3:** Benutzerkonto in Skype for Business online mit Microsoft Teams-Lizenz und verwendet den Teams-Client
 
### <a name="supportability-matrix"></a>Unterstützungsmatrix


|**Benutzerobjekt, das in erstellt wurde**  |**Skype for Business-Dienstanbieter des Benutzers**|**Client des Benutzers**|**Sprachoption**|**Unterstützt**|
| ------------ | --------- | --------- | --------- | -------- |
|Lokal AD| Lokal |Skype for Business   | Enterprise Voice   |Ja|
|Lokal AD|Online| Skype for Business  | Hybrid Voice Connectivity   |Ja |
|Lokal AD|Online |Microsoft Teams |Direktes Routing  |Ja |
|**Nicht unterstützte Kombinationen**    | |         |         |      |
|Azure AD| Lokal/online | Skype for Business/Microsoft Teams|Enterprise-VoIP/Hybrid Voice Connectivity/Direct Routing  |Nein, Benutzerobjekt MUSS zuerst in lokalem AD erstellt werden |
|Lokal AD  |Lokal| Microsoft Teams| Enterprise-VoIP/Hybrid Voice Connectivity/Direct Routing   |Nein, der Microsoft Teams-Client wird nicht mit lokalem Skype for Business unterstützt. |     
|Lokal AD  |Online |Skype for Business  | Direktes Routing  |Nein, Direct Routing wird vom Skype for Business-Client nicht unterstützt  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Supportability Statement für die Hybridumgebung mit PSTN

Für alle Benutzer muss  das Benutzerobjekt im lokalen AD erstellt und mit dem Azure AD Connect-Tool mit Azure AD synchronisiert werden. Das Aktivieren von Benutzern für Teams/Skype for Business **wird** nicht unterstützt, wenn das Benutzerobjekt direkt in Azure AD in einer Hybridkonfiguration erstellt wird. Für neue Benutzer, z. B. einen neuen Mitarbeiter, der direkt für Teams aktiviert wird, muss der Benutzer für Skype for Business mit lokalen Skype for Business-Verwaltungstools aktiviert sein. Das Erstellen von Benutzern in Skype for Business oder Teams online, ohne sie zuerst im lokalen Pool mit Enterprise-VoIP **zu aktivieren, wird nicht unterstützt.** Weitere Informationen hierzu finden Sie unter Planen des Telefonsystems mit einer lokalen [PSTN-Konnektivität in Skype for Business Server.](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)