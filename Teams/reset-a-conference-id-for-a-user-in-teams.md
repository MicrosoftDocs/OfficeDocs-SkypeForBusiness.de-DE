---
title: Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams
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
description: 'Hier finden Sie die Schritte zum Zurücksetzen der Konferenzkennung eines Benutzers in Microsoft Teams sowie Links zu Tools, mit denen Sie Besprechungen aktualisieren und migrieren können. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887852"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams

Eine dynamische Konferenzkennung befindet sich unten in Besprechungseinladungen zusammen mit den Dial-in-Telefonnummern, über die sich Anrufer in die Besprechung einwählen können. Wenn Benutzer diese Telefonnummer wählen, werden sie von der automatischen Telefonzentrale aufgefordert, diese Konferenzkennung einzugeben, damit sie an der Besprechung teilnehmen können.
  
> [!NOTE]
> Wenn Microsoft Ihr Konferenzanbieter ist, sind die Konferenzkennungen der Benutzer standardmäßig auf „Dynamic Only“ (Nur dynamisch) festgelegt. Leider gibt es keine Möglichkeit, die Konferenzkennung in eine statische Kennung zu ändern, da dies zurzeit nicht unterstützt wird. Konferenzkennungen werden nur für Microsoft Teams-Benutzer, die für Audiokonferenzen aktiviert sind, automatisch festgelegt. 


## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenzkennung für einen Benutzer

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie unter **Audiokonferenz** auf **Konferenz-ID zurücksetzen**.

2. Klicken Sie im Fenster **Konferenz-ID zurücksetzen** auf **Zurücksetzen**. Daraufhin wird automatisch eine neue Konferenzkennung erstellt und per E-Mail an den Benutzer gesendet. E-Mails werden standardmäßig an Benutzer gesendet. Dies kann jedoch deaktiviert werden.   

    
> [!NOTE]
> Wenn Sie die Konferenzkennung zurückgesetzt haben, wird eine E-Mail mit der neuen Konferenzkennung an den Benutzer gesendet. Diese E-Mail wird an die primäre E-Mail-Adresse gesendet, das heißt in vielen Fällen an das Office 365-Postfach des Benutzers. Die E-Mail enthält die neue Konferenzkennung, die standardmäßigen Dial-in-Telefonnummern und Anweisungen zum Aktualisieren vorhandener Besprechungen. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können dem Benutzer eine E-Mail mit sämtlichen Konferenzinformationen senden, unter anderem mit der Konferenzkennung und den Dial-in-Telefonnummern. Klicken Sie dazu im Abschnitt **Audiokonferenz** für den Benutzer auf **Send conference info in email** (Konferenzinformationen per E-Mail senden). Die PIN wird nicht gesendet.
    
- Eine Konferenzkennung umfasst sieben Ziffern. Die Länge kann nicht geändert werden.
    
- Nach dem Zurücksetzen wird die neue Konferenzkennung unter **Konferenz-ID** aufgeführt.
    
- Wenn eine neue Konferenzkennung erstellt wurde, können Anrufer die alte Konferenzkennung nicht mehr verwenden. Benachrichtigen Sie die Benutzer, dass sie vorhandene Besprechungseinladungen neu planen müssen, um sicherzustellen, dass die neue Konferenzkennung zu den Einladungen hinzugefügt wird. 

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)
