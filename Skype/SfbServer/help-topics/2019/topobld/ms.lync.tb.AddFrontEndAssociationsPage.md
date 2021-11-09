---
title: Hinzufügen von Front-End-Zuordnungen
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie können die Unterstützung für bestimmte Features aktivieren, die die Bereitstellung anderer Server erfordern, indem Sie die Serverrollen jetzt dem Front-End-Pool zuordnen. Sie können dem Front-End-Pool zu einem späteren Zeitpunkt auch Serverrollen zuordnen. Die Serverrollen, die einem Front-End-Pool zugeordnet werden können, umfassen Folgendes:'
ms.openlocfilehash: a4a7806945a29b43a2acf9184c2a8f04e1af77eb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864122"
---
# <a name="add-front-end-associations"></a>Hinzufügen von Front-End-Zuordnungen

Sie können die Unterstützung für bestimmte Features aktivieren, die die Bereitstellung anderer Server erfordern, indem Sie die Serverrollen jetzt dem Front-End-Pool zuordnen. Sie können dem Front-End-Pool zu einem späteren Zeitpunkt auch Serverrollen zuordnen. Die Serverrollen, die einem Front-End-Pool zugeordnet werden können, umfassen Folgendes:

- A/V-Edgeserver. Ausführliche Informationen zur Implementierung eines A/V-Edgeservers finden Sie in der Planungsdokumentation unter ["Planung für Konferenzen".](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)

> [!IMPORTANT]
> Wenn Sie die Unterstützung für diese Features jetzt aktivieren, enthält das von Ihnen veröffentlichte Topologiedesign die Serverkomponenten, die zum Implementieren der einzelnen ausgewählten Features erforderlich sind. Damit die Veröffentlichung einer Topologie ohne Fehler erfolgreich ist, müssen die physischen Computer mit der Domäne verbunden sein. Wenn Sie beispielsweise die Unterstützung für die Archivierung jetzt aktivieren, müssen Sie einen Archivierungsserver bereitstellen und die entsprechenden Archivierungsoptionen konfigurieren, bevor Sie mit der Archivierungskommunikation für Ihre Organisation beginnen.