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
description: Ermitteln Sie, welcher Microsoft Phone System Calling Plan Ihrer Organisation am besten in der Cloud Voice in Teams dienen soll.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102731"
---
# <a name="which-calling-plan-is-right-for-you"></a>Welcher Anrufplan ist für Sie am besten geeignet? 

Sie haben die Ersten [Schritte abgeschlossen.](get-started-with-teams-quick-start.md) Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Vielleicht haben Sie Besprechungen und [& bereitgestellt.](deploy-meetings-microsoft-teams-landing-page.md) Jetzt sind Sie bereit, Cloud-Sprachworkloads hinzuzufügen, und Sie haben beschlossen, Microsoft Phone System mit Anrufplan zu verwenden, um eine Verbindung mit dem öffentlichen Telefonnetz (Public Switched Telephone Network, PSTN) herzustellen. 

In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Anrufpläne sowie zusätzliche Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation konfigurieren möchten. Sie sollten auch [Cloud Voice in Microsoft Teams lesen,](cloud-voice-landing-page.md) um weitere Informationen zu den Sprachangeboten von Microsoft in der Cloud zu erhalten.


## <a name="learn-more-about-calling-plans"></a>Weitere Informationen zu Anrufplänen

In den folgenden Artikeln finden Sie weitere Informationen zum Bereitstellen und Verwenden von Microsoft-Anrufplänen:

- [Telefonsystem in Microsoft 365 oder Office 365](what-is-phone-system-in-office-365.md)
- [Anrufpläne für Microsoft 365 oder Office 365](calling-plans-for-office-365.md)
- [Einrichten von Anrufplänen](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Um Microsoft als Telefonieanbieter zu verwenden, müssen Sie Lizenzen für den Anrufplan abrufen und sie Ihren Benutzern des Telefonsystems zuweisen. 

Es stehen zwei Arten von Anrufplänen zur Verfügung:

- Pläne für Inlandsrufe 
- Pläne für Inlands- und Auslandsrufe

|Frage|Aktion |
|------------|-------|
|Sind Anrufpläne in meinem Bereich verfügbar? An welchen Benutzerstandorten wird der Anrufplandienst verwendet? | Weitere Informationen finden Sie unter Verfügbarkeit von Ländern und [Regionen für Audiokonferenzen und Anrufpläne.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
Benötigen meine Benutzer Auslandsrufe? | Weitere Informationen finden Sie unter [Anrufpläne für Microsoft 365 oder Office 365.](calling-plans-for-office-365.md) |
Verfügen meine Benutzer über Lizenzen für Anrufpläne? | Informationen zum Kaufen und Zuweisen von Lizenzen finden Sie [unter Schritt 2: Kaufen und Zuweisen von Lizenzen.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
Verfügen meine Benutzer jeweils über eine direkte Nach-innen-Wählnummer (DID) | Informationen zum Erhalten von Telefonnummern finden Sie [unter Schritt 3: Erhalten von Telefonnummern.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Übertragen von Telefonnummern an Microsoft 365 oder Office 365

Es ist ganz einfach, Ihre Telefonnummern von Ihrem aktuellen Dienstanbieter an Teams zu übertragen. Nachdem Sie Ihre Telefonnummern zu Teams portiert haben, wird Microsoft Ihr Dienstanbieter und stellt Ihnen diese Telefonnummern in Rechnung. Weitere Informationen finden Sie unter [Übertragen von Telefonnummern an Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).


### <a name="phone-numbers-and-emergency-locations"></a>Telefonnummern und Notfallstandorte

Bei Anrufplänen in Microsoft 365 oder Office 365 muss jeder Benutzer in Ihrer Organisation über eine eindeutige Did-Telefonnummer (DirectWardWard Dial) und eine entsprechende überprüfte Notfalladresse verfügen. Sie können auch einen Notfallstandort innerhalb der Notfalladresse angeben (z. B. eine Büro- oder Stockwerksnummer). 

|Frage|Aktion |
|:------------|:-------|
|Wie detailliert soll die Notfalladresse und die Standortinformationen sein? |Weitere Informationen finden Sie unter [Was sind Notfallstandorte, Adressen und Anrufrouting?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).


### <a name="calling-identity"></a>Anrufidentität

Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anrufidentität (Anrufer-ID). Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.

|Frage|Aktion |
|:------------|:-------|
|Möchte ich die Anrufer-ID maskieren oder deaktivieren? | Informationen zum Ändern oder Blockieren der Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer.](set-the-caller-id-for-a-user.md) |
|||