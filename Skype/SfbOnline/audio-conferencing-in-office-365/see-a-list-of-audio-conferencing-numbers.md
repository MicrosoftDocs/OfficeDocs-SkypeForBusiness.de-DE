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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie, wie Sie Ihre Einwahlkonferenznummern in Skype for Business Online suchen. '
ms.openlocfilehash: e152cd5d54cd9e1e318027c57cbc4ffda938360b
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012099"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Eine Liste der Audiokonferenznummern in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Informationen zu Audiokonferenznummern in Microsoft Teams finden Sie unter Sehen Sie sich eine Liste der [Audiokonferenznummern in Microsoft Teams an.](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams)

Wenn Sie Audiokonferenzen für Skype for Business-Benutzer einrichten, können Sie die für Audiokonferenzen verfügbaren Telefonnummern anzeigen. Diese Liste enthält alle Audiokonferenz-Telefonnummern, die für Ihre Organisation verfügbar sind.
  
 **Suchen Sie nach Preisen?** Weitere Informationen finden Sie unter [Audiokonferenz] https://www.microsoft.com/microsoft-teams/audio-conferencing) .
  
> [!IMPORTANT]
> **Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält.** Wenn Sie sehen möchten, ob Einwahltelefonnummern in Ihrer Region oder Ihrem Land/Ihrer Region verfügbar sind, wechseln Sie zu **Skype for Business Admin Center**–  >  **Voice**  >  **Phone Numbers**(Sprachtelefonnummern)  und dann auf Hinzufügen und dann auf Neue Servicenummern . Verwenden Sie die Listen für **Land/Region**, **Bundesland/Kanton** und **Ort**, um die Suchergebnisse zu filtern. Wenn Sie nach gebührenfreien Leistungsnummern suchen, wählen Sie außerdem **gebührenfrei** in der Liste **Bundesland/Region** aus.
  
Wenn für Ihre Organisation nur eine Telefonnummer verfügbar ist, wird sie als Standardtelefonnummer für alle Benutzer verwendet. Wenn mehrere Telefonnummern verfügbar sind, können Sie für jeden Benutzer eine Standardtelefonnummer auswählen. Diese Standardnummer ist in den Skype for Business-Besprechungseinladungen enthalten.
  
Informationen zum [Ändern der Einwahltelefonnummer](set-the-phone-numbers-included-on-invites.md) für einen einzelnen Benutzer finden Sie unter Festlegen der in Einladungen enthaltenen Telefonnummern.
  
> [!NOTE]
> Inländische Einwahlnummern sind Ihrer Organisation zugeordnet. Nur solche Nummern können als Standardtelefonnummer eingestellt werden. Internationale Einwahlnummern können von mehreren Organisationen gemeinsam verwendet werden. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>So zeigen Sie Ihre Audiokonferenz-Telefonnummern an

1. Melden Sie sich mit Ihrem Arbeits- oder Schulkonto an.
    
2. Wechseln Sie zum Admin Center > **Skype for Business**.
    
3. Wechseln Sie **im Skype for Business Admin Center** in der linken Navigationsleiste zu Audio **conferencing** Microsoft Bridge , und gehen Sie  >  dann wie hier:
    
   - Sie können die für Audiokonferenzen verfügbaren Telefonnummern anzeigen.
    
   - Sie können auch den Standort sowie die primären und sekundären Sprachen anzeigen, die von der automatischen Telefonkonferenz-Telefonkonferenz verwendet werden.
    
> [!NOTE]
> Sie können zu **Benutzer von Audiokonferenzen** wechseln und die Eigenschaften des Benutzers auswählen, um die Standardnummer zu ändern, indem Sie eine neue Nummer aus der Liste der verfügbaren Nummern  >   in Ihrer Organisation auswählen. Siehe [Festlegen der in Einladungen enthaltenen Telefonnummern](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Get-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Get-CsOnlineDialInConferencingServiceNumber) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Centers viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter Herunterladen und Installieren des [Teams PowerShell-Moduls heruntergeladen werden.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
