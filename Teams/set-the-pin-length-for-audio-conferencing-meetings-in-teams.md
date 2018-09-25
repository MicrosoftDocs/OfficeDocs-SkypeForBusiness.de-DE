---
title: Festlegen der Länge der PIN für Audiokonferenzbesprechungen in Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Hier erhalten Sie Informationen zu den Parametern für die PIN-Länge und die Anforderungen an PINs. Außerdem erfahren Sie, wie Sie die Länge für Besprechungen in Microsoft Teams festlegen.
ms.openlocfilehash: db7c62920dc7440cc8356dd3f5275dd551cdfd78
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014917"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Festlegen der Länge der PIN für Audiokonferenzbesprechungen in Microsoft Teams

Wenn Sie Audiokonferenzen für Microsoft-Teams, einrichten, erhalten Sie eine audiokonferenzbrücke. Eine Konferenzbrücke kann eine oder mehr Telefonnummern umfassen. Die Telefonnummer, die Sie festlegen, wird auf die Besprechung einladen für die Microsoft-Teams app enthalten sein.
  
Die audiokonferenzbrücke beantwortet einen Anruf für Personen, die in einer Besprechung mit einem Telefon einwählen. Von einer automatischen Telefonzentrale und aktivieren Sie dann je nach Ihrer Einstellungen für den Anrufer mit Ansagen Fragen, können Benachrichtigungen wiedergeben, und bitten Anrufer, ihren Namen aufzuzeichnen. **Microsoft-Brücke Einstellungen** können Sie die Einstellungen für Benachrichtigungen für Besprechungen zu ändern und die Besprechung-Teilnahme an, und legen Sie die Länge der Stifte, die von Besprechungsorganisatoren verwendet werden. Besprechungsorganisatoren verwenden PINs Besprechungen starten, wenn die Besprechung mithilfe der Microsoft-Teams app aufgenommen werden können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Festlegen der PIN-Länge

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken). 

2. Klicken Sie oben auf der Seite **Conference Bridges** (Konferenzbrücken) auf **Bridge Settings** (Brückeneinstellungen). 

3. Wählen Sie im Bereich **Bridge settings** (Brückeneinstellungen) unter **PIN-Länge** die gewünschte Ziffernanzahl für die PIN aus.

4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Eine PIN hat nichts mit einer Konferenz-ID zu tun. Konferenz-IDs werden von Anrufern bei der Teilnahme an einer Besprechung verwendet. Sie dienen der Kennzeichnung der Besprechung. Anhand der PIN wird ein Anrufer als Organisator der Besprechung authentifiziert. 

## <a name="want-to-know-more-about-pin-settings"></a>Möchten Sie mehr über PIN-Einstellungen erfahren?

- PINs können von 4 bis 12 Ziffern annehmen. Der Standardwert ist 5. PINs können nur Zahlen umfassen. Buchstaben und Sonderzeichen sind nicht zulässig.
    
- Eine PIN ist nur für Organisator der Besprechung erforderlich, wenn ein Benutzer Microsoft-Teams, die Besprechung noch nicht bereits gestartet. Wenn sich alle Teilnehmer in die Besprechung einwählen, ist die PIN erforderlich, damit der Organisator der Besprechung die Besprechung starten kann.
    
- Die PIN-Sicherheitseinstellungen gelten für alle Telefonnummern, die zu einer Microsoft-Brücke gehören. Sie gelten für alle Besprechungen, bei denen zu einer bestimmten Audiokonferenzbrücke gehörende Telefonnummern genutzt werden. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
