---
title: Einrichten der Funktion „Rückruf“ für Ihre Benutzer
author: SerdarSoysal
ms.author: serdars
ms.reviewer: 'macai, phedry'
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: 'Erfahren Sie, wie Sie das Feature Rückruf in Teams so einrichten, dass Benutzer am Audioteil per Telefon teilnehmen können, wenn ihr Computer für Audio nicht möglich ist.'
ms.localizationpriority: medium
ms.collection:
  - M365-voice
f1.keywords:
  - NOCSH
appliesto:
  - Microsoft Teams
ms.custom: seo-marvel-mar2020
---

# <a name="set-up-the-call-me-feature-for-your-users"></a>Einrichten der Funktion „Rückruf“ für Ihre Benutzer

In Microsoft Teams können Benutzer über die **Funktion Rückruf am** Audioteil einer Besprechung per Telefon teilnehmen. In Szenarien, in denen die Verwendung eines Computers für Audio nicht möglich ist, ist dies praktisch. Benutzer erhalten&mdash; den Audioteil der Besprechung über ihr Mobiltelefon oder ihr Festnetztelefon und den Inhalt der Besprechung, z. B. wenn ein anderer Besprechungsteilnehmer&mdash; seinen Bildschirm teilt oder ein Video über ihren Computer wieder abspielt.

> [!IMPORTANT]
> 
> In Zeiten mit überdurchschnittlich vielen Besprechungen (wie wir sie im Zusammenhang mit dem COVID-19-Ausbruch erlebt haben) empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche <strong>An Teams-Besprechung teilnehmen</strong> klicken, anstatt sich über die Rufnummern der PSTN-Konferenz einzuwählen oder <strong>Rückruf unter</strong> zu verwenden. Dadurch wird das PSTN-Netzwerk nicht überlastet und eine klare Audioqualität sichergestellt.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>Die Benutzererfahrung

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Teilnehmen an einer Besprechung mithilfe eines Telefons für Audio

Klicken **Sie auf** Teilnehmen, um an einer Besprechung  Telefon wählen Sie dann Audio im Bildschirm Video- und **Audiooptionen** auswählen aus, und klicken Sie auf **Jetzt teilnehmen**. Von hier aus können benutzer den Besprechungsanruf anrufen und an ihnen teilnehmen oder sich manuell in die Besprechung einwählen.

![Screenshot der Option Telefon Audio"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Lassen Sie Teams Besprechung anrufen**

Auf dem **Bildschirm Telefon für Audio verwenden** gibt der Benutzer seine Telefonnummer ein und klickt dann auf **Rückruf**. Die Besprechung ruft den Benutzer an und tritt der Besprechung bei.

![Screenshot der Option "Rückruf" auf dem Audiobildschirm "Telefon für Audio verwenden".](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Manuelles Einwählen**

Eine weitere Möglichkeit zur Teilnahme besteht in der direkten Einwahl in die Besprechung. Klicken Sie **auf dem Bildschirm** Telefon für Audio verwenden  auf Manuell einwählen, um eine Liste der Telefonnummern für die Einwahl in die Besprechung zu erhalten.

![Screenshot der Option "Manuell einwählen".](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Zurückrufen, wenn während einer Besprechung ein Audio-Fehler vor sich geht

Wenn bei der Verwendung des Computers während einer Besprechung Audioprobleme auftreten, kann der Benutzer problemlos zur Verwendung des Telefons für Audio wechseln. Teams erkennt, wenn ein Audio- oder Geräteproblem auftritt, und leitet den Benutzer zur Nutzung des Telefons um, indem die Option Rückruf **angezeigt** wird.

Hier ist ein Beispiel für die Nachricht und die Option  Rückruf, die angezeigt wird, wenn Teams kein Mikrofon erkennt.

![Screenshot der Option "Rückruf"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

Der Benutzer klickt **auf Rückruf**, wodurch der Bildschirm Telefon für Audio **verwenden angezeigt** wird. Von hier aus können sie ihre Telefonnummer eingeben und sich Teams besprechungstelefonieren lassen und der Besprechung beitreten oder sich manuell in die Besprechung einwählen.

## <a name="set-up-the-call-me-feature"></a>Einrichten der Funktion "Rückruf"

Um das Feature Rückruf für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert werden:

- Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren). Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) [und Verwalten der Audiokonferenzeinstellungen](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) für einen Benutzer in Teams.

- Besprechungsorganisator kann Auswählen aus Besprechungen herauswählen. Weitere Informationen finden Sie unter [Verwalten der Audiokonferenzeinstellungen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Wenn der Besprechungsorganisator keine Auswahl aus Besprechungen aktiviert hat, ist die Option **Telefon-Audio** auf dem Bildschirm Video- und Audiooptionen auswählen für niemanden verfügbar, und andere Benutzer können keinen Anruf empfangen, um sie an der Besprechung teilzunehmen. Benutzer mit aktivierter Einwahl können nach der Teilnahme an der Besprechung anderen beitreten, indem sie über das Symbol Teilnehmer **anzeigen ihre Rufnummer** wählen.
