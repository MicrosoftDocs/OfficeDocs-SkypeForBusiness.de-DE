---
title: Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 'Um eine vertrauenswürdige Pool vollqualifizierten Domänennamens (FQDN) zu definieren, geben Sie Folgendes ein:'
ms.openlocfilehash: 6934b1a8e80c816bb9132968d31d79d88b6c1c97
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33897422"
---
# <a name="add-trusted-application-pool-fqdn"></a>Hinzufügen des FQDN des vertrauenswürdigen Anwendungspools
 
Um eine vertrauenswürdige Pool vollqualifizierten Domänennamens (FQDN) zu definieren, geben Sie Folgendes ein:
  
Der FQDN des Servers oder Pools von Servern, auf denen vertrauenswürdigen Anwendungen gehostet wird.
  
Wählen Sie **Pool mit mehreren Computern** , wenn Sie einen Pool von Servern für die vertrauenswürdigen Anwendungen Lastenausgleich und hohe Verfügbarkeit bereitstellen, oder wählen **Pool mit einem Computer** aus, wenn Sie keine Lastenausgleich oder hohe Verfügbarkeit zu laden müssen.
  
> [!IMPORTANT]
> Einen einzelnen vertrauenswürdigen Anwendungsserver kann nicht in einem Pool von Servern später konvertiert werden soll. Wenn Sie, dass Sie einen Pool in der Zukunft benötigen können annehmen, können Sie einen Serverpool mit mehreren mit einem einzelnen Computer jetzt bereitstellen und Hinzufügen von Servern bei Bedarf. 
  
Ausführliche Informationen zu vertrauenswürdigen Anwendungspools finden Sie unter [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

