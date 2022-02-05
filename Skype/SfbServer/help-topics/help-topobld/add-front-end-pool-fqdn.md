---
title: Hinzufügen des FQDN des Front-End-Pools
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 'Geben Sie den vollqualifizierten Domänennamen des Front-End-Pools ein, den Sie erstellen. Sie können den vollqualifizierten Domänennamen eines Pools nach Veröffentlichung der Topologie mit dem Front-End-Pool nicht ändern. Wenn Sie den Pool umbenennen müssen, müssen Sie zunächst den Pool löschen und dann einen neuen Pool mit dem neuen vollqualifizierten Domänennamen hinzufügen.'
---

# <a name="add-front-end-pool-fqdn"></a>Hinzufügen des FQDN des Front-End-Pools
 
Geben Sie den vollqualifizierten Domänennamen des Front-End-Pools ein, den Sie erstellen. Sie können den vollqualifizierten Domänennamen eines Pools nach Veröffentlichung der Topologie mit dem Front-End-Pool nicht ändern. Wenn Sie den Pool umbenennen müssen, müssen Sie zunächst den Pool löschen und dann einen neuen Pool mit dem neuen vollqualifizierten Domänennamen hinzufügen.
  
> [!TIP]
> Wenn Sie die Verwendung eines Front-End-Pools für die Zukunft planen, wählen Sie **Pool mit mehreren Computern** aus. Wenngleich ein Pool per Definition mindestens zwei Computer mit Lastenausgleich umfasst, können Sie einen Pool mit einem einzigen Computer sowie einen Pool-FQDN für diesen einzelnen Computer erstellen. Wenn Sie bereit sind, dem Pool später weitere Computer hinzuzufügen, müssen Sie den Topologie-Generator erneut ausführen, um das neue Poolmitglied zu definieren, die neue Topologie zu veröffentlichen und dann das neue Front-End-Poolmitglied über den Skype for Business Server Bereitstellungs-Assistenten einzurichten. Zudem müssen Sie das neue Poolmitglied den entsprechenden Lastenausgleichsmodulen (DNS-Lastenausgleich (Domain Name System) oder Hardwaregerät zum Lastenausgleich) für den Pool hinzufügen. In vielen Fällen verfügen Sie über beide Lastenausgleichssysteme. Stellen Sie sicher, dass Sie den neuen Mitgliedsserver beiden Systemen hinzufügen. 
  

