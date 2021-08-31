---
title: Sehen, ändern und zurücksetzen Sie eine Konferenz-ID, die einem Benutzer in Ihrer Online-Skype for Business wurde
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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie einem Benutzer in Skype for Business Online Konferenzkennungen zuweisen und welche Parameter die Konferenzkennungen haben sollten. '
ms.openlocfilehash: a400536050ea22d4f841e3b401e30c3c14729093
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728004"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Informationen zu Konferenz-IDs von Benutzern in Microsoft Teams finden Sie unter Anzeigen und Zurücksetzen einer [Konferenz-ID,](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)die einem Benutzer in einem Microsoft Teams.

Wenn ein Skype for Business-Benutzer für Audiokonferenzen in Microsoft 365 oder Office 365 eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet wird, wird einem Skype for Business-Benutzer automatisch eine Konferenz-ID zugewiesen. Die zugewiesene Konferenz-ID wird in der Besprechungs-Einladung gesendet, wenn die Besprechung geplant ist. Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.

Konferenzkennungen werden zwar automatisch erstellt und Benutzern zugewiesen, es kann aber auch sein, dass Benutzer diese Nummer nicht verwenden möchten und Sie sie auf eine bestimmte Nummer festlegen möchten oder die Benutzer sich nicht mehr erinnern oder ihre Konferenz-ID vergessen haben. Sie können das **Skype for Business Administrationscenter**  und Windows PowerShell verwenden, um die Konferenz-ID für solche Benutzer anzuzeigen, zu ändern oder zurückzusetzen.

Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält. Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an

![Ein Symbol mit dem Skype for Business Logo.](../images/sfb-logo-30x30.png) **Verwenden des Skype for Business Admin Centers**

Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.

4. Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.

    > [!TIP]
    > Sie können dem Benutzer alle Konferenzinformationen per E-Mail senden, die konferenz-ID und  Audiotelefonnummern enthält. Klicken Sie dazu  auf den Link Konferenzinformationen per E-Mail senden, nachdem Sie den Benutzer auf der Seite Benutzer ausgewählt haben.

**Verwenden von Windows PowerShell**

Sie können Windows PowerShell verwenden, um die Konferenz-ID für einen Benutzer anzuzeigen. Führen Sie dazu dies aus:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Weitere Informationen zum Cmdlet finden Sie unter [Get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)


### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.

![Ein Symbol mit dem Skype for Business Logo.](../images/sfb-logo-30x30.png) **Verwenden des Skype for Business Admin Centers**

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.

2. Wechseln Sie zum Admin Center, > **Skype for Business.**

3. Klicken Sie **Skype for Business Admin Center** Benutzer von >  **Audiokonferenzen** im Aktionsbereich unter  >   **Konferenz-ID** auf **Zurücksetzen**.

4. Klicken Sie **im Fenster Konferenz-ID zurücksetzen?** auf **Ja.** Es wird automatisch eine Konferenz-ID erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.

**Verwenden von Windows PowerShell**

Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Führen Sie dazu dies aus:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nachdem eine neue Konferenz-ID erstellt oder zurückgesetzt wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Benutzer können das Skype for Business Meeting Migration Tool verwenden, um ihre vorhandenen Besprechungen zu aktualisieren. Informationen zum Herunterladen, Installieren und Ausführen des Tools finden Sie unter: Meeting Update Tool für [Skype for Business und Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4) [Skype for Business Online, Meeting Migration Tool (64-Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)und [Skype for Business Online, Meeting Migration Tool (32-Bit)](https://www.microsoft.com/download/details.aspx?id=54079).

- Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).

- Die Konferenz-ID muss die Länge in Ziffern aufweisen, die auf der Audiokonferenzbrücke festgelegt ist. Konferenz-IDs dürfen keine Buchstaben oder Sonderzeichen enthalten. nur Zahlen verwendet werden können.

- Die Konferenz-ID für alle Benutzer von Audiokonferenzen ist standardmäßig 9 Ziffern und kann nicht geändert werden.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Wenn es um Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen oder was nicht. Mit Windows PowerShell können Sie Microsoft 365, Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center gegenüber Geschwindigkeit, Einfachheit und Produktivität viele Vorteile, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
