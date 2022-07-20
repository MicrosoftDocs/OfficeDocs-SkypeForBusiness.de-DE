---
title: Festlegen der in Einladungen enthaltenen Telefonnummern
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Führen Sie die folgenden Schritte aus, um eine Standardtelefonnummer für Anrufer für die Teilnahme an einer Microsoft Teams-Besprechung zu erstellen.
ms.openlocfilehash: f0956007d5df72c1fd6c6ae905433e73bd855a56
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884844"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Audiokonferenzen in Microsoft 365 und Office 365 ermöglichen Benutzern in Ihrer Organisation, Microsoft Teams-Besprechungen zu erstellen und benutzern dann das Einwählen in diese Besprechungen über eine Telefonnummer zu ermöglichen.

Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.

Zusätzlich zu den Telefonnummern, die in der Besprechungseinladung für einen Besprechungsorganisator enthalten sind, gibt es am Ende jeder Besprechungseinladung einen Link, über den die vollständige Liste aller Einwahlnummern geöffnet wird, die für die Teilnahme an einer Besprechung verwendet werden können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>Anfängliche Zuweisung von Telefonnummern, die in den Besprechungseinladungen für Benutzer enthalten sind

Die Telefonnummern, die in den Besprechungseinladungen von Benutzern enthalten sind, die für Audiokonferenzen aktiviert sind, sind in der *TeamsAudioConferencingPolicy* definiert, die Benutzern zugewiesen ist. Wenn einem Benutzer eine *TeamsAudioConferencingPolicy* zugewiesen wird, werden alle gebührenpflichtigen und gebührenfreien Telefonnummern, die in der Richtlinie hinzugefügt wurden, in Besprechungseinladungen für Benutzer einbezogen, die über diese Richtlinie verfügen. Wenn einem Benutzer eine *TeamsAudioConferencingPolicy* zugewiesen ist und der Richtlinie keine gebührenpflichtigen oder gebührenfreien Telefonnummern hinzugefügt werden, werden in diesem Fall die Telefonnummern, die in den Besprechungseinladungen dieser Benutzer angezeigt werden, durch die gebührenpflichtige Standardtelefonnummer für Konferenzen und die gebührenfreie Standardtelefonnummer für Konferenzen in den Einstellungen jedes einzelnen Benutzers definiert.

> [!NOTE]
> Gebührenpflichtige oder gebührenfreie Telefonnummern, die der *TeamsAudioConferencingPolicy* eines Benutzers hinzugefügt wurden, haben Vorrang vor den Telefonnummern, die einzeln unter Verwendung der gebührenpflichtigen Standardtelefonnummer für Konferenzen und der gebührenfreien Standardtelefonnummer für Konferenzen in den Einstellungen eines Benutzers festgelegt werden.

Wie oben erwähnt, enthält jede Besprechungseinladung zusätzlich zu den Telefonnummern einen Link, über den die vollständige Liste aller Einwahlnummern geöffnet wird, die für die Teilnahme an einer bestimmten Besprechung verwendet werden können.

> [!IMPORTANT]
> Es kann bis zu 24 Stunden dauern, bis die zugewiesenen Telefonnummern in Ihrer Besprechungseinladung angezeigt werden. Wenn aktualisierte Nummern nicht angezeigt werden, warten Sie mindestens 24 Stunden, bevor Sie sich an den Support wenden.

### <a name="new-users"></a>Neue Benutzer

Die gebührenpflichtigen und gebührenfreien Telefonnummern, die in Besprechungseinladungen für neue Benutzer enthalten sind, werden auch durch die *TeamsAudioconferencingPolicy* definiert, die diesen Benutzern zugewiesen ist. Standardmäßig wird allen neuen Benutzern die globale *TeamsAudioconferencingPolicy* zugewiesen. Der globalen Richtlinie werden keine Telefonnummern hinzugefügt (es sei denn, dies wird vom Mandantenadministrator geändert). In diesem Fall werden die Telefonnummern, die in die Besprechungseinladungen von Benutzern aufgenommen werden, die für Audiokonferenzen aktiviert sind, durch die gebührenpflichtige Standardtelefonnummer für Konferenzen und die gebührenfreie Standardtelefonnummer für Konferenzen in den Einstellungen jedes Benutzers definiert.

Für einen neuen Benutzer werden die gebührenpflichtigen Standardnummern für Konferenzen basierend auf dem Im Microsoft 365-Verwaltungscenter des Benutzers festgelegten Verwendungsspeicherort zugewiesen, wenn der Benutzer für den Audiokonferenzdienst aktiviert ist. Wenn die Konferenzbrücke eine gebührenpflichtige Nummer enthält, die dem Land des Benutzers entspricht, wird diese Nummer automatisch als gebührenpflichtige Standardnummer des Benutzers zugewiesen. Wenn es keine gibt, wird die Nummer, die als gebührenpflichtige Standardnummer der Konferenzbrücke definiert ist, als gebührenpflichtige Standardnummer des Benutzers zugewiesen.  

Sobald der Benutzer für den Audiokonferenzdienst aktiviert ist, können die gebührenpflichtigen und gebührenfreien Standardtelefonnummern des Benutzers vom Mandantenadministrator nach Bedarf von den ursprünglichen Werten geändert werden.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für Benutzer in PowerShell mithilfe des Cmdlets *"TeamsAudioConferencingPolicy* "

Lesen Sie die [Richtlinieneinstellungen für Audiokonferenzen für gebührenpflichtige und gebührenfreie Telefonnummern](audio-conferencing-toll-free-numbers-policy.md).

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer einzeln

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Klicken Sie im linken Navigationsbereich auf **"Benutzer"**.

    ![Zeigt die Auswahl von Benutzern im Microsoft Teams Admin Center.](media/Admin-users.png)

3. Klicken Sie in der Liste der verfügbaren Benutzer auf den Benutzernamen.

4. Klicken Sie neben **Audiokonferenzen** auf **"Bearbeiten"**.

    ![Klicken Sie neben "Audiokonferenzen" auf "Bearbeiten".](media/teams-set-phone-numbers-on-invites-image3.png)

5. Verwenden Sie die Felder **"Gebührenpflichtige Nummer** " oder " **Gebührenfreie Telefonnummer** ", um die Nummern für den Benutzer einzugeben.

> [!IMPORTANT]
> Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen wiederkehrende und zukünftige Microsoft Teams-Besprechungen aktualisiert und an die Teilnehmer gesendet werden.

> [!NOTE]
> Die in dieser Einstellung eingegebenen Telefonnummern werden nur verwendet, wenn der dem Benutzer *zugewiesenen TeamsAudioConferencingPolicy* keine Telefonnummern hinzugefügt wurden.

## <a name="want-to-use-windows-powershell"></a>Verwenden von Windows PowerShell

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Um die Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer [mithilfe von Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) festzulegen oder zu ändern, legen Sie die oder **`TollFreeServiceNumber`** die **`ServiceNumber`** Parameter des [Cmdlets Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) auf eine der verfügbaren Nummern fest.

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
