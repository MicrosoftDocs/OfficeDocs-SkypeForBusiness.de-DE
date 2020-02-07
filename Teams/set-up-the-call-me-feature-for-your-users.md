---
title: Einrichten der Funktion „Rückruf“ für Ihre Benutzer
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Funktion "anrufen" in Microsoft Teams einrichten, damit Benutzer in Szenarien, in denen die Verwendung Ihres Computers für Audio möglicherweise nicht möglich ist, über das Telefon teilnehmen können.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe895fee4f3bc0872d277429289b5d04d6c9161d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837995"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Einrichten der Funktion „Rückruf“ für Ihre Benutzer

In Microsoft Teams bietet die Funktion " **anrufen** " Benutzern eine Möglichkeit, den Audioteil einer Besprechung per Telefon anzunehmen. Dies ist praktisch in Szenarien, in denen die Verwendung eines Computers für Audio möglicherweise nicht möglich ist. Benutzer erhalten den Audioteil der Besprechung über Ihr Mobiltelefon oder Ihre Festnetz-und den Inhaltsbereich der Besprechung&mdash;, beispielsweise, wenn ein anderer Besprechungsteilnehmer seinen Bildschirm freigibt&mdash;oder ein Video über seinen Computer abspielt.

## <a name="the-user-experience"></a>Die Benutzeroberfläche

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Teilnehmen an einer Besprechung mithilfe des Telefons für Audio

Klicken Sie auf **Teil** nehmen, um an einer Besprechung teilzunehmen, und klicken Sie dann auf der Seite **Wählen Sie Ihre Audio-und Videoeinstellungen aus** auf **Telefon-Audio** . Von hier aus können Benutzer den Besprechungs Anruf führen und an der Besprechung teilnehmen oder sich manuell einwählen.

![Screenshot der Option "Telefon Audio"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Besprechung des Anrufs für Teams**

Auf dem Bildschirm " **Telefon für Audio verwenden** " gibt der Benutzer seine Telefonnummer ein und klickt dann auf " **anrufen**". Die Besprechung Ruft den Benutzer an und verknüpft ihn mit der Besprechung.

![Screenshot der Option "anrufen" auf dem Bildschirm "Telefon für Audio verwenden"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Manuell einwählen**

Eine weitere Möglichkeit, sich anzumelden, besteht darin, sich direkt in die Besprechung einzuwählen. Klicken Sie auf dem Bildschirm **Telefon für Audio verwenden** auf **manuell einwählen** , um eine Liste der Telefonnummern zu erhalten, die Sie für die Einwahl in die Besprechung verwenden möchten.

![Screenshot der Option "manuell einwählen"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Rufen Sie zurück, wenn während einer Besprechung etwas schief geht.

Wenn ein Benutzer bei der Nutzung seines Computers während einer Besprechung Audioprobleme hat, kann der Benutzer einfach zur Verwendung seines Telefons für Audio wechseln. Teams erkennt, wenn ein Audio-oder Geräteproblem auftritt, und leitet den Benutzer zur Verwendung des Telefons ein, indem die Option **Rückruf zurück** angezeigt wird.

Nachfolgend finden Sie ein Beispiel für die Nachricht und die Option **Rückruf zurück** , die angezeigt wird, wenn Teams kein Mikrofon erkennen.

![Screenshot der Option "Rückruf zurück"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

Der Benutzer klickt auf **Rückruf zurück**, wodurch der Bildschirm " **Telefon für Audio verwenden** " angezeigt wird. Von hier aus können Sie Ihre Telefonnummer eingeben und die Teams für Besprechungen anrufen und an der Besprechung teilnehmen oder sich manuell in die Besprechung einwählen.

## <a name="set-up-the-call-me-feature"></a>Einrichten der Funktion "anrufen"

Um die Funktion "anrufen" für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert sein:

- Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren). Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) und [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Benutzer können aus Besprechungen wählen. Weitere Informationen finden Sie unter [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Wenn ein Benutzer die Option "Besprechungen" nicht aktiviert hat, steht die Option " **anrufen** " nicht zur Verfügung, und der Benutzer erhält keinen Anruf, um an der Besprechung teilzunehmen. Stattdessen sieht der Benutzer auf dem Bildschirm " **Telefon für Audio verwenden** " eine Liste mit Telefonnummern, mit denen er sich manuell in die Besprechung auf seinem Telefon einwählen kann.
