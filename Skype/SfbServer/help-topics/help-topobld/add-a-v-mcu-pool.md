---
title: Hinzufügen des A/V-MCU-Pools
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Alle Front-End-Server der Enterprise Edition eines zentralen Standorts, die nicht über einen gleichzeitigen A/V-Konferenzdienst verfügen, können denselben eigenständigen A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und angeben, ob er nur einen einzelnen A/V-Konferenzserver oder mehrere A/V-Konferenzserver mit Lastenausgleich hat.
ms.openlocfilehash: 689f91bd27e4b3bbb2bd31149f34438bac59db46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810465"
---
# <a name="add-av-mcu-pool"></a>Hinzufügen des A/V-MCU-Pools
 
Alle Front-End-Server der Enterprise Edition eines zentralen Standorts, die nicht über einen gleichzeitigen A/V-Konferenzdienst verfügen, können denselben eigenständigen A/V-Konferenzpool verwenden. Für jeden A/V-Konferenzpool müssen Sie einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Pool angeben und angeben, ob er nur einen einzelnen A/V-Konferenzserver oder mehrere A/V-Konferenzserver mit Lastenausgleich hat.
  
> [!IMPORTANT]
> Sie können einen Pool mit einem Server nicht in einen Pool mit mehreren Servern konvertieren. Wenn Sie später entscheiden, dass Ihre Organisation einen Pool mit mehreren Servern benötigt, müssen Sie den Pool mit einem Server löschen und dann den Pool mit mehreren Servern hinzufügen. 
  
> [!TIP]
> Wenn Sie planen, in Zukunft einen A/V-Konferenzpool zu implementieren, wählen Sie Pool mit **mehreren Computern aus.** Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topologie-Generator erneut zum Definieren des neuen Poolmitglieds, veröffentlichen Sie die neue Topologie und richten Sie dann das neue Mitglied des A/V-Konferenzpools über den Skype for Business Server-Bereitstellungs-Assistenten ein. A/V-Konferenzserverpools sind einzigartig, da sie keinen Lastenausgleich zum Erstellen eines Pools benötigen. A/V-Konferenzpools lasten intern und benötigen keine zusätzliche Hardware. 
  

