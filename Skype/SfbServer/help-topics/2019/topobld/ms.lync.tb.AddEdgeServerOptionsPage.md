---
title: Hinzufügen von Edgeserveroptionen
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 'Wählen Sie die Funktionen aus, die für den Edgepool aktiviert werden sollen. Standardmäßig unterstützt der Edgepool Remotebenutzer in Ihrer Organisation, die sich über ein virtuelles privates Netzwerk (VPN) von außerhalb der Firewall anmelden. Zudem sind die folgenden Optionen für die Edgepoolfunktionen verfügbar:'
ms.openlocfilehash: 9ac07d7a15e138c3fe817aab6754ca098f8ff774
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834483"
---
# <a name="add-edge-server-options"></a>Hinzufügen von Edgeserveroptionen

Wählen Sie die Funktionen aus, die für den Edgepool aktiviert werden sollen. Standardmäßig unterstützt der Edgepool Remotebenutzer in Ihrer Organisation, die sich über ein virtuelles privates Netzwerk (VPN) von außerhalb der Firewall anmelden. Zudem sind die folgenden Optionen für die Edgepoolfunktionen verfügbar:

- Verwendung eines einzigen vollqualifizierten Domänennamens (FQDN) und einer einzigen IP-Adresse für alle Edgedienste, einschließlich Zugriffs-Edgedienst, Webkonferenz-Edgedienst und A/V-Edgedienst. Wenn Sie die Option zur Verwendung eines einzigen FQDN und einer einzigen IP-Adresse nicht auswählen, müssen Sie bei der Bereitstellung für jeden dieser drei Edgedienste einen separaten FQDN und eine separate IP-Adresse angeben. Ausführliche Informationen zu den Edgediensten finden Sie unter [Components Required for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-components-required-for-external-user-access) in der Planungsdokumentation.

    > [!NOTE]
    > Bei Auswahl dieser Option müssen Sie für jeden Edgedienst eine separate Portnummer angeben (die empfohlenen Standardporteinstellungen sind 444 für den Zugriffs-Edgedienst, 8057 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Mit dieser Option können potenzielle Konnektivitätsprobleme verhindert werden, und die Konfiguration kann durch die Eingabe eines FQDN für alle drei Dienste vereinfacht werden.

- Unterstützung für den Partnerverbund. Wählen Sie diese Option, wenn die Kommunikation zwischen internen Benutzern und Benutzern in vertrauenswürdigen Domänen außerhalb der Organisation – einschließlich Benutzer eines unterstützten öffentlichen Instant Messaging-Anbieters – unterstützt werden soll. Bei Auswahl dieser Option müssen Sie die Unterstützung für die jeweiligen Partnerdomänen und die gewünschten Dienstanbieter für Verbindungen mit öffentlichen Instant Messaging-Diensten konfigurieren. Ausführliche Informationen zum Konfigurieren der Unterstützung für den Partnerverbund und andere Typen des externen Benutzerzugriffs finden Sie unter [Configuring Support for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-support-for-external-user-access) in der Edgeserver-Bereitstellungsdokumentation.

    > [!NOTE]
    > Innerhalb einer Organisation kann nur ein Front-End-Pool oder Standardedgeserver extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzer öffentlicher Instant Messaging-Dienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

- XMPP-Partnerverbund aktivieren: Wählen Sie diese Option, wenn Sie die Kommunikation zwischen internen Benutzern und vertrauenswürdigen XMPP-Partnern unterstützen möchten.

Sie können Unterstützung für den externen Benutzerzugriff beim Bereitstellen der anfänglichen Topologie oder zu einem späteren Zeitpunkt hinzufügen. Ausführliche Informationen zum Hinzufügen von Edgeservern zu einer vorhandenen Topologie finden Sie unter [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in der Edgeserver-Bereitstellungsdokumentation.