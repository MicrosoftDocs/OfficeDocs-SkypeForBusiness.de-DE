---
title: Anrufpläne in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Ermitteln Sie, welcher Microsoft Phone System-Anrufplan Ihrer Organisation am besten für Cloud-VoIP in Teams zur Verfügung steht.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1fb0abed3477039f4c19c0e2de0ea696626f35
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905027"
---
# <a name="which-calling-plan-is-right-for-you"></a>Welcher Anrufplan ist für Sie am besten geeignet? 

Sie haben die ersten [Schritte](get-started-with-teams-quick-start.md)abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleichthaben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Nun können Sie Cloud-sprach Auslastungen hinzufügen, und Sie haben sich entschieden, Microsoft Phone System mit einem Anrufplan zu verwenden, um eine Verbindung mit dem öffentlichen Telefonnetz (PSTN) herzustellen. 

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Anrufpläne sowie weitere Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation möglicherweise konfigurieren möchten. Sie sollten auch [Cloud-VoIP in Microsoft Teams](cloud-voice-landing-page.md) lesen, um weitere Informationen zu den Cloud-sprach angeboten von Microsoft zu erhalten.


## <a name="learn-more-about-calling-plans"></a>Weitere Informationen zu Anrufplänen

In den folgenden Artikeln finden Sie weitere Informationen zur Bereitstellung und Verwendung von Microsoft-Anrufplänen:

- [Telefonsystem in Office 365](what-is-phone-system-in-office-365.md)
- [Anrufpläne für Office 365](calling-plans-for-office-365.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Wenn Sie Microsoft als Telefonnetzbetreiber verwenden möchten, müssen Sie Lizenzen für den Anrufplan erwerben und diese ihren Telefon System Benutzern zuweisen. 

Es stehen zwei Arten von Anrufplänen zur Verfügung:

- Tarife für Inlandsanrufe 
- Tarife für Inlands-und Auslandsgespräche

|Frage|Aktion |
|------------|-------|
|Sind Anrufpläne in meinem Gebiet verfügbar? An welchen Speicherorten des Benutzers wird ein Anruf Plan Dienst durchgestellt? | Weitere Informationen finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenz-und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Benötigen meine Nutzer Auslandsanrufe? | Weitere Informationen finden Sie unter [Aufrufen von Plänen für Office 365](calling-plans-for-office-365.md). |
Verfügen meine Benutzer über Anruf Plan Lizenzen? | Informationen zum kaufen und Zuweisen von Lizenzen finden Sie unter [Schritt 2: erwerben und Zuweisen von Lizenzen](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Haben meine Benutzer jeweils eine direkte Durchwahl (DID)? | Informationen zum Abrufen von Telefonnummern finden Sie unter [Schritt 3: Abrufen von Telefonnummern](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Übertragen von Telefonnummern zu Office 365

Es ist einfach, ihre Telefonnummern von Ihrem aktuellen Dienstanbieter in Teams zu übertragen. Nachdem Sie Ihre Telefonnummern in Teams portiert haben, wird Microsoft Ihr Dienstanbieter und berechnet Ihnen diese Telefonnummern. Weitere Informationen finden Sie unter [übertragen von Telefonnummern in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Bei Anrufplänen in Office 365 muss jeder Benutzer in Ihrer Organisation über eine eindeutige direkte Durchwahl (DID)-Telefonnummer und eine entsprechende validierte Notfalladresse verfügen. Sie können auch einen Notfall Standort innerhalb der Notfalladresse angeben (beispielsweise eine Büro-oder Boden Nummer). 

|Frage|Aktion |
|:------------|:-------|
|Wie detailliert soll die Notfalladresse und die Standortinformationen sein? |Weitere Informationen finden Sie unter [Was sind Notfall Standorte, Adressen und Anrufweiterleitung?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Identität des Anrufs

Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Soll die Rufnummernanzeige maskiert oder deaktiviert werden? | Informationen zum Ändern oder Blockieren der Rufnummernanzeige finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md). |
|||




