---
title: Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern
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
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Rufen Sie die Schritte zum Erstellen einer Standardrufnummer für Anrufer teilnehmen an einer Besprechung Microsoft-Teams. '
ms.openlocfilehash: 3e6aae2c01962a4cd3c704cded1e284dc2975d28
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464244"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Audiokonferenzen in Office 365 ermöglicht Benutzern in Ihrer Organisation zum Erstellen von Microsoft-Teams, Besprechungen, und klicken Sie dann zulassen, dass Benutzer in diesen treffen mit einem Telefon einwählen.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Anfänglicher Zuweisung von Telefonnummern, die in der Besprechung enthalten sind invites für neue Benutzer

Die Telefonnummern, die Bestandteil der Besprechung erhalten invites von Benutzern für Audiokonferenzen definieren, indem Sie die Standard-Konferenzen gebührenpflichtige Telefonnummer und den Standard-Konferenzen gebührenfreie Telefonnummer Zahl Einstellungen des Benutzers aktiviert. Jede Einstellung gibt an, welche gebührenpflichtige oder gebührenfreie Telefonnummer in der besprechungseinladung eines bestimmten Benutzers eingeschlossen werden sollen. Wie bereits erwähnt, enthält jede Besprechung einladen, eine gebührenpflichtige Nummer, eine optionale gebührenfreie Telefonnummer und ein Link, der die vollständige Liste der alle Zugriffsnummer für Einwahl Telefonnummern wird geöffnet, die Teilnahme an einer bestimmten Besprechung verwendet werden können.

Für einen neuen Benutzer werden die standardmäßigen Conferencing gebührenfreie Nummern zugewiesen je nach Land, das in der Office 365-Profil des Benutzers festgelegt wird, wenn der Benutzer für die Audiokonferenz-Dienst aktiviert ist. Befindet sich eine gebührenpflichtige Telefonnummer in die Konferenzbrücke, die das Land des Benutzers entspricht, wird diese Nummer automatisch als die gebührenpflichtige Standardnummer des Benutzers zugeordnet werden. Wenn nicht vorhanden ist, wird die Zahl, die als die gebührenpflichtige Standardanzahl zulässiger die Konferenzbrücke definiert ist als die gebührenpflichtige Standardnummer des Benutzers zugeordnet werden.  

Nachdem der Benutzer für die Audiokonferenz-Dienst aktiviert ist, können die standardmäßige gebührenpflichtigen und gebührenfreien Telefonnummern des Benutzers vom mandantenadministrator aus die Anfangswerte jederzeit geändert werden.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Festlegen oder Ändern von Audiokonferenzen Standardrufnummer ein Organisator der Besprechung oder eines Benutzers

![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

    ![Zeigt die Auswahl von Benutzern in der Verwaltungskonsole von Microsoft-Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

    ![Klicken Sie auf Bearbeiten in der Verwaltungskonsole von Microsoft-Teams](media/teams-set-phone-numbers-on-invites-image2.png)

3. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**. 
    
    ![Klicken Sie auf Bearbeiten neben Audiokonferenzen](media/teams-set-phone-numbers-on-invites-image3.png)

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
