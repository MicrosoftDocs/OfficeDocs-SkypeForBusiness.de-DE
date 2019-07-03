---
title: Einrichten der Funktion "anrufen" für Ihre Benutzer
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Funktion "anrufen" in Microsoft Teams einrichten, damit Benutzer in Szenarien, in denen die Verwendung Ihres Computers für Audio möglicherweise nicht möglich ist, über das Telefon teilnehmen können.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432135"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Einrichten der Funktion "anrufen" für Ihre Benutzer

In Microsoft Teams bietet die Funktion " **anrufen** " Benutzern eine Möglichkeit, den Audioteil einer Besprechung per Telefon anzunehmen. Dies ist praktisch in Szenarien, in denen die Verwendung eines Computers für Audio möglicherweise nicht möglich ist. Benutzer erhalten den Audioteil der Besprechung über Ihr Mobiltelefon oder Ihre Festnetz-und den Inhaltsbereich der Besprechung&mdash;, beispielsweise, wenn ein anderer Besprechungsteilnehmer seinen Bildschirm freigibt&mdash;oder ein Video über seinen Computer abspielt.

## <a name="the-user-experience"></a>Die Benutzeroberfläche

Klicken Sie auf **Teil** nehmen, um an einer Besprechung teilzunehmen, und klicken Sie dann auf der Seite **Wählen Sie Ihre Audio-und Videoeinstellungen aus** auf **Telefon-Audio** . Von hier aus können Benutzer den Besprechungs Anruf führen und an der Besprechung teilnehmen oder sich manuell einwählen.

![Screenshot der Option "Telefon Audio"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Besprechung des Anrufs für Teams**

Auf dem Bildschirm " **Telefon für Audio verwenden** " gibt der Benutzer seine Telefonnummer ein und klickt dann auf " **anrufen**". Die Besprechung Ruft den Benutzer an und verknüpft ihn mit der Besprechung.

![Screenshot der Option "anrufen" auf dem Bildschirm "Telefon für Audio verwenden"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Manuell einwählen**

Eine weitere Möglichkeit, sich anzumelden, besteht darin, sich direkt in die Besprechung einzuwählen. Klicken Sie auf dem Bildschirm **Telefon für Audio verwenden** auf **manuell einwählen** , um eine Liste der Telefonnummern zu erhalten, die Sie für die Einwahl in die Besprechung verwenden möchten.

![Screenshot der Option "manuell einwählen"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a>Einrichten der Funktion "anrufen"

Um die Funktion "anrufen" für Benutzer in Ihrer Organisation zu aktivieren, muss Folgendes konfiguriert sein:

- Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren). Weitere Informationen finden Sie unter [Einrichten von Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) und [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

- Benutzer können aus Besprechungen wählen. Weitere Informationen finden Sie unter [Verwalten der Einstellungen für Audiokonferenzen für einen Benutzer in Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).

Wenn ein Benutzer die Option "Besprechungen" nicht aktiviert hat, steht die Option " **anrufen** " nicht zur Verfügung, und der Benutzer erhält keinen Anruf, um an der Besprechung teilzunehmen. Stattdessen sieht der Benutzer auf dem Bildschirm " **Telefon für Audio verwenden** " eine Liste mit Telefonnummern, mit denen er sich manuell in die Besprechung auf seinem Telefon einwählen kann.

