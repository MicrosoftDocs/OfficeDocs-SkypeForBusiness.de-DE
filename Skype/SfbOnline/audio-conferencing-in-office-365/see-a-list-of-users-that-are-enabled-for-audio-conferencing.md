---
title: Anzeigen einer Liste der Benutzer, die für Audiokonferenzen in Skype for Business Online aktiviert sind
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to view a list of users in your organization that are enabled for dial-in conferencing from within the Skype for Business admin center. '
ms.openlocfilehash: 2d48d628f77f651477287ff0b22701a2e7fd74e5
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792338"
---
# <a name="see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-skype-for-business-online"></a>Anzeigen einer Liste der Benutzer, die für Audiokonferenzen in Skype for Business Online aktiviert sind

> [!NOTE]
> Informationen zu aktivierten Benutzern in Microsoft Teams finden Sie unter [Anzeigen einer Liste der Benutzer, die in Microsoft Teams für Audiokonferenzen aktiviert sind](/MicrosoftTeams/see-a-list-of-users-that-are-enabled-for-audio-conferencing-in-teams).

Nachdem Sie Skype for Business-Benutzer in Ihrer Organisation für Audiokonferenzen aktiviert haben, können Sie die Liste der Benutzer anzeigen, die aktiviert wurden. Wenn Sie sich die Liste ansehen, sehen Sie auch für jeden Benutzer in der Liste den Typ des verwendeten Audiokonferenz-Anbieters, die Standard-Einwahl Telefonnummer für den Benutzer, und wenn Ihre Organisation für dynamische Konferenz-IDs nicht aktiviert ist, werden die statischen Konferenz-IDs für Audiokonferenz-Besprechungen, die Sie organisieren.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="viewing-a-list-of-users"></a>Anzeige einer Benutzerliste

   
- |||UNTRANSLATED_CONTENT_START|||In the left navigation, go to **Audio conferencing** > **Users**.|||UNTRANSLATED_CONTENT_END|||

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Wenn Sie die Liste der aktivierten Benutzer anzeigen, können Sie in der Liste einen Benutzer auswählen und im Bereich "Aktion" die Einstellungen für die Audiokonferenz für diesen Benutzer bearbeiten.
    
- Wenn Sie einen einzelnen Benutzer auswählen, der für die Verwendung von Microsoft als Anbieter von Audiokonferenzen konfiguriert ist, können Sie die Standardtelefonnummer anzeigen und angeben, ob Ihre Organisation für dynamische Konferenz-IDs aktiviert ist, und Sie können die Konferenz-ID für Besprechungen zurücksetzen, die von der der Benutzer organisiert.
    
- Wenn Sie einen einzelnen Benutzer auswählen, der für die Verwendung eines Drittanbieters für Audiokonferenzen konfiguriert ist, können Sie den Namen des Audiokonferenz-Anbieters, die gebührenpflichtige Telefonnummer und die gebührenfreie Telefonnummer anzeigen (sofern diese eingerichtet sind).
    
- Mithilfe der Filteroptionen können Sie Benutzer mit folgenden Eigenschaften aufrufen:
    
  - **Audiokonferenzen an**
    
  - **Audiokonferenz deaktiviert**
    
  - **Konferenzanbieter - Microsoft**
    
  - **Konferenzanbieter - Andere**
    
- Über die Schaltfläche „Suchen" können Sie Benutzer in der Liste suchen.
    
- Sie können auch mehrere Benutzer auswählen und folgende Aktionen vornehmen:
    
  - Für diese Benutzer eine andere Standardnummer wählen.
    
  - Deaktivieren Sie Audiokonferenzen für den Benutzer, indem Sie den Anbieter in **None**ändern.
    
  - Wechseln Sie zu Microsoft als Audiokonferenz-Anbieter, wenn dem Benutzer eine **Audiokonferenz-** Lizenz zugewiesen wurde.
    
  - Zulassen/nicht zulassen, dass anonyme Benutzer die Telefonbesprechungen der ausgewählten Benutzer aktivieren.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online mit einem zentralen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn mehrere Aufgaben ausgeführt werden müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
