---
title: Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität
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
description: Erfahren Sie mehr über verschiedene Kombinationen der Benutzererstellung und welche Kombinationen unterstützt oder nicht unterstützt werden.
ms.openlocfilehash: f33c7bffadb443aafad6fa0e7d910f6416a95d6f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837285"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität

## <a name="about-the-environment"></a>Informationen zur Umgebung

Dieser Artikel bezieht sich auf Umgebungen, in denen Sie über alle folgenden Themen verfügen: 
 
- Skype for Business Server oder lync Server 2013 
- Ein Office 365-Mandant 
- Zwischen dem Skype for Business Server und dem Skype for Business Online-oder Microsoft Teams-Mandanten konfigurierte Hybrid Konnektivität 
- Benutzer, die für das tätigen und empfangen von PSTN-anrufen (Public Switched Telephone Network) in den und aus dem Client aktiviert sind

 
Wenn Sie eine andere Umgebung (wie Skype for Business Cloud Connector Edition) haben, Hybrid nicht konfiguriert ist oder Ihre Benutzer nicht für PSTN-Anrufe aktiviert sind, ist die Unterstützungsmatrix unterschiedlich.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informationen zu den Kombinationen und der Unterstützungserklärung  

Eine Skype for Business-Hybridumgebung mit PSTN-Konnektivität bietet Flexibilität bei der Bereitstellung von Benutzerdiensten und der Bereitstellung und Verwaltung von Benutzerkonten. Durch die Vielzahl von Optionen können aber einige nicht unterstützte Kombinationen entstehen. In diesem Abschnitt werden verschiedene Kombinationen der Benutzererstellung erläutert, gefolgt von einer unterstützenden Anweisung.


**Definitionen**   
- **Enterprise-VoIP:** Option für den Zugriff auf das PSTN für Benutzer mit lokalem Skype for Business-Benutzerkonto. Der lokale Skype for Business-Vermittlungsserver bietet eine Verbindung zu PSTN.  
- **Hybride sprach Konnektivität:** Option für den Zugriff auf das PSTN für Benutzer mit Skype for Business Online-Konto. Der lokale Skype for Business-Vermittlungsserver bietet eine Verbindung zu PSTN. 
- **Direktes Routing:** Option zum Bereitstellen von Zugriff auf PSTN für Benutzer mit Online-Skype for Business-Konto, Microsoft Teams-Lizenz, mithilfe des Microsoft Teams-Clients. Der SBC ist mit dem SIP-Proxy in Office 365 verbunden, ohne dass eine lokale Software von Microsoft benötigt wird.

  
**Die Umgebung unterstützt die folgenden Kombinationen:**
- **Szenario 1:** Benutzerkonto in Skype for Business lokal und verwendet den Skype for Business-Client mit Enterprise-VoIP
- **Szenario 2:** Benutzerkonto in Skype for Business Online und verwendet den Skype for Business-Client mit Hybrid-VoIP-Konnektivität
- **Szenario 3:** Benutzerkonto in Skype for Business Online mit Microsoft Teams-Lizenz und wird Teams-Client verwenden
 
### <a name="supportability-matrix"></a>Support-Matrix


|**In erstelltes Benutzerobjekt**  |**Skype for Business-Dienstanbieter des Benutzers**|**Client des Benutzers**|**Sprachoption**|**Unterstützt**|
| ------------ | --------- | --------- | --------- | -------- |
|Lokale Anzeige| Lokal |Skype for Business   | Enterprise-VoIP   |Ja|
|Lokale Anzeige|Online| Skype for Business  | Hybride sprach Konnektivität   |Ja |
|Lokale Anzeige|Online |Microsoft Teams |Direktes Routing  |Ja |
|**Nicht unterstützte Kombinationen**    | |         |         |      |
|Azure AD| Lokal/Online | Skype for Business/Microsoft Teams|Enterprise-VoIP/Hybrid-VoIP-Konnektivität/Direktes Routing  |Nein, das Benutzerobjekt muss zuerst in der lokalen Anzeige erstellt werden. |
|Lokale Anzeige  |Lokal| Microsoft Teams| Enterprise-VoIP/Hybrid-VoIP-Konnektivität/Direktes Routing   |Nein, Microsoft Teams-Client wird für lokale Skype for Business nicht unterstützt |     
|Lokale Anzeige  |Online |Skype for Business  | Direktes Routing  |Nein, das direkte Routing wird mit dem Skype for Business-Client nicht unterstützt, und der Benutzer muss für Enterprise-VoIP in Skype for Business zuerst aktiviert sein.  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Unterstützende Anweisung für die Hybridumgebung mit PSTN

Für alle Benutzer **muss** das Benutzerobjekt in der lokalen Anzeige erstellt und mithilfe des Azure AD Connect-Tools mit Azure AD synchronisiert werden. Das Aktivieren von Benutzern für Teams/Skype for Business **wird nicht unterstützt** , wenn das Benutzerobjekt direkt in der Azure AD in einer Hybrid Konfiguration erstellt wird. Für neue Benutzer, beispielsweise für neue Mitarbeiter, die direkt für Teams aktiviert werden, muss der Benutzer für Skype for Business mit den lokalen Skype for Business-Verwaltungstools aktiviert sein. Das Erstellen von Benutzern in Online-Skype for Business oder Teams, ohne diese zuvor im lokalen Pool mit Enterprise-VoIP zu aktivieren, **wird nicht unterstützt**. Weitere Informationen hierzu finden Sie unter Planen des [Telefonsystems in Office 365 mit lokalem PSTN-Konnektivität in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
