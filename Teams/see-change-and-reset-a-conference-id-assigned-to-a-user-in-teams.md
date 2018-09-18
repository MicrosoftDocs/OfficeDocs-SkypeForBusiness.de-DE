---
title: Anzeigen, Ändern und Zurücksetzen einer Konferenzkennung, die einem Benutzer zugewiesen ist, in Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie, wie Sie einem Benutzer in Microsoft Teams eine Konferenzkennung zuweisen und welche Parameter Sie für die Konferenzkennung verwenden sollten. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892033"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Anzeigen und Zurücksetzen einer Konferenzkennung, die einem Benutzer zugewiesen ist, in Microsoft Teams

Eine Konferenzkennung wird Microsoft Teams-Benutzern automatisch zugewiesen, wenn sie für Audiokonferenzen in Office 365 eingerichtet werden und Microsoft als Audiokonferenzanbieter verwenden. Die zugewiesene Konferenzkennung wird in der Besprechungseinladung gesendet, wenn die Besprechung geplant wird. Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen. 
  
Obwohl Konferenzkennungen automatisch generiert und Benutzern zugewiesen werden, kann es vorkommen, dass Benutzer diese Nummer nicht verwenden möchten und Sie daher eine bestimmte Nummer festlegen müssen. Es ist auch möglich, dass Benutzer ihre Konferenzkennung vergessen oder verloren haben. Sie können die Konferenzkennung im Microsoft Teams Admin Center oder mit Windows PowerShell anzeigen, ändern und zurücksetzen.
  
Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält. Weitere Informationen zum Zurücksetzen einer Konferenz-Organisator-PIN, [finden Sie hier](reset-a-conference-id-for-a-user-in-teams.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenzkennung an

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Suchen Sie unter **Audiokonferenz** in **Konferenz-ID**.

    > [!TIP]
    > Sie können dem Benutzer eine E-Mail mit sämtlichen Konferenzinformationen senden, unter anderem mit der Konferenzkennung und den Audiotelefonnummern. Klicken Sie dazu auf den Link **Send conference info in email** (Konferenzinformationen per E-Mail senden).
  
**Verwenden von Windows PowerShell**

Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenzkennung zurück

Sie können eine Konferenzkennung für einen Benutzer zurücksetzen, beispielsweise wenn der Benutzer sie vergessen hat.
  
![teams-logo-30x30.png](media/teams-logo-30x30.png) **Verwendung der Microsoft-Teams und Skype for Business Admin Center:**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.

4. Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**. Daraufhin wird automatisch eine neue Konferenzkennung erstellt und per E-Mail an den Benutzer gesendet.
  
**Verwenden von Windows PowerShell**

Weitere Informationen finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Wenn eine neue Konferenzkennung erstellt oder eine Konferenzkennung zurückgesetzt wurde, können Anrufer die alte Konferenzkennung nicht mehr verwenden. Benachrichtigen Sie die Benutzer, dass sie vorhandene Besprechungseinladungen neu planen müssen, um sicherzustellen, dass die neue Konferenzkennung zu den Einladungen hinzugefügt wird. 
  
    
- Die Länge der Konferenzkennung muss der Ziffernanzahl entsprechen, die in der Audiokonferenzbrücke festgelegt ist. Konferenzkennungen dürfen keine Buchstaben und Sonderzeichen, sondern nur Zahlen enthalten.
    
- Die Konferenzkennung für alle Audiokonferenzbenutzer besteht standardmäßig aus sieben Ziffern. Die Anzahl der Ziffern kann nicht geändert werden.
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

