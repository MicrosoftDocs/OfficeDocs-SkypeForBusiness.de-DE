---
title: Verwalten der Audiokonferenz Einstellungen für einen Benutzer
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Als ein Office 365-Administrator können Sie die Einstellungen für die Audiokonferenz bearbeiten – wie der Anbieter, Standard gebührenpflichtige oder gebührenfreie Telefonnummer, Konferenz-ID oder PIN – für einen einzelnen Benutzer in Ihrer Organisation. Wenn Sie Einstellungen für die Organisation bearbeiten möchten, finden Sie unter Verwalten der Audiokonferenz Einstellungen für meine Organisation.
ms.openlocfilehash: 141ede21a99ff251786c7dfc63f4c55358b61c72
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-a-user"></a>Verwalten der Audiokonferenz Einstellungen für einen Benutzer

Als ein Office 365-Administrator können Sie die Einstellungen für die Audiokonferenz bearbeiten – wie der Anbieter, Standard gebührenpflichtige oder gebührenfreie Telefonnummer, Konferenz-ID oder PIN – für einen einzelnen Benutzer in Ihrer Organisation. Wenn Sie Einstellungen für die Organisation bearbeiten möchten, finden Sie unter [die Audiokonferenz Einstellungen für meine Organisation verwalten](manage-the-audio-conferencing-settings-for-my-organization.md).

![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Ändern Sie unter **Audiokonferenzen**eine der folgenden aus:

|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|**Audiokonferenzen**|Audiokonferenzen aktivieren oder Deaktivieren für den Benutzer, klicken Sie auf **Bearbeiten** , neben **Audiokonferenzen**, und klicken Sie dann im Bereich **Audiokonferenzen** ein-/ausschalten **Audiokonferenzen** aktiviert oder deaktiviert.|
|**Konferenz-Informationen in e-Mail senden**  |Klicken Sie auf diesen Link, nur, wenn Sie eine e-Mail an den Benutzer mit seinem Konferenz-ID und Telefonnummer sofort senden möchten. (Diese e-Mail ist die PIN nicht enthalten.) Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).  |
|**Konferenz-ID**  |Klicken Sie auf **Zurücksetzen Konferenz-ID** , wenn Sie die Konferenz-ID für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).  |
|**PIN-NUMMER** |Klicken Sie auf **Zurücksetzen PIN** , wenn Sie die PIN für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Audio Conferencing PIN zurücksetzen](reset-the-audio-conferencing-pin.md). |
|**Default Conferencing gebührenpflichtige Telefonnummer** (erforderlich) |Diese werden Zahlen, die für die audiokonferenzbrücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll. Um die standardmäßige gebührenpflichtige Nummer zu ändern, klicken Sie auf **Bearbeiten** weiter zu **Audiokonferenzen** und in der **Audiokonferenz** Sie im Bereich Wählen Sie eine Zahl unter **gebührenpflichtige Nummer**aus. |
|**Invites von diesem Benutzer können die gebührenfreie Telefonnummer enthalten.**|Wenn Sie diese Einstellung ändern, klicken Sie auf **Bearbeiten** , neben **Audiokonferenzen** und klicken Sie im Bereich **Audiokonferenzen** , umschalten Sie **gebührenfreie Nummern in Besprechungsanfragen von diesem Benutzer umfassen** , aktiviert oder deaktiviert. |
|**Dial-Out-Berechtigungen**|Wenn Sie diese Einstellung ändern, klicken Sie auf **Bearbeiten** , neben **Audiokonferenzen** und klicken Sie im Bereich **Audiokonferenzen** , wählen Sie eine Option unter **Dial-Out - Berechtigung von Besprechungen**.|

![Zeigt die Audiokonferenz Einstellungen für einen Benutzer](../images/sfbaudioconf-usersettings.png)
 
![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**
 
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie in der Skype für Business Administrationscenter **Benutzer**.
    
4. Wählen Sie den Benutzer, für den Sie verwalten möchten, und klicken Sie dann im Bereich Aktion auf **Bearbeiten**![zeigt das Symbol bearbeiten](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. Wählen Sie im linken Navigationsbereich **Audiokonferenzen** aus, und klicken Sie dann auf der Seite **Eigenschaften** für den Benutzer ändern Sie eines der folgenden:
    
|**Einstellung**|**Beschreibung**|
|:-----|:-----|
|**Name des Anbieters** <br/> |Wählen Sie aus der Liste der Anbieter.  <br/><br/> **Hinweis:** Die restlichen Einstellungen in dieser Tabelle gelten nur, wenn Sie Microsoft als Anbieter von Audiokonferenzen aktivieren.           |
|**Standardmäßige gebührenpflichtige Nummer** (erforderlich) <br/> |Für Drittanbieter sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, werden diese Zahlen, die für die audiokonferenzbrücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Standardmäßige gebührenfreie Anzahl** <br/> |Für Drittanbieter sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben. Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, werden diese Zahlen, die für die audiokonferenzbrücke festgelegt werden. Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.  <br/> |
|**Zulassen Sie mit dem gebührenfreie Nummern in der Microsoft-Bridge Ihrer Organisation zur Teilnahme an Besprechungen dieses Benutzers** <br/> |Wählen Sie diese Option, wenn Sie den Benutzer über gebührenfreie Nummern zum Teilnehmen an Besprechungen zulassen möchten.  <br/> |
|**Konferenz-Informationen per e-Mail senden** <br/> |Klicken Sie auf diesen Link, nur, wenn Sie eine e-Mail an den Benutzer mit seinem Konferenz-ID und Telefonnummer sofort senden möchten. (Diese e-Mail ist die PIN nicht enthalten.) Finden Sie unter [senden eine e-Mail an einen Benutzer mit ihren Audiokonferenzen Informationen](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Konferenz-ID** <br/> |Wählen Sie **Zurücksetzen** aus, wenn Sie die Konferenz-ID für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).  <br/> |
|**PIN-NUMMER** <br/> |Wählen Sie **Zurücksetzen** aus, wenn Sie die PIN für den Benutzer zurücksetzen müssen. Weitere Informationen finden Sie unter [Audio Conferencing PIN zurücksetzen](reset-the-audio-conferencing-pin.md).  <br/> |
|**Anrufern Sie nicht authentifizierte werden die ersten Personen in einer Besprechung** <br/> |Wählen Sie diese Option, ob nicht authentifizierter Anrufer werden die erste an Besprechungen teilnehmen können.  <br/> |
|**DFÜ-Outs von Besprechungen dieses Benutzers Einschränkungen** <br/> |Wählen Sie eine Option in dieser Liste, wenn Sie auf nur DFÜ-Outs beschränken möchten, oder wenn Sie verhindern möchten, alle DFÜ-Outs von Besprechungen.  <br/> |
  
![Zeigt die Seite Audio Webkonferenz-Eigenschaften für einen Benutzer](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>See Also

[Verwalten der Audiokonferenzeinstellungen für meine Organisation](manage-the-audio-conferencing-settings-for-my-organization.md)

[Allgemeine Fragen zu Audiokonferenz](audio-conferencing-common-questions.md)
