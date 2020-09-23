---
title: Hinzufügen des Director-Pools
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
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Wählen Sie unter FQDN des Directorpools definieren entweder die Option Pool mit mehreren Computern, wobei der Pool mindestens zwei Directors in einem Pool mit Lastenausgleich umfasst, oder die Option Pool mit einem Computer aus. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der zum Herstellen einer Verbindung mit dem Directorpool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool aus Director-Computern ist dies der DNS-Eintrag (Domain Name System) für die virtuelle IP-Adresse eines Hardwaregeräts zum Lastenausgleich oder der gemeinsame DNS-Eintrag für den DNS-Lastenausgleich.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219486"
---
# <a name="add-director-pool"></a>Hinzufügen des Director-Pools
 
Wählen Sie unter **FQDN des Directorpools definieren** entweder die Option **Pool mit mehreren Computern**, wobei der Pool mindestens zwei Directors in einem Pool mit Lastenausgleich umfasst, oder die Option **Pool mit einem Computer** aus. Sie müssen auch den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) eingeben, der zum Herstellen einer Verbindung mit dem Directorpool oder dem FQDN des einzelnen Directors verwendet wird. Bei einem Pool aus Director-Computern ist dies der DNS-Eintrag (Domain Name System) für die virtuelle IP-Adresse eines Hardwaregeräts zum Lastenausgleich oder der gemeinsame DNS-Eintrag für den DNS-Lastenausgleich.
  
> [!TIP]
> Wenn Sie für die Zukunft die Implementierung eines Director-Pools planen, wählen Sie **Pool mit mehreren Computern** aus. Obwohl ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzelnen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie den Topologie-Generator erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann den neuen Directorpool-Member über den Skype for Business Server-Bereitstellungs-Assistenten einzurichten. Zudem müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichsmodulen hinzufügen (für den Pool, den DNS-Lastenausgleich (Domain Name System) oder das Hardwaregerät zum Lastenausgleich). In vielen Fällen verfügen Sie über beide Lastenausgleichssysteme. Stellen Sie sicher, dass Sie den neuen Mitgliedsserver beiden Systemen hinzufügen. 
  

