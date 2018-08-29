---
title: Anzeigen, Ändern und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie einem Benutzer in Skype for Business eine Konferenz-ID zuweisen und wie die Parameter der Konferenz-ID lauten sollten. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252308"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde

> [!Note]
> Informationen zu Benutzerkonferenz-IDs in Microsoft-Teams finden Sie unter [Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams  zugewiesen wurde](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Eine Konferenz-ID wird einem Skype for Business-Benutzer automatisch zugewiesen, wenn er in Office 365 für Audiokonferenzen eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet. Die zugewiesene Konferenz-ID wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant wird. Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.

Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es jedoch geschehen, dass ein Benutzer diese nicht verwenden und sie durch eine bestimmte Zahl ersetzen möchte, oder Ihr Benutzer kann sich seine Konferenz-ID nicht merken oder hat sie verloren. Sie können das **Skype for Business Administrationscenter**  und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.

Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält. Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>Um die Konferenz-ID anzuzeigen

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admincenters**

Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.

4. Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.

    > [!TIP]
    > Sie können alle Konferenzinformationen in einer E-Mail mit der Konferenz-ID und den Audio-Telefonnummern an den Benutzer senden, indem Sie nach Auswahl des Benutzers auf den Link **  Konferenzinformationen per E-Mail senden** klicken, nachdem Sie den Benutzer auf der Seite ** Benutzer** ausgewählt haben.

**Verwenden von Windows PowerShell**

Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen. Führen Sie dazu Folgendes aus:

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Um die Konferenz-ID zurückzusetzen

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Nutzung des Skype for Business Admincenters**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**auf **Zurücksetzen**.

4. Im Fenster **Konferenz-ID zurücksetzen?** klicken Sie auf **Ja**. Eine Konferenz-ID wird automatisch erstellt und eine E-Mail mit der neuen Konferenz-ID wird an den Benutzer gesendet.

**Verwenden von Windows PowerShell**

Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Zu diesem Zweck führen Sie Folgendes aus:

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nachdem eine neue Konferenz-ID erstellt oder eine zurückgesetzt wurde, kann die alte Konferenz-ID von den Anrufern nicht mehr verwendet werden. Informieren Sie Benutzer von Plänen deren vorhandene Besprechungs-Einladungen neu zu planen, um sicher zu stellen, dass die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Benutzer können das Skype for Business Meeting-Migrationstool für ihre vorhandenen Meetings aktualisieren. Informationen zum Herunterladen, Installieren und Ausführen des Skype for Business Meeting-Updatetools finden Sie unter: [Meeting-Updatetool für Skype for Business und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting-Migrationstool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), und  [Skype for Business Online, Meeting-Migrationstool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Sehen Sie [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) um mehr über cmdlet zu erfahren.

- Die Konferenz-ID muss die in der Audiokonferenz-Brücke festgelegte Länge an Ziffern aufweisen. Konferenz-IDs dürfen keine Buchstaben und Sonderzeichen, sondern nur Zahlen enthalten.

- Die Länge der Konferenz-ID für Benutzer von Audiokonferenzen ist standardmäßig auf 7 Ziffern festgelegt. Die Zahl der Stellen kann nicht geändert werden.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:

  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

