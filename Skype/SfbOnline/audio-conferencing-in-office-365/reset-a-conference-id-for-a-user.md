---
title: Eine Konferenz-ID für einen Benutzer in Skype für Business Online zurücksetzen
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
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier erfahren Sie die Schritte ein Benutzers Zurücksetzen des meeting-Konferenz-ID in Skype für Business Online sowie Get links auf meeting Update und Migration Tools. '
ms.openlocfilehash: d569dfb015db5cea79c57233ba455adfd90a3182
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887545"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Eine Konferenz-ID für einen Benutzer in Skype für Business Online zurücksetzen

> [!NOTE]
> Informationen zum Zurücksetzen des Konferenz-ID in Microsoft Teams, finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Eine dynamische Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können. Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.
  
> [!NOTE]
> Wenn Ihr Konferenzanbieter Microsoft ist, sind die Konferenz-IDs Ihrer Benutzer standardmäßig auf "Nur dynamisch" eingestellt. Leider gibt es keine Möglichkeit, es im Skype for Business Admin Center zu ändern oder Windows PowerShell zu verwenden, damit es statisch wird, da dies nun nicht mehr unterstützt wird. Konferenz-IDs werden automatisch nur für Skype for Business-Benutzer festgelegt, die für Audiokonferenzen aktiviert sind. 

## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenz-ID für einen Benutzer
   
1. Klicken Sie in der **Skype für Business Administrationscenter**auf **Audiokonferenzen** > **Benutzer**, wählen einen Benutzer aus, und klicken Sie dann im Aktionsbereich unter **Konferenz-ID** **Zurücksetzen**.
    
2. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.
    
> [!NOTE]
> Nach dem Zurücksetzen der Konferenz-ID wird die neue Konferenz-ID per E-Mail an den Benutzer geschickt. Diese E-Mail wird an die Haupt-E-Mail-Adresse geschickt. Dabei handelt es sich oftmals um das Office 365-Postfach. Die E-Mail umfasst die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen, wie bestehende Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisiert werden können. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern enthält, indem Sie für den Benutzer im Aktionsbereich auf **Konferenz Informationen per e-Mail senden** . Die PIN wird nicht gesendet.
    
- Enthält eine Konferenz-ID 7 Ziffern, und deren Länge in der Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell können nicht geändert werden.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Wenn Sie den Benutzer auf der Seite **Benutzer** auswählen, kann die Konferenz-ID für einen Benutzer für Audiokonferenzen am unteren Rand der Aktionsbereich unter **Audiokonferenzen** angezeigt werden.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. Die Benutzer können Skype für Business Besprechung Tool um vorhandenen Besprechungen zu aktualisieren. Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, Meeting Migration Tool (64 Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, Meeting Migration Tool (32 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See Also

[Die Audiokonferenz PIN zurücksetzen](reset-the-audio-conferencing-pin.md)
