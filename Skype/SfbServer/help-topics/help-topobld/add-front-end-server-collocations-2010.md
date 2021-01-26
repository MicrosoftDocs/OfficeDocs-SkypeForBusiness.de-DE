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
localization_priority: Normal
ms.assetid: 4d328bf4-85bc-4870-8d6f-008c0e46520e
description: Für eine Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungsserver oder beide gemeinsam mit dem Front-End-Pool verbinden bzw. als eigenständige Server bereitstellen. Bei einer Standard Edition-Serverbereitstellung wird der A/V-Konferenzdienst stets verbunden, sofern die Konferenzfunktion aktiviert ist.
ms.openlocfilehash: 1cd253c9415027eb36affe11dcd58832d6c07e8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824105"
---
# <a name="add-front-end-server-collocations-2010"></a>Hinzufügen der Front-End-Server-Kollokationen – 2010

Für eine Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungsserver oder beide gemeinsam mit dem Front-End-Pool verbinden bzw. als eigenständige Server bereitstellen. Bei einer Standard Edition-Serverbereitstellung wird der A/V-Konferenzdienst stets verbunden, sofern die Konferenzfunktion aktiviert ist.

> [!NOTE]
> Ein A/V-Konferenzdienst ist erforderlich, wenn **Konferenz** auf der Seite **Funktionen auswählen** ausgewählt wurde. Ein Front-End-Pool der Enterprise Edition kann einen gemeinsam ausgeführten A/V-Konferenzdienst oder eigenständigen A/V-Konferenzpool verwenden. Wenn die Konferenzfunktion nicht ausgewählt wurde, steht der Dienst zum gemeinsamen Ausführen der A/V-Konferenz nicht zur Verfügung.

Sie können die Vermittlungsserverrolle auf einem Front-End-Server der Standard Edition oder in einem Front-End-Pool der Enterprise Edition ausführen. Bei Bereitstellung von direkten SIP-Verbindungen mit einem qualifizierten PSTN-Gateway (Public Switched Telephone Network), das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungsserver erforderlich. Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können. Es wird außerdem empfohlen, den Vermittlungsserver in einem Front-End-Pool zu verbinden, wenn Sie IP-PBXs bereitgestellt haben, oder eine Verbindung mit dem Session Border Controller (SBC) eines Anbieters für Internettelefonieserver herzustellen, solange eine der folgenden Bedingungen erfüllt ist:

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

Mit dem Microsoft Lync Server 2013-Planungstool können Sie prüfen, ob der Front-End-Pool, in dem Sie den Vermittlungsserver verbinden möchten, die Last bewältigen kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Im Allgemeinen wird die Kollokation von A/V-Konferenzservern oder Vermittlungsservern nicht empfohlen, wenn in Ihrer Organisation Anforderungen an hohe Verfügbarkeit und Skalierbarkeit gelten. Ausführliche Informationen zum Verbinden dieser Serverrollen in einem Front-End-Pool in einer Enterprise Edition-Bereitstellung finden Sie unter "Definieren und Konfigurieren eines [Front-End-Pools"](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zu A/V-Konferenzfunktion und -komponenten finden Sie unter [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in der Planungsdokumentation. Ausführliche Informationen zu Enterprise-VoIP und Komponenten, einschließlich Vermittlungsserver, finden Sie unter ["Plan for Enterprise-VoIP in Skype for Business Server 2015"](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.


