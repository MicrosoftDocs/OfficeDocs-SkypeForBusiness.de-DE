---
title: Zurücksetzen der PIN für Audiokonferenzen in Skype for Business Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, was Sie über PINs wissen sollten und wie Sie sie in Skype for Business Online zurücksetzen können. '
ms.openlocfilehash: 4b042775a5a0525099c0116d7d55d0092f560cdf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114201"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Zurücksetzen der PIN für Audiokonferenzen in Skype for Business Online

> [!Note]
> Informationen zum Zurücksetzen von PINs für Audiokonferenzen in Microsoft Teams finden Sie unter Zurücksetzen der PIN für [Audiokonferenzen in Microsoft Teams.](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

Eine PIN ist ein Code aus Zahlen, der für jeden Skype for Business-Benutzer erstellt wird, der für Audiokonferenzen aktiviert ist. Pins für Audiokonferenzen werden von Besprechungsorganisatoren verwendet, um zu erkennen, dass sie der Besprechungsorganisator sind und es ihnen ermöglichen, eine Besprechung über das Telefon zu starten. Wenn sie die Skype for Business-App zum Starten der Besprechung verwenden, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und sie in der E-Mail, die ihnen gesendet wurde, als sie für Audiokonferenzen aktiviert wurden, nicht finden können, kann ein Administrator seine PIN zurücksetzen oder seine eigene PIN zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer über die Skype for Business-App beitritt oder der Organisator über das Telefon mit seiner PIN beitritt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.
  
## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

1. Melden Sie sich mit Ihrem Arbeits-, Schul- oder Schulkonto an.
    
2. Wechseln Sie zum Admin Center > **Skype for Business,** und klicken Sie in der linken Navigation auf **Audiokonferenzen.**
    
3. Klicken Sie **auf Benutzer**, und wählen Sie den Benutzer aus, für den Sie die PIN zurücksetzen möchten.
    
4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Zurücksetzen der eigenen PIN durch einen Benutzer

Ein Benutzer kann eine PIN  mithilfe der Option PIN zurücksetzen auf der Seite **Einwahlkonferenzen** zurücksetzen. Auf diese Seite kann auf eine von drei Arten zugegriffen werden:

* Wechseln Sie in einem Browser zu [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) .
* Klicken Sie in Skype for Business auf **den** Pfeil Menü anzeigen neben **Optionen,** und klicken Sie dann auf **Einwahlkonferenzeinstellungen**  >  **extras.**
* Klicken Sie in Skype for  Business auf **Optionen,** klicken Sie im linken Menü auf Anruf weiterleiten, und klicken Sie dann im Abschnitt Weitere **Anrufeinstellungen** auf Einstellungen **online bearbeiten.** 

## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN von einem Administrator zurückgesetzt wurde, wird die PIN im **Skype for Business Admin Center** als *********** und in den Ergebnissen aufgeführt, wenn sie Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert sind oder wenn die PIN zurückgesetzt wird. Wenn Sie jedoch das automatische Senden von E-Mails deaktiviert haben, wird keine E-Mail zum Zurücksetzen der PIN an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung besteht im Nichtanrufen einer Besprechung durch anonyme Anrufer.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, werden standardmäßig E-Mails gesendet, die Konferenzinformationen und deren PIN enthalten. Der Benutzer muss über ein Microsoft 365- oder Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN eine neue PIN per E-Mail an die primäre SMTP-Adresse (Alias) gesendet wird, die für den Benutzer festgelegt ist.
    
- Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die Einstellung für die PIN-Länge ändern, wird die Einstellung nur auf neu generierte PINs angewendet und nicht auf die PIN-Einstellung für vorhandene Benutzer angewendet, die für Audiokonferenzen aktiviert sind. Weitere Informationen finden Sie unter Festlegen [der Länge der PIN für Audiokonferenzbesprechungen.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- Die E-Mail wird standardmäßig auf die primäre MICROSOFT 365- oder Office 365-SMTP-Adresse des Benutzers festgelegt. Sie können eine E-Mail an eine Nicht-Microsoft 365- oder Nicht-Office 365-Adresse senden, z. B. eine Hotmail oder MSN-E-Mail-Adresse. Sie können die Standard-E-Mail-Adresse überschreiben, indem Sie Windows PowerShell. Dies ist nützlich, wenn die Benutzer kein Exchange-Postfach in Microsoft 365 oder Office 365 haben.
    
- Um die Standardbenutzeradresse zu überschreiben, an die die E-Mail gesendet wird, kann der Mandantenadministrator das folgende Cmdlet verwenden: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". Der Parameter SendEmail ist erforderlich, um die E-Mail-Adresse des Benutzers außer Kraft zu setzen.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) nutzen.
    
- Sie können die PIN für Amos Marble konfigurieren, indem Sie Folgendes ausführen:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user.md)