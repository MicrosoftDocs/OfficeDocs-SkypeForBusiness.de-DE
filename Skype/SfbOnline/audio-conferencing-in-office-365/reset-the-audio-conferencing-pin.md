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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, was Sie über PINs wissen sollten und wie Sie diese in Ihrer Skype for Business zurücksetzen. '
ms.openlocfilehash: c3e33655a5d92dbc24522611a1551c4240c4c228
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011929"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Zurücksetzen der Audiokonferenz-PIN in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Informationen zum Zurücksetzen von PINs für Audiokonferenzen in Microsoft Teams finden Sie unter Zurücksetzen der [Audiokonferenz-PIN in Microsoft Teams.](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams)

Eine PIN ist ein aus Zahlen besteht Code, der für jeden benutzer Skype for Business, der für Audiokonferenzen aktiviert ist, erstellt wird. Audiokonferenzen PINs werden von Besprechungsorganisatoren verwendet, um zu identifizieren, dass sie der Besprechungsorganisator sind, und ermöglichen ihnen, eine Besprechung per Telefon zu starten. Wenn er die Skype for Business-App zum Starten der Besprechung verwendet, ist keine PIN erforderlich. Wenn Benutzer ihre PIN vergessen und diese in der E-Mail, die ihnen bei der Aktivierung für Audiokonferenzen gesendet wurde, nicht finden können, kann ein Administrator ihre PIN oder ihre eigene PIN zurücksetzen.
  
Besprechungen können gestartet werden, wenn ein authentifizierter Benutzer mit der Skype for Business-App teilnimmt oder der Organisator per Telefon mit seiner PIN teilnimmt. Wenn die Besprechung zum Starten eine PIN erfordert, werden alle Benutzer, die sich per Telefon einwählen standardmäßig im Wartebereich platziert und hören Warteschleifenmusik, bis die Besprechung beginnt. Wenn der Organisator einer Besprechung keine PIN zum Starten der Besprechung per Telefon benötigt, werden Anrufer nicht nach einer PIN gefragt, wenn sie sich für die Besprechung einwählen.
  
## <a name="reset-a-users-pin"></a>Zurücksetzen der PIN eines Benutzers

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.
    
2. Wechseln Sie zum Admin Center > **Skype for Business**, und klicken Sie in der linken Navigationsleiste auf **Audio conferencing (Audiokonferenz).**
    
3. Klicken Sie **auf Benutzer**, und wählen Sie den Benutzer aus, für den Sie die PIN zurücksetzen möchten.
    
4. Klicken Sie im Aktionsbereich unter **PIN** auf **Zurücksetzen**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Benutzer die eigene PIN zurücksetzen

Benutzer können eine PIN mithilfe der Option **PIN** zurücksetzen auf der Seite für **Einwahlkonferenzen** zurücksetzen. Auf diese Seite kann auf eine von drei Arten zugegriffen werden:

* Wechseln Sie in einem Browser zu [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling) .
* Klicken Skype for Business auf den  Pfeil Menü anzeigen neben Optionen **,** und klicken Sie dann auf **Extras**  >  **Einwahlkonferenz Einstellungen.**
* Klicken Skype for Business Im linken Menü  auf Optionen **,** klicken Sie im linken Menü auf Anruf weiterleiten, und klicken Sie dann im Abschnitt Weitere Anruf **Einstellungen** auf Einstellungen **online bearbeiten**. 

## <a name="what-else-should-you-know-about-pins"></a>Was sollten Sie sonst über PINs wissen?

- Aus Sicherheitsgründen wird die PIN einem Administrator nur ein Mal gezeigt, wenn die PIN zurückgesetzt wird. Nachdem die PIN von einem Administrator zurückgesetzt wurde, wird die PIN im **Skype for Business Admin Center** als *********** und in den Ergebnissen aufgeführt, wenn sie Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Das automatische Senden von E-Mails an Benutzer ist standardmäßig aktiviert, und Benutzer erhalten eine E-Mail mit ihrer PIN, wenn sie für Audiokonferenzen aktiviert oder die PIN zurückgesetzt wird. Wenn Sie das automatische Senden von E-Mails deaktiviert haben, wird keine E-Mail zum Zurücksetzen der PIN an einen Benutzer gesendet, und Sie müssen die PIN-Informationen manuell an den Benutzer senden.
    
- Beim Start einer Besprechung nehmen alle Benutzer im Wartebereich automatisch an dieser teil. Wenn beispielsweise 2 Teilnehmer versuchen, vor dem Start der Besprechung an dieser teilzunehmen, werden sie im Wartebereich platziert und hören Warteschleifenmusik. Sobald der Organisator der Besprechung mit seiner PIN per Telefon teilnimmt, beginnt die Besprechung und alle Teilnehmer im Wartebereich nehmen an der Besprechung teil.
    
- Die Standardeinstellung ist, dass das Starten einer Besprechung durch anonyme Anrufer nicht zulässig ist.
    
- Wenn Sie einen Benutzer für Audiokonferenzen aktivieren, wird ihm standardmäßig eine E-Mail gesendet, die Konferenzinformationen und die eigene PIN enthält. Der Benutzer muss über ein Microsoft 365- oder Office 365-Postfach verfügen, da beim Zurücksetzen einer PIN dem Benutzer eine neue PIN per E-Mail an die für den Benutzer festgelegte primäre SMTP-Adresse (Alias) gesendet wird.
    
- Wenn Sie Audiokonferenzen einrichten, legen Sie die Ziffern fest, die für die PINs in Ihrer Organisation erforderlich sind. PINs können 4 bis 12 Ziffern enthalten, standardmäßig werden 5 Ziffern verwendet. Wenn Sie die PIN-Längeneinstellung ändern, wird die Einstellung nur auf neu generierte PINs angewendet und nicht auf PIN-Einstellungen für vorhandene Benutzer, die für Audiokonferenzen aktiviert sind. Weitere [Informationen finden Sie unter Festlegen der Länge der PIN für Audiokonferenzbesprechungen.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- Die E-Mail wird standardmäßig auf die Adresse Microsoft 365 oder Office 365 SMTP-Adresse des Benutzers festgelegt. Sie können eine E-Mail an eine Nicht-Microsoft 365-Adresse Office 365, z. B. eine E-Hotmail MSN-Adresse, senden. Sie können die standardmäßige E-Mail-Adresse über Windows PowerShell. Dies ist nützlich, wenn die Benutzer nicht über ein Postfach Exchange In Microsoft 365 Postfach Office 365.
    
- Zum Überschreiben der Standardbenutzeradresse, an die die E-Mail gesendet wird, kann der Mandantenadministrator das folgende Cmdlet verwenden: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". Der Parameter SendEmail ist erforderlich, um die E-Mail-Adresse des Benutzers zu überschreiben.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) nutzen.
    
- Sie können die PIN für Amos Marble konfigurieren, indem Sie Folgendes ausführen:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter Herunterladen und Installieren des Teams [PowerShell-Moduls heruntergeladen werden.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen einer Konferenzkennung für einen Benutzer](reset-a-conference-id-for-a-user.md)
