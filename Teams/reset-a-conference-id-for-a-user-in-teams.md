---
title: Zurücksetzen einer Konferenz-ID für einen Benutzer in Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Hier erfahren Sie die Schritte zum eines Benutzers Zurücksetzen des meeting-Konferenz-ID in der Microsoft-Teams sowie Get links auf meeting Update und Migration Tools. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887852"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Zurücksetzen einer Konferenz-ID für einen Benutzer in Microsoft-Teams

Eine dynamische Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können. Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.
  
> [!NOTE]
> Wenn Ihr Konferenzanbieter Microsoft ist, sind die Konferenz-IDs Ihrer Benutzer standardmäßig auf "Nur dynamisch" eingestellt. Leider besteht keine Möglichkeit, ändern es statisch sein, wie dies nun ist nicht unterstützt. Konferenz-IDs werden für Benutzer mit Microsoft-Teams für Audiokonferenzen nur automatisch festgelegt. 


## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenz-ID für einen Benutzer

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenzen** auf **Konferenz-ID zurückgesetzt**.

2. Klicken Sie auf **Zurücksetzen**, klicken Sie im Fenster **Konferenz-ID zurückgesetzt** . A conference ID will be automatically created and an email sent to the user with the new conference ID. Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.   

    
> [!NOTE]
> Nachdem Sie die Konferenz-ID zurücksetzen, wird eine e-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Diese e-Mail wird an die primäre e-Mail-Adresse in vielen Fällen ihre Office 365-Postfach gesendet. Die e-Mail enthält die neue Konferenz-ID sowie die Zugriffsnummer für Einwahl Telefonnummern für Standard und Informationen zum Aktualisieren vorhandener Besprechungen. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern durch Klicken auf **Konferenz Informationen in e-Mail-Nachricht senden** , für den Benutzer im Abschnitt **Audiokonferenzen** enthält. Die PIN wird nicht gesendet.
    
- Enthält eine Konferenz-ID 7 Ziffern, und deren Länge kann nicht geändert werden.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [Referenz zu Microsoft-Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) für Weitere Informationen.
    
## <a name="related-topics"></a>Verwandte Themen

[Die Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin-in-teams.md)
