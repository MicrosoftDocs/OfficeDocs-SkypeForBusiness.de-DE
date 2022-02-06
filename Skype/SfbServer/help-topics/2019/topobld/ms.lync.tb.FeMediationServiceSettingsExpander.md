---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
---

# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie den Vermittlungsserver in den Front-End-Pool oder den Standard Edition-Server verbinden, aktivieren Sie das Kontrollkästchen **"Verbundener Vermittlungsserver" aktiviert**. Wenn Sie den Vermittlungsserver nicht verbinden möchten, gibt es in diesem Abschnitt keine definierbaren Einstellungen.

Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungsportbereich des Servers für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen (Public Switched Telephone Network, Telefonfestnetz) dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

Sie definieren PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway, und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition Front-End-Pool oder Standard Edition-Server finden Sie unter ["Definieren und Konfigurieren der Topologie](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) und [Bereitstellen von Vermittlungsservern und Definieren von Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)".