---
title: Anzeigen einer Liste der Audiokonferenz Zahlen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to look up your dial-in conferencing numbers from within Skype for Business. '
ms.openlocfilehash: d4e1ef41a02a0197133d2b5cc08a4f35f961e4ee
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="see-a-list-of-audio-conferencing-numbers"></a>Anzeigen einer Liste der Audiokonferenz Zahlen

Wenn Sie Audiokonferenzen für Skype für Unternehmen und die Microsoft-Teams, einrichten, können Sie die angezeigten Rufnummern anzeigen, die Ihnen für Audiokonferenzen verfügbar sind. Diese Liste müssen alle Rufnummern Audiokonferenzen, die für Ihre Organisation verfügbar sind.
  
 **Sie suchen Preise?** Finden Sie unter [Preise für Audiokonferenzen](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Es ist keine Ressource, die eine Auflistung aller die Einwahlnummern für Audiokonferenzen enthält.** Wenn Sie suchen, um festzustellen, ob in Ihrer Stadt oder Land/Region-Einwahl Telefonnummern vorhanden sind, gehen Sie zu **Skype für Business Administrationscenter** > **VoIP** > **Telefonnummern**klicken Sie auf **Hinzufügen**, und klicken Sie dann auf **neuen Dienst Zahlen**. Verwenden Sie die Listen für **Land/Region**, **Bundesland/Kanton** und **Ort**, um die Suchergebnisse zu filtern. Auch wenn Sie für gebührenfreie Service Zahlen suchen, wählen Sie **gebührenfreie Rufnummer** aus **Bundesland/Kanton** Liste.
  
Wenn für Ihre Organisation nur eine Telefonnummer verfügbar ist, wird sie als Standardtelefonnummer für alle Benutzer verwendet. Wenn mehrere Telefonnummern verfügbar sind, können Sie für jeden Benutzer eine Standardtelefonnummer auswählen. Diese Standardrufnummer wird in Skype für Geschäfts- und Microsoft-Teams, besprechungseinladungen enthalten sein.
  
Finden Sie unter So ändern Sie die Telefonnummer Zugriffsnummer für Einwahl für einen einzelnen Benutzer [gewählte Nummern auf enthalten invites Telefonnummern festgelegt](set-the-phone-numbers-included-on-invites.md) .
  
> [!NOTE]
> Inländische Einwahlnummern sind Ihrer Organisation zugeordnet. Nur solche Nummern können als Standardtelefonnummer eingestellt werden. Internationale Einwahlnummern können von mehreren Organisationen gemeinsam verwendet werden. 
  
## <a name="to-view-your-audio-conferencing-phone-numbers"></a>So zeigen Sie Ihre Rufnummern Audiokonferenzen an

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
    
3. Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Microsoft Bridge**, und führen Sie dann:
    
  - Sie können die Telefonnummern anzeigen, die für Audiokonferenzen verfügbar sind.
    
  - Sie können auch den Speicherort anzeigen, und die primären und sekundären Sprachen, die durch die Audiokonferenz verwendet werden automatische Telefonzentrale.
    
> [!NOTE]
> Sie können wechseln Sie zur **Audiokonferenz** > **Benutzer** und wählen Sie Eigenschaften so ändern Sie die Standardeinstellung des Benutzers zu nummerieren, indem Sie eine neue Nummer aus der Liste der verfügbaren Nummern in Ihrer Organisation auswählen. Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](set-the-phone-numbers-included-on-invites.md). 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 über einen zentralen Administrationspunkt verwalten und so Ihre tägliche Arbeit vereinfachen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet gegenüber der alleinigen Verwendung des Office 365 Admin Center unzählige Vorteile in Bezug auf Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie die Einstellungen für viele Benutzer gleichzeitig ändern. In den folgenden Themen erfahren Sie mehr über diese Vorteile:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>See Also

[Testen oder Erwerben von Audiokonferenzen in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
