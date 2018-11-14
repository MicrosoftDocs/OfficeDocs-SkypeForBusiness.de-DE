---
title: Benutzerkonten in einer hybridumgebung mit PSTN-Anbindung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service:
- msteams
- skype-for-business-online
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Informationen Sie zu verschiedenen Kombinationen der Erstellung des Benutzers und welche Kombinationen unterstützt oder nicht unterstützt werden.
ms.openlocfilehash: f742efc18de05997f73a33b96800cc10a9a9d124
ms.sourcegitcommit: 5d8b5dee1dea84494aea92bbce568dea10752af9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2018
ms.locfileid: "26510622"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Benutzerkonten in einer hybridumgebung mit PSTN-Anbindung

## <a name="about-the-environment"></a>Über die Umgebung

Dieser Artikel bezieht sich auf Umgebungen, in denen Sie alle der folgenden haben: 
 
- Skype für Business Server oder Lync Server 2013 
- Office 365-Mandanten 
- Hybridkonnektivität zwischen dem Skype für Business Server und Skype für Business Online oder Microsoft-Teams Mandanten konfiguriert 
- Tätigen und Entgegennehmen von Anrufen (Public Switched Telephone Network, PSTN), zum und vom Client aktivierte Benutzer

 
Wenn Sie eine andere Umgebung (beispielsweise Skype für Business Cloud Connector Edition) verfügen, Hybrid nicht konfiguriert ist oder Ihre Benutzer ist nicht für PSTN-Anrufe aktiviert, wird die unterstützbarkeitsmatrix abweichen.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Zu den Kombinationen und die Support-Anweisung  

Eine Skype für Business-hybridumgebung mit PSTN-Anbindung bietet Flexibilität im Hinblick auf, in dem Benutzerdienste bereitgestellt werden und wie Benutzerkonten bereitgestellt und verwaltet werden. Aber die Fülle von Optionen möglicherweise nicht unterstützten Kombinationen erstellen. In diesem Abschnitt wird erläutert, verschiedene Kombinationen der Erstellung des Benutzers, gefolgt von einer Supportability-Anweisung.


**Definitionen:**   
- **Enterprise-VoIP:** Option zum Zugriff auf das PSTN für Benutzer mit lokalen Skype für Business-Benutzerkontos. Lokale Skype für Business Vermittlungsserver stellt zunehmende Verbindung untereinander PSTN bereit.  
- **Hybrid-VoIP-Konnektivität:** Option zum Zugriff auf das PSTN für mit online Skype für Business-Konto. Lokale Skype für Business Vermittlungsserver stellt zunehmende Verbindung untereinander PSTN bereit. 
- **Direktes routing:** Option zum Zugriff auf das PSTN für Benutzer mit online Skype mit Microsoft-Teams, Client für Microsoft-Teams, Lizenz, Business-Konto. Der SBC ist mit der SIP-Proxy in Office 365 ohne lokale Software von Microsoft verbunden.

  
**Die Umgebung werden folgenden Kombinationen unterstützt:**
- **Szenario 1:** Benutzer für Unternehmen lokal Skype-Konto und das Skype für das Business-Client mit Enterprise-VoIP verwendet wird
- **Szenario 2:** Benutzer Skype-Konto für Unternehmen online und verwendet die Skype für Business-Client mit Hybrid-VoIP-Konnektivität
- **Szenario 3:** Benutzer für Unternehmen online Skype-Konto mit Lizenz für den Microsoft-Teams und Teams Client verwenden
 
### <a name="supportability-matrix"></a>-Unterstützbarkeitsmatrix


|**Benutzerobjekt in erstellt**  |**Skype für Business Dienstanbieter des Benutzers**|**Client des Benutzers**|**VoIP-option**|**Unterstützt**|
|---------|---------|---------|---------|--------|
|Lokal AD| Lokal |Skype for Business   | Enterprise-VoIP   |Ja|
|Lokal AD|Online| Skype for Business  | Hybrid-VoIP-Konnektivität   |Ja |
|Lokal AD|Online |Microsoft Teams |Direktes Routing  |Ja |
|**Nicht unterstützte Kombinationen**    | |         |         |
|Azure AD| Lokale/Online | Skype für Business/Microsoft-Teams|Enterprise-VoIP/Hybrid-VoIP Connectivity/Direct-Routing  |Nein, muss User-Objekt erstellt werden, der lokale AD zuerst |
|Lokal AD  |Lokal| Microsoft Teams| Enterprise-VoIP/Hybrid-VoIP Connectivity/Direct-Routing   |Nein, Microsoft-Teams, Client nicht mit lokalen Skype für Unternehmen unterstützt |
|Lokal AD  |Online |Skype for Business | Direktes Routing  | Nein, Skype für Business-Client nicht mit direktem Routing unterstützt  |
|Lokal AD  |Online |Skype for Business  | Direktes Routing  |Nein, direkten Routing wird mit nicht unterstützt Skype für Business-Client und Benutzer muss zunächst für Enterprise-VoIP in Skype für Unternehmen aktiviert werden  |
|   |         |         |         ||

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Support-Anweisung für die hybridumgebung mit PSTN

Für alle Benutzer, der Benutzer-Objekts **muss** erstellt werden, in der lokalen AD und synchronisiert auf Azure Active Directory mit dem Tool Azure Active Directory verbinden. Aktivieren von Benutzern für Teams/Skype für Business **wird nicht unterstützt** , wenn das Benutzerobjekt direkt in Azure AD in einer hybridkonfiguration erstellt wird. Für neue Benutzer, wie eine neue Mitarbeiter, wer direkt für Teams aktiviert wird, muss der Benutzer für Skype für Unternehmen für die Business-Verwaltungstools lokal Skype verwenden aktiviert sein. Erstellen von Benutzern in online Skype für Geschäftskunden und Teams ohne ersten ermöglicht es ihnen im lokalen Pool mit Enterprise-VoIP **wird nicht unterstützt**. Zum Aktivieren von Benutzern für Skype für Unternehmen in hybridkonfiguration finden Sie [in diesem Artikel](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises) finden Sie weitere Details.
