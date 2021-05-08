---
title: Festlegen der PIN-Länge für Audiokonferenzbesprechungen in Skype for Business Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Hier erhalten Sie Informationen zu den Parametern für die Länge und Anforderungen einer PIN und erfahren, wie Sie die Länge für Besprechungen in Skype for Business.
ms.openlocfilehash: 2e4e1d087ad6e0f91d034c6a5abe513e8b3aab01
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238600"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Festlegen der PIN-Länge für Audiokonferenzbesprechungen in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> Informationen zum Festlegen der PIN-Länge in Microsoft Teams finden Sie unter Festlegen der [PIN-Länge für Audiokonferenzbesprechungen in Microsoft Teams.](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams)

Wenn Sie Audiokonferenzen für Skype for Business einrichten, erhalten Sie eine Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Die von Ihnen festgelegte Telefonnummer wird in den Besprechungs-Einladungen für die App Skype for Business enthalten.
  
Die Audiokonferenzbrücke nimmt Anrufe von Benutzern an, die sich über ein Telefon in eine Besprechung einwählen. Sie beantwortet den Anrufer mit Sprachanrufen einer automatischen Telefonisten und kann dann je nach Ihren Einstellungen Benachrichtigungen abspielen und Anrufer bitten, ihren Namen zu notieren. **Mit den Einstellungen von Microsoft Bridge** können Sie die Einstellungen für Besprechungsbenachrichtigungen und die Teilnahme an Besprechungen ändern und die Länge der PINs festlegen, die von Besprechungsorganisatoren verwendet werden. Besprechungsorganisatoren verwenden PINs, um Besprechungen zu starten, wenn sie nicht über die App "Besprechungs-App Skype for Business können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Konfigurieren der PIN-Länge
 
1. Wechseln Sie **Skype for Business linken** Navigationsbereich im Admin Center zu **Audio conferencing**  >  **Microsoft Bridge-Einstellungen**.
    
2. Wählen **Sie unter Länge** der Sicherheits-PIN die Anzahl der Ziffern für die PIN aus, und klicken Sie dann auf  >   **Speichern.**
    
> [!NOTE]
> Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert. 

## <a name="want-to-know-more-about-pin-settings"></a>Möchten Sie mehr über PIN-Einstellungen erfahren?

- PINs können zwischen 4 und 12 Ziffern sein. der Standardwert ist 5. PINs können nur Zahlen umfassen. Buchstaben und Sonderzeichen sind nicht zulässig.
    
- Eine PIN ist für den Besprechungsorganisator nur erforderlich, wenn Skype for Business Benutzer noch nicht die Besprechung gestartet hat. Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.
    
- Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings) nutzen.
    
- So stellen Sie die Anzahl der Ziffern in der PIN auf 8 Ziffern ein:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Centers viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen: 
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="see-also"></a>Mehr dazu

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
