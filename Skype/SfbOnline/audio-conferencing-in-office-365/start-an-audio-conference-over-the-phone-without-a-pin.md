---
title: Starten einer Audiokonferenz per Telefon ohne PIN in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 146a23c35bca8e313f193dbd1407990fc8c6a788
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "35535866"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Skype for Business Online

> [!Note]
> Informationen zum Starten einer Audiokonferenz ohne PIN in Microsoft Teams finden Sie unter [Starten einer Audiokonferenz per Telefon ohne PIN in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Es ist möglicherweise frustrierend, dass Benutzer, die sich in eine Besprechung einwählen, in der Besprechungslobby abgehalten werden, um Musik zu hören, da der Skype for Business-Besprechungsorganisator die Besprechung noch nicht gestartet hat. 
  
Wenn ein Besprechungsorganisator in die Besprechung einruft, ist standardmäßig eine PIN erforderlich, um eine Besprechung zu starten. Sie können es so einrichten, dass sich jeder in eine Besprechung einwählen kann und nicht zur Eingabe einer PIN aufgefordert wird, um die Besprechung zu starten. Sie können diese Einstellung für einen einzelnen Benutzer im Skype for Business Admin Center aktivieren oder deaktivieren.
  
Eine PIN ist für den Besprechungsorganisator nicht erforderlich, wenn eine andere Person die Besprechung über die Skype for Business-App gestartet hat. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den audiobenutzer gesendet, wenn Ihnen die **Audiokonferenz** -Lizenz zugewiesen wurde und für Audiokonferenzen aktiviert ist. Weitere Informationen finden Sie unter [Senden einer e-Mail-Nachricht an einen Benutzer mit ihren](send-an-email-to-a-user-with-their-dial-in-information.md) Audiokonferenzinformationen und [e-Mails, die automatisch an Benutzer gesendet werden, wenn sich Ihre audiokonferenzeinstellungen ändern](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung
    
1. Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu Audiokonferenz **** > -**Benutzer**. 
    
2. Wählen Sie in der Liste den Benutzer aus, und klicken Sie im Bereich "Aktion" auf **Bearbeiten**. 
    
3. Aktivieren oder deaktivieren Sie auf der Eigenschaftenseite des Benutzers unter **Besprechungsoptionen**die Option zulassen, dass **nicht authentifizierte Anrufer die ersten Personen in einer Besprechung sind. Wenn dies nicht der Fall ist, werden Sie in der Lobby warten, bis ein authentifizierter Benutzer Beitritt**.
    
4. Klicken Sie auf **Speichern**. 


    
 **Verwenden von Windows PowerShell**
  
- Führen Sie Folgendes aus: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Wenn Sie die PIN zurücksetzen möchten, lesen Sie [Zurücksetzen der Audiokonferenz-Pin](reset-the-audio-conferencing-pin.md).
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN nicht erforderlich ist, ist deaktiviert:
    
  - Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung vorhanden): ein Anrufer wird aufgefordert, wenn er der Organisator ist; Wenn er "Ja" sagt, wird er aufgefordert, seine PIN einzugeben, und nachdem er die PIN angegeben hat, wird die Besprechung gestartet, und der Benutzer wird an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): ein Anrufer wird nicht gefragt, ob er der Organisator ist, und er wird nie zur Eingabe der PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird teilnehmen.
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung keine PIN erfordert, ist aktiviert:
    
  - Wenn die Besprechung noch nicht begonnen hat (es ist noch niemand in der Besprechung vorhanden): ein Anrufer wird nicht dazu aufgefordert, wenn er der Organisator ist, und wird nie zur Eingabe der PIN aufgefordert. Da die Einstellung für Organizer auf aus festgelegt ist, wird die Besprechung gestartet, und die anonymen Anrufer werden an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): ein Anrufer wird nicht dazu aufgefordert, wenn Sie der Organisator ist, und Sie wird nie zur Eingabe der PIN aufgefordert; die Besprechung wurde bereits gestartet, und der Anrufer wird teilnehmen.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang für mehrere Benutzer zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) nutzen.
    
- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
