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
description: Ermitteln Sie, welcher Anrufplan für Das Microsoft-Telefonsystem Ihre Organisation am besten mit Cloud Voice in Teams bedient.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebe826b55d043c7f8ae8fea76c2d8e59ae5543bd
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268786"
---
# <a name="which-calling-plan-is-right-for-you"></a>Welcher Anrufplan ist für Sie am besten geeignet?

Sie haben die ["Erste Schritte](get-started-with-teams-quick-start.md)" abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md) bereitgestellt. Jetzt können Sie Cloud-VoIP-Workloads hinzufügen, und Sie haben beschlossen, das Microsoft-Telefonsystem mit Anrufplan zu verwenden, um eine Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) herzustellen.

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Anrufpläne und andere Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation konfigurieren möchten. Sie sollten auch [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) lesen, um weitere Informationen zu den Cloud-VoIP-Angeboten von Microsoft zu finden.

## <a name="learn-more-about-calling-plans"></a>Weitere Informationen zu Anrufplänen

Die folgenden Artikel enthalten weitere Informationen zum Bereitstellen und Verwenden von Microsoft-Anrufplänen:

- [Telefonsystem in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md)
- [Anrufpläne für Microsoft 365 oder Office 365](calling-plans-for-office-365.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Um Microsoft als Telefonieanbieter zu verwenden, müssen Sie Anrufplanlizenzen anfordern und diesen Ihren Telefonsystembenutzern zuweisen.

Es sind drei Arten von Anrufplänen verfügbar:

- Inlandsanrufpläne
- Internationale Anrufpläne
- Pay-as-You-Go-Anrufpläne

| Frage | Aktion |
|--------------|--------|
| Sind Anrufpläne in meinem Bereich verfügbar? Welche Benutzerstandorte verfügen über einen Anrufplandienst? | Weitere Informationen finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). |
| Benötigen meine Benutzer auslandsanrufe? | Weitere Informationen finden Sie unter [Anrufpläne für Microsoft 365 oder Office 365](calling-plans-for-office-365.md). |
| Wenn einige meiner Benutzer keine signifikante Anzahl ausgehender Anrufe tätigen, ist der Pay-As-You-Go-Anrufplan für sie die wirtschaftlichste Option? | Weitere Informationen finden Sie unter [Anrufpläne für Microsoft 365 oder Office 365](calling-plans-for-office-365.md). |
| Verfügen meine Benutzer über Anrufpläne-Lizenzen? | Informationen zum Kaufen und Zuweisen von Lizenzen finden Sie in [Schritt 2: Kaufen und Zuweisen von Lizenzen](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
| Verfügen meine Benutzer jeweils über eine DID-Telefonnummer (Direct Inward Dial)? | Informationen zum Abrufen von Telefonnummern finden Sie in [Schritt 3: Abrufen von Telefonnummern](set-up-calling-plans.md#step-3-get-phone-numbers). |

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Übertragen von Telefonnummern an Microsoft 365 oder Office 365

Es ist einfach, Ihre Telefonnummern von Ihrem aktuellen Dienstanbieter zu Teams zu übertragen. Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter und berechnet Ihnen diese Telefonnummern. Weitere Informationen finden Sie unter [Übertragen von Telefonnummern an Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

### <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Bei Anrufplänen in Microsoft 365 oder Office 365 muss jeder Benutzer in Ihrer Organisation über eine eindeutige DID-Telefonnummer (Direct Inward Dial) und eine entsprechende validierte Notfalladresse verfügen. Sie können auch einen Notfallstandort innerhalb der Notfalladresse angeben (z. B. eine Büro- oder Bodennummer).

|Frage|Aktion |
|:------------|:-------|
|Wie detailliert soll die Notfalladresse und die Standortinformationen sein? |Weitere Informationen finden Sie unter [Was sind Notfallstandorte, Notfalladressen und Anrufweiterleitung?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).

### <a name="calling-identity"></a>Anrufer-ID

Standardmäßig wird bei allen ausgehenden Anrufen die zugewiesene Telefonnummer als Anrufer-ID verwendet. Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Möchte ich die Anrufer-ID maskieren oder deaktivieren? | Informationen zum Ändern oder Blockieren der Anrufer-ID finden [Sie unter Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md). |
|||
