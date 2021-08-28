---
title: Hinzufügen des A/V-MCU-Pools
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
ROBOTS: NOINDEX, NOFOLLOW
description: Alle Enterprise Edition Front-End-Server eines zentralen Standorts, die nicht über einen verbundenen A/V-Konferenzdienst verfügen, können den gleichen eigenständigen A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und angeben, ob er nur über einen einzelnen A/V-Konferenzserver oder mehrere A/V-Konferenzserver mit Lastenausgleich verfügt.
ms.openlocfilehash: 114d67f6643fe2629cf3a6c1a72daa70eb2db65f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626867"
---
# <a name="add-av-mcu-pool"></a>Hinzufügen des A/V-MCU-Pools
 
Alle Enterprise Edition Front-End-Server eines zentralen Standorts, die nicht über einen verbundenen A/V-Konferenzdienst verfügen, können den gleichen eigenständigen A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und angeben, ob er nur über einen einzelnen A/V-Konferenzserver oder mehrere A/V-Konferenzserver mit Lastenausgleich verfügt.
  
> [!IMPORTANT]
> Sie können einen Pool mit einem Server nicht in einen Pool mit mehreren Servern konvertieren. Wenn Sie später entscheiden, dass Ihre Organisation einen Pool mit mehreren Servern benötigt, müssen Sie den Einzelserverpool löschen und dann den Pool mit mehreren Servern hinzufügen. 
  
> [!TIP]
> Wenn Sie beabsichtigen, in Zukunft einen A/V-Konferenzpool zu implementieren, wählen Sie **"Pool mit mehreren Computern"** aus. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topologie-Generator erneut erstellen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue A/V-Konferenzpoolmitglied über den Skype for Business Server Bereitstellungs-Assistenten einzurichten. A/V-Konferenzserverpools sind einzigartig, da sie zum Erstellen eines Pools keine Lastenausgleichsmodule benötigen. A/V-Konferenzpools lasten intern und benötigen keine zusätzliche Hardware. 
  

