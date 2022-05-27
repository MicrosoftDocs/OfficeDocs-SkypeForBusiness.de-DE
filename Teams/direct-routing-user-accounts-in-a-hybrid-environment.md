---
title: Benutzerkonten in hybrider Umgebung mit PSTN
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
description: Erfahren Sie mehr über verschiedene Kombinationen der Benutzererstellung und welche Kombinationen unterstützt oder nicht unterstützt werden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97d1a3ac433db78792ca3cc512d32c5a8fec243
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676417"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Benutzerkonten in einer hybriden Umgebung mit PSTN-Konnektivität

## <a name="about-the-environment"></a>Informationen zur Umgebung

Dieser Artikel bezieht sich auf Umgebungen, in denen Sie über folgende Elemente verfügen:

- Skype for Business Server oder Lync Server 2013
- Eine Microsoft 365 oder Office 365 Organisation
- Hybridkonnektivität zwischen dem Skype for Business Server und Skype for Business Online- oder Microsoft Teams-Mandanten konfiguriert
- Benutzer, die PSTN-Anrufe (Public Switched Telephone Network) an und vom Client tätigen und empfangen können


Wenn Sie über eine andere Umgebung verfügen (z. B. Skype for Business Cloud Connector Edition), die Hybridbereitstellung nicht konfiguriert ist oder Ihre Benutzer nicht für PSTN-Anrufe aktiviert sind, ist die Unterstützungsmatrix unterschiedlich.

## <a name="about-the-combinations-and-the-supportability-statement"></a>Informationen zu den Kombinationen und zur Unterstützungsmöglichkeitserklärung

Eine Skype for Business Hybridumgebung mit PSTN-Konnektivität bietet Flexibilität in Bezug auf die Bereitstellung und Verwaltung von Benutzerkonten. Aber die Fülle von Optionen kann einige nicht unterstützte Kombinationen erzeugen. In diesem Abschnitt werden verschiedene Kombinationen der Benutzererstellung erläutert, gefolgt von einer Unterstützungserklärung.

**Definitionen:**

- **Enterprise-VoIP:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit lokalem Skype for Business Benutzerkonto. Der lokale Skype for Business Vermittlungsserver ermöglicht die Anbindung an das PSTN.
- **Hybride VoIP-Konnektivität:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit Skype for Business Onlinekonto. Der lokale Skype for Business Vermittlungsserver ermöglicht die Anbindung an das PSTN.
- **Direktes Routing:** Option zum Bereitstellen des Zugriffs auf das PSTN für Benutzer mit Online-Skype for Business-Konto, Microsoft Teams Lizenz, mithilfe Microsoft Teams Clients. Der SBC ist in Microsoft 365 oder Office 365 ohne lokale Software von Microsoft mit dem SIP-Proxy verbunden.

**Die Umgebung unterstützt die folgenden Kombinationen:**

- **Szenario 1:** Benutzerkonto in Skype for Business lokal und verwendet den Skype for Business-Client mit Enterprise-VoIP
- **Szenario 2:** Benutzerkonto in Skype for Business online und verwendet den Skype for Business-Client mit Hybrid Voice Connectivity
- **Szenario 3:** Benutzerkonto in Skype for Business online mit Microsoft Teams Lizenz und verwendet Teams Client

### <a name="supportability-matrix"></a>Unterstützungsmatrix

|Benutzerobjekt erstellt in|Skype for Business Dienstanbieter des Benutzers|Client des Benutzers|VoIP-Option|Unterstützt|
|---|---|---|---|---|
|Lokales AD|Lokal|Skype for Business|Enterprise Voice|Ja|
|Lokales AD|Online|Skype for Business|Hybride Sprachkonnektivität|Ja|
|Lokales AD|Online|Microsoft Teams|Direct Routing|Ja|
|**Nicht unterstützte Kombinationen**|||||
|Azure AD|Lokal/online|Skype for Business/Microsoft Teams|Enterprise-VoIP/Hybrid voice connectivity/Direct Routing|Nein, das Benutzerobjekt MUSS zuerst in lokalem AD erstellt werden.|
|Lokales AD|Lokal|Microsoft Teams|Enterprise-VoIP/Hybrid voice connectivity/Direct Routing|Nein, Microsoft Teams Client wird von lokalen Skype for Business nicht unterstützt.|
|Lokales AD|Online|Skype for Business|Direct Routing|Nein, Direct Routing wird mit Skype for Business Client nicht unterstützt.|

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Unterstützungserklärung für die Hybridumgebung mit PSTN

Für alle Benutzer **muss** das Benutzerobjekt im lokalen AD erstellt und mithilfe des Azure AD-Verbinden-Tools mit Azure AD synchronisiert werden. Das Aktivieren von Benutzern für Teams/Skype for Business **wird nicht unterstützt**, wenn das Benutzerobjekt direkt in Azure AD in einer Hybridkonfiguration erstellt wird. Für neue Benutzer, z. B. neue Mitarbeiter, die direkt für Teams aktiviert werden, muss der Benutzer für Skype for Business mithilfe lokaler Skype for Business Verwaltungstools aktiviert sein. Das Erstellen von Benutzern in Online-Skype for Business oder Teams, ohne sie zuvor im lokalen Pool mit Enterprise-VoIP zu aktivieren, **wird nicht unterstützt**. Weitere Informationen hierzu erfahren Sie im [Plan Telefonsystem mit lokaler PSTN-Anbindung in Skype for Business Server](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
