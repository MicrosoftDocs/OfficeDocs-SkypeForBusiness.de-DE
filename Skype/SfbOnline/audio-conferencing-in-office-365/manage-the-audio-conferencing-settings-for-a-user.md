---
title: Verwalten der Audio-Konferenzeinstellungen für einen Benutzer in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Als Microsoft 365-oder Office 365-Administrator können Sie die Einstellungen für die Audiokonferenz von Skype for Business online bearbeiten – beispielsweise den Anbieter, die standardmäßige gebührenpflichtige oder gebührenfreie Nummer, Konferenz-ID oder PIN – für einen einzelnen Benutzer in Ihrer Organisation. '
ms.openlocfilehash: 47ad2b0d6b5684d2a897055ad43e253e55c67109
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943848"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Verwalten der Audio-Konferenzeinstellungen für einen Benutzer in Skype for Business Online

> [!Note]
> Wenn Sie Benutzereinstellungen in Microsoft Teams verwalten möchten, lesen Sie [Verwalten der audiokonferenzeinstellungen für einen Benutzer in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

Als Microsoft 365-oder Office 365-Administrator können Sie die audiokonferenzeinstellungen wie den Anbieter, die standardmäßige gebührenpflichtige oder gebührenfreie Nummer, Konferenz-ID oder PIN für einen einzelnen Benutzer in Ihrer Organisation bearbeiten. Wenn Sie die Einstellungen für Ihre Organisation bearbeiten möchten, lesen Sie [Verwalten der Einstellungen für die Audiokonferenz für meine Organisation](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Mit Ihrem Firmen-oder Schulkonto anmelden
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie im Skype for Business Admin Center die Option **Benutzer**aus.
    
4. Wählen Sie den Benutzer, für den Sie die Einstellungen verwalten möchten, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**![Anzeige des Bearbeiten-Icons](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Wählen Sie im linken Navigationsbereich **Audiokonferenzen** aus, und ändern Sie dann auf der Seite **Eigenschaften** für den Benutzer eines der folgenden:
    
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|**Anbietername** <br/> |Wählen Sie Ihren Anbieter in der Liste aus.  <br/><br/> **Hinweis:** Die restlichen Einstellungen in dieser Tabelle gelten nur, wenn Sie Microsoft als Anbieter von Audiokonferenzen aktivieren.           |
|**Standardmäßige gebührenpflichtige Nummer** (erforderlich) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Gebührenfreie Standardnummer** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Lassen Sie die Nutzung gebührenfreier Nummern in der Microsoft-Bridge Ihrer Organisation zur Teilnahme an Besprechungen dieses Benutzers zu** <br/> |Wählen Sie diese Option, wenn Sie den Benutzer von gebührenfreien Nummern zum Teilnehmen an Besprechungen zulassen möchten.  <br/> |
|**Konferenz Informationen per e-Mail senden** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Konferenz-ID** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**Erlauben Sie nicht authentifizierten Anrufern die ersten Personen in einer Besprechung zu sein** <br/> |Wählen Sie diese Option, um nicht authentifizierten Anrufern zu ermöglichen, als erste an Besprechungen teilnehmen zu können.  <br/> |
|**Beschränkungen von Wählmöglichkeiten in Besprechungen für diesen Benutzer** <br/> |Wählen Sie eine Option in dieser Liste, wenn Sie Anrufe aus einer Besprechung heraus auf lokale Anrufe beschränken möchten, oder wenn Sie alle Anrufe aus Besprechungen heraus unterbinden möchten.  <br/> |
  
![Zeigt die Seite Eigenschaftenseite von Audiokonferenzen für einen Benutzer](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für meine Organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Allgemeine Fragen zu Audiokonferenzen](/MicrosoftTeams/audio-conferencing-common-questions)
