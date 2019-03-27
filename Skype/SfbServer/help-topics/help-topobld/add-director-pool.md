---
title: Hinzufügen des Director-Pools
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Um den FQDN des Director-Pools zu definieren, wählen Sie einen Pool mit mehreren Computern, der aus zwei oder mehr Directors in einem Pool mit Lastenausgleich bestehen wird oder einen Pool mit einem Computer aus. Sie müssen auch den vollqualifizierten Domänennamen (FQDN) eingeben, der zum Verbinden mit den Director-Pool oder den einzelnen Director-FQDN verwendet werden. Für einen Pool von Computern Director würde dies den Eintrag Domain Name System (DNS) für die virtuelle IP-Adresse des ein Hardwaregerät zum Lastenausgleich oder den freigegebenen DNS-Eintrag für DNS-Lastenausgleich sein.
ms.openlocfilehash: 8dfccfdac8ee2651c935b626f2deb0e688488b54
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879272"
---
# <a name="add-director-pool"></a>Hinzufügen des Director-Pools
 
Wählen Sie mit **dem FQDN des Director-Pools definieren**entweder einen **Pool mit mehreren Computern** , die aus zwei oder mehr Directors in einem Pool mit Lastenausgleich bestehen wird oder einen **Pool mit einem Computer**aus. Sie müssen auch den vollqualifizierten Domänennamen (FQDN) eingeben, der zum Verbinden mit den Director-Pool oder den einzelnen Director-FQDN verwendet werden. Für einen Pool von Computern Director würde dies den Eintrag Domain Name System (DNS) für die virtuelle IP-Adresse des ein Hardwaregerät zum Lastenausgleich oder den freigegebenen DNS-Eintrag für DNS-Lastenausgleich sein.
  
> [!TIP]
> Wenn Sie einen Director-Pool in der Zukunft implementieren möchten, wählen Sie **Pool mit mehreren Computern**. Obwohl ein Pool als zwei oder mehr Computer, die Lastenausgleich sind definiert ist, können Sie einen Pool mit einem Computer erstellt und erstellen einen Pool-FQDN für die einzelnen Computer. Wenn Sie später weitere Computer zum Pool hinzufügen möchten, müssen Sie Topology Builder erneut aus, um das neue Mitglied Pool definieren, die neue Topologie veröffentlichen und setup wird das neue Mitglied der Director-Pool über die Skype für Business Server-Bereitstellungs-Assistenten ausführen. Sie müssen auch fügen Sie den neuen Pool Member für die entsprechenden Lastenausgleich für den Pool, für Domain Name System (DNS)-Netzwerklastenausgleich, oder für Hardware-Lastenausgleichsmodule. In vielen Fällen müssen Sie beide Systeme direkten-Lastenausgleich. Stellen Sie sicher, dass Sie sowohl den neue Mitgliedsserver hinzugefügt werden müssen. 
  

