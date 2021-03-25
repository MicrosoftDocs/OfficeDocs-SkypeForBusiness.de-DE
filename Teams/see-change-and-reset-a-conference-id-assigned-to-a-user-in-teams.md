---
title: Sehen, Ändern und Zurücksetzen der Konferenz-ID eines Benutzers
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie einem Benutzer in Microsoft Teams eine Konferenz-ID zuweisen und welche Parameter die Konferenz-IDs sein sollten.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117208"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Anzeigen und Zurücksetzen einer Konferenz-ID, die einem Benutzer in Microsoft Teams zugewiesen wurde

Eine Konferenz-ID wird einem Microsoft Teams-Benutzer automatisch zugewiesen, wenn er für Audiokonferenzen in Microsoft 365 oder Office 365 eingerichtet ist und Microsoft als Audiokonferenzanbieter verwendet. Die zugewiesene Konferenz-ID wird in der Besprechungs-Einladung gesendet, wenn die Besprechung geplant ist. Jedem Meeting, das ein Benutzer plant wird eine eindeutige Konferenz-ID zugewiesen. 
  
Obwohl eine Konferenz-ID automatisch erstellt und einem Benutzer zugewiesen wird, kann es zu Zeiten kommen, in denen ein Benutzer diese nicht verwenden möchte und sie auf eine bestimmte Nummer festlegen möchte oder wenn die Benutzer ihre Konferenz-ID nicht mehr merken oder verloren haben. Sie können das Microsoft Teams Admin Center oder Windows PowerShell zum Anzeigen, Ändern und Zurücksetzen der Konferenz-ID verwenden.
  
Eine E-Mail wird mit der Konferenz-ID und den Standard-Audiokonferenz-Telefonnummern an den Benutzer gesendet. Wenn Sie die Konferenz-ID zurücksetzen, wird eine andere E-Mail gesendet, die die Konferenz-ID, jedoch keine PIN enthält. Weitere Informationen zum Zurücksetzen der PIN eines Konferenzorganisators finden Sie unter Zurücksetzen einer Konferenz-ID für einen Benutzer [in Microsoft Teams.](reset-a-conference-id-for-a-user-in-teams.md) 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Anzeigen und Zurücksetzen der Konferenz-IDs

### <a name="to-view-the-conference-id"></a>So zeigen Sie die Konferenz-ID an

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten.**

3. Suchen **Sie unter Audiokonferenzen** unter **Konferenz-ID**.

    > [!TIP]
    > Sie können alle Konferenzinformationen in einer E-Mail, die konferenz-ID und Audiotelefonnummern enthält, an den Benutzer senden, indem Sie auf den Link Konferenzinformationen **in** E-Mail senden klicken.
  
**Verwenden von Windows PowerShell**

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)
    
  
### <a name="to-reset-the-conference-id"></a>So setzen Sie die Konferenz-ID zurück

Sie können eine Konferenz-ID für einen Benutzer zurücksetzen, wenn er diese beispielsweise vergessen hat.
  
![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten.**

3. Klicken **Sie unter Audiokonferenzen** auf **Konferenz-ID zurücksetzen.**

4. Klicken Sie **im Fenster Konferenz-ID** zurücksetzen auf **Zurücksetzen.** Eine Konferenz-ID wird automatisch erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet.
  
**Verwenden von Windows PowerShell**

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)


## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

   > [!IMPORTANT]
   >  Nachdem eine neue Konferenz-ID erstellt oder zurückgesetzt wurde, kann die alte Konferenz-ID von Anrufern nicht mehr verwendet werden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. 
  
    
- Die Konferenz-ID muss die auf der Audiokonferenzbrücke festgelegte Länge in Ziffern erfüllen. Sie können keine alphabetischen oder Sonderzeichen in Konferenz-IDs verwenden. es können nur Zahlen verwendet werden.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzelnen Verwaltungspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)