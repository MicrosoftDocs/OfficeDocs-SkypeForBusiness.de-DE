---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215146"
---
# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie das Vermittlungsserver auf dem Front-End-Pool oder dem Standard Edition-Server abstimmen, aktivieren Sie das Kontrollkästchen verbunden **Vermittlungsserver aktiviert**. Wenn Sie die Vermittlungsserver nicht collocate, gibt es in diesem Abschnitt keine definierbaren Einstellungen.

Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungsportbereich des Servers für Transport Layer Security (TLS) festlegen. Standardmäßig lautet dieser Port 5067. Wenn Sie **TCP-Port aktivieren** aktivieren, müssen Sie für den verbundenen Vermittlungsserver einen TCP-Port (Transmission Control Protocol) angeben. Diese Einstellung ist optional. Überprüfen Sie die Gateway- bzw. PSTN-Anforderungen (Public Switched Telephone Network, Telefonfestnetz) dahingehend, ob diese Einstellung erforderlich ist. Standardmäßig ist der Wert des TCP-Ports auf 5068 festgelegt.

Sie definieren PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn bereits Gateways definiert wurden, stehen sie für eine Zuordnung zum Vermittlungsserver zur Verfügung.

Wenn einem Vermittlungsserver mehrere Gateways zugeordnet sind, ist das erste zugeordnete Gateway das Standardgateway. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway, und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Enterprise Edition-Front-End-Pool oder-Standard Edition-Server finden Sie unter [definieren und Konfigurieren der Topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Bereitstellen von Vermittlungsservern und Definieren von Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


