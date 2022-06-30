---
title: Behandeln von Verbindungsproblemen mit dem Teams-Client
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Behandeln Sie Konnektivitätsprobleme mit dem Microsoft Teams-Client, die in erster Linie durch die Firewall- oder Proxyverbindung verursacht werden, und informieren Sie sich, wie Sie diese beheben können.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8974aa7cf54ab61cb15650b839185daad1b82cc7
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562164"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Behandeln von Konnektivitätsproblemen mit dem Microsoft Teams-Client

Die meisten erkannten Probleme mit dem Microsoft Teams-Client sind auf die Firewall- oder Proxykonnektivität zurückzuführen. Wenn Sie sich vergewissern, dass die notwendigen URLs, IP-Adressen und Ports in der Firewall oder im Proxy geöffnet sind, können Sie unnötige Problembehandlungsmaßnahmen auf ein Minimum reduzieren. Konkrete Informationen zu den für Microsoft Teams erforderlichen URLs und IPs finden Sie im Supportartikel [Microsoft 365 und Office 365 URLs und IP-Adressen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). Für die folgenden Szenarien müssen bestimmte URLs und Ports in der Firewall geöffnet sein.

- Authentifizierung

- Microsoft Teams-Clientkonnektivität

- Zusammenarbeit

- Medien

- Gemeinsame Dienste

- Drittanbieterintegration

- Interoperabilität von Skype for Business

- Interoperabilität des Skype for Business-Clients

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a>Wenn Teams offline oder unter Bedingungen mit geringer Bandbreite ist

Die gute Nachricht ist, dass Teams weiter ausgeführt wird, auch wenn Sie offline oder unter Bedingungen mit geringer Bandbreite sind. Teams speichert alle nicht gesendeten Nachrichten für vorhandene Chats (bis zu 24 Stunden) und sendet sie, sobald Sie wieder online sind. Wenn Sie länger als 24 Stunden offline sind, lässt Teams Sie auswählen, ob nicht gesendete Nachrichten erneut gesendet oder gelöscht werden sollen. Wir arbeiten am Hinzufügen dieser Funktionalität für neue Chats und werden diese Dokumentation aktualisieren, sobald dies verfügbar ist.

## <a name="related-topics"></a>Verwandte Themen

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)