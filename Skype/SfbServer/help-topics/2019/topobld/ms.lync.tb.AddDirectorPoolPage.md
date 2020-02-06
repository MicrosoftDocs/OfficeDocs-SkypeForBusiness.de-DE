---
title: Hinzufügen des Director-Pools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Um den FQDN des Director-Pools zu definieren, wählen Sie entweder einen Pool mit mehreren Computern aus, der aus zwei oder mehr Directors in einem Lastenausgleichspool oder einem einzelnen Computerpool bestehen soll. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der für die Verbindung mit dem Director-Pool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool von Director-Computern handelt es sich hierbei um den DNS-Eintrag (Domain Name System) für die virtuelle IP eines Hardwarelastenausgleichs oder den freigegebenen DNS-Eintrag für den DNS-Lastenausgleich.
ms.openlocfilehash: 491d50c733314e1811aac38c556a6d4683b6956b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796574"
---
# <a name="add-director-pool"></a>Hinzufügen des Director-Pools
 
Um **den FQDN des Director-Pools zu definieren**, wählen Sie entweder einen **Pool mit mehreren Computern** aus, der aus zwei oder mehr Directors in einem Lastenausgleichspool oder einem **einzelnen Computerpool**bestehen soll. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der für die Verbindung mit dem Director-Pool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool von Director-Computern handelt es sich hierbei um den DNS-Eintrag (Domain Name System) für die virtuelle IP eines Hardwarelastenausgleichs oder den freigegebenen DNS-Eintrag für den DNS-Lastenausgleich.
  
> [!TIP]
> Wenn Sie beabsichtigen, einen Director-Pool in Zukunft zu implementieren, wählen Sie den **Pool für mehrere Computer**aus. Obwohl ein Pool als zwei oder mehr Computer definiert ist, die Lastenausgleich aufweisen, können Sie einen einzelnen Computerpool erstellen und einen Pool-FQDN für den einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topology Builder erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Director-Pool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten. Darüber hinaus müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichs Komponenten für den Pool, für den DNS-Lastenausgleich (Domain Name System) oder für Hardwarelastenausgleichs hinzufügen. In vielen Fällen sind beide Lastenausgleichssysteme vorhanden. Stellen Sie sicher, dass Sie beide den neuen Mitgliedsserver hinzufügen. 
  

