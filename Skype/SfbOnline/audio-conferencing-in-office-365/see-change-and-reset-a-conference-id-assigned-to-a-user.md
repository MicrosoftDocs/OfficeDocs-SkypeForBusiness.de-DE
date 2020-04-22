---
title: Anzeigen, ändern und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen ist
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie einem Benutzer in Skype for Business Online eine Konferenz-ID zuweisen und was die Konferenz-IDs-Parameter sein sollten. '
ms.openlocfilehash: b5ed8bb8ec32277e0bebca43338ae233aa6d38f6
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776840"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Skype for Business Online zugewiesen wurde

> [!Note]
> Informationen zu Benutzer Konferenz-IDs in Microsoft Teams finden Sie unter [anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams zugewiesen](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)ist.

A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

Sie können ihre Konferenz-ID anzeigen und an Benutzer senden.

1. Mit Ihrem Firmen-oder Schulkonto anmelden

2. Wechseln Sie zum Admin Center > **Skype for Business**.

3. Im **Skype für Business Administrationscenter**> **Audiokonferenzen** > **Benutzer**, wählen Sie den Benutzer aus, der die Konferenz-ID benötigt.

4. Sehen Sie auf der Aktions-Seie unter **Konferenz-ID**.

    > [!TIP]
    > Sie können alle Konferenz Informationen an den Benutzer in einer e-Mail senden, die die Konferenz-ID und die audiorufnummern enthält, indem Sie auf den Link **Konferenz Informationen per e-Mail senden** klicken, nachdem Sie den Benutzer auf der Seite **Benutzer** ausgewählt haben.

**Verwenden von Windows PowerShell**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Weitere Informationen zum Cmdlet finden Sie unter [Get-csonlinedialinconferencinguser zeigt](https://go.microsoft.com/fwlink/?LinkId=617693 ) .


### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1. Mit Ihrem Firmen-oder Schulkonto anmelden

2. Wechseln Sie zum Admin Center > **Skype for Business**.

3. Klicken Sie **im Skype for Business Admin Center**> **-Audiokonferenz** > -**Benutzer**im Bereich "Aktion" unter **Konferenz-ID**auf **Zurücksetzen**.

4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Ja**. Eine Konferenz-ID wird automatisch erstellt und eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.

**Verwenden von Windows PowerShell**

Sie können die Konferenz-ID für einen Benutzer mithilfe der Windows PowerShell zurücksetzen. Führen Sie dazu die folgenden Aktionen aus:

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nach dem Erstellen einer neuen Konferenz-ID oder eines Zurücksetzens wird die alte Konferenz-ID nicht von den Anrufern verwendet. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Benutzer können das Skype for Business-Besprechungs Migrations Tool verwenden, um Ihre vorhandenen Besprechungen zu aktualisieren. Informationen zum herunterladen, installieren und Ausführen des Tools finden Sie unter: [Update Tool für Besprechungen für Skype for Business und lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)und [Skype for Business Online, Meeting Migration Tool (32-Bit)](https://www.microsoft.com/download/details.aspx?id=54079).

- Weitere Informationen zum Cmdlet finden Sie unter [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- Die Konferenz-ID muss die für die Audiokonferenz-Brücke eingestellte Länge in Ziffern erfüllen. In Konferenz-IDs können keine alphabetischen oder Sonderzeichen verwendet werden. Es können nur Zahlen verwendet werden.

- Die Konferenz-ID für alle Audiokonferenz-Benutzer ist standardmäßig 7 Ziffern, und die Anzahl der Ziffern kann nicht geändert werden.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

