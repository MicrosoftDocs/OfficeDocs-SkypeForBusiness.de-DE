---
title: Anzeigen einer Liste von Audiokonferenz-Nummern in Skype for Business Online
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
description: 'Erfahren Sie, wie Sie Ihre Einwahlkonferenz Nummern in Skype for Business Online nachschlagen können. '
ms.openlocfilehash: 48cca375f2039a1cebbd07100a8bcd8d275f55f0
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164684"
---
# <a name="see-a-list-of-audio-conferencing-numbers-in-skype-for-business-online"></a>Anzeigen einer Liste von Audiokonferenz-Nummern in Skype for Business Online

> [!NOTE]
> Informationen zu Audiokonferenz-Nummern in Microsoft Teams finden Sie unter [Anzeigen einer Liste der Audiokonferenznummer in Microsoft Teams](/MicrosoftTeams/see-a-list-of-audio-conferencing-numbers-in-teams).

Wenn Sie Audiokonferenzen für Skype for Business-Benutzer einrichten, können Sie die Telefonnummern anzeigen, die für Audiokonferenzen zur Verfügung stehen. Diese Liste enthält alle Audiokonferenz-Telefonnummern, die für Ihre Organisation verfügbar sind.
  
 **Suchen Sie nach Preisen?** Siehe [Preise für Audiokonferenzen](https://products.office.com/skype-for-business/audio-conferencing#Requirements).
  
> [!IMPORTANT]
> **Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält.** Wenn Sie feststellen möchten, ob Einwahlnummern in Ihrem Land/Ihrer Region verfügbar sind, gehen Sie zu **Skype for Business Admin Center** > **Voice** > -**Telefonnummern**, klicken Sie auf **Hinzufügen**und dann auf **neue Service Nummern**. Verwenden Sie die Listen für **Land/Region**, **Bundesland/Kanton** und **Ort**, um die Suchergebnisse zu filtern. Wenn Sie nach gebührenfreien Servicenummern suchen, wählen Sie **gebührenfrei** in der Liste **Bundesland/Region** .
  
Wenn für Ihre Organisation nur eine Telefonnummer verfügbar ist, wird sie als Standardtelefonnummer für alle Benutzer verwendet. Wenn mehrere Telefonnummern verfügbar sind, können Sie für jeden Benutzer eine Standardtelefonnummer auswählen. Diese Standardnummer wird in Skype for Business-Besprechungseinladungen enthalten sein.
  
Sie können [feststellen, welche Telefonnummern in Einladungen enthalten sind](set-the-phone-numbers-included-on-invites.md) , um die Einwahl Telefonnummer für einen einzelnen Benutzer zu ändern.
  
> [!NOTE]
> Inländische Einwahlnummern sind Ihrer Organisation zugeordnet. Nur solche Nummern können als Standardtelefonnummer eingestellt werden. Internationale Einwahlnummern können von mehreren Organisationen gemeinsam verwendet werden. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="to-view-your-audio-conferencing-phone-numbers"></a>So zeigen Sie Ihre Audiokonferenz-Telefonnummern an

1. Mit Ihrem Firmen-oder Schulkonto anmelden
    
2. Wechseln Sie zum Admin Center > **Skype for Business**.
    
3. Wechseln Sie im **Skype for Business Admin Center**in der linken Navigationsleiste zu **Audio Conferencing** > **Microsoft Bridge**, und klicken Sie dann auf:
    
   - Sie können die Telefonnummern anzeigen, die für Audiokonferenzen zur Verfügung stehen.
    
   - Sie können auch den Standort sowie die primären und sekundären Sprachen anzeigen, die von der automatischen Telefonzentrale für Audiokonferenzen verwendet werden.
    
> [!NOTE]
> Sie können zu **Audiokonferenz** > -**Benutzern** wechseln und die Eigenschaften des Benutzers auswählen, um die Standardnummer zu ändern, indem Sie in der Liste der verfügbaren Nummern in Ihrer Organisation eine neue Nummer auswählen. Weitere Informationen finden Sie unter [Einrichten der Telefonnummern, die in Einladungen enthalten sind](set-the-phone-numbers-included-on-invites.md). 

  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Get-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) nutzen.
    
- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell bietet zahlreiche Vorteile bei der Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Mithilfe des Windows PowerShell-Moduls für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, bei der eine Verbindung mit Skype for Business Online hergestellt wird. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden.
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
  
