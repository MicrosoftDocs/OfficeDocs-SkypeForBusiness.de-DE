---
title: Hinzufügen von Front-End-Server-Kollokationen – 2010
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Für eine Enterprise Edition-Bereitstellung möglich, entweder den A / V-Konferenzdienst, den Vermittlungsserver oder beides auf den Front-End-Pool, oder Sie können jede als eigenständige Server bereitstellen. Für einen Standard Edition-Server-Bereitstellung, A / V-Konferenzdienst ist immer verbunden, wenn die Konferenz aktiviert ist.
ms.openlocfilehash: 42fd773c8874ec1416ac8c161bc60b8baba52f0e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875341"
---
# <a name="add-front-end-server-collocations-2010"></a>Hinzufügen von Front-End-Server-Kollokationen – 2010

Für eine Enterprise Edition-Bereitstellung möglich, entweder den A / V-Konferenzdienst, den Vermittlungsserver oder beides auf den Front-End-Pool, oder Sie können jede als eigenständige Server bereitstellen. Für einen Standard Edition-Server-Bereitstellung, A / V-Konferenzdienst ist immer verbunden, wenn die Konferenz aktiviert ist.

> [!NOTE]
> Ein A / V-Konferenzdienst ist erforderlich, wenn **Live Meeting** auf der Seite **Features auswählen** ausgewählt wurde. Möglicherweise verwenden Sie ein Enterprise Edition-Front-End-Pool einen verbundenen A / V-Konferenzdienst oder einen eigenständigen A / V-konferenzpool. Wenn die Konferenz wurde nicht ausgewählt, die verbinden A / V-Konferenzdienst wird nicht verfügbar sein.

Sie können die Mediation Server-Rolle auf einem Standard Edition-Front-End-Server oder Enterprise Edition-Front-End-Pool verbinden. Ein eigenständiger vermittlungsserverpool ist nicht erforderlich, wenn Sie direkte SIP-Verbindungen mit einem qualifizierten Telefonfestnetz-Gateway (Telefonfestnetz), die die medienumgehung und Domain Name System (DNS) Lastenausgleich unterstützt bereitstellen. Ein eigenständiger vermittlungsserverpool ist nicht erforderlich, da qualifizierten Gateways sind in der Lage, mit dem DNS-Lastenausgleich in einen Pool von Vermittlungsservern und können sie Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen. Darüber hinaus sollten Sie verbinden den Vermittlungsserver auf einem Front-End-Pool, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder die Verbindung zu einem Internet Telephony Server Provider Session Border Controller (SBC) als eine der folgenden Bedingungen erfüllt sind:

- Die IP-Nebenstellenanlage oder der SBC ist so konfiguriert, dass er Datenverkehr von einem beliebigen Vermittlungsserver im Pool empfängt und kann Datenverkehr einheitlich weiterleiten an alle Vermittlungsserver im Pool.

- Die IP-Nebenstellenanlage oder der SBC ist so konfiguriert, dass er Datenverkehr von einem beliebigen Vermittlungsserver im Pool empfängt und kann Datenverkehr einheitlich weiterleiten an alle Vermittlungsserver im Pool.

Sie können die Microsoft Lync Server 2013, Planungstool untersuchen, ob der Front-End-Pool, wo Sie den Vermittlungsserver verbinden möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diesen Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen vermittlungsserverpool bereitstellen.

Im Allgemeinen, Verbinden von A / V-Konferenzserver oder Vermittlungsserver wird nicht empfohlen, wenn Ihre Organisation hohe Verfügbarkeit und Skalierbarkeit herangehen Details über diese Serverrollen in einem Front-End-Pool in einer Enterprise Edition Verbindung verfügt. Bereitstellung, finden Sie unter [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zu den A / V-Konferenzen Features und Komponenten, finden unter [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in der Planungsdokumentation. Ausführliche Informationen zu Enterprise-VoIP-Features und Komponenten, einschließlich des Vermittlungsservers finden Sie unter [Planen für Enterprise-VoIP in Skype für Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.


