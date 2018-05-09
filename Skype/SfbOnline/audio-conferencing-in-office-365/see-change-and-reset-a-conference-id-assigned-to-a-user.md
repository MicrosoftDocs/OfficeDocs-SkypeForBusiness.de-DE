---
title: Anzeigen, Bearbeiten und Zurücksetzen einer Konferenz-ID, die einem Nutzer zugewiesen wurde
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 73c5d3cc95b7967cd9d6eaae83a14e19143e431b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a>Anzeigen und eine Konferenz-ID, die einem Benutzer zugewiesenen zurücksetzen

Eine Konferenz-ID wird automatisch auf einen Skype für Business oder Microsoft-Teams, Benutzer zugewiesen, für Audiokonferenzen in Office 365 einrichten und Verwenden von Microsoft als Anbieter von Audiokonferenzen. Die Konferenz-ID zugewiesen wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist. Jede Besprechung, die ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen 
  
Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten, und es eine bestimmte Anzahl festgelegt werden soll, oder wenn Ihre Benutzer können nicht merken oder ihre Konferenz-ID. verloren haben Sie können die **Skype für Business Administrationscenter** und Windows PowerShell verwenden, anzeigen, ändern und Zurücksetzen ihrer Konferenz-ID.
  
Dem Benutzer mit der Konferenz-ID und die Telefonnummern der Standard-Audiokonferenzen wird eine e-Mail gesendet werden, oder wenn Sie die Konferenz-ID zurücksetzen eine e-Mail gesendet wird, die die Konferenz-ID, aber nicht mit einer PIN enthalten wird. Weitere Informationen zum Zurücksetzen einer Konferenzorganisator PIN, [Wechseln Sie hier](reset-a-conference-id-for-a-user.md). 
  
## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an.

![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Suchen Sie unter **Audiokonferenzen**klicken Sie unter **Konferenz-ID**ein.

    > [!TIP]
    > Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern enthält durch Klicken auf den Link **Konferenz Informationen in e-Mail-Nachricht senden** .

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen. Führen Sie dazu Folgendes aus:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

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

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück.

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen "If"; beispielsweise, wenn sie es vergessen.
  
![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen**auf **Konferenz-ID zurückgesetzt**.

4. Klicken Sie auf **Zurücksetzen**, klicken Sie im Fenster **Konferenz-ID zurückgesetzt** . A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Zu diesem Zweck führen Sie Folgendes aus:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**, klicken Sie auf **Zurücksetzen**.
    
4. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
    
    Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Zu diesem Zweck führen Sie Folgendes aus:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nachdem eine neue Konferenz-ID erstellt wird oder eine zurückgesetzt wird, kann nicht die alte Konferenz-ID BSSID verwendet werden. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen. Informationen zum Herunterladen, installieren und Ausführen des Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)und [Skype für Online Business Besprechung Migration Tool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.
    
- Die Konferenz-ID muss die Länge in Ziffern legen Sie für die audiokonferenzbrücke erfüllen. Sie können nicht alphabetische oder Sonderzeichen im Konferenz-IDs verwenden. nur Zahlen können verwendet werden.
    
- Die Konferenz-ID für alle Ihre audiokonferenzbenutzer werden standardmäßig 7 Ziffern, und die Anzahl der Nachkommastellen kann nicht geändert werden.
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See Also

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

