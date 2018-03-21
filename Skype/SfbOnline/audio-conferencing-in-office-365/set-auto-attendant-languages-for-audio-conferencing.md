---
title: "Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Finden Sie unter Wählen Sie die Audiokonferenz Auto attendant Sprachen für eine Audiokonferenz Zahl."
ms.openlocfilehash: 85dd6fb9328e3362d84315f7c8a7f3d7e8e2df86
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen

Die Audiokonferenz automatische Telefonzentrale für Skype für Unternehmen und die Microsoft-Teams kann Anrufer audio in einer Reihe von verschiedenen Sprachen begrüßen, beim Beitritt zu einer Besprechung.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die primäre Sprache, die Sie festlegen zuerst verwendet werden und die sekundären Sprachen werden durch die automatische Telefonzentrale verwendet werden, dass Sie auswählen. 
  
> [!NOTE]
>  Sie können die Sprachen auf nur Telefonnummern nationalen audio Zugriff konfigurieren.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Festlegen der Konferenzen Auto attendant Sprachen

Sie müssen ein [globaler Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder [Skype für Business-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) zum Ausführen dieses Schritts sein.
  
1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.
    
4. Wählen Sie die Audiokonferenz Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich, klicken Sie auf **Sprachen festlegen**. 
    
5. Klicken Sie auf der Seite **festlegen Sprachen** auf der Liste der **primären Sprache** , um die vollständige Liste der verfügbaren Sprachen anzuzeigen. Wenn Sie möchten, klicken Sie auf die **sekundären Sprachen** Listen sekundären Sprache auszuwählen.
    
    > [!NOTE]
    > Die primären und sekundären Sprachen, die unterstützt werden, sind aufgeführt. Die Reihenfolge, in der Sie sie in den Listen auswählen, wird die Reihenfolge der Sprachen zu den Anrufern präsentiert werden. 
  
6. Klicken Sie auf **Speichern**.
    
## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Die Liste der unterstützten Sprachen für Audiokonferenzen, finden Sie unter [Audiokonferenzen unterstützte Sprachen](audio-conferencing-supported-languages.md).
    
- Sprachen können für dedizierte, aber nicht nach freigegebenen Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen in der Audiokonferenzen in Office 365 mithilfe von Microsoft als Anbieter verfügbar ist, finden Sie unter [Rufnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell verwenden?

Wenn dieser Schritt automatisieren möchten, können Sie die Cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) und [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) verwenden.
  
Weitere Informationen finden Sie unter [Mithilfe von Windows PowerShell allgemeine Skype Business Online Verwaltungsaufgaben ausführen](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See Also

[Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](set-up-audio-conferencing.md)

