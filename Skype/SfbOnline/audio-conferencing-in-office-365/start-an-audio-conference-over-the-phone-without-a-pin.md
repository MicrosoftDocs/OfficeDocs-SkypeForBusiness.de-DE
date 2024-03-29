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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie die Teilnahme anonymer Anrufer an einer Besprechung über Skype for Business Admin Center oder mithilfe eines PowerShell-Skripts aktivieren oder deaktivieren. '
ms.openlocfilehash: d420acff8d5822aa4badd8980481d67bd2eae35b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013369"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Starten einer Audiokonferenz per Telefon ohne PIN in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Informationen zum Starten einer Audiokonferenz ohne PIN in Microsoft Teams finden Sie unter Starten einer Audiokonferenz über das Telefon ohne [PIN in Microsoft Teams.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)

Es kann für Benutzer, die sich in eine Besprechung einwählen, frustrierend sein, wenn sie im Wartebereich der Besprechung Musik hören, da der Skype for Business-Besprechungsorganisator die Besprechung noch nicht gestartet hat. 
  
Wenn sich ein Besprechungsorganisator in die Besprechung ein anruft, ist zum Starten einer Besprechung standardmäßig eine PIN erforderlich. Sie können einrichten, dass sich jeder in eine Besprechung einwählen kann und nicht zur Eingabe einer PIN zum Starten der Besprechung aufgefordert wird. Sie können diese Einstellung für einen einzelnen Benutzer im Skype for Business Admin Center aktivieren oder deaktivieren.
  
Der Besprechungsorganisator benötigt keine PIN, wenn jemand die Besprechung über die App Skype for Business hat. Eine PIN ist nur erforderlich, wenn der Organisator einer Besprechung per Telefon an der Besprechung teilnimmt. Die PIN für Besprechungen wird an den Audiobenutzer gesendet, wenn ihm die Lizenz für **Audiokonferenzen** zugewiesen ist und er für Audiokonferenzen aktiviert ist. Weitere Informationen finden Sie unter Senden einer E-Mail mit den Informationen zur [Audiokonferenz](send-an-email-to-a-user-with-their-dial-in-information.md) an einen Benutzer und E-Mails, die automatisch an Benutzer gesendet werden, wenn sich ihre [Audiokonferenzeinstellungen ändern.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Aktivieren oder Deaktivieren anonymer Anrufer für die Teilnahme an einer Besprechung
    
1. Navigieren Sie **im Skype for Business Admin Center** in der linken Navigationsleiste zu Benutzer für **Audiokonferenzen.**  >   
    
2. Wählen Sie in der Liste den Benutzer aus, und klicken Sie im Aktionsbereich auf **Bearbeiten**. 
    
3. Aktivieren oder löschen Sie auf der Eigenschaftenseite des Benutzers unter Besprechungsoptionen die Option Zulassen, dass nicht authentifizierte Anrufer die ersten Personen **in einer Besprechung sind. Andern falls nicht, wartet er im Wartebereich, bis ein authentifizierter Benutzer beitritt.**
    
4. Klicken Sie auf **Speichern**. 


    
 **Verwenden Windows Powershell**
  
- Führen Sie Folgendes aus: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>Was sollten Sie noch wissen?

- Informationen zum Zurücksetzen der PIN finden Sie unter Zurücksetzen der [Audiokonferenz-PIN.](reset-the-audio-conferencing-pin.md)
    
- Wenn der anonyme Zugriff oder das Starten einer Besprechung ohne PIN deaktiviert ist:
    
  - Wenn die Besprechung noch nicht begonnen hat (es gibt noch niemand in der Besprechung): Ein Anrufer wird aufgefordert, ob er der Organisator ist. Wenn er ja sagt, wird er zur Eingabe seiner PIN aufgefordert. Nach Eingabe der PIN beginnt die Besprechung, und der Benutzer wird an der Besprechung teilnehmen.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person befindet sich bereits in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird auch nicht zur Eingabe der PIN aufgefordert. Die Besprechung ist bereits gestartet, und der Anrufer wird ihr beitreten.
    
- Wenn der anonyme Zugriff aktiviert ist oder zum Starten einer Besprechung keine PIN erforderlich ist:
    
  - Wenn die Besprechung noch nicht begonnen hat (es gibt noch niemand in der Besprechung): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird auch nicht zur Eingabe der PIN aufgefordert. Da die Einstellung für den Organisator deaktiviert ist, beginnt die Besprechung und die anonymen Anrufer nehmen an der Besprechung teil.
    
  - Wenn die Besprechung bereits begonnen hat (eine andere Person hat bereits an der Besprechung teil): Ein Anrufer wird nicht aufgefordert, wenn er der Organisator ist, und er wird auch nicht zur Eingabe der PIN aufgefordert; die Besprechung ist bereits begonnen, und der Anrufer wird an der Besprechung teilnehmen.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang für mehrere Benutzer zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) nutzen.
    
- In Bezug auf Windows PowerShell dreht sich bei Skype for Business Online alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter Herunterladen und Installieren des Teams [PowerShell-Moduls heruntergeladen werden.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
