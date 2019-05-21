---
title: Einstellungen für den Vermittlungsdienst – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Für Vermittlungsserver können Sie Folgendes angeben:'
ms.openlocfilehash: fcff87faeb5911d12806f80499c2b2f0d63caff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285603"
---
# <a name="mediation-service-settings-expander"></a>Einstellungen für den Vermittlungsdienst – Erweiterung

Für **Vermittlungsserver** können Sie Folgendes angeben:

Wenn Sie den Vermittlungsserver auf dem Front-End-Pool oder auf dem Standard Edition-Server abstimmen, aktivieren Sie das Kontrollkästchen für den **Mediationsserver aktiviert**. Wenn Sie den Vermittlungs Server nicht collocate möchten, gibt es in diesem Abschnitt keine definierbaren Einstellungen.

Wenn Sie die Übertragung des Vermittlungsservers aktiviert haben, müssen Sie den Überwachungs Portbereich auf dem Server für TLS (Transport Layer Security) definieren. Standardmäßig ist dieser Port 5067. Wenn Sie **TCP-Port aktivieren**auswählen, müssen Sie einen TCP-Port (Transmission Control Protocol) für den beiliegenden Vermittlungs Server definieren. Hierbei handelt es sich um eine optionale Einstellung, auf die Sie sich beziehen sollten, um festzustellen, ob dies erforderlich ist, wenn Sie sich auf die Anforderungen Ihres Gateways oder der PSTN-Anforderungen (Public Switched Telephone Network) beziehen Standardmäßig ist der TCP-Port-Wert 5068.

Sie definieren PSTN-Gateways, die dem zusammengefassten Vermittlungs Server zugeordnet sind. Wenn Sie bereits Gateways definiert haben, stehen diese dem Vermittlungs Server zur Verfügung.

Wenn einem Vermittlungs Server mehr als ein Gateway zugeordnet ist, ist das erste zugeordnete Gateway das Standardgateway. Falls Sie ein anderes Gateway als Standardgateway auswählen müssen, markieren Sie das gewünschte Gateway und klicken Sie auf **Als Standard**. Klicken Sie auf **Festlegung als Standardeinstellung aufheben**, um die Festlegung als Standardeinstellung aufzuheben.

Details zum Definieren und Konfigurieren der Einstellungen für den Enterprise Edition-Front-End-Pool oder Standard Edition-Server finden Sie unter [definieren und Konfigurieren der Topologie](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) und [Bereitstellen von Vermittlungsservern und definieren](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)von Peers.


