---
title: Aufrufen von Plänen in Microsoft-Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Aufrufen von Plan Zielseite
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3299460eeb504c53737d163a6026081775fce5d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595400"
---
# <a name="phone-system-with-calling-plans"></a>Telefonsystem mit Anrufplänen 

Sie haben das [Erste Schritte](get-started-with-teams-quick-start.md)abgeschlossen. Sie haben, Teams mit [Chat, Teams, Kanäle, &-apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation zurückgesetzt. Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt. Sie können nun Cloud VoIP Arbeitslasten hinzufügen, und Sie haben entschieden, Microsoft Telefonsystem mit Aufrufen planen Verbindung zu im Public Switched Telephone Network, (PSTN) zu verwenden. 

Dieser Artikel beschreibt Core Bereitstellung Entscheidungen für das Aufrufen von plant sowie weitere Aspekte zu beachten, dass Sie möglicherweise konfigurieren möchten, basierend auf der Anforderungen Ihrer Organisation. [Cloud-VoIP in Microsoft-Teams,](cloud-voice-landing-page.md) lesen Sie auch weitere Informationen zu VoIP Cloudlösungen von Microsoft.


## <a name="learn-more-about-calling-plans"></a>Erfahren Sie mehr über die Pläne aufrufen

Die folgenden Artikel enthalten weitere Informationen zur Bereitstellung und Verwendung von Microsoft plant aufrufen:

- [Telefonsystem in Office 365](what-is-phone-system-in-office-365.md)
- [Anrufpläne für Office 365](calling-plans-for-office-365.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Zentrale Bereitstellung Entscheidungen

Um Microsoft als Ihr Netzbetreiber Telefonie verwenden, müssen Sie planen der Aufruf von Lizenzen zu erhalten, und weisen Sie diese den Benutzern Telefonsystem. 

Es gibt zwei Arten von Aufrufen Pläne verfügbar:

- Anrufe von nationalen Pläne 
- Aufrufen von nationalen und internationalen Pläne

|Fragen Sie sich|Aktion |
|------------|-------|
|Stehen plant aufrufen im Bereich Meine? Welche Benutzerstandorte müssen Service aufrufen planen? | Weitere Informationen finden Sie unter [Ländern und Regionen Verfügbarkeit für Audiokonferenzen und plant aufrufen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). | 
Benötigen die Benutzer internationaler? | Weitere Informationen finden Sie unter [Aufrufen für Office 365 Plans](calling-plans-for-office-365.md). |
Müssen meine Benutzer Lizenzen plant aufrufen? | Zu erwerben, Lizenzen zuweisen, finden Sie unter [Schritt2: kaufen und Zuweisen von Lizenzen](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
Sind meine Benutzer ein direkt nach innen (DID) Telefonnummer vorhanden? | Wenn Sie Rufnummern erhalten möchten, finden Sie unter [Schritt 3: Abrufen von Telefonnummern](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Übertragen von Telefonnummern zu Office 365

Es ist einfach, Ihre Rufnummern aus Ihren aktuellen Dienstanbieter Teams übertragen. Nachdem Sie Ihre Rufnummern Teams port, wird Microsoft Ihr Dienstanbieter und Sie für diese Nummern Rechnung wird. Weitere Informationen finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).


### <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Mit Aufrufen in Office 365-Pläne () jedem Benutzer in Ihrer Organisation muss eine eindeutige nach innen Durchwahl Anzahl und eine entsprechende überprüfte Notfall Adresse Telefon. Sie können auch einen Notfall Ort innerhalb der Notfall Adresse (zum Beispiel geschäftliche Rufnummer oder Floor-Nummer) angeben. 

|Fragen Sie sich|Aktion |
|:------------|:-------|
|Wie detailliert soll ich die Notfall-Adresse und den Ort Informationen werden? |Weitere Informationen finden Sie unter [Was notfallstandorten, Adressen und Anrufrouting sind?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Anrufer-ID

Alle ausgehenden Anrufe verwenden standardmäßig die zugewiesene Telefonnummer als aufrufende Identität (Anrufer-ID). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Fragen Sie sich|Aktion |
|:------------|:-------|
|Soll so aktivieren oder Deaktivieren der Anrufer-ID werden? | Ändern oder die Anrufer-ID zu blockieren, finden Sie unter [Legen Sie die Anrufer-ID für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user). |
|||




