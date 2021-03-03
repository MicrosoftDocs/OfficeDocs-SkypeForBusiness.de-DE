---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: b3b22cfbe4b85a237dfffbce1c22da3abde75f57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819505"
---
# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie den Vermittlungsserver mit dem Front-End-Pool oder dem Standard Edition-Server verbinden, aktivieren Sie das Kontrollkästchen **"Collocated Mediation Server" aktiviert.** Wenn Sie den Vermittlungsserver nicht verbinden möchten, gibt es in diesem Abschnitt keine eindefinierbaren Einstellungen.

Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungsportbereich des Servers für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen (Public Switched Telephone Network, Telefonfestnetz) dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

Sie definieren PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway, und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Weitere Informationen zum Definieren und Konfigurieren der Einstellungen für den Front-End-Pool der Enterprise Edition oder den Standard Edition-Server finden Sie unter Definieren und Konfigurieren der [Topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und Bereitstellen von [Vermittlungsservern](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)und Definieren von Peers .


