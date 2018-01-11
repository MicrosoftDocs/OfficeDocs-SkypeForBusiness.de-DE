---
title: "Einrichten einer Konferenz-ID für einen Benutzer"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2f2cbd6efa61e05defb17ef05f86fd9a228987ac
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="reset-a-conference-id-for-a-user"></a>Einrichten einer Konferenz-ID für einen Benutzer

Wenn Ihr Unternehmen noch nicht für dynamische Konferenz IDs aktiviert wurde, wird eine statische Konferenz-ID automatisch erstellt, wenn ein Skype für Benutzer Business oder Microsoft-Teams für Microsoft als Anbieter von Audiokonferenzen aktiviert ist. Diese Konferenz-ID ist enthalten am unteren Rand Besprechungsanfragen zusammen mit der Zugriffsnummer für Einwahl Telefonnummern, die von Anrufern zu einer Besprechung Anrufen verwendet werden können. Wenn der Benutzer die Telefonnummer wählt, wird die automatische Telefonzentrale für die Besprechung bitten Sie den Anrufer an diese Konferenz-ID eingeben, damit sie an der Besprechung teilnehmen können.
  
> [!NOTE]
> Ist Ihr Konferenzanbieter Microsoft, werden Ihrer Benutzer Konferenz-IDs auf dynamische nur in der Standardeinstellung festgelegt. Leider werden Sie kann nicht in der Skype für Business-Verwaltungskonsole oder mithilfe von Windows Powershell geändert. Sie müssen Microsoft-Supportmitarbeiter kontaktieren. 
  
Statische-IDs werden verwendet, wenn Personen in Ihrer Organisation keine Zufallszahl merken möchten; Sie können wählen Sie eine bestimmte Zahl oder verwenden Sie eine, die leicht zu merken ist. Wenn dynamische Konferenz-IDs verwendet werden, jeder Sitzung, die eine vom Benutzer geplant werden eine eindeutige Konferenz-ID. zugewiesen Wenn Sie zuweisen dynamische statt statische Konferenz-IDs, [Wechseln Sie hier möchten](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Konferenz-IDs werden nur für Skype für Geschäfts- und Microsoft-Teams für Audiokonferenzen aktivierte Benutzer nur automatisch festgelegt als Anbieter von Audiokonferenzen mithilfe von Microsoft. Wenn Sie müssen eine Konferenz-ID für einen Benutzer zurückgesetzt werden, die einen Drittanbieter-Audiokonferenzen (ACP) verwendet wird, müssen Sie eine Konferenz-ID manuell auf der Eigenschaftenseite für den Benutzer eingeben.
  
## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenz-ID für einen Benutzer

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Klicken Sie in der **Skype für Business Administrationscenter**auf **Audiokonferenzen** > **Benutzer**, wählen einen Benutzer aus, und klicken Sie dann im Aktionsbereich unter **Konferenz-ID** **Zurücksetzen**.
    
4. In der **Konferenz-ID zurücksetzen?** Fenster, klicken Sie auf **Ja**. Eine Konferenz die ID wird automatisch erstellt werden und eine e-Mail an den Benutzer mit der neuen Konferenz-ID gesendet Standardmäßig werden e-Mails an Benutzer gesendet, aber dies kann deaktiviert werden.
    
    > [!NOTE]
    > Nach dem Zurücksetzen der Konferenz-ID wird die neue Konferenz-ID per E-Mail an den Benutzer geschickt. Diese E-Mail wird an die Haupt-E-Mail-Adresse geschickt. Dabei handelt es sich oftmals um das Office 365-Postfach. Die E-Mail umfasst die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen, wie bestehende Besprechungen mithilfe des Skype for Business Meeting Update Tool aktualisiert werden können. 
  
## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können alle Konferenzinformationen in einer e-Mail an den Benutzer senden, die die Konferenz-ID und die Zugriffsnummer für Einwahl Telefonnummern enthält, indem Sie für den Benutzer im Aktionsbereich auf **Konferenz Informationen per e-Mail senden** . Die PIN senden nicht.
    
- Enthält eine Konferenz-ID 7 Ziffern, und deren Länge in der Skype für Business-Verwaltungskonsole oder mithilfe von Windows PowerShell können nicht geändert werden.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Wenn Sie den Benutzer auf der Seite **Benutzer** auswählen, kann die Konferenz-ID für einen Benutzer für Audiokonferenzen am unteren Rand der Aktionsbereich unter **Audiokonferenzen** angezeigt werden.
    
- Nachdem eine neue Konferenz-ID erstellt wurde, kann nicht die alte Konferenz-ID BSSID verwendet werden. Informieren Sie Benutzer von Plänen ihrer vorhandenen meeting-Einladungen für sicher, dass die neue Konferenz ansetzen, die ID der Einladungen hinzugefügt wird. Die Benutzer können Skype für Business Besprechung Tool um vorhandenen Besprechungen zu aktualisieren. Informationen zum Herunterladen, installieren und führen Sie die Skype für Business Besprechung Update-Tools finden Sie unter:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, Meeting Migration Tool (64 Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, Meeting Migration Tool (32 Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen der Audio-Konferenzen PIN für einen Benutzer](reset-the-audio-conferencing-pin-for-a-user.md)
