---
title: Festlegen der Länge der PIN für Audiokonferenzbesprechungen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Lernen Sie die Parameter für die Länge und Anforderungen einer PIN sowie die Länge für Besprechungen in einem Microsoft Teams.
ms.openlocfilehash: 7030849f59679ff63e71e6013757a1e455fa951d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731954"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Festlegen der Länge der PIN für Audiokonferenzbesprechungen in Microsoft Teams

Wenn Sie Audiokonferenzen für Microsoft Teams einrichten, erhalten Sie eine Audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Die von Ihnen festgelegte Telefonnummer wird in den Besprechungs-Einladungen für die App Microsoft Teams eingeschlossen.
  
Die Audiokonferenzbrücke nimmt Anrufe von Benutzern an, die sich über ein Telefon in eine Besprechung einwählen. Sie beantwortet den Anrufer mit Sprachanrufen einer automatischen Telefonisten und kann dann je nach Ihren Einstellungen Benachrichtigungen abspielen und Anrufer bitten, ihren Namen zu notieren. **Mit den Einstellungen von Microsoft Bridge** können Sie die Einstellungen für Besprechungsbenachrichtigungen und die Teilnahme an Besprechungen ändern und die Länge der PINs festlegen, die von Besprechungsorganisatoren verwendet werden. Besprechungsorganisatoren verwenden PINs, um Besprechungen zu starten, wenn sie nicht über die App "Besprechungs-App Microsoft Teams können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Konfigurieren der PIN-Länge

![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Wählen Sie **im Bereich Einstellungen der** Brücke unter **PIN-Länge** die Anzahl der Ziffern für die PIN aus.

4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert. 

## <a name="want-to-know-more-about-pin-settings"></a>Möchten Sie mehr über PIN-Einstellungen erfahren?

- PINs können zwischen 4 und 12 Ziffern sein. der Standardwert ist 5. PINs können nur Zahlen umfassen. Buchstaben und Sonderzeichen sind nicht zulässig.
    
- Eine PIN ist für den Besprechungsorganisator nur erforderlich, wenn ein Microsoft Teams noch nicht die Besprechung gestartet hat. Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.
    
- Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)