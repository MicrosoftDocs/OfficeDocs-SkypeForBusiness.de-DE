---
title: Benutzer können ihren Namen aufzeichnen, wenn sie an einer Besprechung in Skype for Business Online teilnehmen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Erfahren Sie, wie Sie aktivieren oder deaktivieren können, ob Ihre Benutzer ihre Namen aufzeichnen können, wenn sie an einer Besprechung in Skype for Business Online teilnehmen.
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114241"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Benutzer können ihren Namen aufzeichnen, wenn sie an einer Besprechung in Skype for Business Online teilnehmen

> [!Note]
> Wenn Sie Benutzern erlauben möchten, ihre Namen in Teams aufzuzeichnen, lesen Sie [Ermöglichen Sie Benutzern, ihren Namen aufzuzeichnen, wenn sie an einem Meeting in Microsoft Teams teilnehmen](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Wenn Sie Audiokonferenzen in Microsoft 365 oder Office 365 einrichten, erhalten Sie Telefonnummern und die so genannte Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die eine dedizierte oder freigegebene Telefonnummer sein können.
  
Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.

## <a name="set-whether-callers-should-record-their-name"></a>Festlegen, ob Anrufer ihren Namen aufzeichnen sollen
    
1. Wechseln Sie **im Skype for Business Admin Center** in der linken Navigationsleiste zu Einstellungen für **Audiokonferenzen von** Microsoft  >  **Bridge.**
    
2. Unter **Besprechung beitreten**  sehen Sie das Kontrollkästchen **Besprechungseintrag aktivieren und Benachrichtigungen beenden wird aktiviert** .
    
   - **Aktivierte** Anrufer werden aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen. Diese Option ist standardmäßig aktiviert.
    
   - **Nicht aktivierte** Anrufer werden nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.
    
3. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) nutzen.
    
- Windows PowerShell geht es um die Verwaltung von Benutzern und die Benutzer, die dies tun dürfen. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)