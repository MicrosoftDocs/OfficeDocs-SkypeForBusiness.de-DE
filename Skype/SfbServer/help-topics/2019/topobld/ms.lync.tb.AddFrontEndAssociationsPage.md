---
title: Hinzufügen von Front-End-Zuordnungen
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Sie können die Unterstützung für bestimmte Features aktivieren, die die Bereitstellung anderer Server erfordern, indem Sie die Serverrollen jetzt dem Front-End-Pool zuordnen. Sie können dem Front-End-Pool zu einem späteren Zeitpunkt auch Serverrollen zuordnen. Die Serverrollen, die einem Front-End-Pool zugeordnet werden können, umfassen Folgendes:'
ms.openlocfilehash: 1a528fbeeabc4ca9a4c676a9f064b651c37298c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122656"
---
# <a name="add-front-end-associations"></a>Hinzufügen von Front-End-Zuordnungen

Sie können die Unterstützung für bestimmte Features aktivieren, die die Bereitstellung anderer Server erfordern, indem Sie die Serverrollen jetzt dem Front-End-Pool zuordnen. Sie können dem Front-End-Pool zu einem späteren Zeitpunkt auch Serverrollen zuordnen. Die Serverrollen, die einem Front-End-Pool zugeordnet werden können, umfassen Folgendes:

- A/V-Edgeserver. Ausführliche Informationen zur Implementierung eines A/V-Edgeservers finden Sie unter [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in der Planungsdokumentation.

> [!IMPORTANT]
> Wenn Sie jetzt die Unterstützung für eines dieser Features aktivieren, enthält das von Ihnen veröffentlichte Topologiedesign die Serverkomponenten, die zum Implementieren der einzelnen ausgewählten Features erforderlich sind. Damit die Veröffentlichung einer Topologie ohne Fehler erfolgreich ist, müssen die physischen Computer der Domäne beigetreten sein. Wenn Sie beispielsweise jetzt die Unterstützung für die Archivierung aktivieren, müssen Sie einen Archivierungsserver bereitstellen und die entsprechenden Archivierungsoptionen konfigurieren, bevor Sie mit der Archivierungskommunikation für Ihre Organisation beginnen.