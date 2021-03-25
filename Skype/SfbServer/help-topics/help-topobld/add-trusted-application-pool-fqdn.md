---
title: >
  Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
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
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Geben Sie zum Definieren des vollqualifizierten Domänennamens (FQDN) eines vertrauenswürdigen Anwendungspools Folgendes an:'
ms.openlocfilehash: fc4817bad1c82d0ae0e50be6a5c08d03bb73687e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122479"
---
# <a name="add-trusted-application-pool-fqdn"></a>Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
 
Geben Sie zum Definieren des vollqualifizierten Domänennamens (FQDN) eines vertrauenswürdigen Anwendungspools Folgendes an:
  
Den FQDN des Servers oder Serverpools, der die vertrauenswürdigen Anwendungen hostet.
  
Wählen Sie **Pool mit mehreren Computern** aus, wenn Sie zum Gewährleisten eines Lastenausgleichs oder einer hohen Verfügbarkeit einen Serverpool bereitstelle. Wählen Sie **Pool mit einem Computer aus**, wenn Lastenausgleich bzw. hohe Verfügbarkeit nicht erforderlich sind.
  
> [!IMPORTANT]
> Ein einzelner vertrauenswürdiger Anwendungsserver kann später nicht in einen Serverpool umgewandelt werden. Wenn Sie annehmen, dass Sie künftig ggf. einen Pool benötigen, können Sie einen Pool mit mehreren Servern bereitstellen, der anfänglich nur einen Server enthält, und bei Bedarf weitere Server hinzufügen. 
  
Ausführliche Informationen zu vertrauenswürdigen Anwendungspools finden Sie unter [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
