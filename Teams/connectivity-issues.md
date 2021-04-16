---
title: Behandeln von Verbindungsproblemen mit dem Teams-Client
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101161"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a>Behandeln von Konnektivitätsproblemen mit dem Microsoft Teams-Client
==============================================================

Die meisten Probleme, die mit dem Microsoft Teams-Client festgestellt wurden, lassen sich auf die Firewall- oder Proxy-Verbindungen zurückführen. Wenn Sie sicherstellen, dass die notwendigen URLs, IP-Adressen und Ports in Ihrer Firewall oder Ihrem Proxy freigegeben sind, können Sie unnötige Problembehandlungen minimieren. Spezifische Informationen zu URLs und IPs, die für Microsoft Teams erforderlich sind, finden Sie im Support-Artikel zu [Microsoft 365- und Office 365-URLs und -IP-Adressen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2). Die folgende Szenarien benötigen spezifische, freigegebene URLs und Ports in der Firewall.

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