---
title: Zurücksetzen der Audiokonferenz-PIN in Skype for Business Online
ms.author: tonysmit
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Informieren Sie sich, was Sie über Pins wissen sollten, und wie Sie Sie in Skype for Business Online zurücksetzen können. '
ms.openlocfilehash: ca2bbef02b0c6ecdefef700ca316188f5c544070
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792278"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Zurücksetzen der Audiokonferenz-PIN in Skype for Business Online

> [!Note]
> Informationen zum Zurücksetzen von Audiokonferenz-Pins in Microsoft Teams finden Sie unter [Zurücksetzen der Audiokonferenz-PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Eine PIN ist ein Code, der aus Zahlen besteht, die für jeden Skype for Business-Benutzer erstellt werden, der für Audiokonferenzen aktiviert ist. Audiokonferenz-Pins werden von Besprechungsorganisatoren verwendet, um zu erkennen, dass Sie der Organisator der Besprechung sind, und Ihnen gestatten, eine Besprechung per Telefon zu starten. Wenn Sie die Skype for Business-App zum Starten der Besprechung verwenden, ist keine PIN erforderlich. Wenn Benutzer Ihre PIN vergessen haben und Sie Sie nicht in der e-Mail finden können, die an Sie gesendet wurde, als Sie für Audiokonferenzen aktiviert wurden, kann ein Administrator Ihre PIN zurücksetzen, oder Sie können Ihre eigene PIN zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer mit der Skype for Business-App verbunden ist oder wenn der Organisator mit seiner PIN über das Telefon verbunden ist. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.
  
## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zum Admin Center #a0 **Skype for Business**, und klicken Sie im linken Navigationsbereich **** auf Audiokonferenzen.
    
3. Klicken Sie auf **Benutzer**, und wählen Sie den Benutzer aus, für den Sie die PIN zurücksetzen möchten.
    
4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Festlegen, dass ein Benutzer seine eigene Pin zurücksetzt

Ein Benutzer kann eine PIN mithilfe der Option " **PIN zurücksetzen** " auf der Seite " **Einwahlkonferenzen** " zurücksetzen. Auf diese Seite kann auf eine von drei Arten zugegriffen werden:

* Wechseln Sie in einem Browser zu [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Klicken Sie in Skype for Business auf den Pfeil **Menü anzeigen** neben **Optionen**, und klicken Sie dann auf **Extras** > **Einwahlkonferenzeinstellungen**.
* Klicken Sie in Skype for Business auf **Optionen**, klicken Sie im linken Menü auf **Anrufweiterleitung** , und klicken Sie dann im Abschnitt **Weitere Anrufeinstellungen** **Online auf Einstellungen bearbeiten**. 

## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN von einem Administrator zurückgesetzt wurde, wird die PIN als * * * * * * * * * * * im **Skype for Business Admin Center** und in den Ergebnissen aufgeführt, wenn Sie Get-CsCsOnlineDialInConfencingUser in Windows PowerShell verwenden.
    
- Das automatische Senden von e-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine e-Mail mit ihrer PIN, wenn Sie für Audiokonferenzen aktiviert sind oder wenn die PIN zurückgesetzt wird. Wenn Sie jedoch das automatische Senden von e-Mails deaktiviert haben, wird eine e-Mail mit Pin-Reset nicht an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung ist, dass eine Besprechung nicht von anonymen Anrufern gestartet werden kann.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig e-Mail-Nachrichten gesendet, die Konferenz Informationen und Ihre PIN enthalten. Der Benutzer muss über ein Office 365-Postfach verfügen, denn wenn eine PIN zurückgesetzt wird, wird eine neue PIN an den Benutzer in einer e-Mail an die primäre SMTP-Adresse (Alias) gesendet, die für den Benutzer festgesetzt wurde.
    
- Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die Pins in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die Einstellung für die PIN-Länge ändern, wird die Einstellung nur auf neu generierte Pins angewendet und nicht auf die PIN-Einstellung für vorhandene Benutzer angewendet, die für Audiokonferenzen aktiviert sind. Informationen finden Sie unter [Festlegung der Länge der PIN für Audiokonferenz-Besprechungen](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Die e-Mail-Adresse wird standardmäßig auf die primäre SMTP-Adresse von Office 365 des Benutzers eingestellt. Sie können eine e-Mail an eine nicht-Office 365-Adresse wie eine Hotmail-oder MSN-e-Mail-Adresse senden. Sie können die Standard-e-Mail-Adresse mithilfe von Windows PowerShell außer Kraft setzen. Dies ist hilfreich, wenn die Benutzer kein Exchange-Postfach in Office 365 haben.
    
- Um die Standardbenutzer Adresse zu überschreiben, an die die e-Mail gesendet wird, kann der mandantenadministrator das folgende Cmdlet verwenden: Satz-csonlinedialinconferencinguser zeigt-Amos. Marble-ResetLeaderPIN-SendEmail-SendEmailToAddress "u@hotmail.com". Der SendEmail-Parameter ist erforderlich, um die e-Mail-Adresse des Benutzers zu überschreiben.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
- Sie können die PIN für Amos Marble konfigurieren, indem Sie Folgendes ausführen:
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen. Learn about these advantages in the following topics:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user.md)
