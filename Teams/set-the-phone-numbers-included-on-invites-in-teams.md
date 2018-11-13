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
ms.openlocfilehash: 859bf6f4a99f95c67123385c99061b1546eaa60c
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296271"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Mit Audiokonferenzen in Office 365 können Benutzer in Ihrer Organisation Microsoft Teams-Besprechungen erstellen und Benutzern die telefonische Einwahl in die Besprechung ermöglichen. In Office 365 haben Sie die Möglichkeit, eine Microsoft-Audiokonferenzbrücke oder eine Audiokonferenzbrücke von einem Drittanbieter zu verwenden, die von einem genehmigten Audiokonferenzanbieter (ACP) gehostet wird.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) Verwenden des Microsoft-Teams und Skype for Business-Verwaltungskonsole

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

    ![Zeigt die Auswahl von Benutzern in der Microsoft-Teams und Skype für Business Admin Center](media/teamsselectusers.png)

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

    ![Klicken Sie auf Bearbeiten in der Microsoft-Teams und Skype für Business Admin Center](media/teamsedituser.png)

3. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**. 
    
    ![Klicken Sie auf Bearbeiten neben Audiokonferenzen](media/teamseditaudioconf.png)

4. Verwenden Sie die Felder **gebührenpflichtige** oder **gebührenfreie Nummer** , die Zahlen für den Benutzer eingeben.


> [!IMPORTANT]
> Wenn Sie einen Benutzer Audiokonferenzen Einstellungen ändern, müssen sich wiederholenden und zukünftige Microsoft-Teams, Besprechungen aktualisiert und an die Teilnehmer gesendet werden. 

## <a name="want-to-use-windows-powershell"></a>Wollen Sie Windows PowerShell verwenden?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Erwerben von Audiokonferenzen in Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
