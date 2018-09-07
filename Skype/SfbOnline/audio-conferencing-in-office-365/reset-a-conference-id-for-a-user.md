---
title: Eine Konferenz-ID für einen Benutzer in Skype for Business Online zurücksetzen
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Lernen Sie die Schritte zum Zurücksetzen der Konferenz-ID eines Benutzers kennen und erhalten Sie Links zu den Tools für die Aktualisierung und Migration von Besprechungen. '
ms.openlocfilehash: 34e165d92f4dc63eea8fc31c05612b6e20b64025
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850061"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Eine Konferenz-ID für einen Benutzer in Skype for Business Online zurücksetzen

> [!NOTE]
> Informationen zum Zurücksetzen des Konferenz-ID in Microsoft Teams, finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Eine dynamische Konferenz-ID befindet sich am Ende der Besprechungseinladungen zusammen mit den Einwahlnummern, die von den Anrufern zum Einwählen in eine Besprechung verwendet werden können. Wenn der Benutzer diese Telefonnummer wählt, wird er von der automatischen Telefonzentrale aufgefordert, diese Konferenz-ID einzugeben, damit er an der Besprechung teilnehmen kann.
  
> [!NOTE]
> Wenn Ihr Konferenzanbieter Microsoft ist, sind die Konferenz-IDs Ihrer Benutzer standardmäßig auf "Nur dynamisch" eingestellt. Leider gibt es keine Möglichkeit, es im Skype for Business Admin Center zu ändern oder Windows PowerShell zu verwenden, damit es statisch wird, da dies nun nicht mehr unterstützt wird. Konferenz-IDs werden automatisch nur für Skype for Business-Benutzer festgelegt, die für Audiokonferenzen aktiviert sind. 

## <a name="resetting-the-conference-id-for-a-user"></a>Konferenz-ID der Besprechung für einen Benutzer zurücksetzen
   
1. Klicken Sie in der **Skype for Business Admin Center** auf **Audiokonferenzen** > **Benutzer**, wählen Sie einen Benutzer aus und klicken Sie dann im Aktionsbereich unter **Konferenz-ID** auf **Reset**.
    
2. Im Fenster **Konferenz-ID zurücksetzen?** klicken Sie auf **Ja**. Es wird automatisch eine Konferenz-ID erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Standardmäßig werden E-Mails an Benutzer gesendet, diese können jedoch deaktiviert werden.
    
> [!NOTE]
> Nach dem Zurücksetzen der Konferenz-ID wird die neue Konferenz-ID per E-Mail an den Benutzer geschickt. Diese E-Mail wird an die Haupt-E-Mail-Adresse geschickt. Dabei handelt es sich oftmals um das Office 365-Postfach. Die E-Mail umfasst die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen, wie bestehende Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisiert werden können. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können alle Konferenzinformationen an den Benutzer in einer E-Mail senden, die die Konferenz-ID und Einwahlnummern enthält, indem Sie im Aktionsbereich auf **Konferenzinformationen per E-Mail senden** für den Benutzer anklicken. Die PIN wird nicht gesendet.
    
- Eine Konferenz-ID umfasst 7 Ziffern. Die Länge kann weder im Skype for Business Admin Center noch mit der Windows PowerShell geändert werden.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Die Konferenz-ID für Audiokonferenzen für einen Benutzer wird unten im Bereich „Aktion" unter **Audiokonferenzen** angezeigt, wenn Sie auf der Seite **Benutzer** einen Benutzer auswählen.
    
- Nachdem eine neue Konferenz-ID erstellt wurde, kann die alte Konferenz-ID nicht mehr verwendet werden. Sie sollten die Benutzer benachrichtigen, ihre bestehenden Besprechungseinladungen neu zu planen, um sicherzustellen, dass die neue Konferenz-ID zu den Einladungen hinzugefügt wird. Die Benutzer können das Skype for Business Meeting Migration Tool verwenden, um ihre bestehenden Besprechungen zu aktualisieren. Informationen zum Download, zur Installation und zum Ausführen des Skype for Business Meeting Update Tool finden Sie unter:
    
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

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin.md)
