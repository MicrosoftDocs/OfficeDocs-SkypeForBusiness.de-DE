---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: ae8cf24e9d4ba42f3b97a8f32e0bcdaf2aae4c77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912015"
---
# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie den Vermittlungsserver auf den Front-End-Pool oder Standard Edition-Server kombinieren, aktivieren Sie das Kontrollkästchen **verbundener Vermittlungsserver aktiviert**. Wenn Sie nicht, den der Vermittlungsserver zusammenzustellen auswählen, sind keine definierbaren Einstellungen in diesem Abschnitt.

Wenn Sie die gemeinsame Ausführung des Vermittlungsservers aktiviert haben, müssen Sie die überwachungsportbereich auf dem Server für Transport Layer Security (TLS) zu definieren. Standardmäßig ist dieser Port 5067. Wenn Sie **Aktivieren TCP-Port**auswählen, müssen Sie einen Port (TCP = Transmission Control Protocol) für den verbundenen Vermittlungsserver definieren. Dies ist eine optionale Einstellung, und verweisen Sie auf die Anforderungen Ihres Gateways oder öffentlichen Telefonnetz (PSTN) netzwerkanforderungen zu ermitteln, ob dies notwendig ist. Standardmäßig ist der Wert des TCP-Ports 5068.

Definieren Sie PSTN-Gateways, die dem verbundenen Vermittlungsserver zugeordnet sind. Wenn Sie bereits Gateways definiert haben, werden sie zur Verfügung, die der Vermittlungsserver zugeordnet.

Wenn Sie mehr als ein Gateway einen Vermittlungsserver zugeordnet haben, wird das erste Gateway verknüpften Standardgateway sein. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition-Front-End-Pool oder Standard Edition-Server finden Sie unter [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).


