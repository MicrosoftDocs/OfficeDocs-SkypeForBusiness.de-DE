---
title: Verwalten von Einstellungen für die Audiokonferenz für einen Benutzer in Skype für Business Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Sie können als ein Office 365-Administrator die Skype for Business Online-Audiokonferenzeinstellungen – wie z.B. der Anbieter, gebührenpflichtige oder gebührenfreie Telefonnummer als Standard, Konferenz-ID oder PIN – für einen einzelnen Benutzer in Ihrer Organisation bearbeiten. '
ms.openlocfilehash: 06fd99987df725e235f308af20542fa45b0286fd
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886401"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Verwalten von Einstellungen für die Audiokonferenz für einen Benutzer in Skype für Business Online

> [!Note]
> Wenn Sie Benutzer in Microsoft-Teams verwalten möchten, finden Sie unter [verwalten die Audiokonferenz Einstellungen für einen Benutzer in Microsoft-Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

Sie können als ein Office 365-Administrator die Audiokonferenzeinstellungen – wie z.B. der Anbieter, gebührenpflichtige oder gebührenfreie Telefonnummer als Standard, Konferenz-ID oder PIN – für einen einzelnen Benutzer in Ihrer Organisation bearbeiten. Wenn Sie Einstellungen für die Organisation bearbeiten möchten, finden Sie unter [die Audiokonferenz Einstellungen für meine Organisation verwalten](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie in der Skype für Business Administrationscenter **Benutzer**.
    
4. Wählen Sie den Benutzer, für den Sie die Einstellungen verwalten möchten, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**![Anzeige des Bearbeiten-Icons](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Wählen Sie im linken Navigationsbereich **Audiokonferenzen** aus, und ändern Sie dann auf der Seite **Eigenschaften** für den Benutzer eines der folgenden:
    
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|**Name des Anbieters** <br/> |Wählen Sie aus der Liste der Anbieter.  <br/><br/> **Hinweis:** Die restlichen Einstellungen in dieser Tabelle gelten nur, wenn Sie Microsoft als Anbieter von Audiokonferenzen aktivieren.           |
|**Standardmäßige gebührenpflichtige Nummer** (erforderlich) <br/> |Für Drittanbieter sind diese Rufnummern diejenigen, die Sie vom Anbieter für Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Standardmäßige gebührenfreie Rufnummer** <br/> |Für Drittanbieter sind diese Rufnummern diejenigen, die Sie vom Anbieter für Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Lassen Sie die Nutzung gebührenfreier Nummern in der Microsoft-Bridge Ihrer Organisation zur Teilnahme an Besprechungen dieses Benutzers zu** <br/> |Wählen Sie diese Option, wenn Sie den Benutzer von gebührenfreien Nummern zum Teilnehmen an Besprechungen zulassen möchten.  <br/> |
|**Konferenz-Informationen per e-Mail senden** <br/> |Klicken Sie nur auf diesen Link, wenn Sie sofort eine E-Mail an den Benutzer mit dessen Konferenz-ID und Telefonnummer senden möchten. (Diese E-Mail enthält nicht die PIN.) Weitere Informationen finden Sie unter [Eine E-Mail an einen Benutzer mit dessen Audiokonferenzen-Informationen senden](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Konferenz-ID** <br/> |Wählen Sie **Zurücksetzen** aus, wenn Sie die Konferenz-ID für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN-NUMMER** <br/> |Wählen Sie **Zurücksetzen** aus, wenn Sie die PIN für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen der PIN für Audiokonferenzen](reset-the-audio-conferencing-pin.md).  <br/> |
|**Erlauben Sie nicht authentifizierten Anrufern die ersten Personen in einer Besprechung zu sein** <br/> |Wählen Sie diese Option, um nicht authentifizierten Anrufern zu ermöglichen, als erste an Besprechungen teilnehmen zu können.  <br/> |
|**Beschränkungen von Wählmöglichkeiten in Besprechungen für diesen Benutzer** <br/> |Wählen Sie eine Option in dieser Liste, wenn Sie Anrufe aus einer Besprechung heraus auf lokale Anrufe beschränken möchten, oder wenn Sie alle Anrufe aus Besprechungen heraus unterbinden möchten.  <br/> |
  
![Zeigt die Seite Eigenschaftenseite von Audiokonferenzen für einen Benutzer](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für meine Organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Allgemeine Fragen zu Audiokonferenz](/MicrosoftTeams/audio-conferencing-common-questions)
