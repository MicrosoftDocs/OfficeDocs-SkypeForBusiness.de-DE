---
title: "E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Einwahlkonferenzeinstellungen ändern"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/10/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
description: "Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. "
---

# E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre Einwahlkonferenzeinstellungen ändern

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
E-Mails werden automatisch an die Benutzer gesendet, die für [Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md) mit Microsoft als Einwahlkonferenzanbieter aktiviert sind.
  
Standardmäßig gibt es vier Arten von E-Mails, die an die Benutzer gesendet werden, die für Einwahlkonferenzen aktiviert sind. Wenn Sie die Anzahl von E-Mails, die an die Benutzer gesendet werden, einschränken möchten, können Sie diese Einstellung deaktivieren. Über Einwahlkonferenzen in Skype for Business Online wird Ihren Benutzern eine E-Mail gesendet, wenn:
  
- **Ihnen eine Lizenz für **Skype for Business PSTN-Konferenz** zugewiesen wird oder wenn Sie den Anbieter von Einwahlkonferenzen zu Microsoft ändern.**
    
     Diese E-Mail enthält die Konferenz-ID, die Standardeinwahlnummer für Besprechungen, die PIN für Einwahlkonferenzen für den Benutzer sowie Anweisungen und den Link zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Siehe[Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) oder[Zuweisen von Microsoft als Audiokonferenzanbieter](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Informationen zur entsprechenden Konfiguration finden Sie unter [Verwenden von Audiokonferenzanbieter dynamische IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    So kann diese E-Mail aussehen:
    
     ![Skype for Business Verify License](../images/17913e03-8b4a-4563-b58d-2f09b65fbcaa.png)
  
    Weitere Informationen zur Skype for Business-Lizenzierung finden Sie unter [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md),
    
- **Sich die Konferenz-ID oder die Standardtelefonnummer eines Benutzers ändert.**
    
    Diese E-Mail umfasst die Konferenz-ID, die Standardeinwahlnummer sowie Anweisungen und die Verknüpfung zum Skype for Business Online Meeting Update Tool, welches zur Aktualisierung bereits für den Benutzer geplanter Besprechungen verwendet wird. Sie enthält jedoch nicht die PIN des Benutzers für Einwahlkonferenzen. Siehe [Einrichten einer Konferenz-ID für einen Benutzer](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Informationen zur entsprechenden Konfiguration finden Sie unter [Verwenden von Audiokonferenzanbieter dynamische IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    So kann diese E-Mail aussehen:
    
     ![Die Informationen für Dial-In-Konferenzen wurden geändert.](../images/d6d3e028-d9fb-48c4-97c0-a73d6ade5ea3.png)
  
- **Die Einwahlkonferenz-PIN eines Benutzers wird zurückgesetzt.**
    
    Diese E-Mail enthält die Einwahlkonferenz-PIN des Organisators, die vorhandene Konferenz-ID und die Standardeinwahlnummer für den Benutzer. Siehe [Zurücksetzen der Einwahlkonferenz-PIN für einen Benutzer](reset-the-audio-conferencing-pin-for-a-user.md). 
    
    > [!NOTE]
    > Wenn Ihre Organisation für dynamische Konferenz-IDs aktiviert wurde, weisen alle geplanten Besprechungen eines Benutzers eine eindeutige Konferenz-ID auf. Informationen zur entsprechenden Konfiguration finden Sie unter [Verwenden von Audiokonferenzanbieter dynamische IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    So kann diese E-Mail aussehen:
    
     ![Die PIN für die Dial-In-Konferenz wurde geändert.](../images/df8df4f8-d11f-41b8-9187-99e66a88831b.png)
  
- **Die Lizenz eines Benutzers wird entfernt, wenn sein Einwahlkonferenzanbieter von Microsoft zu einem anderen Anbieter oder zu keinem Anbieter wechselt.**
    
    Das geschieht, wenn die Lizenz für **Skype for Business PSTN-Konferenz** von einem Benutzer entfernt wird, und zwar durch Änderung des Anbieters von Einwahlkonferenzen für einen Benutzer von Microsoft auf einen externen Audiokonferenzanbieter oder durch Einstellen des Anbieters auf **Kein**. Diese E-Mail enthält Anweisungen und Informationen zur Verwendung des Skype for Business Online Meeting Update Tool, insbesondere zum Entfernen von Informationen zu einer bestimmten Einwahlkonferenz, z. B. der Standardeinwahlnummer oder der Konferenz-ID.
    
    Finden Sie unter [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) oder[Zuweisen eines Drittanbieters für Audiokonferenzen](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    So kann diese E-Mail aussehen:
    
     !["Dial-In-Konferenzen" ist deaktiviert.](../images/4ebc8ae6-b516-452e-8d27-6177e145daba.png)
  
## Änderungen an den E-Mail-Nachrichten, die ihnen geschickt werden

Sie können die e-Mail-Nachricht ändern, die automatisch gesendet wird, um Ihre Benutzer, einschließlich der e-Mail-Adresse und den Anzeigenamen, der in den Kontaktinformationen  *aus*  enthalten ist. Standardmäßig werden in Office 365 der Absender die e-Mail-Nachrichten, jedoch können Sie die e-Mail-Adresse ändern und den Anzeigenamen mithilfe von Windows PowerShell und das Cmdlet "[Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ". Um die e-Mail-Adresse ändern, die die e-Mail zu versenden wird müssen die Benutzer Sie:
  
- Die E-Mail-Adresse in den Parameter  _SendEmailFromAddress_ eingeben.
    
- Den in der E-Mail angezeigten Namen in den Parameter  _SendEmailFromDisplayName_ eingeben.
    
- Den Parameter  _SendEmailOverride_ auf _True_ einstellen.
    
Sie können Änderungen an der E-Mail vornehmen, die an Benutzer gesendet wird. Zum Beispiel können Sie die E-Mail-Adresse, von der die E-Mail gesendet wird, und den in der E-Mail angezeigten Namen ändern. Führen Sie dazu Folgendes aus:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
> Wenn Sie die E-Mail-Adressinformationen ändern möchten, müssen Sie sicherstellen, dass die Richtlinien Ihrer Umgebung für eingehende E-Mails zulassen, dass E-Mails von der benutzerdefinierten Absenderadresse gesendet werden. > Wenn Sie die Kontaktinformationen des  *Absenders*  überschreiben, sollten Sie prüfen, dass die E-Mails korrekt an die Benutzer gesendet werden. Sie können dies mit einem Benutzer in Ihrem Unternehmen testen.
  
Das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) " können Sie andere Einstellungen für Ihre Organisation, einschließlich e-Mail verwalten.
  
## Wie gehen Sie vor, wenn Sie Benutzern keine E-Mails senden möchten?

Wenn Sie das Senden von E-Mails deaktivieren, werden keine E-Mails an die Benutzer gesendet, auch nicht, wenn ihnen eine Lizenz zugewiesen wird. Wenn dies der Fall ist, werden die Konferenz-ID, die Standardeinwahlnummer und, noch wichtiger, auch die PIN für Einwahlkonferenzen nicht an den Benutzer gesendet. Wenn dies geschieht, müssen Sie dem Benutzer eine separate E-Mail schreiben oder ihn anrufen, um ihm diese Mitteilung zu machen.
  
Standardmäßig werden E-Mails an Ihre Benutzer gesendet. Wenn Sie nicht möchten, dass Ihre Benutzer E-Mails für Einwahlkonferenzen erhalten, können Sie das Skype for Business Admin Center oder Windows PowerShell nutzen. 
  
### Verwenden des Skype for Business Admin Center

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Rufen Sie in der linken Navigationsleiste des **Skype for Business Admin Center** **Einwahlkonferenzen** > **Einstellungen von Microsoft Bridge** auf.
    
4. Aktivieren oder deaktivieren Sie auf der Seite **Einstellungen von Microsoft Bridge** die Option **Bei einer Änderung der PSTN-Einwahlkonfiguration automatisch E-Mails an Benutzer senden**.
    
5. Klicken Sie auf **Speichern**.
    
### Verwenden von Windows PowerShell

- Führen Sie das Folgende aus, um das Senden von E-Mails an alle Benutzer zu deaktivieren:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Die [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) können Sie andere Einstellungen für Ihre Organisation, einschließlich e-Mail verwalten.
  
## Was sollten Sie sonst über diese E-Mails wissen?

- Weitere Informationen zur Aktivierung und Deaktivierung automatisch verschickter E-Mails an Ihre Benutzer finden Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md).
    
- Gelegentlich verlieren Benutzer ihre Einwahlinformationen. Dann müssen Sie in der Lage sein, ihnen sämtliche Einwahlinformationen zu senden. Dazu können Sie im Skype for Business Admin Center unter den Einwahleigenschaften für einen Benutzer auf **Konferenzinformationen per E-Mail senden** klicken. Siehe[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-audio-conferencing-information.md). Diese Information enthält allerdings nicht die PIN für die Einwahlkonferenz.
    
    Hier ist ein Beispiel für eine E-Mail, die an die Benutzer gesendet wird:
    
     ![E-Mail zu einer Dial-In-Konferenz](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Standardmäßig werden in Office 365 der Absender die e-Mail-Nachrichten, jedoch können Sie die e-Mail-Adresse ändern und den Anzeigenamen mithilfe von Windows PowerShell und das Cmdlet " [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) ".
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zur Verwaltung von Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  
## Siehe auch
<a name="MT_Footer"> </a>

#### Weitere Ressourcen

[Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-audio-conferencing-settings-change.md)
  
[Senden einer E-Mail mit den Informationen zur Einwahlkonferenz an einen Benutzer](send-an-email-to-a-user-with-their-audio-conferencing-information.md)

