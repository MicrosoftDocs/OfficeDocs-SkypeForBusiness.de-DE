---
title: Zurücksetzen der Audiokonferenz PIN in Skype für Business Online
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Erfahren Sie, was Sie Drehbezugspunkten wissen sollten und wie diese in Skype für Business Online zurückzusetzen. '
ms.openlocfilehash: 257f59f59d4fc86c91aa5496fe3db42573269065
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882138"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Zurücksetzen der Audiokonferenz PIN in Skype für Business Online

> [!Note]
> Informationen zum Zurücksetzen von Audio Conferencing PINs in Microsoft-Teams, finden Sie unter [PIN Audio Conferencing in Microsoft-Teams, Zurücksetzen](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Eine PIN ist ein Code bestehend aus Zahlen, die für jeden Skype für Geschäftsbenutzer erstellt werden, die für Audiokonferenzen aktiviert ist. Audiokonferenzen PINs von Besprechungsorganisatoren dienen zum Identifizieren, sie der Organisator der Besprechung sind und ermöglicht es ihnen, eine Besprechung über das Telefon zu starten. Wenn sie die Skype für Geschäfts-app verwenden, um die Besprechung zu starten, ist eine PIN nicht erforderlich. Wenn Benutzer ihre PIN vergessen, und sie können nicht gefunden werden in der e-Mail, die an sie gesendet wurde, wenn sie für die Audiokonferenz aktiviert wurden, ein Administrator kann ihre PIN zurücksetzen, oder sie können ihre eigenen PIN zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer Beitritt mithilfe der Skype-Geschäfts-app oder wenn der Organisator mit seinem PIN über das Telefon Beitritt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.
  
## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zu der **Office 365 Administrationscenter** > **Skype für Unternehmen**, und klicken Sie im linken Navigationsbereich auf **Audiokonferenzen**.
    
3. Klicken Sie auf **Benutzer**, wählen Sie den Benutzer, dem Sie für die PIN zurücksetzen möchten.
    
4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Ein Benutzer seine PIN zurücksetzen

Ein Benutzer kann eine PIN zurücksetzen, mithilfe der Option **PIN zurücksetzen** auf der Seite **Einwahlkonferenzen** . Auf dieser Seite kann auf drei Arten zugegriffen werden:

* Wechseln Sie in einem Browser zu [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* In Skype für Unternehmen, klicken Sie auf den Pfeil **Menü anzeigen** neben **Optionen**, und klicken Sie dann auf **Extras** > **Konferenz Einwähleinstellungen**.
* Klicken Sie in Skype für Unternehmen auf **Optionen**, klicken Sie im linken Menü auf **Anrufweiterleitung** und in den Abschnitt **Weitere Einstellungen aufrufen,** klicken Sie dann auf **Bearbeiten von online-Einstellungen**. 

## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN durch einen Administrator zurückgesetzt wird, werden die PIN-Nummer als aufgelistet *** in der **Skype für Business-Verwaltungskonsole** und in den Ergebnissen, wenn sie Get-CsCsOnlineDialInConfencingUser in Windows PowerShell verwenden.
    
- Automatisch Senden von e-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine e-Mail mit ihrer PIN, wenn sie aktiviert sind, für Audiokonferenzen oder wenn die PIN zurückgesetzt wird. Aber wenn Sie automatisch deaktiviert haben Senden von e-Mails, eine PIN zurücksetzen-e-Mail wird nicht an einen Benutzer gesendet werden und Sie müssen die PIN-Informationen für den Benutzer manuell veranlassen.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung ist mit eine Besprechung gestartet werden, indem anonyme Anrufer nicht zu ermöglichen.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig sie-e-Mails gesendet, die Informationen zur Telefonkonferenz und ihre PIN enthalten. Der Benutzer muss ein Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN ist eine neue PIN in e-Mails an ihre primäre SMTP-Adresse (Alias) an den Benutzer gesendet wird, die für den Benutzer festgelegt ist.
    
- Wenn Sie Audiokonferenzen eingerichtet haben, legen Sie die Ziffern, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die PIN-Länge-Einstellung ändern, wird diese Einstellung gilt nur für neu generierte PINs und wird nicht angewendet, um die PIN-Einstellung für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind. Finden Sie unter [Legen Sie die PIN für Audiokonferenzen Besprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Die e-Mail standardmäßig wird auf die Office 365 primäre SMTP-Adresse des Benutzers festgelegt werden. Sie können eine e-Mail an eine nicht - Office 365-Adresse wie Hotmail oder MSN e-Mail-Adresse senden. Mithilfe von Windows PowerShell können Sie die Standard-e-Mail-Adresse außer Kraft setzen. Dies ist nützlich, wenn der Benutzer nicht über ein Exchange-Postfach in Office 365 verfügen.
    
- Um die Standard-Benutzer-Adresse zu überschreiben, die e-Mail-Nachricht gesendet wird, kann den Administrator des Mandanten verwenden Sie das folgende Cmdlet: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendenEMail - SendEmailToAddress "u@hotmail.com". Der SendenEMail-Parameter ist erforderlich, die e-Mail-Adresse des Benutzers außer Kraft gesetzt.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
- Sie können die PIN für Amos Marble konfigurieren, indem Sie Folgendes ausführen:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>See Also

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user.md)
