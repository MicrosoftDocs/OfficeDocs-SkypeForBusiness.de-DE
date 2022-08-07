---
title: Verwalten von Audiokonferenzeinstellungen für Benutzer
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
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
description: Ein Microsoft 365- oder Office 365-Administrator kann die Teams-Audiokonferenzeinstellungen bearbeiten, einschließlich Anbieter, gebührenpflichtiger oder gebührenfreier Standardnummer, Konferenz-ID oder PIN für einen Benutzer.
ms.openlocfilehash: 13e44c9f7d8d983325c5f4cf3bb88237a9ad1fb9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269686"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Verwalten der Audiokonferenz-Einstellungen für einen Benutzer in Microsoft Teams

Als Microsoft 365- oder Office 365-Administrator können Sie die Audiokonferenzeinstellungen ( z. B. Anbieter, gebührenpflichtige oder gebührenfreie Standardnummer, Konferenz-ID oder PIN ) für einen einzelnen Benutzer in Ihrer Organisation bearbeiten. Wenn Sie Einstellungen für Ihre Organisation bearbeiten möchten, lesen [Sie "Verwalten der Audiokonferenzeinstellungen für Ihre Organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)".

## <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer**", und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie auf **"Bearbeiten"**.

3. Ändern Sie unter **"Audiokonferenzen**" eine der folgenden Optionen:

|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|**Audiokonferenzen**|Wenn Sie audiokonferenzen für den Benutzer aktivieren oder deaktivieren möchten, klicken Sie neben **Audiokonferenzen** auf **"Bearbeiten**", und schalten Sie dann im Bereich "**Audiokonferenzen**" **audiokonferenzen** ein oder aus.|
|**Senden von Konferenzinformationen per E-Mail**  |Klicken Sie nur auf diesen Link, wenn Sie sofort eine E-Mail an den Benutzer mit dessen Konferenz-ID und Telefonnummer senden möchten. (Diese E-Mail enthält nicht die PIN.) Weitere Informationen finden Sie unter [Eine E-Mail an einen Benutzer mit dessen Audiokonferenzen-Informationen senden](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).  |
|**Konferenz-ID**  |Klicken Sie auf **"Konferenz-ID zurücksetzen** ", wenn Sie die Konferenz-ID für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user-in-teams.md).  |
|**Pin** |Klicken Sie auf **"PIN zurücksetzen** ", wenn Sie die PIN für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen der PIN für Audiokonferenzen](reset-the-audio-conferencing-pin-in-teams.md). |
|**Gebührenpflichtige Standardtelefonnummer für Konferenzen** (erforderlich) |Dies sind Nummern, die für die Audiokonferenzbrücke festgelegt sind. Formatieren Sie die Zahlen so, wie sie in Skype for Business- und Microsoft Teams-Besprechungsanfragen angezeigt werden sollen. Um die gebührenpflichtige Standardnummer zu ändern, klicken Sie neben **"Audiokonferenzen****" auf "Bearbeiten**", und wählen Sie im Bereich "**Audiokonferenzen**" unter "**Gebührenpflichtige Nummer**" eine Nummer aus. Sie können Telefonnummern auch festlegen, indem Sie sie der TeamsAudioConferencingPolicy hinzufügen und die Richtlinie Ihren Benutzern zuweisen. Telefonnummern, die der Richtlinie hinzugefügt wurden, haben Vorrang vor den Telefonnummern, die mit der **gebührenpflichtigen Standardtelefonnummer für Konferenzen** festgelegt wurden. Wenn der TeamsAudioConferencingPolicy keine Telefonnummern hinzugefügt werden, wird die telefonnummer, die mit der **gebührenpflichtigen Standardkonferenznummer** festgelegt wurde, in Microsoft Teams-Besprechungsanfragen angezeigt. |
|**Einladungen von diesem Benutzer können gebührenfreie Telefonnummern enthalten.**|Diese Einstellung kann nur mithilfe der TeamsAudioconferecningPolicy geändert werden. |
|**Nicht authentifizierte Benutzer können die erste Person in der Besprechung sein**|Um diese Einstellung zu ändern, **können nicht authentifizierte Benutzer als erste Person in der Besprechung** ein- oder ausgeschaltet sein.
|**Auswahlberechtigungen**|Um diese Einstellung zu ändern, klicken Sie neben **Audiokonferenzen** auf **"Bearbeiten**", und wählen Sie im **Bereich "Audiokonferenzen**" eine Option unter "**Aus Besprechungen wählen" aus**.|

![Zeigt die Audiokonferenzeinstellungen für einen Benutzer an.](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für Ihre Organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[Allgemeine Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md)
