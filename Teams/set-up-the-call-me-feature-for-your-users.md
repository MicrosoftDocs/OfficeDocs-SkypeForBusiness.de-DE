---
title: Einrichten der Funktion „Rückruf“ für Ihre Benutzer
author: CarolynRowe
ms.author: crowe
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie das Feature "Rückruf" in Teams einrichten, damit Benutzer dem Audioteil per Telefon beitreten können, wenn sie ihren Computer für Audio verwenden.
ms.localizationpriority: medium
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a144e6a751f44ff520ee0317dbbcb390f30abbfd
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794533"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Einrichten der Funktion „Rückruf“ für Ihre Benutzer

In Microsoft Teams bietet das Feature **"Rückruf** " Benutzern die Möglichkeit, per Telefon am Audioteil einer Besprechung teilzunehmen. Dies ist in Szenarien praktisch, in denen die Verwendung eines Computers für Audio möglicherweise nicht möglich ist. Benutzer erhalten den Audioteil der Besprechung über ihr Mobiltelefon oder die Festnetzleitung und den Inhaltsbereich der Besprechung&mdash;, z. B. wenn ein anderer Besprechungsteilnehmer ihren Bildschirm teilt oder ein Video&mdash;über ihren Computer wiedergibt.

> [!IMPORTANT]
> 
> In Zeiten mit überdurchschnittlich vielen Besprechungen (wie wir sie im Zusammenhang mit dem COVID-19-Ausbruch erlebt haben) empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche <strong>An Teams-Besprechung teilnehmen</strong> klicken, anstatt sich über die Rufnummern der PSTN-Konferenz einzuwählen oder <strong>Rückruf unter</strong> zu verwenden. Dadurch wird das PSTN-Netzwerk nicht überlastet und eine klare Audioqualität sichergestellt.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>Die Benutzeroberfläche

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Teilnehmen an einer Besprechung per Telefon für Audio

Klicken Sie auf "**Teilnehmen**", um an einer Besprechung teilzunehmen, und dann auf dem Bildschirm "**Video- und Audiooptionen auswählen**" auf "**Audiotelefonieren**", und klicken Sie auf **"Jetzt teilnehmen**". Von hier aus können Benutzer den Besprechungsanruf führen und ihnen beitreten oder sich manuell in die Besprechung einwählen.

![Screenshot der Option "Telefonaudio".](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Teams-Besprechungsanruf zulassen**

Auf dem **Bildschirm "Telefon für Audio** verwenden" gibt der Benutzer seine Telefonnummer ein und klickt dann auf " **Anrufen**". Die Besprechung ruft den Benutzer an und schließt sich der Besprechung an.

![Screenshot der Option "Rückruf" auf dem Bildschirm "Telefon für Audio verwenden".](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Manuelles Einwählen**

Eine weitere Möglichkeit zur Teilnahme besteht darin, sich direkt in die Besprechung einwählen. Klicken Sie auf dem Bildschirm " **Telefon für Audio verwenden** " **auf "Manuell einwählen** ", um eine Liste der Telefonnummern zum Einwählen in die Besprechung abzurufen.

![Screenshot der Option "Manuell einwählen".](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Abrufen eines Rückrufs, wenn bei Audio während einer Besprechung ein Fehler auftritt

Wenn bei der Verwendung des Computers während einer Besprechung Audioprobleme auftreten, kann der Benutzer problemlos zur Verwendung seines Telefons für Audio wechseln. Teams erkennt, wenn ein Audio- oder Geräteproblem auftritt, und leitet den Benutzer zur Verwendung seines Telefons um, **indem eine** Rückrufoption angezeigt wird.

Hier ist ein Beispiel für die Nachricht **und die** Rückrufoption, die angezeigt wird, wenn Teams kein Mikrofon erkennt.

![Screenshot der Option "Rückruf".](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

Der Benutzer klickt auf **"Rückruf**", wodurch das **Telefon für den Audiobildschirm** angezeigt wird. Von hier aus können sie ihre Telefonnummer eingeben und den Teams-Besprechungsanruf führen und an der Besprechung teilnehmen oder sich manuell in die Besprechung einwählen.

## <a name="set-up-the-call-me-feature"></a>Einrichten des Features "Rückruf"

Um das Feature "Rückruf" für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert werden:

- Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren). Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) und [Verwalten der Audiokonferenzeinstellungen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Der Besprechungsorganisator kann sich aus Besprechungen herauswählen. Weitere Informationen finden Sie unter [Verwalten der Audiokonferenzeinstellungen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Wenn für den Besprechungsorganisator keine Auswahl aus Besprechungen aktiviert ist, ist die Option **"Telefonaudio** " auf dem Bildschirm " **Video- und Audiooptionen auswählen** " für niemanden verfügbar, und andere Benutzer können keinen Anruf empfangen, um an der Besprechung teilzunehmen. Für Benutzer mit aktivierter Ausgehendkeit können sie, nachdem sie der Besprechung beigetreten sind, an anderen Personen teilnehmen, die ihre Nummer über das Symbol " **Teilnehmer anzeigen** " wählen.
