---
title: "Finden Sie unter ändern und eine Konferenz-ID, die einem Benutzer zugewiesenen zurücksetzen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Hier erfahren Sie, wie eine Konferenz-ID eines Benutzers in Skype für Unternehmen zugewiesen und welche die Konferenz-IDs Parameter werden sollte. "
ms.openlocfilehash: 46edf684a835984524ce988da532b6b9a14931da
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>Finden Sie unter ändern und eine Konferenz-ID, die einem Benutzer zugewiesenen zurücksetzen

Eine Konferenz-ID wird automatisch auf einen Skype für Business oder Microsoft-Teams, Benutzer zugewiesen, für Audiokonferenzen in Office 365 einrichten und Verwenden von Microsoft als Anbieter von Audiokonferenzen. Die Konferenz-ID zugewiesen werden kann, statische oder dynamische und wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist.
  
Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist. Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen Wenn Sie zuweisen dynamische statt statische Konferenz-IDs, [Wechseln Sie hier möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Zwar eine statische Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten, und es eine bestimmte Anzahl festgelegt werden soll, oder wenn Ihre Benutzer können nicht merken oder ihre Konferenz-ID. verloren haben Sie können die **Skype für Business Administrationscenter** und Windows PowerShell verwenden, anzeigen, ändern und Zurücksetzen ihrer Konferenz-ID.
  
Dem Benutzer mit der Konferenz-ID und die Telefonnummern der Standard-Audiokonferenzen wird eine e-Mail gesendet werden, oder wenn Sie die Konferenz-ID zurücksetzen eine e-Mail gesendet wird, die die Konferenz-ID, aber nicht mit einer PIN enthalten wird.
  
## <a name="view-and-change-conference-ids"></a>Anzeigen und Ändern der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an.

Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, den Benutzer auswählen, muss die Konferenz-ID.
    
4. Suchen Sie auf der Seite Aktion unter **Konferenz-ID**ein.
    
    > [!TIP]
    > Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern durch Klicken auf den Link **Konferenz Informationen per e-Mail senden** , nachdem Sie den Benutzer auf der Seite **Benutzer** auswählen enthält.
  
    Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen. Führen Sie dazu Folgendes aus:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Finden Sie unter [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) erfahren Sie mehr über das Cmdlet.
    
### <a name="to-assign-or-change-the-conference-id"></a>Zuweisen oder ändern die Konferenz-ID

Sie können zuweisen oder eine Konferenz-ID für einen Benutzer ändern, wenn Sie beispielsweise eine Person eine Konferenz-ID möchte, die leicht zu merken ist.

  > [!NOTE]
  > Die Skype für Business-Verwaltungskonsole kann nicht verwendet werden, so bearbeiten Sie eine Konferenz-ID, die automatisch erstellt wurde, aber Sie können Windows PowerShell verwenden, bearbeiten oder ändern eine Konferenz-ID, die Sie festgelegt haben. 
     
Zum Bearbeiten oder ändern die Konferenz-ID für einen Benutzer, führen Sie Folgendes aus:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > Eine Konferenz-ID muss 7 Ziffern enthalten, und Sie ihn in die Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell nicht ändern können. 
  
### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück.

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen "If"; beispielsweise, wenn sie es vergessen.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**, klicken Sie auf **Zurücksetzen**.
    
4. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**. Eine Konferenz die ID wird automatisch erstellt werden und eine e-Mail an den Benutzer mit der neuen Konferenz-ID gesendet
    
    Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Zu diesem Zweck führen Sie Folgendes aus:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nachdem eine neue Konferenz-ID erstellt wird oder eine zurückgesetzt wird, kann nicht die alte Konferenz-ID BSSID verwendet werden. Informieren Sie Benutzer von Plänen ihrer vorhandenen meeting-Einladungen für sicher, dass die neue Konferenz ansetzen, die ID der Einladungen hinzugefügt wird. Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen. Informationen zum Herunterladen, installieren und Ausführen des Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und [Skype für Online Business Besprechung Migration Tool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- Finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) erfahren Sie mehr über das Cmdlet.
    
- Die Konferenz-ID muss die Länge in Ziffern legen Sie für die audiokonferenzbrücke erfüllen. Sie können nicht alphabetische oder Sonderzeichen im Konferenz-IDs verwenden. nur Zahlen können verwendet werden.
    
- Die Konferenz-ID für alle Ihre audiokonferenzbenutzer werden standardmäßig 7 Ziffern, und die Anzahl der Nachkommastellen kann nicht geändert werden.
    
- Wenn der Benutzer von Microsoft als Anbieter von Audiokonferenzen, um einen Drittanbieter-Audiokonferenzen verschoben wird oder der Anbieter von Audiokonferenzen auf **None**festgelegt ist, wird die Konferenz-ID nicht mehr funktionsfähig. Finden Sie unter [Zuweisen von Drittanbietern als Anbieter von Audiokonferenzen](assign-a-third-party-as-the-audio-conferencing-provider.md) oder [Verschieben eines Benutzers für Audiokonferenzen an Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)
  

