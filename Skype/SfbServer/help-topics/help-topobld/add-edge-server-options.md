---
title: Hinzufügen von Edgeserveroptionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Wählen Sie die Funktionen aus, die für den Edgepool aktiviert werden sollen. Der Edgepool unterstützt standardmäßig Remotebenutzer in Ihrer Organisation, die sich außerhalb der Firewall über ein VPN (Virtuelles Privates Netzwerk) anmelden. Zudem sind die folgenden Optionen für die Edgepoolfunktionen verfügbar:'
ms.openlocfilehash: 2c266db6fc9f43719a26242212071051670a633e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283703"
---
# <a name="add-edge-server-options"></a>Hinzufügen von Edgeserveroptionen

Wählen Sie die Funktionen aus, die für den Edgepool aktiviert werden sollen. Der Edgepool unterstützt standardmäßig Remotebenutzer in Ihrer Organisation, die sich außerhalb der Firewall über ein VPN (Virtuelles Privates Netzwerk) anmelden. Zudem sind die folgenden Optionen für die Edgepoolfunktionen verfügbar:

- Verwendung eines einzigen vollqualifizierten Domänennamens (FQDN) und einer einzigen IP-Adresse für alle Edgedienste, einschließlich Zugriffs-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst. Wenn Sie die Option zur Verwendung eines einzigen FQDN und einer einzigen IP-Adresse nicht auswählen, müssen Sie bei der Bereitstellung für jeden dieser drei Edgedienste einen separaten FQDN und eine separate IP-Adresse angeben. Ausführliche Informationen zu den Edgediensten finden Sie in der Planungsdokumentation unter [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx).

    > [!NOTE]
    > Bei Auswahl dieser Option müssen Sie für jeden Edgedienst eine separate Portnummer angeben (die empfohlenen Standardporteinstellungen sind 444 für den Zugriffs-Edgedienst, 8057 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Mit dieser Option können potenzielle Konnektivitätsprobleme verhindert werden und die Konfiguration kann durch die Eingabe eines FQDN für alle drei Dienste vereinfacht werden.

- Unterstützung für den Partnerverbund. Wählen Sie diese Option, wenn die Kommunikation zwischen internen Benutzern und Benutzern in vertrauenswürdigen Domänen außerhalb der Organisation – einschließlich Benutzern eines unterstützten öffentlichen Chatanbieters – unterstützt werden soll. Bei Auswahl dieser Option müssen Sie die Unterstützung für die jeweiligen Partnerdomänen und die gewünschten Dienstanbieter für Verbindungen mit öffentlichen Chatdiensten konfigurieren. Ausführliche Informationen zum Konfigurieren der Unterstützung für den Partnerverbund und andere Typen des externen Benutzerzugriffs finden Sie unter [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) in der Edgeserver-Bereitstellungsdokumentation.

    > [!NOTE]
    > Innerhalb einer Organisation kann nur ein Front-End-Pool oder Standardedgeserver extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Instant Messaging-Dienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder den einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder den einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

- XMPP-Partnerverbund aktivieren: Wählen Sie diese Option, wenn Sie die Kommunikation zwischen internen Benutzern und vertrauenswürdigen XMPP-Partnern unterstützen möchten.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern zu einer vorhandenen Topologie finden Sie in der Edgeserver-Bereitstellungsdokumentation unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


