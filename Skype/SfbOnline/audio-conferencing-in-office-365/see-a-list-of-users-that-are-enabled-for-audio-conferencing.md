---
title: Eine Liste der Benutzer, die für Audiokonferenzen in Ihrer Online Skype for Business sind
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bd0cd155-4c6d-424d-a2c9-af7974a2d34c
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
description: 'Erfahren Sie, wie Sie eine Liste der Benutzer in Ihrer Organisation anzeigen, die im Skype for Business Admin Center für Einwahlkonferenzen aktiviert sind. '
ms.openlocfilehash: 91ac12b07465491b2b8e721f7e876bb9e35cd9af
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618291"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Eine Liste der Benutzer, die für Audiokonferenzen in Ihrer Online Skype for Business sind

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Informationen zu aktivierten Benutzern in Microsoft Teams finden Sie unter Eine Liste der Benutzer, die für [Audiokonferenzen in](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams)Microsoft Teams.

Nachdem Sie die Skype for Business in Ihrer Organisation für Audiokonferenzen aktiviert haben, können Sie die Liste der aktivierten Benutzer anzeigen. Wenn Sie sich die Liste anschauen, sehen Sie auch für jeden Benutzer in der Liste den Typ des verwendeten Audiokonferenzanbieters, die Standardeinwahlnummer für den Benutzer und, wenn Ihre Organisation nicht für dynamische Konferenz-IDs aktiviert ist, die statischen Konferenz-IDs für Audiokonferenzbesprechungen, die er organisiert.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Anzeige einer Benutzerliste

   
- |||UNTRANSLATED_CONTENT_START|||In the left navigation, go to **Audio conferencing** > **Users**.|||UNTRANSLATED_CONTENT_END|||

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Wenn Sie die Liste der aktivierten Benutzer anzeigen, können Sie einen Benutzer aus der Liste auswählen und den Aktionsbereich verwenden, um die Audiokonferenzeinstellungen für diesen Benutzer zu bearbeiten.
    
- Wenn Sie einen einzelnen Benutzer auswählen, der für die Verwendung von Microsoft als Audiokonferenzanbieter konfiguriert ist, können Sie die Standardtelefonnummer anzeigen und festlegen, ob Ihre Organisation für dynamische Konferenz-IDs aktiviert ist, und Sie können die Konferenz-ID für vom Benutzer organisierten Besprechungen zurücksetzen.
    
- Wenn Sie einen einzelnen Benutzer auswählen, der für die Verwendung eines Drittanbieters für Audiokonferenzen konfiguriert ist, können Sie (sofern eingerichtet) den Namen des Audiokonferenzanbieters, die gebührenpflichtige Telefonnummer und die gebührenfreie Telefonnummer anzeigen.
    
- Mithilfe der Filteroptionen können Sie Benutzer mit folgenden Eigenschaften aufrufen:
    
  - **Audiokonferenzen ein**
    
  - **Audiokonferenzen deaktiviert**
    
  - **Konferenzanbieter - Microsoft**
    
  - **Konferenzanbieter - Andere**
    
- Über die Schaltfläche „Suchen" können Sie Benutzer in der Liste suchen.
    
- Sie können auch mehrere Benutzer auswählen und folgende Aktionen vornehmen:
    
  - Für diese Benutzer eine andere Standardnummer wählen.
    
  - Deaktivieren Sie Audiokonferenzen für den Benutzer, indem Sie den Anbieter in Keine **ändern.**
    
  - Wechseln Sie zu Microsoft als Audiokonferenzanbieter, wenn dem Benutzer eine Lizenz für **Audiokonferenzen zugewiesen** wurde.
    
  - Zulassen/nicht zulassen, dass anonyme Benutzer die Telefonbesprechungen der ausgewählten Benutzer aktivieren.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365, Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung der Microsoft 365 Admin Center gegenüber Geschwindigkeit, Einfachheit und Produktivität viele Vorteile, z. B. wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
