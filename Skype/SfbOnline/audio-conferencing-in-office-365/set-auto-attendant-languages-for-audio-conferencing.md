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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Wählen Sie die Audiokonferenz-Telefonzentralen-Sprache für eine Audiokonferenznummer in Skype for Business Online.
ms.openlocfilehash: 393ba3433ba7241ca5c992114de02191b7fb1044
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788985"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online

> [!Note]
> Informationen zum Festlegen der automatischen Telefonzentralensprache in Microsoft Teams finden Sie unter [Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Die automatische Audiokonferenz-Telefonzentrale für Skype for Business kann Anrufer in verschiedenen Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die primäre Sprache, die Sie festlegen zuerst verwendet werden und die sekundären Sprachen werden durch die automatische Telefonzentrale verwendet werden, dass Sie auswählen. 
  
> [!NOTE]
>  Sie können nur die Sprachen von Audiokonferenzen Zahlen ändern, die der Kategorie dedizierten sind. Die Sprachen Shared Audiokonferenzen Zahl können nicht geändert werden.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Legen Sie die Sprachen für die automatische Telefonzentrale fest

Sie müssen ein [globaler Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder [Skype for Business-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) zum Ausführen dieses Schritts sein.
    
1. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich **Legacy**-Portal. Wählen Sie einmal **Audiokonferenzen**im legacy-Portal, und klicken Sie dann auf **Microsoft-Brücke**.
    
2. Wählen Sie die Audiokonferenz Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich, klicken Sie auf **Sprachen festlegen**. Es ist nur möglich, die Sprachen von dedizierten Audiokonferenzen Zahlen ändern.  
    
3. Klicken Sie auf der Seite **Sprachen festlegen** auf **Primäre Sprache**, um die vollständige Liste der verfügbaren Sprachen anzuzeigen. Wenn Sie möchten, klicken Sie auf die **Sekundären Sprachen**-Liste um sekundäre Sprache auszuwählen.
    
    > [!NOTE]
    > Die primär und sekundär unterstützten Sprachen werden aufgeführt. Die Reihenfolge, in der Sie sie in den Listen auswählen, wird die Reihenfolge der Sprachen zu den Anrufern präsentiert werden. 
  
4. Klicken Sie auf **Speichern**.
    
## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Unter [Unterstützte Sprachen für Audiokonferenzen](/MicrosoftTeams/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.
    
- Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen in der Audiokonferenzen in Office 365 mit Microsoft als Anbieter verfügbar ist, finden Sie unter [Rufnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Wollen Sie Windows PowerShell verwenden?

Wenn dieser Schritt automatisieren möchten, können Sie die Cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) und [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) verwenden.
  
Weitere Informationen finden Sie unter [Mithilfe von Windows PowerShell allgemeine Skype Business Online Verwaltungsaufgaben ausführen](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
