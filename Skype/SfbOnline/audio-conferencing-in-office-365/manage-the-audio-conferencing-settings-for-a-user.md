---
title: Verwalten der Audiokonferenzeinstellungen für einen Benutzer in Skype for Business Online
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
description: 'Als Microsoft 365- oder Office 365-Administrator können Sie die Einstellungen für Skype for Business Online-Audiokonferenzen – z. B. Den Anbieter, die gebührenpflichtige oder gebührenfreie Standardnummer, die Konferenz-ID oder die PIN – für einen einzelnen Benutzer in Ihrer Organisation bearbeiten. '
ms.openlocfilehash: 648bb27ce8e6745d765b8fc400494188fd43b5e866ecf0cf927f36fd4d7ca676
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54335715"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Verwalten der Audiokonferenzeinstellungen für einen Benutzer in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Informationen zum Verwalten von Benutzereinstellungen in Microsoft Teams Sie unter Verwalten der Audiokonferenzeinstellungen für einen Benutzer [in Microsoft Teams.](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams)

Als Microsoft 365- oder Office 365-Administrator können Sie die Audiokonferenzeinstellungen für einen einzelnen Benutzer in Ihrer Organisation bearbeiten , z. B. den Anbieter, die gebührenpflichtige oder gebührenfreie Standardnummer, die Konferenz-ID oder die PIN. Wenn Sie die Einstellungen für Ihre Organisation bearbeiten möchten, lesen Sie Verwalten der [Audiokonferenzeinstellungen für meine Organisation.](manage-the-audio-conferencing-settings-for-my-organization.md)

 
1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie Skype for Business Admin Center Benutzer **aus.**
    
4. Wählen Sie den Benutzer, für den Sie die Einstellungen verwalten möchten, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**![Anzeige des Bearbeiten-Icons](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Wählen Sie im linken Navigationsbereich **Audiokonferenzen** aus, und ändern Sie dann auf der Seite **Eigenschaften** für den Benutzer eines der folgenden:
    
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|**Anbietername** <br/> |Wählen Sie Ihren Anbieter aus der Liste aus.  <br/><br/> **Hinweis:** Die restlichen Einstellungen in dieser Tabelle gelten nur, wenn Sie Microsoft als Anbieter von Audiokonferenzen aktivieren.           |
|**Standardmäßige gebührenpflichtige Nummer** (erforderlich) <br/> |Für Drittanbieter sind diese Rufnummern diejenigen, die Sie vom Anbieter für Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Nummern so, wie sie in Besprechungsanfragen angezeigt Skype for Business Microsoft Teams werden sollen.  <br/> |
|**Gebührenfreie Standardnummer** <br/> |Für Drittanbieter sind diese Rufnummern diejenigen, die Sie vom Anbieter für Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Nummern so, wie sie in Besprechungsanfragen angezeigt Skype for Business Microsoft Teams werden sollen.  <br/> |
|**Lassen Sie die Nutzung gebührenfreier Nummern in der Microsoft-Bridge Ihrer Organisation zur Teilnahme an Besprechungen dieses Benutzers zu** <br/> |Wählen Sie diese Option, wenn Sie den Benutzer von gebührenfreien Nummern zum Teilnehmen an Besprechungen zulassen möchten.  <br/> |
|**Senden von Konferenzinformationen per E-Mail** <br/> |Klicken Sie nur auf diesen Link, wenn Sie sofort eine E-Mail an den Benutzer mit dessen Konferenz-ID und Telefonnummer senden möchten. (Diese E-Mail enthält nicht die PIN.) Weitere Informationen finden Sie unter [Eine E-Mail an einen Benutzer mit dessen Audiokonferenzen-Informationen senden](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Konferenz-ID** <br/> |Wählen Sie **Zurücksetzen** aus, wenn Sie die Konferenz-ID für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN** <br/> |Wählen Sie **Zurücksetzen** aus, wenn Sie die PIN für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen der PIN für Audiokonferenzen](reset-the-audio-conferencing-pin.md).  <br/> |
|**Erlauben Sie nicht authentifizierten Anrufern die ersten Personen in einer Besprechung zu sein** <br/> |Wählen Sie diese Option, um nicht authentifizierten Anrufern zu ermöglichen, als erste an Besprechungen teilnehmen zu können.  <br/> |
|**Beschränkungen von Wählmöglichkeiten in Besprechungen für diesen Benutzer** <br/> |Wählen Sie eine Option in dieser Liste, wenn Sie Anrufe aus einer Besprechung heraus auf lokale Anrufe beschränken möchten, oder wenn Sie alle Anrufe aus Besprechungen heraus unterbinden möchten.  <br/> |
  
![Zeigt die Seite Eigenschaftenseite von Audiokonferenzen für einen Benutzer](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für meine Organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Allgemeine Fragen zu Audiokonferenzen](/MicrosoftTeams/audio-conferencing-common-questions)
