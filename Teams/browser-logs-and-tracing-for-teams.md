---
title: Browserprotokolle und Ablaufverfolgung für Teams
author: wlibebe
ms.author: wlibebe
manager: serdars
ms.date: 06/21/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Erfahren Sie mehr über browser- und WebRTC-Protokolle, die von Microsoft Teams erstellt wurden, wo sie zu finden sind, wie Sie Protokolle mit Microsoft-Support sammeln und wie sie bei der Überwachung und Problembehandlung helfen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9592091d97ad4fb34f02e906888757f0c7ab14ec
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005467"
---
# <a name="browser-logs-and-tracing-for-teams"></a>Browserprotokolle und Ablaufverfolgung für Teams

Bei einigen Kategorien von Fehlern müssen Microsoft-Support möglicherweise eine Browserablaufverfolgung sammeln. Diese Informationen können wichtige Details zum Status des Teams-Clients liefern, wenn der Fehler auftritt. In diesem Artikel wird beschrieben, wie Browser- und WebRTC-Protokolle für Teams gesammelt werden.

## <a name="browser-logs"></a>Browserprotokolle

Bevor Sie die Browserablaufverfolgung starten, stellen Sie sicher, dass Sie bei Teams angemeldet sind. Dies ist wichtig, bevor Sie die Ablaufverfolgung starten, damit die Ablaufverfolgung keine vertraulichen Anmeldeinformationen enthält.

Nachdem Sie sich angemeldet haben, wählen Sie je nach Browser einen der folgenden Links aus, und führen Sie die angegebenen Schritte aus. 

-   [Chrome & Edge (Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> Ersetzen Sie in den Schritten alle Verweise auf die Azure-Portal durch den Teams-Client.
  
## <a name="webrtc-logs-in-browsers"></a>WebRTC-Protokolle in Browsern

WebRTC-Protokolle können Microsoft-Support unterstützen, indem Verbindungsdetails für Audio- und Videoanrufe bereitgestellt werden. Führen Sie die Schritte aus, um auf die WebRTC-Protokolle in Edge (Chromium) oder Chrome zuzugreifen:
  
1. Öffnen Sie eine neue Registerkarte, und wechseln Sie zu einer der folgenden URLs:
    - Edge (Chromium):`edge://webrtc-internals/`
    - Chrome: `chrome://webrtc-internals/`
  
2. Öffnen Sie die Teams-Webanwendung, und reproduzieren Sie das Problem.
  
3. Zurück zu der Registerkarte, auf die in Schritt 1 zugegriffen wurde, und es werden mindestens zwei Registerkarten angezeigt:
    - GetUserMedia-Anforderungen
    - `https://teams.microsoft.com/url`

4. Wählen Sie die Registerkarte mit dem Namen der Teams-Anwendung aus, und speichern Sie den Seiteninhalt.

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)

[Konfigurieren von Protokolldateien für die Überwachung und Problembehandlung in Teams](/MicrosoftTeams/log-files)
