---
title: Hinzufügen des Director-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Um den FQDN des Director-Pools zu definieren, wählen Sie entweder einen Pool mit mehreren Computern aus, der aus zwei oder mehr Directors in einem Lastenausgleichspool oder einem einzelnen Computerpool bestehen soll. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der für die Verbindung mit dem Director-Pool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool von Director-Computern handelt es sich hierbei um den DNS-Eintrag (Domain Name System) für die virtuelle IP eines Hardwarelastenausgleichs oder den freigegebenen DNS-Eintrag für den DNS-Lastenausgleich.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304786"
---
# <a name="add-director-pool"></a>Hinzufügen des Director-Pools
 
Um **den FQDN des Director-Pools zu definieren**, wählen Sie entweder einen **Pool mit mehreren Computern** aus, der aus zwei oder mehr Directors in einem Lastenausgleichspool oder einem **einzelnen Computerpool**bestehen soll. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der für die Verbindung mit dem Director-Pool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool von Director-Computern handelt es sich hierbei um den DNS-Eintrag (Domain Name System) für die virtuelle IP eines Hardwarelastenausgleichs oder den freigegebenen DNS-Eintrag für den DNS-Lastenausgleich.
  
> [!TIP]
> Wenn Sie beabsichtigen, einen Director-Pool in Zukunft zu implementieren, wählen Sie den **Pool für mehrere Computer**aus. Obwohl ein Pool als zwei oder mehr Computer definiert ist, die Lastenausgleich aufweisen, können Sie einen einzelnen Computerpool erstellen und einen Pool-FQDN für den einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topology Builder erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Director-Pool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten. Darüber hinaus müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichs Komponenten für den Pool, für den DNS-Lastenausgleich (Domain Name System) oder für Hardwarelastenausgleichs hinzufügen. In vielen Fällen sind beide Lastenausgleichssysteme vorhanden. Stellen Sie sicher, dass Sie beide den neuen Mitgliedsserver hinzufügen. 
  

