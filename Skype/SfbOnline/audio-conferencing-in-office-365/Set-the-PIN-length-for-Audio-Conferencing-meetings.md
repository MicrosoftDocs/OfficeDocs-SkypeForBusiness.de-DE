---
title: "Legen Sie die PIN-Mindestlänge für Audiokonferenzen Besprechungen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 308bce9196f085c1f9473e74746bccd2f0ca96c5
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Legen Sie die PIN-Mindestlänge für Audiokonferenzen Besprechungen

Wenn Sie Audiokonferenzen im für Skype für Geschäftskunden und Microsoft-Teams, einrichten, erhalten Sie eine audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Die Telefonnummer, die Sie festlegen, wird auf die Besprechung einladen für Skype für Geschäfts- und Microsoft-Teams, apps enthalten sein.
  
Die audiokonferenzbrücke beantwortet einen Anruf für Personen, die in einer Besprechung mit einem Telefon einwählen. Von einer automatischen Telefonzentrale und aktivieren Sie dann je nach Ihrer Einstellungen für den Anrufer mit Ansagen Fragen, können Benachrichtigungen wiedergeben, und bitten Anrufer, ihren Namen aufzuzeichnen. **Microsoft-Brücke Einstellungen** können Sie die Einstellungen für Benachrichtigungen für Besprechungen zu ändern und die Besprechung-Teilnahme an, und legen Sie die Länge der Stifte, die von Besprechungsorganisatoren verwendet werden. Besprechungsorganisatoren verwenden PINs Besprechungen starten, wenn die Besprechung mithilfe der Skype für Business oder Microsoft-Teams app aufgenommen werden können.
  
## <a name="setting-the-pin-length"></a>Konfigurieren der PIN-Länge

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Klicken Sie unter **Sicherheit** > **PIN-Mindestlänge**, wählen Sie die Anzahl der Nachkommastellen für die PIN werden soll, und klicken Sie dann auf **Speichern**.
    
> [!NOTE]
> Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert. 
  
## <a name="want-to-know-more-about-pin-settings"></a>Möchten Sie weitere Informationen zu PIN-Einstellungen wissen?

- PINs können von 4 bis 12 Ziffern annehmen. Der Standardwert ist 5. PINs können nur Zahlen umfassen. Buchstaben und Sonderzeichen sind nicht zulässig.
    
- Eine PIN ist nur erforderlich für den Organisator der Besprechung bei einer Skype für Business oder Microsoft-Teams, Benutzer die Besprechung noch nicht bereits gestartet. Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.
    
- Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) nutzen.
    
- So stellen Sie die Anzahl der Ziffern in der PIN auf 8 Ziffern ein:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber einer alleinigen Verwendung von Office 365 Admin Center in Bezug auf Geschwindigkeit, Einfachheit und Produktivität unzählige Vorteile, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="see-also"></a>Siehe auch

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

