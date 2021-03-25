---
title: Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: Wählen Sie die Audiokonferenz-Telefonzentralen-Sprache für eine Audiokonferenznummer in Skype for Business Online.
ms.openlocfilehash: d2b4c0d9be666a6ee7de9c2bd36b8dd06cccdf32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109997"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online

> [!Note]
> Informationen zum Festlegen der automatischen Telefonzentralensprache in Microsoft Teams finden Sie unter [Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Die automatische Audiokonferenz-Telefonzentrale für Skype for Business kann Anrufer in verschiedenen Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die von Ihnen festgelegte Primäre Sprache wird zuerst verwendet, und die sekundären Sprachen werden von der automatischen Attendant in der von Ihnen ausgewählten Reihenfolge verwendet. 
  
> [!NOTE]
>  Sie können nur die Sprachen von Audiokonferenznummern ändern, die der Kategorie "Dedizierte" zugeordnet sind. Die Sprachen der Nummer für freigegebene Audiokonferenzen können nicht geändert werden.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Legen Sie die Sprachen für die automatische Telefonzentrale fest

Sie müssen ein globaler [Administrator oder](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Skype [for Business-Administrator sein,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) um diesen Schritt ausführen zu können.
    
1. Wechseln Sie **im Skype for Business Admin Center** in der linken Navigationsleiste zu **Legacyportal.** Wählen Sie im Legacyportal **Audiokonferenzen** aus, und klicken Sie dann auf **Microsoft Bridge.**
    
2. Wählen Sie in der Liste die Telefonnummer für Audiokonferenzen aus, und klicken Sie im Aktionsbereich **auf Sprachen festlegen.** Es ist nur möglich, die Sprachen von Dedizierte Audiokonferenznummern zu ändern.  
    
3. Klicken Sie auf der Seite **Sprachen festlegen** auf **Primäre Sprache**, um die vollständige Liste der verfügbaren Sprachen anzuzeigen. Wenn Sie möchten, klicken Sie auf die **Sekundären Sprachen**-Liste um sekundäre Sprache auszuwählen.
    
    > [!NOTE]
    > Die primär und sekundär unterstützten Sprachen werden aufgeführt. Die Reihenfolge, in der Sie sie in den Listen auswählen, ist die Reihenfolge der Sprachen, die Anrufern angezeigt werden. 
  
4. Klicken Sie auf **Speichern**.
    
## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Unter [Unterstützte Sprachen für Audiokonferenzen](/MicrosoftTeams/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.
    
- Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen, in denen Audiokonferenzen in Microsoft 365 oder Office 365 mit Microsoft als Anbieter verfügbar sind, finden Sie unter Telefonnummern für [Audiokonferenzen.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Wollen Sie Windows PowerShell verwenden?

Zum Automatisieren dieses Schritts können Sie die [Cmdlets Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) und [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) verwenden.
  
Weitere Informationen finden Sie unter Verwenden [Windows PowerShell zum Ausführen gängiger Skype for Business Online-Verwaltungsaufgaben.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)