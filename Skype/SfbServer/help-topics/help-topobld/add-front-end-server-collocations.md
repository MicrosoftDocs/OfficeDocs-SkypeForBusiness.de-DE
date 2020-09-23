---
title: Hinzufügen von Front-End-Server-Kollokationen
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
- ms.lync.tb.AddFrontEndCollocationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 23e3bda7-a8bf-4da4-88e5-098ae2aa268f
description: Für eine Enterprise Edition-Bereitstellung wird der A/V-Konferenzdienst mit dem Front-End-Pool verbunden. Sie können den Vermittlungsserver auch mit dem Front-End-Pool verbinden, oder Sie können ihn als eigenständigen Server bereitstellen. Der A/V-Konferenzdienst ist bei aktivierter Konferenzfunktion immer verbunden.
ms.openlocfilehash: 015570d42482b0e4f34e6679bab27aa2c40f2f88
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216506"
---
# <a name="add-front-end-server-collocations"></a>Hinzufügen von Front-End-Server-Kollokationen

Für eine Enterprise Edition-Bereitstellung wird der A/V-Konferenzdienst mit dem Front-End-Pool verbunden. Sie können den Vermittlungsserver auch mit dem Front-End-Pool verbinden, oder Sie können ihn als eigenständigen Server bereitstellen. Der A/V-Konferenzdienst ist bei aktivierter Konferenzfunktion immer verbunden.

> [!NOTE]
> Ein A/V-Konferenzdienst ist erforderlich, wenn **Konferenz** auf der Seite **Funktionen auswählen** ausgewählt wurde. Ein Front-End-Pool der Enterprise Edition verwendet einen verbundenen A/V-Konferenzdienst. Wenn die Konferenzfunktion nicht ausgewählt wurde, steht die Funktion zum Verbinden des A/V-Konferenzdiensts nicht zur Verfügung.

Sie können die Vermittlungsserverrolle auf einem Front-End-Server der Standard Edition oder in einem Front-End-Pool der Enterprise Edition ausführen. Bei Bereitstellung von direkten SIP-Verbindungen mit einem qualifizierten PSTN-Gateway (Public Switched Telephone Network), das Medienumgehung und DNS-Lastenausgleich unterstützt, ist kein eigenständiger Vermittlungsserver erforderlich. Der Grund ist, dass qualifizierte Gateways einen DNS-Lastenausgleich (Domain Name System) für einen Pool aus Vermittlungsservern implementieren und Datenverkehr von jedem Vermittlungsserver innerhalb eines Pools empfangen können. Außerdem wird empfohlen, dass Sie die Vermittlungsserver auf einem Front-End-Pool collocate, wenn Sie IP-Nebenstellenanlagen bereitgestellt haben oder eine Verbindung mit dem Session Border Controller (SBC) eines Internet Telefonie-Server Anbieters herstellen, sofern eine der folgenden Bedingungen erfüllt ist:

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

- Die IP-Nebenstellenanlage oder der SBC ist für den Empfang von Datenverkehr von einem beliebigen Vermittlungsserver in dem Pool konfiguriert und kann Datenverkehr einheitlich an alle Vermittlungsserver im Pool weiterleiten.

Mit dem Microsoft lync Server 2013 Planungs Tool können Sie auswerten, ob der Front-End-Pool, in dem Sie die Vermittlungsserver collocate möchten, die Last verarbeiten kann. Falls diese Anforderungen in Ihrer Umgebung nicht erfüllt sind, müssen Sie einen eigenständigen Vermittlungsserverpool bereitstellen.

Im Allgemeinen wird die Verbindung des Vermittlungsservers nicht empfohlen, wenn in Ihrer Organisation hohe Anforderungen an Verfügbarkeit und Skalierbarkeit gelten. Ausführliche Informationen zur Verbindung dieser Serverrollen in einem Front-End-Pool einer Enterprise Edition-Bereitstellung finden Sie unter [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation. Ausführliche Informationen zu A/V-Konferenzfunktion und -komponenten finden Sie unter [Planning for Conferencing](https://technet.microsoft.com/library/983a272a-e1b3-4d70-8f84-836b092fe526.aspx) in der Planungsdokumentation. Ausführliche Informationen zu Enterprise-VoIP-Features und-Komponenten, einschließlich Vermittlungsserver, finden Sie unter [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md) in der Planungsdokumentation.


