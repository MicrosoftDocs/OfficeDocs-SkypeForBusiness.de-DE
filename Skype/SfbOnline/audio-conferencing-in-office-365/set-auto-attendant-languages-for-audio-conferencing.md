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
ms.openlocfilehash: 044d05ec8b67f1e7732140a90c47b0666568fafe241fe3a45f2d02c46824e903
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326991"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Informationen zum Festlegen der automatischen Telefonzentralensprache in Microsoft Teams finden Sie unter [Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Die automatische Audiokonferenz-Telefonzentrale für Skype for Business kann Anrufer in verschiedenen Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die primäre Sprache, die Sie festlegen, wird zuerst verwendet, und die sekundären Sprachen werden von der automatischen Attendant in der von Ihnen ausgewählten Reihenfolge verwendet. 
  
> [!NOTE]
>  Sie können nur die Sprachen von Audiokonferenznummern ändern, die der Kategorie De dedicated zugeordnet sind. Die Sprachen der Nummer für freigegebene Audiokonferenzen können nicht geändert werden.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Legen Sie die Sprachen für die automatische Telefonzentrale fest

Sie müssen ein globaler Administrator [oder ein Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) [sein,](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) um diesen Schritt ausführen zu können.
    
1. Wechseln Sie **Skype for Business admin center** in der linken Navigationsleiste zum **Legacyportal**. Wählen Sie im Legacyportal **Audio conferencing (Audiokonferenz)** aus, und klicken Sie dann auf **Microsoft Bridge.**
    
2. Wählen Sie die Telefonnummer für Audiokonferenzen aus der Liste aus, und klicken Sie im Aktionsbereich auf **Sprachen festlegen.** Es ist nur möglich, die Sprachen von De dedicated audio conferencing numbers zu ändern.  
    
3. Klicken Sie auf der Seite **Sprachen festlegen** auf **Primäre Sprache**, um die vollständige Liste der verfügbaren Sprachen anzuzeigen. Wenn Sie möchten, klicken Sie auf die **Sekundären Sprachen**-Liste um sekundäre Sprache auszuwählen.
    
    > [!NOTE]
    > Die primär und sekundär unterstützten Sprachen werden aufgeführt. Die Reihenfolge, in der Sie diese in den Listen auswählen, ist die Reihenfolge, in der die Sprachen Anrufern angezeigt werden. 
  
4. Klicken Sie auf **Speichern**.
    
## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Unter [Unterstützte Sprachen für Audiokonferenzen](/MicrosoftTeams/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.
    
- Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen, in denen Audiokonferenzen in Microsoft 365 oder Office 365 mit Microsoft als Anbieter verfügbar sind, finden Sie unter Telefon-Nummern für [Audiokonferenzen.](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>Wollen Sie Windows PowerShell verwenden?

Zum Automatisieren dieses Schritts können Sie die [Cmdlets Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) und [Get-CsOnlineDialInConferencingLanguagesSupported](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported) verwenden.
  
Weitere Informationen finden Sie unter Verwenden [von Windows PowerShell zum Ausführen Skype for Business Online-Verwaltungsaufgaben.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
