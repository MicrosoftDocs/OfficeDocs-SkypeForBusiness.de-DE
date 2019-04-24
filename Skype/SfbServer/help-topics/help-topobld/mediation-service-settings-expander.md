---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: 12bbb6908be0f369b48c0630d97e4e01b3a91f7a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200060"
---
# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie den Vermittlungsserver auf den Front-End-Pool oder Standard Edition-Server kombinieren, aktivieren Sie das Kontrollkästchen **verbundener Vermittlungsserver aktiviert**. Wenn Sie nicht, den der Vermittlungsserver zusammenzustellen auswählen, sind keine definierbaren Einstellungen in diesem Abschnitt.

Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie die überwachungsportbereich auf dem Server für Transport Layer Security (TLS) zu definieren. Standardmäßig ist dieser Port 5067. Wenn Sie **Aktivieren TCP-Port**auswählen, müssen Sie einen Port (TCP = Transmission Control Protocol) für den verbundenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen Ihres Gateways oder öffentlichen Telefonnetz (PSTN) netzwerkanforderungen zu ermitteln, ob dies notwendig ist. Standardmäßig ist der Wert des TCP-Ports 5068.

Definieren Sie PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn Sie bereits Gateways definiert haben, werden sie zur Verfügung, die der Vermittlungsserver zugeordnet.

Wenn Sie mehr als ein Gateway einen Vermittlungsserver zugeordnet haben, wird das erste Gateway verknüpften Standardgateway sein. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition-Front-End-Pool oder Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


