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
ms.openlocfilehash: 34ed4ccee5239923f68b089ce14551fe43c32320
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776800"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Automatische Telefonzentralen-Spracheinstellung für Audiokonferenzen in Skype for Business Online

> [!Note]
> Informationen zum Festlegen der automatischen Telefonzentralensprache in Microsoft Teams finden Sie unter [Einrichten von automatischen Telefonzentralensprachen für Audiokonferenzen in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

Die automatische Audiokonferenz-Telefonzentrale für Skype for Business kann Anrufer in verschiedenen Sprachen begrüßen, wenn sie an einer Besprechung teilnehmen.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Sie können nur die Sprachen der Audiokonferenz-Nummern ändern, die der dedizierten Kategorie entsprechen. Die Sprachen der freigegebenen Audiokonferenz-Nummer können nicht geändert werden.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Legen Sie die Sprachen für die automatische Telefonzentrale fest

Sie müssen ein [globaler Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder ein [Skype for Business-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) sein, um diesen Schritt ausführen zu können.
    
1. Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu **Legacy Portal**. Wählen Sie im Legacy Portal **Audio Conferencing**aus, und klicken Sie dann auf **Microsoft Bridge**.
    
2. Wählen Sie die Telefonnummer für Audiokonferenzen in der Liste aus, und klicken Sie im Bereich "Aktion" auf **Sprachen festlegen**. Es ist nur möglich, die Sprachen für dedizierte Audiokonferenz-Nummern zu ändern.  
    
3. Klicken Sie auf der Seite **Sprachen festlegen** auf **Primäre Sprache**, um die vollständige Liste der verfügbaren Sprachen anzuzeigen. Wenn Sie möchten, klicken Sie auf die **Sekundären Sprachen**-Liste um sekundäre Sprache auszuwählen.
    
    > [!NOTE]
    > Die primär und sekundär unterstützten Sprachen werden aufgeführt. Die Reihenfolge, in der Sie Sie in den Listen auswählen, ist die Reihenfolge der für die Anrufer vorgestellten Sprachen. 
  
4. Klicken Sie auf **Speichern**.
    
## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Unter [Unterstützte Sprachen für Audiokonferenzen](/MicrosoftTeams/audio-conferencing-supported-languages) finden Sie eine Liste der für Audiokonferenzen unterstützten Sprachen.
    
- Sprachen können für dedizierte, aber nicht für freigegebene Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen in der Audiokonferenzen in Office 365 mit Microsoft als Anbieter verfügbar ist, finden Sie unter [Rufnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Wollen Sie Windows PowerShell verwenden?

Um diesen Schritt zu automatisieren, können Sie die Cmdlets " [Satz-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) " und " [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) " verwenden.
  
Weitere Informationen finden Sie unter [Verwenden von Windows PowerShell zum Ausführen häufiger Skype for Business Online-Verwaltungsaufgaben](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
