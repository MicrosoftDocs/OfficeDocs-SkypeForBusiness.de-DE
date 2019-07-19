---
title: Einrichten der PIN-Länge für Audiokonferenz-Besprechungen in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 4e4308eab334b37d32cbd53d047ba5fd077a1cad
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792737"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Einrichten der PIN-Länge für Audiokonferenz-Besprechungen in Skype for Business Online


> [!NOTE]
> Informationen zum Festlegen der PIN-Länge in Microsoft Teams finden Sie unter [Festlegen der PIN-Länge für Audiokonferenz-Besprechungen in Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).

Wenn Sie Audiokonferenzen für Skype for Business einrichten, erhalten Sie eine Audiokonferenz-Brücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Die von Ihnen festgelegte Telefonnummer wird in die Besprechungseinladungen für die Skype for Business-App aufgenommen.
  
Die Audiokonferenz-Brücke beantwortet einen Anruf für Personen, die sich per Telefon in eine Besprechung einwählen. Sie beantwortet den Anrufer mit Sprachansagen von einer automatischen Telefonzentrale und kann dann – je nach Ihren Einstellungen – Benachrichtigungen abspielen und Anrufer bitten, deren Namen aufzuzeichnen. Mit den **Microsoft Bridge-Einstellungen** können Sie die Einstellungen für Besprechungs Benachrichtigungen und die Besprechungsteilnahme ändern und die Länge der Pins festlegen, die von Besprechungsorganisatoren verwendet werden. Besprechungsorganisatoren verwenden Pins zum Starten von Besprechungen, wenn Sie nicht mit der Skype for Business-APP an der Besprechung teilnehmen können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Konfigurieren der PIN-Länge
 
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. Wählen Sie unter **Sicherheits** > -**PIN-Länge**die gewünschte Anzahl der Ziffern für die PIN aus, und klicken Sie auf **Speichern**.
    
> [!NOTE]
> Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert. 

## <a name="want-to-know-more-about-pin-settings"></a>Möchten Sie mehr über die PIN-Einstellungen erfahren?

- Pins können von 4 bis 12 Ziffern sein; der Standardwert ist 5. PINs können nur Zahlen umfassen. Buchstaben und Sonderzeichen sind nicht zulässig.
    
- Eine PIN ist nur für den Besprechungsorganisator erforderlich, wenn ein Skype for Business-Benutzer die Besprechung noch nicht gestartet hat. Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.
    
- Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) nutzen.
    
- So stellen Sie die Anzahl der Ziffern in der PIN auf 8 Ziffern ein:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Änderungen an den Einstellungen vornehmen. Learn about these advantages in the following topics: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="see-also"></a>Siehe auch

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
