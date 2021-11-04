---
title: >
  Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Geben Sie zum Definieren des vollqualifizierten Domänennamens (FQDN) eines vertrauenswürdigen Anwendungspools Folgendes an:'
ms.openlocfilehash: 2f08944c55d5a265c01f449c062a1e6d411cc533
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776795"
---
# <a name="add-trusted-application-pool-fqdn"></a>Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
 
Geben Sie zum Definieren des vollqualifizierten Domänennamens (FQDN) eines vertrauenswürdigen Anwendungspools Folgendes an:
  
Den FQDN des Servers oder Serverpools, der die vertrauenswürdigen Anwendungen hostet.
  
Wählen Sie **Pool mit mehreren Computern** aus, wenn Sie zum Gewährleisten eines Lastenausgleichs oder einer hohen Verfügbarkeit einen Serverpool bereitstelle. Wählen Sie **Pool mit einem Computer aus**, wenn Lastenausgleich bzw. hohe Verfügbarkeit nicht erforderlich sind.
  
> [!IMPORTANT]
> Ein einzelner vertrauenswürdiger Anwendungsserver kann später nicht in einen Serverpool umgewandelt werden. Wenn Sie annehmen, dass Sie künftig ggf. einen Pool benötigen, können Sie einen Pool mit mehreren Servern bereitstellen, der anfänglich nur einen Server enthält, und bei Bedarf weitere Server hinzufügen. 
  
Ausführliche Informationen zu vertrauenswürdigen Anwendungspools finden Sie unter [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
