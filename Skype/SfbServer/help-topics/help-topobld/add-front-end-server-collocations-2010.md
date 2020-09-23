---
title: Hinzufügen der Front-End-Server-Kollokationen – 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 86bef8bdcbdd36033e64912bdce2d9ea3469e45c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216516"
---
# <a name="add-front-end-server-collocations-2010"></a>Hinzufügen der Front-End-Server-Kollokationen – 2010

Für eine Enterprise Edition-Bereitstellung können Sie entweder den A/V-Konferenzdienst, den Vermittlungsserver oder beide gemeinsam mit dem Front-End-Pool verbinden bzw. als eigenständige Server bereitstellen. Bei einer Standard Edition-Serverbereitstellung wird der A/V-Konferenzdienst stets verbunden, sofern die Konferenzfunktion aktiviert ist.

> [!NOTE]
> Ein A/V-Konferenzdienst ist erforderlich, wenn **Konferenz** auf der Seite **Funktionen auswählen** ausgewählt wurde. Ein Front-End-Pool der Enterprise Edition kann einen gemeinsam ausgeführten A/V-Konferenzdienst oder eigenständigen A/V-Konferenzpool verwenden. Wenn die Konferenzfunktion nicht ausgewählt wurde, steht der Dienst zum gemeinsamen Ausführen der A/V-Konferenz nicht zur Verfügung.

Sie können die Vermittlungsserverrolle auf einem Front-End-Server der Standard Edition oder in einem Front-End-Pool der Enterprise Edition ausführen. Bei Bereitstellung von direkten SIP-Verbindungen mit einem qualifizierten PSTN-Gateway (Public Switched Telephone Network), das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungsserver erforderlich. Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können. Außerdem wird empfohlen, dass Sie die Vermittlungsserver auf einem Front-End-Pool collocate, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Server Anbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob der Front-End-Pool, in dem Sie die Vermittlungsserver collocate möchten, die Last verarbeiten kann. Falls Ihre Umgebung diese Anforderungen nicht erfüllen kann, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Im Allgemeinen wird die Zusammenstellung von A/V-Konferenzserver oder Vermittlungsserver nicht empfohlen, wenn Ihre Organisation über hohe Verfügbarkeit und Skalierbarkeit verfügt requirementsFor Details zu abstimmen diese Server Rollen in einer Front-End-Pool in einer Enterprise Edition-Bereitstellung finden Sie unter [define and configure A Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zu A/V-Konferenzfunktion und -komponenten finden Sie unter [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in der Planungsdokumentation. Ausführliche Informationen zu Enterprise-VoIP-Features und-Komponenten, einschließlich Vermittlungsserver, finden Sie unter [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.


