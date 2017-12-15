---
title: "Anzeigen, Bearbeiten und Zurücksetzen einer Konferenz-ID, die einem Nutzer zugewiesen wurde"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# Anzeigen, Bearbeiten und Zurücksetzen einer Konferenz-ID, die einem Nutzer zugewiesen wurde

Wenn Sie für einen Nutzer Einwahlkonferenzen einrichten und Microsoft der Einwahlkonferenzen-Anbieter ist, wird dem Nutzer automatisch eine Konferenz-ID zugewiesen. Die zugewiesene Konferenz-ID kann eine feste oder dynamische, nach dem Zufallsprinzip generierte Nummer sein und wird in der Einladung zur geplanten Besprechung angegeben. 
  
Feste Nummern werden verwendet, wenn sich die Mitarbeiter Ihres Unternehmens keine Zufallszahlenkombinationen merken möchten und es bevorzugen, eine bestimmte bzw. leicht zu merkende Nummer auszuwählen. Bei der Verwendung von dynamischen Konferenz-IDs wird für jede, vom Nutzer geplante Besprechung, eine eindeutige Konferenz-ID zugewiesen. Wenn Sie dynamische Konferenz-IDs zuweisen möchten, klicken Sie [Verwenden von Audiokonferenzanbieter dynamische IDs in Ihrer Organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Obwohl feste Konferenz-IDs automatisch generiert und dem Nutzer zugewiesen werden, kann es jedoch vorkommen, dass der Nutzer aus einem bestimmten Grund diese Nummer nicht verwenden möchte und Sie daher die Nummer ändern müssen. Wenn der Nutzer eine leichter zu merkende Konferenz-ID möchte oder seine ID vergessen hat, können Sie sie im Skype for Business Admin Center und in der Windows PowerShell anzeigen, ändern und zurücksetzen.
  
Der Nutzer erhält eine E-Mail mit der Konferenz-ID und den Standardtelefonnummern für Einwahlkonferenzen. Wenn Sie die Konferenz-ID zurücksetzen, erhält der Nutzer eine andere E-Mail, die zwar die Konferenz-ID, aber keine PIN enthält. 
  
## 

### So zeigen Sie die Konferenz-ID an

Sie können die Konferenz-ID des Nutzers anzeigen und ihm zusenden.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wählen Sie im **Skype for Business Admin Center**unter **Einwahlkonferenzen** in der Benutzerliste den Benutzer aus, der eine Konferenz-ID benötigt.
    
4. Sehen Sie im Bereich „Aktion" unter **Konferenz-ID** nach.
    
    > [!TIP]
    > Sie können dem Benutzer eine E-Mail mit sämtlichen Informationen zur Konferenz schicken, u. a. mit der Konferenz-ID und den Einwahlnummern. Klicken Sie dazu auf den Link **Konferenzinformationen per E-Mail senden**, nachdem Sie den Benutzer auf der Seite **Benutzer mit eingehenden Verbindungen** ausgewählt haben.
  
    Sie können die Konferenz-ID eines Benutzers über die Windows PowerShell anzeigen, indem Sie Folgendes ausführen:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Weitere Informationen zum Cmdlet finden Sie unter [Get-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617693 ).
    
### So weisen Sie die Konferenz-ID zu oder ändern sie

Wenn der Nutzer eine leichter zu merkende Konferenz-ID wünscht, können Sie die Konferenz-ID ändern und dem Nutzer zuweisen.
  
> [!NOTE]
> Das Skype for Business Admin Center kann nicht zum Bearbeiten von Konferenz-IDs verwendet werden, die automatisch erstellt wurden. Verwenden Sie stattdessen die Windows PowerShell zum Bearbeiten oder Ändern einer von Ihnen festgelegten Konferenz-ID. 
  
- Führen Sie zum Bearbeiten oder Ändern der Konferenz-ID für einen Benutzer Folgendes aus:
    
    > [!TIP]
    >  Eine Konferenz-ID muss 7 Ziffern umfassen. Sie kann nicht im Skype for Business Admin Center oder mit der Windows PowerShell geändert werden.
  
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

### So setzen Sie die Konferenz-ID zurück

Sie können die Konferenz-ID des Nutzers zurücksetzen, wenn dieser z. B. sein Konferenz-ID vergessen hat.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Klicken Sie im **Skype for Business Admin Center**auf **Einwahlkonferenzen** und dann im Bereich „Aktion" unter **Konferenz-ID** auf **Zurücksetzen**.
    
4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen?** auf **Ja**. Daraufhin wird automatisch eine neue Konferenz-ID generiert und per E-Mail an den Benutzer geschickt.
    
    Sie können die Konferenz-ID eines Benutzers mithilfe der Windows PowerShell zurücksetzen. Führen Sie dazu Folgendes aus:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## Was sollten Sie noch wissen?

-     > [!IMPORTANT]
    >  Nachdem eine neue Konferenz-ID erstellt oder die ID zurückgesetzt wurde, können die Anrufer die alte Konferenz-ID nicht mehr nutzen. Sie sollten Nutzer benachrichtigen, damit sie ihre angesetzten Besprechungseinladungen neu planen, um sicherzustellen, dass die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Nutzer können angesetzte Besprechungen mithilfe des Skype for Business Meeting Migration Tool aktualisieren. Informationen zum Download, zur Installation und zum Ausführen des Tools finden Sie unter:> [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)> [Skype for Business Online, Meeting Migration Tool (64 Bit)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype for Business Online, Meeting Migration Tool (32 Bit)](http://go.microsoft.com/fwlink/?LinkID=626046)
  
- Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](http://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Die Konferenz-ID muss die Länge (in Ziffern) aufweisen, die auf der Einwahlkonferenzbrücke festgelegt wurde. Konferenz-IDs dürfen keine Buchstaben und Sonderzeichen, sondern nur Zahlen enthalten.
    
- Die Länge der Konferenz-ID für Benutzer von Einwahlkonferenzen ist standardmäßig auf 7 Ziffern festgelegt. Die Zahl der Stellen kann nicht geändert werden.
    
- Wenn Microsoft als Anbieter von Einwahlkonferenzen auf einen externen Anbieter von Audiokonferenzen geändert wird oder der Anbieter von Einwahlkonferenzen auf **Kein** festgelegt wird, funktioniert die Konferenz-ID nicht mehr. Weitere Informationen finden Sie unter[Zuweisen eines Drittanbieters für Audiokonferenzen](assign-a-third-party-as-the-audio-conferencing-provider.md) oder[Ändern des Anbieters von Einwahlkonferenzen für Benutzer](https://support.office.com/article/9b74f053-4d23-485f-9232-3d30370a8c6e).
    
## Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Sechs Gründe für die Verwendung von Windows PowerShell zum Verwalten von Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Siehe auch

#### Weitere Ressourcen

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

