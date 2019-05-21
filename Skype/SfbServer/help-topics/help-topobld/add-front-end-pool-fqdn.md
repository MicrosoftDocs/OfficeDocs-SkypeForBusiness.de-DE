---
title: Hinzufügen des FQDN des Front-End-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools an, den Sie erstellen. Sie können den FQDN eines Pools nicht ändern, nachdem Sie die Topologie mit dem Front-End-Pool veröffentlicht haben. Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool löschen und dann einen neuen Pool mit dem neuen FQDN hinzufügen.
ms.openlocfilehash: 058e1cc6a1e510ba57bb28a694a9ddc7e9759f90
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275360"
---
# <a name="add-front-end-pool-fqdn"></a>Hinzufügen des FQDN des Front-End-Pools
 
Geben Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools an, den Sie erstellen. Sie können den FQDN eines Pools nicht ändern, nachdem Sie die Topologie mit dem Front-End-Pool veröffentlicht haben. Wenn Sie einen Pool umbenennen müssen, müssen Sie den Pool löschen und dann einen neuen Pool mit dem neuen FQDN hinzufügen.
  
> [!TIP]
> Wenn Sie beabsichtigen, in Zukunft einen Front-End-Pool zu implementieren, wählen Sie den **Pool für mehrere Computer**aus. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topology Builder erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Front-End-Pool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten. Darüber hinaus müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichs Komponenten für den Pool, DNS-Lastenausgleich (Domain Name System) oder Hardwarelastenausgleichs hinzufügen. In vielen Fällen sind beide Lastenausgleichssysteme vorhanden. Stellen Sie sicher, dass Sie beide den neuen Mitgliedsserver hinzufügen. 
  

