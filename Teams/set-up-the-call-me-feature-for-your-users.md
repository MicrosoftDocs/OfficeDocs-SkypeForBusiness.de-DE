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
description: Erfahren Sie, wie Sie das Feature Anrufen in Teams so einrichten, dass Benutzer dem Audioteil per Telefon beitreten können, wenn sie ihren Computer für Audio verwenden.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623132"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a>Einrichten der Funktion „Rückruf“ für Ihre Benutzer

In Microsoft Teams bietet das **Feature "Anrufen"** benutzern die Möglichkeit, telefonisch am Audioteil einer Besprechung teil zu nehmen. Dies ist in Szenarien praktisch, wenn die Verwendung eines Computers für Audio möglicherweise nicht möglich ist. Benutzer erhalten den Audioteil der Besprechung über ihr Mobiltelefon oder ihre Festnetzleitung und den Inhaltsteil der Besprechung, z. B. wenn ein anderer Besprechungsteilnehmer seinen Bildschirm teilt oder ein Video über seinen &mdash; &mdash; Computer abspielt.

> [!IMPORTANT]
> 
> In Zeiten mit überdurchschnittlich vielen Besprechungen (wie wir sie im Zusammenhang mit dem COVID-19-Ausbruch erlebt haben) empfehlen wir, dass Benutzer an Besprechungen teilnehmen, indem Sie auf die Schaltfläche <strong>An Teams-Besprechung teilnehmen</strong> klicken, anstatt sich über die Rufnummern der PSTN-Konferenz einzuwählen oder <strong>Rückruf unter</strong> zu verwenden. Dadurch wird das PSTN-Netzwerk nicht überlastet und eine klare Audioqualität sichergestellt.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a>Die Benutzeroberfläche

### <a name="join-a-meeting-by-using-phone-for-audio"></a>Teilnehmen an einer Besprechung mithilfe eines Telefons für Audio

Klicken **Sie auf** Teilnehmen,  um an einer Besprechung teil zu nehmen, und wählen Sie dann audio auf dem Bildschirm Video- und **Audiooptionen** auswählen aus, und klicken Sie auf **Jetzt teilnehmen.** Von hier aus können Benutzer den Besprechungsanruf durchführen und an ihnen teilnehmen oder sich manuell zur Besprechung einwählen.

![Screenshot der Audiooption Telefon](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

**Lassen Sie den Besprechungsanruf von Teams**

Auf dem **Bildschirm Telefon für Audio verwenden** gibt der Benutzer seine Telefonnummer ein und klickt dann auf **Anrufen.** Die Besprechung ruft den Benutzer an und schließt sich der Besprechung an.

![Screenshot der Option "Anrufen" auf dem Bildschirm "Telefon für Audio verwenden"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

**Manuelles Einwählen**

Eine weitere Möglichkeit zur Teilnahme besteht in der direkten Einwahl zur Besprechung. Klicken Sie auf dem Bildschirm  Telefon für **Audio verwenden** auf Manuelles Einwählen, um eine Liste der Telefonnummern anzuzeigen, die zum Einwählen in die Besprechung verwendet werden können.

![Screenshot der Option "Manuell einwählen"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a>Zurückrufen, wenn während einer Besprechung ein Fehler bei Audiodaten vorkommt

Wenn bei der Verwendung ihres Computers während einer Besprechung Audioprobleme auftreten, kann der Benutzer ganz einfach zur Verwendung des Telefons für Audio wechseln. Teams erkennt, wenn ein Audio- oder Geräteproblem auftritt, und leitet den Benutzer durch Anzeigen einer Rückrufoption zur Nutzung des Telefons **um.**

Hier sehen Sie ein Beispiel  für die Nachricht und die Option Rückruf, die angezeigt wird, wenn Teams kein Mikrofon erkennt.

![Screenshot der Option "Zurückrufen"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

Der Benutzer klickt **auf Rückruf**, wodurch der Bildschirm Telefon für Audio **verwenden angezeigt** wird. Von hier aus können sie ihre Telefonnummer eingeben und den Besprechungsanruf von Teams durchführen lassen und an der Besprechung teilnehmen oder sich manuell zur Besprechung einwählen.

## <a name="set-up-the-call-me-feature"></a>Einrichten der Funktion "Anrufen"

Zum Aktivieren der Funktion "Mich anrufen" für Benutzer in Ihrer Organisation muss Folgendes konfiguriert sein:

- Audiokonferenzen sind für Benutzer in Ihrer Organisation aktiviert, die Besprechungen planen (Besprechungsorganisatoren). Weitere Informationen finden Sie unter Einrichten von [Audiokonferenzen für Teams](set-up-audio-conferencing-in-teams.md) und Verwalten der Einstellungen für [Audiokonferenzen](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)für einen Benutzer in Teams.

- Der Besprechungsorganisator kann sich aus Besprechungen herauswählen. Weitere Informationen finden Sie unter Verwalten der [Audiokonferenzeinstellungen für einen Benutzer in Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

Wenn für den Besprechungsorganisator kein Auswählen  von Besprechungen  aktiviert ist, steht die Option Telefonaudio auf dem Bildschirm Video- und Audiooptionen auswählen niemandem zur Verfügung, und andere Benutzer können keinen Anruf erhalten, um an der Besprechung teilzunehmen. Für Benutzer mit aktivierter Einwahl können sie nach der Teilnahme an der Besprechung an anderen Personen teilnehmen, indem sie ihre Nummer über das Symbol Teilnehmer **anzeigen** auswählen auswählen.
