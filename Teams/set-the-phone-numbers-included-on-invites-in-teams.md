---
title: Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie die Schritte zum Erstellen einer Standardtelefonnummer, über die Anrufer an einer Microsoft Teams-Besprechung teilnehmen können. '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882960"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Mit Audiokonferenzen in Office 365 können Benutzer in Ihrer Organisation Microsoft Teams-Besprechungen erstellen und Benutzern die telefonische Einwahl in die Besprechung ermöglichen. In Office 365 haben Sie die Möglichkeit, eine Microsoft-Audiokonferenzbrücke oder eine Audiokonferenzbrücke von einem Drittanbieter zu verwenden, die von einem genehmigten Audiokonferenzanbieter (ACP) gehostet wird.
  
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
