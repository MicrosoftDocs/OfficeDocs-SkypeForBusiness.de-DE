---
title: Hinzufügen von Front-End-Zuordnungen
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
description: 'Sie können die Unterstützung für bestimmte Features aktivieren, die die Bereitstellung anderer Server erfordern, indem Sie die Serverrollen jetzt dem Front-End-Pool zuordnen. Sie können dem Front-End-Pool zu einem späteren Zeitpunkt auch Serverrollen zuordnen. Die Serverrollen, die einem Front-End-Pool zugeordnet werden können, umfassen Folgendes:'
ms.openlocfilehash: 9d2e2912b6f9ad53dc194c4fa0267f29d83263f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762703"
---
# <a name="add-front-end-associations"></a>Hinzufügen von Front-End-Zuordnungen

Sie können die Unterstützung für bestimmte Features aktivieren, die die Bereitstellung anderer Server erfordern, indem Sie die Serverrollen jetzt dem Front-End-Pool zuordnen. Sie können dem Front-End-Pool zu einem späteren Zeitpunkt auch Serverrollen zuordnen. Die Serverrollen, die einem Front-End-Pool zugeordnet werden können, umfassen Folgendes:

- A/V-Edgeserver. Ausführliche Informationen zur Implementierung eines A/V-Edgeservers finden Sie in der Planungsdokumentation unter ["Planung für Konferenzen".](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing)

> [!IMPORTANT]
> Wenn Sie die Unterstützung für diese Features jetzt aktivieren, enthält das von Ihnen veröffentlichte Topologiedesign die Serverkomponenten, die zum Implementieren der einzelnen ausgewählten Features erforderlich sind. Damit die Veröffentlichung einer Topologie ohne Fehler erfolgreich ist, müssen die physischen Computer mit der Domäne verbunden sein. Wenn Sie beispielsweise die Unterstützung für die Archivierung jetzt aktivieren, müssen Sie einen Archivierungsserver bereitstellen und die entsprechenden Archivierungsoptionen konfigurieren, bevor Sie mit der Archivierungskommunikation für Ihre Organisation beginnen.