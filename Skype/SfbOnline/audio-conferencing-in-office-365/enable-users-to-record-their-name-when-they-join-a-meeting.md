---
title: Zulassen, dass Benutzer ihren Namen aufzeichnen, wenn Sie in Skype for Business Online an einer Besprechung teilnehmen
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
description: Erfahren Sie, wie Sie aktivieren oder deaktivieren können, ob Ihre Benutzer ihre Namen aufzeichnen können, wenn Sie in Skype for Business Online an einer Besprechung teilnehmen.
ms.openlocfilehash: d6bb98c2d3c6b12479aea4fbdfdc717491c9893e
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164154"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Zulassen, dass Benutzer ihren Namen aufzeichnen, wenn Sie in Skype for Business Online an einer Besprechung teilnehmen

> [!Note]
> Wenn Sie Benutzern erlauben möchten, ihre Namen in Teams aufzuzeichnen, lesen Sie [Ermöglichen Sie Benutzern, ihren Namen aufzuzeichnen, wenn sie an einem Meeting in Microsoft Teams teilnehmen](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Wenn Sie Audio-Conferencing in Microsoft 365 oder Office 365 einrichten, erhalten Sie Telefonnummern und eine sogenannte Audiokonferenz-Brücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten, die eine dedizierte oder freigegebene Telefonnummer sein können.
  
Die Konferenzbrücke nimmt den Anruf eines Benutzers an, der sich mit einem Telefon in eine Besprechung einwählt. Die Konferenzbrücke nimmt den Anruf an und gibt Sprachansagen einer automatischen Telefonzentrale aus. Je nach den festgelegten Einstellungen gibt sie Benachrichtigungen wieder und fordert Anrufer auf, ihren Namen aufzuzeichnen. Zudem richtet sie die PIN-Sicherheit für die Organisatoren der Besprechung ein. Der Organisator der Besprechung erhält PINs, damit er eine Besprechung starten kann. Sie können in Ihren Einstellungen jedoch festlegen, dass zum Start einer Besprechung keine PIN erforderlich ist.

## <a name="set-whether-callers-should-record-their-name"></a>Festlegen, ob Anrufer ihren Namen aufzeichnen sollen
    
1. Wechseln Sie im **Skype for Business Admin Center**in der linken Navigationsleiste zu **Audiokonferenz** > -**Einstellungen für Microsoft Bridge**.
    
2. Unter ** Besprechung beitreten**  sehen Sie das Kontrollkästchen ** Besprechungseintrag aktivieren und Benachrichtigungen beenden wird aktiviert** .
    
   - **Aktivierte** Anrufer werden aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen. Diese Option ist standardmäßig aktiviert.
    
   - **Nicht aktivierte** Anrufer werden nicht aufgefordert, ihren Namen aufzuzeichnen, bevor sie an der Besprechung teilnehmen.
    
3. Nachdem Sie die Änderungen vorgenommen haben, klicken Sie auf **Speichern**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) nutzen.
    
- In Windows PowerShell geht es um die Verwaltung von Benutzern und was Benutzer tun dürfen. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Die ersten Schritte mit Windows PowerShell finden Sie in den folgenden Themen:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Weitere Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
