---
title: "Ändern der Einstellungen für eine Audiokonferenz-Brücke"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Hier finden Sie die Schritte, die Sie Einstellungen für eine Microsoft-Einwahl Konferenzbrücke ändern, mit der Aufforderung Anrufer und Namen und Pins für Besprechungsorganisatoren sammeln, wenn sie nicht Skype für Business Clients verwenden, müssen. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Ändern der Einstellungen für eine Audiokonferenz-Brücke

Wenn Sie Audiokonferenzen in Office 365 einrichten, erhalten Sie Telefonnummern für Ihre Benutzer von was eine audiokonferenzbrücke aufgerufen wird. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten. Diese Rufnummern werden verwendet, wenn Anrufer in einer Besprechung einwählen. Die Telefonnummer ist am unteren Rand der Skype für Business oder Microsoft-Teams Besprechung einladen enthalten.
  
Die Konferenzbrücke beantwortet eines Anrufs und zeigt den Anrufer Ansagen mithilfe einer Besprechung Auto attendant, und klicken Sie dann je nach Ihrer Einstellungen wiedergeben Benachrichtigungen, bitten Sie ihren Namen aufzeichnen Anrufer, und kann die PIN-Einstellungen steuern. Stifte, Besprechungsorganisatoren zugewiesen sind, können an eine Besprechung starten werden beim werden nicht mithilfe einer Skype für Business oder Microsoft-Teams, app.

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Ändern der Einstellungen für eine audiokonferenzbrücke

 **Richten Sie die besprechungsumgebung, wenn Anrufer an einer Besprechung teilnehmen**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Navigieren Sie in der **Skype für Business-Verwaltungskonsole**im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Wählen Sie auf der Seite **Microsoft-Brücke-Einstellungen** unter **Erleben Sie die Teilnahme an einer Besprechung**:
    
  - **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden** Diese Option ist standardmäßig ausgewählt. Wenn Sie das Kontrollkästchen deaktivieren, werden nicht Benutzer, die bereits an der Besprechung benachrichtigt, wenn ein Benutzer eingibt oder die Besprechung verlässt.
    
    Bei der Auswahl von **Besprechungseintrag aktivieren, und beenden Sie Benachrichtigungen aktiviert werden**, können Sie diese Optionen aus der Liste **Entry/Exit Ankündigung** auswählen:
    
  - **Namen oder Telefonnummern** Wenn der Benutzer in einer Besprechung einwählen, wird beim Beitritt zu es ihre Telefonnummer wiedergegeben.
    
  - **Töne** Wenn der Benutzer in einer Besprechung einwählen, wird beim Beitritt zu es ein audio Ton wiedergegeben.
    
    > [!NOTE]
    > Unter Verwendung von **Tone** Dateityp Ankündigung ist als Vorschaufeature derzeit für alle Kunden zur Verfügung.
  
  - **Ask Anrufer ihren Namen vor der Teilnahme an der Besprechung aufzeichnen** Diese Option ist standardmäßig ausgewählt. Wenn Sie das Kontrollkästchen deaktivieren, werden nicht Anrufer aufgefordert, ihren Namen aufzeichnen müssen, bevor sie an einer Besprechung teilnehmen.
    
5. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
**Legen Sie die PIN-Mindestlänge für Besprechungen**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Geben Sie auf der Seite **Microsoft-Brücke-Einstellungen** unter **Sicherheit**die Anzahl der Ziffern, die Sie für die PIN-Nummer in der Liste der **PIN-Länge** verwenden möchten, und klicken Sie dann auf **Speichern**.
    
    > [!IMPORTANT]
    > Die PIN muss zwischen 4 und 12 Ziffern. 
  
**Wählen Sie, ob das Senden von e-Mails an Ihre Benutzer**
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Klicken Sie auf der Seite **Microsoft-Brücke Einstellungen** aktivieren Sie oder deaktivieren Sie **automatisch für Benutzer-e-Mails gesendet, wenn die Konfiguration ihrer Audiokonferenzen ändert**, und klicken Sie dann auf **Speichern**.
    
    Weitere Informationen finden Sie unter [e-Mails werden automatisch für Benutzer, wenn Ändern ihrer Einstellungen für die Audiokonferenz gesendet](emails-sent-to-users-when-their-settings-change.md) .
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit sparen oder diesen Prozess automatisieren, können Sie das Cmdlet [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) verwenden.
    
- Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind. Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie ändert sich die Einstellung für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

