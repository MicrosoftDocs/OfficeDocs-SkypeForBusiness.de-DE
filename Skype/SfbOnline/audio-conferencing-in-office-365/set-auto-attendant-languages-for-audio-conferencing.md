---
title: Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Finden Sie unter Wählen Sie die Audiokonferenz Auto attendant Sprachen für eine Audiokonferenz Zahl.
ms.openlocfilehash: c4461f61ce05afedc2663a3e5b61d37370394cd4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Festlegen der automatischen Telefonzentrale Sprachen für Audio-Konferenzen

Die Audiokonferenz automatische Telefonzentrale für Skype für Unternehmen und die Microsoft-Teams kann Anrufer audio in einer Reihe von verschiedenen Sprachen begrüßen, beim Beitritt zu einer Besprechung.
  
Wählen Sie eine primäre Sprache und bis zu vier sekundäre Sprachen. Die primäre Sprache, die Sie festlegen zuerst verwendet werden und die sekundären Sprachen werden durch die automatische Telefonzentrale verwendet werden, dass Sie auswählen. 
  
> [!NOTE]
>  Sie können die Sprachen auf nur Telefonnummern nationalen audio Zugriff konfigurieren.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Festlegen der Konferenzen Auto attendant Sprachen

![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**

1. Wechseln Sie im linken Navigationsbereich auf **Besprechungen** > **Konferenz Brücken**.

2. Wählen Sie die Audiokonferenz Telefonnummer aus der Liste aus, und klicken Sie am oberen Rand der Seite aus, klicken Sie auf **Bearbeiten**.

3. Wählen Sie im Bereich auf der rechten Seite die gewünschten Standardsprache und alle alternativen Sprachen. 
 
    > [!NOTE]
    > Der standardmäßige und alternative Sprachen, die unterstützt werden, sind aufgeführt. Die Reihenfolge, in der Sie sie in den Listen auswählen, wird die Reihenfolge der Sprachen zu den Anrufern präsentiert werden. 

4. Klicken Sie auf **Anwenden**.

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **Skype für Unternehmen online verwenden**

Sie müssen ein [globaler Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) oder [Skype für Business-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) zum Ausführen dieses Schritts sein.
    
1. Navigieren Sie in der linken Navigationsleiste des **Skype for Business Admin Center** zu **Audio conferencing** (Audiokonferenz), und klicken Sie dann auf **Microsoft Bridge**.
    
2. Wählen Sie die Audiokonferenz Telefonnummer aus der Liste aus, und klicken Sie im Aktionsbereich, klicken Sie auf **Sprachen festlegen**. 
    
3. Klicken Sie auf der Seite **festlegen Sprachen** auf der Liste der **primären Sprache** , um die vollständige Liste der verfügbaren Sprachen anzuzeigen. Wenn Sie möchten, klicken Sie auf die **sekundären Sprachen** Listen sekundären Sprache auszuwählen.
    
    > [!NOTE]
    > Die primären und sekundären Sprachen, die unterstützt werden, sind aufgeführt. Die Reihenfolge, in der Sie sie in den Listen auswählen, wird die Reihenfolge der Sprachen zu den Anrufern präsentiert werden. 
  
4. Klicken Sie auf **Speichern**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-else-should-i-know"></a>Was sollte ich noch wissen?

- Die Liste der unterstützten Sprachen für Audiokonferenzen, finden Sie unter [Audiokonferenzen unterstützte Sprachen](audio-conferencing-supported-languages.md).
    
- Sprachen können für dedizierte, aber nicht nach freigegebenen Telefonnummern festgelegt werden.
    
- Eine Liste der Länder/Regionen in der Audiokonferenzen in Office 365 mithilfe von Microsoft als Anbieter verfügbar ist, finden Sie unter [Rufnummern für Audiokonferenzen](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>Windows PowerShell verwenden?

Wenn dieser Schritt automatisieren möchten, können Sie die Cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) und [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) verwenden.
  
Weitere Informationen finden Sie unter [Mithilfe von Windows PowerShell allgemeine Skype Business Online Verwaltungsaufgaben ausführen](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See Also

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
