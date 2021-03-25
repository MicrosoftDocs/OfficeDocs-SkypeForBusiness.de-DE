---
title: Festlegen automatischer Telefonkonferenzsprachen für Audiokonferenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Erfahren Sie, wie Sie die Sprachen für automatische Audiokonferenzen für eine Audiokonferenznummer in Microsoft Teams auswählen.
ms.openlocfilehash: 0a27015fefe8c290f8e122f5d9edf46aa3c8583f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117183"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a>Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams

Die automatische Telefonkonferenz für Microsoft Teams kann Audioanrufer in einer Reihe verschiedener Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die von Ihnen festgelegte Primäre Sprache wird zuerst verwendet, und die sekundären Sprachen werden von der automatischen Attendant in der von Ihnen ausgewählten Reihenfolge verwendet. 
  
> [!NOTE]
>  Sie können nur die Sprachen von Audiokonferenznummern ändern, die der Kategorie "Dedizierte" zugeordnet sind. Die Sprachen der Nummer für freigegebene Audiokonferenzen können nicht geändert werden.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Legen Sie die Sprachen für die automatische Telefonzentrale fest

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Navigieren Sie in der linken Navigationsleiste zu **Besprechungen** > **Conference Bridges** (Konferenzbrücken).

2. Wählen Sie **in** der Liste eine Telefonnummer für dedizierte Audiokonferenzen aus, und klicken Sie oben auf der Seite auf **Bearbeiten.** Es ist nur möglich, die Sprachen von Dedizierte Audiokonferenznummern zu ändern. Die **Option** Bearbeiten wird nur angezeigt, wenn eine Dedizierte Audiokonferenznummer ausgewählt ist.

3. Wählen Sie im Bereich auf der rechten Seite die Standardsprache und alle anderen Sprachen aus. 
 
    > [!NOTE]
    > Die unterstützten Standardsprachen und alternativen Sprachen werden aufgelistet. Die Reihenfolge, in der Sie sie in den Listen auswählen, ist die Reihenfolge der Sprachen, die Anrufern angezeigt werden. 

4. Klicken Sie auf **Speichern**.

    
## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Unter [Unterstützte Sprachen für Audiokonferenzen](/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.
    
- Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen, in denen Audiokonferenzen in Microsoft 365 oder Office 365 mit Microsoft als Anbieter verfügbar sind, finden Sie unter Telefonnummern für [Audiokonferenzen.](phone-numbers-for-audio-conferencing-in-teams.md)
    
## <a name="want-to-use-windows-powershell"></a>Wollen Sie Windows PowerShell verwenden?

Weitere Informationen finden Sie in der [Microsoft Teams PowerShell-Referenz.](/powershell/module/teams/?view=teams-ps)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)