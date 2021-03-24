---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: 60312afc4ab487be474eeef6a8432e3522058275
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104421"
---
# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie den Vermittlungsserver mit dem Front-End-Pool oder dem Standard Edition-Server verbinden, aktivieren Sie das Kontrollkästchen Vermittlungsserver **aktiviert.** Wenn Sie den Vermittlungsserver nicht verbinden möchten, gibt es in diesem Abschnitt keine definierbaren Einstellungen.

Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungsportbereich des Servers für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen (Public Switched Telephone Network, Telefonfestnetz) dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

Sie definieren PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway, und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Weitere Informationen zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition-Front-End-Pool oder Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).