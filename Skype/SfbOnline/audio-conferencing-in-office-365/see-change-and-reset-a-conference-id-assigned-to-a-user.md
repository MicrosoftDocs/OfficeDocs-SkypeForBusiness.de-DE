---
title: Finden Sie unter ändern und eine Konferenz-ID, die einem Benutzer in Skype für Business Online zugewiesenen zurücksetzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Hier erfahren Sie, wie eine Konferenz-ID eines Benutzers in Skype für Business Online zugewiesen und was die Konferenz-IDs-Parameter werden soll. '
ms.openlocfilehash: 7996cc91bd9461f733f82da3eb01eeac7109604a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883415"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde

> [!Note]
> Informationen zu Benutzerkonferenz-IDs in Microsoft-Teams finden Sie unter [Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams  zugewiesen wurde](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Eine Konferenz-ID wird einem Skype for Business-Benutzer automatisch zugewiesen, wenn er in Office 365 für Audiokonferenzen eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet. Die Konferenz-ID zugewiesen wird in der besprechungseinladung gesendet, wenn die Besprechung geplant ist. Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.

Zwar eine Konferenz-ID wird automatisch erstellt und einem Benutzer zugewiesen werden, kann es jedoch Zeiten, wenn ein Benutzer nicht für diese verwenden möchten, und es eine bestimmte Anzahl festgelegt werden soll, oder wenn Ihre Benutzer können nicht merken oder ihre Konferenz-ID. verloren haben Sie können das **Skype for Business Administrationscenter**  und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.

Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält. Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an.

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.

4. Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.

    > [!TIP]
    > Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und audio Telefonnummern durch Klicken auf den Link **Konferenz Informationen per e-Mail senden** , nachdem Sie den Benutzer auf der Seite **Benutzer** auswählen enthält.

**Verwenden von Windows PowerShell**

Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen. Führen Sie dazu Folgendes aus:

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück.

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.

2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.

3. In der **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, klicken Sie im Aktionsbereich unter **Konferenz-ID**, klicken Sie auf **Zurücksetzen**.

4. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**. A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Verwenden von Windows PowerShell**

Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Zu diesem Zweck führen Sie Folgendes aus:

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nachdem eine neue Konferenz-ID erstellt wird oder eine zurückgesetzt wird, kann nicht die alte Konferenz-ID BSSID verwendet werden. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Die Benutzer können die Skype für Business Besprechung Migrationstool aktualisieren vorhandenen Besprechungen. Informationen zum Herunterladen, installieren und Ausführen des Tools finden Sie unter: [Meeting Aktualisierungstool für Skype für Unternehmen und Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype für Online Business Besprechung Migrationstool (64-Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)und [Skype für Online Business Besprechung Migration Tool (32-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

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

