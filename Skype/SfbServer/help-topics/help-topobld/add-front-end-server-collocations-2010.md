---
title: Hinzufügen von Front-End-Server-Kollokationen – 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Bei einer Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungs Server oder beide im Front-End-Pool collocate, oder Sie können jede als eigenständige Server bereitstellen. Bei einer Standard Edition-Server Bereitstellung befindet sich der a/V-Konferenzdienst immer, wenn Konferenzen aktiviert sind.
ms.openlocfilehash: 8a8191f29a30052fec837ee9136203eb5db1ee0d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275353"
---
# <a name="add-front-end-server-collocations-2010"></a>Hinzufügen von Front-End-Server-Kollokationen – 2010

Bei einer Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungs Server oder beide im Front-End-Pool collocate, oder Sie können jede als eigenständige Server bereitstellen. Bei einer Standard Edition-Server Bereitstellung befindet sich der a/V-Konferenzdienst immer, wenn Konferenzen aktiviert sind.

> [!NOTE]
> Ein A/V-Konferenzdienst ist erforderlich, wenn **Konferenz** auf der Seite **"Features auswählen** " ausgewählt wurde. Bei einem Enterprise Edition-Front-End-Pool wird möglicherweise ein a/v-Konferenzdienst oder ein eigenständiger a/v-Konferenz Pool verwendet. Wenn Konferenz nicht ausgewählt wurde, ist der Collocate A/V-Konferenzdienst nicht verfügbar.

Sie können die collocate-Funktion auf einem Front-End-Server der Standard Edition oder in Enterprise Edition-Front-End-Pool übernehmen. Wenn Sie direkte SIP-Verbindungen zu einem qualifizierten PSTN-Gateway (Public Switched Telephone Network) bereitstellen, das die medienumgehung und den DNS-Lastenausgleich (Domain Name System) unterstützt, ist kein eigenständiger Vermittlungs Server Pool erforderlich. Ein eigenständiger Vermittlungs Server Pool ist nicht erforderlich, da qualifizierte Gateways in der Lage sind, den DNS-Lastenausgleich zu einem Pool von Vermittlungsservern durchzuführen und Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen können. Wir empfehlen außerdem, dass Sie den Vermittlungs Server in einem Front-End-Pool collocate, wenn Sie IP-PBX-Anlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Serveranbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:

- Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.

- Die IP-PBX-oder SBC-Konfiguration ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver im Pool konfiguriert und kann den Datenverkehr gleicherweise an alle Vermittlungsserver im Pool weiterleiten.

Sie können das Planungs Tool Microsoft lync Server 2013 verwenden, um zu evaluieren, ob der collocate, in dem Sie den Vermittlungsserver belegen möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungs Server Pool bereitstellen.

Im Allgemeinen wird die Zusammenstellung von A/V-Konferenzservern oder Vermittlungsservern nicht empfohlen, wenn Ihre Organisation über eine höhere Verfügbarkeit und Skalierbarkeit verfügt requirementsFor Details zu abstimmen dieser Serverrollen in einem Front-End-Pool in einer Enterprise-Edition Bereitstellung finden Sie unter [definieren und Konfigurieren eines Front-End-Pools](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation. Details zu den A/V-Konferenzfeatures und-Komponenten finden Sie unter [Planen von Konferenzen](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in der Planungsdokumentation. Details zu den Enterprise-VoIP-Features und-Komponenten, einschließlich Mediation Server, finden Sie unter [Planen von Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.


