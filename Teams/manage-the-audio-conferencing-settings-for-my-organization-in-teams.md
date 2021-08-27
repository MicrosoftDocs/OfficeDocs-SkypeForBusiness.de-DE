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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Lesen Microsoft Teams Schritte zum Zuweisen einer Lizenz für Einwahlkonferenzen und einer Konferenz-ID zu einem Benutzer und vielen anderen Einstellungen für Einwahlkonferenzen. '
ms.openlocfilehash: 41ca513706e9aeb7028266d4ac6d494d1826af1d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624587"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Verwalten der Audiokonferenz-Einstellungen für Ihre Organisation in Microsoft Teams.

Möglicherweise ist es für Sie einfacher, alle Audiokonferenzeinstellungen für ihre Microsoft Teams an einem Ort zu sehen. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="assign-an-audio-conferencing-license"></a>Zuweisen einer Lizenz für Audiokonferenzen

> [!NOTE]
> Sie können lizenzen nicht mithilfe von Teams. Sie müssen die -Microsoft 365 Admin Center. Weitere [Informationen finden Microsoft Teams Zuweisen von Add-On-Lizenzen.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) 
  
 **So weisen Sie einem Benutzer eine Lizenz zu**
  
1. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Microsoft 365 an.
    
2. Navigieren Sie im linken Navigationsbereich **Microsoft 365 Admin Center** zu Benutzer aktive Benutzer , und wählen Sie dann den oder die Benutzer aus der Liste  >  der verfügbaren Benutzer aus.
    
    > [!NOTE]
    > Wenn Sie Lizenzen für bis zu 20 Benutzer gleichzeitig zuweisen, können Sie eine der Optionen in der Dropdownliste **Ansicht auswählen** auswählen oder eine eigene Ansicht erstellen. Klicken Sie dann auf **Bearbeiten** und zweimal auf **Weiter**, wählen Sie die Lizenz aus, und klicken Sie auf **Übermitteln**.  
  
3. Klicken Sie im Aktionsbereich unter **Produktlizenzen** auf **Bearbeiten**. 
    
4. Aktivieren Sie **auf der Seite** Produktlizenzen die Schaltfläche Audio **conferencing (Audiokonferenz),** und klicken Sie dann auf **Speichern.** Weitere Informationen zur Lizenzierung finden Sie [unter Microsoft Teams- und Add-On-Lizenzierung.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
   > [!NOTE]
   > Nachdem Sie die Lizenz zugewiesen haben, wird Microsoft möglicherweise nicht zuerst in der Liste als Audiokonferenzanbieter angezeigt. Melden Sie sich in diesem Fall beim Admin Center ab, oder drücken Sie STRG+F5, um das Browserfenster zu aktualisieren. 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Aktivieren oder Deaktivieren von E-Mails, die an Audiokonferenzbenutzer gesendet wurden

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Aktivieren oder **deaktivieren Sie im Bereich** Einstellungen der Brücke die Option Automatisches Senden von E-Mails an Benutzer, wenn sich **deren Einwahleinstellungen ändern.**

4. Klicken Sie auf **Speichern**.

    
**Verwenden von Windows PowerShell**
  
Weitere Informationen Microsoft Teams Sie in der [PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)
  
## <a name="reset-the-meeting-conference-id"></a>Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

![Symbol mit dem Teams ](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich **auf Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken **Sie unter Audiokonferenzen** auf **Konferenz-ID zurücksetzen**.  

3. Klicken Sie **im Fenster Konferenz-ID zurücksetzen?** auf **Zurücksetzen**. Wenn das Senden von E-Mails an Ihre Benutzer aktiviert ist, werden automatisch eine neue Konferenz-ID und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. It's enabled by default.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen Konferenzkennungen werden zwar automatisch erstellt und Benutzern zugewiesen, es kann aber auch sein, dass Benutzer diese Nummer nicht verwenden möchten und Sie diese Nummer festlegen möchten oder die Benutzer ihre Konferenz-ID vergessen oder verloren haben. 

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich **auf Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken **Sie unter Audiokonferenz** auf **PIN zurücksetzen**, und klicken Sie dann auf **Zurücksetzen.** 
  
Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert werden oder wenn die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird allerdings keine E-Mail zum Zurücksetzen der PIN gesendet. In diesem Fall müssen Sie die PIN manuell an den Benutzer senden. Die PIN wird nach dem Zurücksetzen nur einmal angezeigt. Nachdem sie unmittelbar nach dem Zurücksetzen angezeigt wurde, wird die PIN in den Benutzereigenschaften nicht mehr angezeigt. Stattdessen wird ***** angezeigt. 
  
Weitere [Informationen finden Sie unter Zurücksetzen der Audiokonferenz-PIN.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Senden einer E-Mail mit Audiokonferenzinformationen an einen Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich **auf Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken **Sie unter Audiokonferenz auf** **Konferenzinformationen per E-Mail senden**. 

    > [!NOTE]
    > Damit wird die Audiokonferenz-PIN nicht an den Benutzer gesendet. 

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Festlegen der in Einladungen enthaltenen Telefonnummern

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich **auf Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **neben Audiokonferenz** auf **Bearbeiten**.
 
3. Im **Bereich Audiokonferenz können** Sie die  gebührenpflichtige Nummer und, falls zulässig, die **gebührenfreie Nummer festlegen.**

4. Klicken Sie auf **Speichern**.
    
Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites-in-teams.md).
  
  
## <a name="choose-audio-conferencing-bridge-settings"></a>Auswählen der Einstellungen für die Audiokonferenzbrücke

**Festlegen der Besprechungserfahrung, wenn Anrufer an einer Besprechung teilnehmen**

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Aktivieren oder deaktivieren Sie im Bereich **Bridge settings** (Brückeneinstellungen) die Option **Meeting entry and exit notifications** (Benachrichtigungen bei Zu- oder Abgang in Besprechungen).

    Dies ist standardmäßig aktiviert. Wenn Sie diese Option deaktivieren, werden Benutzer, die der Besprechung bereits standardmäßig beigetreten sind, nicht benachrichtigt, wenn jemand der Besprechung beitritt oder diese verlässt.

4. Wählen **Sie unter Ankündigungstyp für Zu-/Abgang** entweder **Töne** oder **Namen oder Telefonnummern aus.** 

    Wenn Sie Namen **oder Telefonnummern** auswählen, können Sie Anrufer bitten, ihren Namen vor der Teilnahme an der Besprechung zu aktivieren **oder deaktivieren.** 
    > [!NOTE]
    > Standardmäßig können externe Teilnehmer die Telefonnummern der einwählten Teilnehmer nicht sehen. Wenn Sie die Vertraulichkeit dieser Telefonnummern wahren wollen, wählen Sie **Töne** für **Typ der Ankündigungen von Ein-/Ausgängen** aus (dies verhindert, dass die Nummern von Teams ausgelesen werden).


5. Klicken Sie auf **Speichern**.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Festlegen der Länge der PIN für Besprechungen**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Geben Sie **im Bereich Einstellungen der** Brücke in der Liste **PIN-Länge** die Anzahl der Ziffern für die PIN ein, und klicken Sie dann auf **Speichern.**

    Die PIN muss aus 4 bis 12 Ziffern bestehen. Der Standardwert beträgt 5.

    
Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Aktivieren oder Deaktivieren des Sendens von E-Mails an Audiobenutzer**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der **Seite Konferenzbrücken** auf **Einstellungen für Brücke.** 

3. Aktivieren oder **deaktivieren Sie im Bereich** Einstellungen der Brücke die Option Automatisches Senden von E-Mails an Benutzer, wenn sich **deren Audiokonferenzeinstellungen ändern.**

4. Klicken Sie auf **Speichern**. 
 
    Sie können dem Benutzer auch eine E-Mail mit den Audiokonferenzeinstellungen senden, indem Sie zu den Audiokonferenzeigenschaften des Benutzers gehen und auf Konferenzinformationen **per E-Mail senden klicken.**
    
    Damit wird eine E-Mail gesendet, die nur die Konferenz-ID und die Konferenztelefonnummer enthält, nicht aber die PIN.

Siehe [Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Lesen und Festlegen der primären (Standard) und sekundären (alternativen) Sprachen für eine Audiokonferenzbrücke

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie **auf Bearbeiten**.

3. Wählen Sie unter Standardsprache und **Alternative** Sprachen (optional) die **Sprachen aus, die Sie verwenden möchten.**

4. Klicken Sie auf **Speichern**.


Siehe [Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Anzeigen von Einwahlnummern für Audiokonferenzen

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Wählen Sie eine Telefonnummer aus der Liste aus, und klicken Sie **auf Bearbeiten**. Hier können Sie:
    
   - Zeigen Sie die Telefonnummern an, die für Audiokonferenzen verwendet werden sollen. 
    
   - Zeigen Sie den Standort und die primäre Sprache an, die von der automatischen Telefonkonferenz-Telefonkonferenz verwendet wird.

  
Weitere Informationen finden Sie unter Sehen Sie sich [eine Liste der Audiokonferenznummern an.](see-a-list-of-audio-conferencing-numbers-in-teams.md)
  

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
    
## <a name="related-topics"></a>Verwandte Themen

[Verwalten der Audiokonferenzeinstellungen für einen Benutzer](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)