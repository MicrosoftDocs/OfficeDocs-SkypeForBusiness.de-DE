---
title: Einrichten der Funktion „Rückruf“ für Ihre Benutzer
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Sie das Feature "Rückruf" in Teams so einrichten, dass Benutzer am Audioteil per Telefon teilnehmen können, wenn sie ihren Computer für Audio verwenden.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6b78edc01f68df19e850a85eb0ffa99163b9edae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821095"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Einrichten der Funktion „Rückruf“ für Ihre Benutzer

In Microsoft Teams bietet das **Feature** "Rückruf" Benutzern die Möglichkeit, per Telefon am Audioteil einer Besprechung teilnehmen. In Szenarien, in denen die Verwendung eines Computers für Audio nicht möglich ist, ist dies praktisch. Benutzer erhalten den Audioteil der Besprechung über ihr Mobiltelefon oder ihr Festnetztelefon und den Inhalt der Besprechung, z. B. wenn ein anderer Besprechungsteilnehmer seinen Bildschirm teilt oder ein Video über ihren &mdash; &mdash; Computer wieder abspielt.

> [!IMPORTANT]
> 
> In Zeiten mit überdurchschnittlich vielen Besprechungen (wie wir sie im Zusammenhang mit dem COVID-19-Ausbruch erlebt haben) empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche <strong>An Teams-Besprechung teilnehmen</strong> klicken, anstatt sich über die Rufnummern der PSTN-Konferenz einzuwählen oder <strong>Rückruf unter</strong> zu verwenden. Dadurch wird das PSTN-Netzwerk nicht überlastet und eine klare Audioqualität sichergestellt. 

> [!IMPORTANT]
> Während der Dauer des COVID-19-Ausbruchs empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche **An Teams-Besprechung teilnehmen** klicken, anstatt sich über die Rufnummern der PSTN-Konferenz einzuwählen oder **Rückruf unter**</strong> zu verwenden. Grund hierfür ist in erster Linie die Überlastung der Telefonie-Infrastrukturen in den von COVID-19 betroffenen Ländern. Wenn Sie Anrufe über das Telefonfestnetz vermeiden, werden Sie wahrscheinlich eine bessere Tonqualität feststellen. 

## <a name="the-user-experience"></a>Die Benutzeroberfläche

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Teilnehmen an einer Besprechung mithilfe eines Telefons für Audio

Klicken **Sie auf "Teilnehmen",**  um an einer Besprechung teilnehmen, und klicken Sie dann im Bildschirm "Audio- und Videoeinstellungen auswählen" auf **"Telefonaudio"** aus. Von hier aus können Die Benutzer den Besprechungsanruf durchführen und an der Besprechung teilnehmen oder sich manuell in die Besprechung einwählen.

![Screenshot der Audiooption "Telefon"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Lassen Sie die Besprechungssitzung in Teams anrufen**

Auf dem **Bildschirm "Telefon für Audio verwenden"** gibt der Benutzer seine Telefonnummer ein und klickt dann auf "Rückruf".  Die Besprechung ruft den Benutzer an und tritt der Besprechung bei.

![Screenshot der Option "Rückruf" auf der Seite "Telefon für Audio verwenden"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Manuelles Einwählen**

Eine weitere Möglichkeit zur Teilnahme besteht im direkten Einwählen in die Besprechung. Klicken Sie auf dem Bildschirm  **"Telefon für Audio verwenden"** auf "Manuell einwählen", um eine Liste der Telefonnummern zum Einwählen in die Besprechung zu erhalten.

![Screenshot der Option "Manuelles Einwählen"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Einen Rückruf erhalten, wenn während einer Besprechung ein Fehler mit Audiodaten vor sich geht

Wenn bei der Verwendung des Computers während einer Besprechung Audioprobleme auftreten, kann der Benutzer ganz einfach zur Verwendung des Telefons für Audio wechseln. Teams erkennt, wenn ein Audio- oder Geräteproblem auftritt, und leitet den Benutzer durch Anzeige einer Rückrufoption zur Nutzung des Telefons **um.**

Hier ist ein Beispiel für  die Nachricht und die Rückrufoption, die angezeigt wird, wenn Teams kein Mikrofon erkennt.

![Screenshot der Option "Rückruf"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

Der Benutzer klickt auf **"Rückruf",** wodurch das Bildschirm "Telefon für **Audio verwenden" angezeigt** wird. Von hier aus können sie ihre Telefonnummer eingeben und sich den Team-Besprechungsanruf geben lassen und der Besprechung beitreten oder sich manuell in die Besprechung einwählen.

## <a name="set-up-the-call-me-feature"></a>Einrichten des Features "Rückruf"

Um das Feature "Rückruf" für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert sein:

- Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren). Weitere Informationen finden Sie unter ["Einrichten von Audiokonferenzen](set-up-audio-conferencing-in-teams.md) für Teams und Verwalten der Audiokonferenzeinstellungen für einen Benutzer [in Teams".](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- Benutzer können aus Besprechungen heraus wählen. Weitere Informationen finden Sie unter ["Verwalten der Audiokonferenzeinstellungen für einen Benutzer in Teams".](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Wenn für einen Benutzer kein Auswählen  aus Besprechungen aktiviert ist, ist die Option "Rückruf" nicht verfügbar, und der Benutzer erhält keinen Anruf, um an der Besprechung teilzunehmen. Stattdessen wird dem Benutzer auf dem  Bildschirm "Telefon für Audio verwenden" eine Liste mit Telefonnummern angezeigt, mit der er sich manuell in die Besprechung auf dem Telefon einwählen kann.
