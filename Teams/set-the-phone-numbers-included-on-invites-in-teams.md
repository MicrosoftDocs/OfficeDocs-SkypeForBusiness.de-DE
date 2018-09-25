---
title: Festlegen des Telefons, die Zahlen enthalten auf invites in Microsoft-Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Rufen Sie die Schritte zum Erstellen einer Standardrufnummer für Anrufer teilnehmen an einer Besprechung Microsoft-Teams. '
ms.openlocfilehash: f62a6e63181c474d19f403d6c81f858177bd8cd0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016197"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Audiokonferenzen in Office 365 ermöglicht Benutzern in Ihrer Organisation zum Erstellen von Microsoft-Teams, Besprechungen, und klicken Sie dann zulassen, dass Benutzer in diesen treffen mit einem Telefon einwählen. In Office 365 verfügen Sie über die Möglichkeit, eine audiokonferenzbrücke von Microsoft oder einem Drittanbieter-audiokonferenzbrücke, die von einem Provider genehmigte Audiokonferenzen (ACP) gehostet wird.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer in der Liste der verfügbaren Benutzer aus.

    ![Zeigt das Auswählen von Benutzern im Admin Center für Microsoft Teams und Skype for Business.](media/teamsselectusers.png)

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

    ![Klicken Sie im Admin Center für Microsoft Teams und Skype for Business auf „Bearbeiten“.](media/teamsedituser.png)

3. Klicken Sie neben **Audiokonferenz** auf **Bearbeiten**. 
    
    ![Klicken Sie neben „Audiokonferenz“ auf „Bearbeiten“.](media/teamseditaudioconf.png)

4. Verwenden Sie die Felder **Gebührenpflichtige Nummer** und **Gebührenfreie Nummer**, um die Nummern für den Benutzer einzugeben.


> [!IMPORTANT]
> Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen Besprechungsserien und zukünftige Microsoft Teams-Besprechungen aktualisiert und an die Teilnehmer gesendet werden. 

## <a name="want-to-use-windows-powershell"></a>Möchten Sie Windows PowerShell verwenden?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
