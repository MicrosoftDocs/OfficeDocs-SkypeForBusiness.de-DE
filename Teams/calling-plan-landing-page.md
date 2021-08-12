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
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Bestimmen Sie, Microsoft-Telefon Systemanrufplan Ihrer Organisation am besten mit Cloud-Voice in Ihrem Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c71c52f8209cc0030ee978b8c8b051c5d8101a55700f80f9dbe52fe36e84b3c3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347530"
---
# <a name="which-calling-plan-is-right-for-you"></a>Welcher Anrufplan ist für Sie am besten geeignet? 

Sie haben die ersten Schritte [abgeschlossen.](get-started-with-teams-quick-start.md) Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Möglicherweise haben Sie Besprechungen oder & [bereitgestellt.](deploy-meetings-microsoft-teams-landing-page.md) Jetzt können Sie Cloud-Voice Workloads hinzufügen, und Sie haben sich entschieden, Microsoft-Telefon-System mit Anrufplan zu verwenden, um eine Verbindung zum öffentlichen Telefonnetz (PSTN) herzustellen. 

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Anrufpläne sowie weitere Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation konfigurieren möchten. Weitere Informationen zu [Cloud Voice-Angeboten](cloud-voice-landing-page.md) von Microsoft Microsoft Teams sie auch in Cloud Voice.


## <a name="learn-more-about-calling-plans"></a>Weitere Informationen zu Anrufplänen

Die folgenden Artikel enthalten weitere Informationen zum Bereitstellen und Verwenden von Microsoft-Anrufplänen:

- [Telefonsystem in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md)
- [Anrufpläne für Microsoft 365 oder Office 365](calling-plans-for-office-365.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Wenn Sie Microsoft als Telefonieanbieter verwenden möchten, müssen Sie Anrufplanlizenzen erwerben und diese Ihren Telefonie Telefonsystem zuweisen. 

Es stehen zwei Arten von Anrufplänen zur Verfügung:

- Pläne für Inlandsrufe 
- Anrufpläne für In- und Ausland

|Frage|Aktion |
|------------|-------|
|Sind Anrufpläne in meiner Gegend verfügbar? An welchen Benutzerstandorten gibt es einen Anrufplandienst? | Weitere Informationen finden Sie unter Verfügbarkeit von Ländern [und Regionen für Audiokonferenzen und Anrufpläne.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
Benötigen meine Benutzer Auslandsrufe? | Weitere Informationen finden Sie unter [Anrufpläne für Microsoft 365 oder Office 365.](calling-plans-for-office-365.md) |
Verfügen meine Benutzer über Anrufplanlizenzen? | Informationen zum Kaufen und Zuweisen von Lizenzen finden Sie unter [Schritt 2: Kaufen und Zuweisen von Lizenzen.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
Verfügen meine Benutzer jeweils über eine direkt nach innen gerichtete Rufnummer ?? | Telefonnummern finden Sie unter [Schritt 3: Erhalten von Telefonnummern.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Übertragen von Telefonnummern an Microsoft 365 Oder Office 365

Es ist ganz einfach, Ihre Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams. Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft zu Ihrem Dienstanbieter und stellt Ihnen diese Telefonnummern in Rechnung. Weitere Informationen finden Sie unter [Übertragen von Telefonnummern an Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Bei Anrufplänen in Microsoft 365 oder Office 365 muss jeder Benutzer in Ihrer Organisation über eine eindeutige DID-Telefonnummer (Direct InWard Dial) und eine entsprechende validierte Notfalladresse verfügen. Sie können auch einen Notfallstandort innerhalb der Notfalladresse angeben (z. B. eine Büro- oder Stockwerksnummer). 

|Frage|Aktion |
|:------------|:-------|
|Wie detailliert sollen die Informationen zu Notfalladresse und -standort sein? |Weitere Informationen finden Sie unter [Was sind Notfallstandorte, Notfalladressen und Anrufrouting?.](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>Aufrufen der Identität

Standardmäßig wird für alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anrufidentität (Anrufer-ID) verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Möchte ich die Anrufer-ID maskieren oder deaktivieren? | Informationen zum Ändern oder Blockieren der Anrufer-ID finden Sie unter Festlegen der [Anrufer-ID für einen Benutzer.](set-the-caller-id-for-a-user.md) |
|||