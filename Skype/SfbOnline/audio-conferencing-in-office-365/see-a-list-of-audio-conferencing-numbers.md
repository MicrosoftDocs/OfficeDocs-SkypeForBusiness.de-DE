---
title: Eine Liste der Audiokonferenznummern in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 2d6b4ed4-e12b-4691-8405-fae720d69425
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
description: 'Erfahren Sie, wie Sie Ihre Einwahlkonferenznummern in Skype for Business Online nachschauen. '
ms.openlocfilehash: f7343010cfdc34325d2f164b5560c542af0551ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114151"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Eine Liste der Audiokonferenznummern in Skype for Business Online

> [!NOTE]
> Informationen zu Audiokonferenznummern in Microsoft Teams finden Sie unter Eine Liste der Nummern für [Audiokonferenzen in Microsoft Teams.](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)

Wenn Sie Audiokonferenzen für Skype for Business-Benutzer einrichten, können Sie die Telefonnummern anzeigen, die ihnen für Audiokonferenzen zur Verfügung stehen. Diese Liste enthält alle Telefonnummern für Audiokonferenzen, die für Ihre Organisation verfügbar sind.
  
 **Suchen Sie nach Preisen?** Weitere Informationen finden Sie unter Preise [für Audiokonferenzen.](https://products.office.com/skype-for-business/audio-conferencing#Requirements)
  
> [!IMPORTANT]
> **Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält.** Wenn Sie sehen möchten, ob in Ihrer Region oder Ihrem Land/Ihrer Region Einwahlnummern verfügbar sind, wechseln Sie zu **Skype for Business Admin Center** Voice Phone Numbers , klicken Sie auf Hinzufügen und dann auf Neue  >    >   **Servicenummern**.  Verwenden Sie die Listen für **Land/Region**, **Bundesland/Kanton** und **Ort**, um die Suchergebnisse zu filtern. Wenn Sie außerdem nach gebührenfreien Servicenummern suchen, wählen Sie **in** der Liste **Bundesland/Region** die Option Gebührenfrei aus.
  
Wenn für Ihre Organisation nur eine Telefonnummer verfügbar ist, wird sie als Standardtelefonnummer für alle Benutzer verwendet. Wenn mehrere Telefonnummern verfügbar sind, können Sie für jeden Benutzer eine Standardtelefonnummer auswählen. Diese Standardnummer wird in Skype for Business-Besprechungseinladungen enthalten.
  
Sie sehen Festlegen der [Telefonnummern, die in](set-the-phone-numbers-included-on-invites.md) Einladungen enthalten sind, um die Einwahltelefonnummer für einen einzelnen Benutzer zu ändern.
  
> [!NOTE]
> Inländische Einwahlnummern sind Ihrer Organisation zugeordnet. Nur solche Nummern können als Standardtelefonnummer eingestellt werden. Internationale Einwahlnummern können von mehreren Organisationen gemeinsam verwendet werden. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>So zeigen Sie Ihre Telefonnummern für Audiokonferenzen an

1. Melden Sie sich mit Ihrem Arbeits-, Schul- oder Schulkonto an.
    
2. Wechseln Sie zum Admin Center > **Skype for Business**.
    
3. Wechseln Sie **im Skype for Business Admin Center** in der linken Navigation zu Microsoft Bridge für **Audiokonferenzen**  >  und dann:
    
   - Sie können die Telefonnummern anzeigen, die für Audiokonferenzen verfügbar sind.
    
   - Sie können auch den Speicherort sowie die primären und sekundären Sprachen anzeigen, die von der automatischen Telefonkonferenz für Audiokonferenzen verwendet werden.
    
> [!NOTE]
> Sie können zu **Audiokonferenz benutzer** wechseln und die Eigenschaften des Benutzers auswählen, um die Standardnummer zu ändern, indem Sie in der Liste der verfügbaren Nummern in Ihrer Organisation eine neue  >   Nummer auswählen. Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
