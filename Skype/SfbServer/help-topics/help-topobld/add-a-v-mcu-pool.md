---
title: Hinzufügen des A/V-MCU-Pools
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Alle Enterprise Edition-Front-End-Server eines zentralen Standorts, die nicht über eine zusammengefasste A/V-Konferenzdienst verfügen, können dieselbe eigenständige A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und festlegen, ob nur ein einzelner A/V-Konferenzserver oder mehrere a/V-Konferenzserver mit Lastenausgleich vorhanden sein sollen.
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217476"
---
# <a name="add-av-mcu-pool"></a>Hinzufügen des A/V-MCU-Pools
 
Alle Enterprise Edition-Front-End-Server eines zentralen Standorts, die nicht über eine zusammengefasste A/V-Konferenzdienst verfügen, können dieselbe eigenständige A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und festlegen, ob nur ein einzelner A/V-Konferenzserver oder mehrere a/V-Konferenzserver mit Lastenausgleich vorhanden sein sollen.
  
> [!IMPORTANT]
> Sie können einen Pool mit einem Server nicht in einen Pool mit mehreren Servern konvertieren. Wenn Sie später entscheiden, dass Ihre Organisation einen Pool mit mehreren Servern benötigt, müssen Sie den Pool mit einem Server löschen und dann den Pool mit mehreren Servern hinzufügen. 
  
> [!TIP]
> Wenn Sie eine A/V-Konferenzpool in der Zukunft implementieren möchten, wählen Sie **Pool mit mehreren Computern**aus. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie den Topologie-Generator erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue A/V-Konferenzpool Mitglied über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten. A/V-Konferenzserver Pools sind insofern eindeutig, als Sie keine Lastenausgleichsmodule benötigen, um einen Pool zu erstellen. A/V-Konferenz Pools laden den Lastenausgleich intern und benötigen keine zusätzliche Hardware. 
  

