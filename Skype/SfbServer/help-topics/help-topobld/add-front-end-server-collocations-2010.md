---
title: Hinzufügen der Front-End-Server-Kollokationen – 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndCollocationsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Für eine Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungsserver oder beide gemeinsam mit dem Front-End-Pool verbinden bzw. als eigenständige Server bereitstellen. Bei einer Standard Edition-Serverbereitstellung wird der A/V-Konferenzdienst stets verbunden, sofern die Konferenzfunktion aktiviert ist.
ms.openlocfilehash: c0efab1ee8b388a7d8dfa710c8937f314e83721e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626647"
---
# <a name="add-front-end-server-collocations-2010"></a>Hinzufügen der Front-End-Server-Kollokationen – 2010

Für eine Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungsserver oder beide gemeinsam mit dem Front-End-Pool verbinden bzw. als eigenständige Server bereitstellen. Bei einer Standard Edition-Serverbereitstellung wird der A/V-Konferenzdienst stets verbunden, sofern die Konferenzfunktion aktiviert ist.

> [!NOTE]
> Ein A/V-Konferenzdienst ist erforderlich, wenn **Konferenz** auf der Seite **Funktionen auswählen** ausgewählt wurde. Ein Front-End-Pool der Enterprise Edition kann einen gemeinsam ausgeführten A/V-Konferenzdienst oder eigenständigen A/V-Konferenzpool verwenden. Wenn die Konferenzfunktion nicht ausgewählt wurde, steht der Dienst zum gemeinsamen Ausführen der A/V-Konferenz nicht zur Verfügung.

Sie können die Vermittlungsserverrolle auf einem Front-End-Server der Standard Edition oder in einem Front-End-Pool der Enterprise Edition ausführen. Bei Bereitstellung von direkten SIP-Verbindungen mit einem qualifizierten PSTN-Gateway (Public Switched Telephone Network), das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungsserver erforderlich. Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können. Außerdem wird empfohlen, dass Sie den Vermittlungsserver in einem Front-End-Pool verbinden, wenn Sie IP-PBXs bereitgestellt oder eine Verbindung mit dem Session Border Controller (SBC) eines Internettelefonieserveranbieters hergestellt haben, solange eine der folgenden Bedingungen erfüllt ist:

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

Sie können das Microsoft Lync Server 2013-Planungstool verwenden, um zu bewerten, ob der Front-End-Pool, in dem Sie den Vermittlungsserver verbinden möchten, die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Im Allgemeinen wird die Kollokation von A/V-Konferenzservern oder Vermittlungsservern nicht empfohlen, wenn Ihre Organisation anforderungen an hohe Verfügbarkeit und Skalierbarkeit hat. Ausführliche Informationen zum Verbinden dieser Serverrollen in einem Front-End-Pool in einer Enterprise Edition Bereitstellung finden Sie in der Bereitstellungsdokumentation unter ["Definieren und Konfigurieren eines Front-End-Pools".](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) Ausführliche Informationen zu A/V-Konferenzfunktion und -komponenten finden Sie unter [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in der Planungsdokumentation. Ausführliche Informationen zu Enterprise-VoIP Features und Komponenten, einschließlich Vermittlungsserver, finden Sie [unter Plan for Enterprise-VoIP in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.