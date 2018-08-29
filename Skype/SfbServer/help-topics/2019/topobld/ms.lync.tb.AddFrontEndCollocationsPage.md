---
title: Hinzufügen von Front-End-Server-Kollokationen
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
ROBOTS: NOINDEX, NOFOLLOW
description: Für eine Enterprise Edition-Bereitstellung der A / V-Konferenzdienst auf den Front-End-Pool verbunden ist. Sie können auch den Vermittlungsserver auf den Front-End-Pool verbinden, oder Sie können es als eigenständiger Server bereitstellen. Der A / V-Konferenzdienst ist immer verbunden, wenn die Konferenz aktiviert ist.
ms.openlocfilehash: 07c43ee7c9e336bfa9d18a07ca73b4d278d48d22
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "23263788"
---
# <a name="add-front-end-server-collocations"></a>Hinzufügen von Front-End-Server-Kollokationen

Für eine Enterprise Edition-Bereitstellung der A / V-Konferenzdienst auf den Front-End-Pool verbunden ist. Sie können auch den Vermittlungsserver auf den Front-End-Pool verbinden, oder Sie können es als eigenständiger Server bereitstellen. Der A / V-Konferenzdienst ist immer verbunden, wenn die Konferenz aktiviert ist.

> [!NOTE]
> Ein A / V-Konferenzdienst ist erforderlich, wenn **Live Meeting** auf der Seite **Features auswählen** ausgewählt wurde. Ein Enterprise Edition-Front-End-Pool verwendet einen verbundenen A / V-Konferenzdienst. Wenn die Konferenz wurde nicht ausgewählt, die verbinden A / V-Konferenzdienst wird nicht verfügbar sein.

Sie können die Mediation Server-Rolle auf einem Standard Edition-Front-End-Server oder Enterprise Edition-Front-End-Pool verbinden. Ein eigenständiger vermittlungsserverpool ist nicht erforderlich, wenn Sie direkte SIP-Verbindungen mit einem qualifizierten Telefonfestnetz-Gateway (Telefonfestnetz), die die medienumgehung und Domain Name System (DNS) Lastenausgleich unterstützt bereitstellen. Ein eigenständiger vermittlungsserverpool ist nicht erforderlich, da qualifizierten Gateways sind in der Lage, mit dem DNS-Lastenausgleich in einen Pool von Vermittlungsservern und können sie Datenverkehr von einem beliebigen Vermittlungsserver in einem Pool empfangen. Darüber hinaus sollten Sie verbinden den Vermittlungsserver auf einem Front-End-Pool, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder die Verbindung zu einem Internet Telephony Server Provider Session Border Controller (SBC) als eine der folgenden Bedingungen erfüllt sind:

- Die IP-Nebenstellenanlage oder der SBC ist so konfiguriert, dass er Datenverkehr von einem beliebigen Vermittlungsserver im Pool empfängt und kann Datenverkehr einheitlich weiterleiten an alle Vermittlungsserver im Pool.

- Die IP-Nebenstellenanlage oder der SBC ist so konfiguriert, dass er Datenverkehr von einem beliebigen Vermittlungsserver im Pool empfängt und kann Datenverkehr einheitlich weiterleiten an alle Vermittlungsserver im Pool.

Das Planungstool können Sie ermitteln, ob der Front-End-Pool, wo Sie den Vermittlungsserver verbinden möchten, die Last verarbeiten kann. Wenn Ihre Umgebung diesen Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen vermittlungsserverpool bereitstellen.

Verbinden der Vermittlungsserver wird im Allgemeinen nicht empfohlen, wenn Ihre Organisation hohe Verfügbarkeit und Skalierbarkeitsanforderungen verfügt. Ausführliche Informationen zur Verbindung diese Serverrollen in einem Front-End-Pool in einer Enterprise Edition-Bereitstellung finden Sie unter [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zu den A / V-Konferenzen Features und Komponenten, finden unter [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in der Planungsdokumentation. Ausführliche Informationen zu Enterprise-VoIP-Features und Komponenten, einschließlich des Vermittlungsservers finden Sie unter [Planen für Enterprise-VoIP in Skype für Business Server](../../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.


