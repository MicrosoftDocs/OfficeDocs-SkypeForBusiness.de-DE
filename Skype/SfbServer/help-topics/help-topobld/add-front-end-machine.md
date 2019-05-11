---
title: Hinzufügen von Front-End-Computern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Geben Sie den vollqualifizierten Domänennamen (FQDN) jeder Computer, den Sie als Front-End-Server in diesem Pool hinzufügen möchten. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Nach der Veröffentlichung der Topologie erfordert das Ändern des vollqualifizierten Domänennamens Löschen des Servers im Topologie-Generator, und klicken Sie dann einen neuen Server mit den neuen FQDN dem Pool hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter Define and Configure a Front End Pool in der Bereitstellungsdokumentation.
ms.openlocfilehash: b161530bc58cfba2712e3642f71a8da65ab3eb0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904258"
---
# <a name="add-front-end-machine"></a>Hinzufügen von Front-End-Computern

Geben Sie den vollqualifizierten Domänennamen (FQDN) jeder Computer, den Sie als Front-End-Server in diesem Pool hinzufügen möchten. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Nach der Veröffentlichung der Topologie erfordert das Ändern des vollqualifizierten Domänennamens Löschen des Servers im Topologie-Generator, und klicken Sie dann einen neuen Server mit den neuen FQDN dem Pool hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation.

> [!IMPORTANT]
> Beachten Sie, dass Topologie-Generator gibt an, dass Sie bis zu 20 Front-End-Servern in einem Pool verfügen können. Die maximale unterstützte Anzahl von Servern lautet 12. Sie können bis zu 20 Statefull Server definierten im Fabric, von dem 12 aktiv und online jeweils werden kann.


