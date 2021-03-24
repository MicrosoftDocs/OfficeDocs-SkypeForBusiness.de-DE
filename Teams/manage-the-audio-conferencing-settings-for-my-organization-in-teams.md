---
title: Verwalten von Audiokonferenzeinstellungen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Weitere Informationen finden Sie unter Microsoft Teams-Schritte zum Zuweisen einer Lizenz für Einwahlkonferenzen und einer Konferenz-ID zu einem Benutzer und vielen anderen Einstellungen für Einwahlkonferenzen. '
ms.openlocfilehash: 96a8995b995340642c6b58be9d5062eacd3cd29c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101091"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams.

Möglicherweise sind alle Audiokonferenzeinstellungen für Microsoft Teams an einem Ort einfacher zu sehen. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audiokonferenzen

> [!NOTE]
> Sie können keine Lizenzen mithilfe von Teams zuweisen. Sie müssen das Microsoft 365 Admin Center verwenden. Weitere Informationen finden Sie unter Zuweisen von [Microsoft Teams-Add-On-Lizenzen.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **So weisen Sie einem Benutzer eine Lizenz zu**
  
1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.
    
2. Wechseln Sie in der linken **Navigationsleiste des Microsoft 365 Admin Centers** zu Aktive Benutzer , und wählen Sie dann den Benutzer oder die Benutzer aus der Liste der verfügbaren Benutzer   >  aus.
    
    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**.  
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**. 
    
4. Aktivieren Sie **auf der** Seite Produktlizenzen **Audiokonferenzen,** und klicken Sie dann auf **Speichern.** Weitere Informationen zur Lizenzierung finden Sie unter [Microsoft Teams-Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
    
   > [!NOTE]
   > Nachdem Sie die Lizenz zugewiesen haben, wird Microsoft möglicherweise nicht zuerst als Audiokonferenzanbieter in der Liste angezeigt. Melden Sie sich in diesem Fall entweder beim Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren von E-Mails, die an Benutzer von Audiokonferenzen gesendet wurden

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Brückeneinstellungen.** 

3. Aktivieren oder **deaktivieren Sie im** Bereich Bridge-Einstellungen automatisch E-Mails an Benutzer senden, wenn sich deren **Einwahleinstellungen ändern.**

4. Klicken Sie auf **Speichern**.

    
**Verwenden von Windows PowerShell**
  
Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)
  
## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

![Ein Symbol mit dem Teams-Logo ](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken **Sie unter Audiokonferenzen** auf **Konferenz-ID zurücksetzen.**  

3. Klicken Sie **im Fenster Konferenz-ID zurücksetzen?** auf **Zurücksetzen.** Eine Konferenz-ID wird automatisch erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet, wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist. It's enabled by default.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es zu Zeiten kommen, in denen ein Benutzer diese nicht verwenden möchte und sie auf eine bestimmte Nummer festlegen möchte, oder die Benutzer ihre Konferenz-ID nicht mehr merken oder verloren haben. 

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken **Sie unter Audiokonferenzen** auf **PIN zurücksetzen,** und klicken Sie dann auf **Zurücksetzen.** 
  
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt. 
  
Weitere [Informationen finden Sie unter Zurücksetzen der PIN für Audiokonferenzen.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken **Sie unter Audiokonferenzen** auf **Konferenzinformationen per E-Mail senden.** 

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet. 

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **neben Audiokonferenzen** auf **Bearbeiten.**
 
3. Im Bereich **Audiokonferenzen können** Sie die  Gebührenfreie Nummer und, falls zulässig, die **gebührenfreie Nummer festlegen.**

4. Klicken Sie auf **Speichern**.
    
Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Auswählen der Einstellungen für Audiokonferenzbrücke

**Festlegen der Besprechungserfahrung, wenn Anrufer an einer Besprechung teilnehmen**

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Brückeneinstellungen.** 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).

    Dies ist standardmäßig aktiviert. Wenn Sie diese Option deaktivieren, werden Benutzer, die der Besprechung bereits standardmäßig beigetreten sind, nicht benachrichtigt, wenn jemand die Besprechung ein- oder verlässt.

4. Wählen **Sie unter Eingabe-/Ausgangsankündigungstyp** entweder **Töne** oder **Namen oder Telefonnummern aus.** 

    Wenn Sie **Namen oder Telefonnummern** auswählen, können Sie auch Anrufer bitten aktivieren oder deaktivieren, ihren Namen vor der Teilnahme an der **Besprechung zu notieren.** 
    > [!NOTE]
    > Standardmäßig können externe Teilnehmer die Telefonnummern der einwählten Teilnehmer nicht sehen. Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden).


5. Klicken Sie auf **Speichern**.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Brückeneinstellungen.** 

3. Geben Sie **im Bereich** Bridge-Einstellungen in der Liste PIN-Länge die Anzahl der Ziffern für die **PIN** ein, und klicken Sie dann auf **Speichern.**

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Brückeneinstellungen.** 

3. Aktivieren oder **deaktivieren Sie im Bereich** Bridge-Einstellungen die Option Automatisches Senden von E-Mails an Benutzer, wenn sich die Einstellungen für **Audiokonferenzen ändern.**

4. Klicken Sie auf **Speichern**. 
 
    Sie können dem Benutzer auch E-Mails mit den Audiokonferenzeinstellungen senden, indem Sie zu den Audiokonferenzeigenschaften des Benutzers gehen und auf Konferenzinformationen per E-Mail **senden klicken.**
    
    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Sehen und Festlegen der primären (Standard-) und sekundären (alternativen) Sprachen auf einer Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten.**

3. Wählen Sie unter  Standardsprache und Alternative Sprachen (optional) die sprachen **aus, die Sie verwenden möchten.**

4. Klicken Sie auf **Speichern**.


Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie auf **Bearbeiten.** Hier können Sie:
    
   - Zeigen Sie die Telefonnummern an, die für Audiokonferenzen verwendet werden sollen. 
    
   - Zeigen Sie den Speicherort und die primäre Sprache an, die von der automatischen Telefonkonferenz für Audiokonferenzen verwendet wird.

  
Weitere Informationen finden Sie unter Eine [Liste der Nummern für Audiokonferenzen.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)