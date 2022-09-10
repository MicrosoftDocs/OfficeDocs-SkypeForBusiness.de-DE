---
title: Anzeigen, Ändern und Zurücksetzen der Konferenz-ID eines Benutzers
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einem Benutzer in Microsoft Teams eine Konferenz-ID zuweisen und wie die Konferenz-IDs-Parameter sein sollten.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642116"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams zugewiesen ist

Eine Konferenz-ID wird einem Microsoft Teams-Benutzer automatisch zugewiesen, wenn er für Audiokonferenzen in Microsoft 365 oder Office 365 eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet. Die zugewiesene Konferenz-ID wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant ist. Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen.
  
Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es vorkommen, dass ein Benutzer diese nicht verwenden möchte und Sie diese auf eine bestimmte Zahl festlegen möchten oder wenn sich Ihre Benutzer ihre Konferenz-ID nicht merken können oder verloren haben. Sie können das Microsoft Teams Admin Center oder Windows PowerShell verwenden, um ihre Konferenz-ID anzuzeigen, zu ändern und zurückzusetzen.
  
Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält. Weitere Informationen zum [Zurücksetzen der PIN eines Konferenzorganisators finden Sie unter Zurücksetzen einer Konferenz-ID für einen Benutzer in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) .

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Anzeigen der Konferenz-ID im Microsoft Teams Admin Center

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer**", und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **"Bearbeiten"**.

3. Suchen Sie unter **"Audiokonferenzen**" unter **"Konferenz-ID"**.

    > [!TIP]
    > Sie können alle Konferenzinformationen in einer E-Mail an den Benutzer senden, die die Konferenz-ID und Audiotelefonnummern enthält, indem Sie auf den Link " **Konferenzinformationen per E-Mail senden** " klicken.
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Anzeigen der Konferenz-ID mithilfe von Windows PowerShell

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .

### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Zurücksetzen der Konferenz-ID mithilfe des Microsoft Teams Admin Centers

1. Klicken Sie im linken Navigationsbereich auf **"Benutzer**", und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **"Bearbeiten"**.

3. Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurücksetzen**.

4. Klicken Sie im Fenster " **Konferenz-ID zurücksetzen** " auf **"Zurücksetzen"**. Eine Konferenz-ID wird automatisch erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Zurücksetzen der Konferenz-ID mithilfe von Windows PowerShell

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

> [!IMPORTANT]
> Nachdem eine neue Konferenz-ID erstellt oder eine zurückgesetzt wurde, kann die alte Konferenz-ID von Anrufern nicht mehr verwendet werden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird.

- Die Konferenz-ID muss die Länge in Ziffern erfüllen, die auf der Audiokonferenzbrücke festgelegt sind. Sie können in Konferenz-IDs keine buchstaben- oder Sonderzeichen verwenden. es können nur Zahlen verwendet werden.

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben erledigen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Methoden zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen von Audiokonferenzen in Microsoft 365 für Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
