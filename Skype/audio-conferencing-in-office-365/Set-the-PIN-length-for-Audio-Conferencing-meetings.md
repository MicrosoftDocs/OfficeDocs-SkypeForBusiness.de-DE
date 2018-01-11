---
title: "Legen Sie die PIN-Mindestlänge für Audiokonferenzen Besprechungen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: "Hier erfahren Sie, die Parameter für die Kennwortlänge und Anforderungen einer PIN und finden Sie unter Festlegen von die Länge für Besprechungen in Skype für Unternehmen."
ms.openlocfilehash: 853a8ed74377dd76b38eab62b04fc75e3295df2d
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Legen Sie die PIN-Mindestlänge für Audiokonferenzen Besprechungen

Wenn Sie Audiokonferenzen im für Skype für Geschäftskunden und Microsoft-Teams, einrichten, erhalten Sie eine audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehrere Telefonnummern enthalten. Die Telefonnummer, die Sie festlegen, wird auf die Besprechung einladen für Skype für Geschäfts- und Microsoft-Teams, apps enthalten sein.
  
Die audiokonferenzbrücke beantwortet einen Anruf für Personen, die in einer Besprechung mit einem Telefon einwählen. Von einer automatischen Telefonzentrale und aktivieren Sie dann je nach Ihrer Einstellungen für den Anrufer mit Ansagen Fragen, können Benachrichtigungen wiedergeben, und bitten Anrufer, ihren Namen aufzuzeichnen. **Microsoft-Brücke Einstellungen** können Sie die Einstellungen für Benachrichtigungen für Besprechungen zu ändern und die Besprechung-Teilnahme an, und legen Sie die Länge der Stifte, die von Besprechungsorganisatoren verwendet werden. Besprechungsorganisatoren verwenden PINs Besprechungen starten, wenn die Besprechung mithilfe der Skype für Business oder Microsoft-Teams app aufgenommen werden können.
  
## <a name="setting-the-pin-length"></a>Festlegen der PIN-Länge

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge-Einstellungen**.
    
4. Klicken Sie unter **Sicherheit** > **PIN-Mindestlänge**, wählen Sie die Anzahl der Nachkommastellen für die PIN werden soll, und klicken Sie dann auf **Speichern**.
    
> [!NOTE]
> Eine PIN unterscheidet sich von einer Konferenz-ID. Konferenz-IDs werden vom Anrufer verwendet, wenn sie an die Besprechung teilnehmen. Sie werden verwendet, um die Besprechung zu identifizieren. Die PIN wird verwendet, um ein Anrufer als Organisator der Besprechung zu authentifizieren. 
  
## <a name="want-to-know-more-about-pin-settings"></a>Möchten Sie weitere Informationen zu PIN-Einstellungen wissen?

- PINs können von 4 bis 12 Ziffern annehmen. Der Standardwert ist 5. Nummern werden nur beim Erstellen von PINs verwendet. Briefe und Sonderzeichen werden nicht verwendet.
    
- Eine PIN ist nur erforderlich für den Organisator der Besprechung bei einer Skype für Business oder Microsoft-Teams, Benutzer die Besprechung noch nicht bereits gestartet. Wenn jeder in die Besprechung einwählen ist, ist die PIN für den Organisator der Besprechung die Besprechung starten erforderlich.
    
- PIN-Sicherheitseinstellungen gelten für alle Rufnummern, die mit einem Microsoft-Brücke verknüpft sind. Sie werden für alle Besprechungen angewendet, die die angegebenen Brücke zugeordneten Telefonnummern verwenden. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit sparen oder dies automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) verwenden.
    
- Die Anzahl der Nachkommastellen in die PIN auf 8 festgelegt:`Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell ist alles über das Verwalten von Benutzern und welche Benutzer zugelassen oder Aktionen nicht zulässig sind. Mit Windows PowerShell können Sie eine zentrale Verwaltung Ihrer täglichen Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen, die mit Office 365 verwalten. Siehe folgende Themen, um Windows PowerShell zu verwenden:
    
  - [Warum müssen Sie mithilfe von Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell hat viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität über nur über das Office 365 Administrationscenter, beispielsweise wenn Sie Einstellungen Änderungen für viele Benutzer gleichzeitig durchführen. Informationen Sie zu dieser Vorteile in den folgenden Themen: 
    
  - [Eine Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="see-also"></a>Siehe auch

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

