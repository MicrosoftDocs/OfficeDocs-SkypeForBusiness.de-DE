---
title: Hinzufügen eines Front-End-Computers
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
ROBOTS: NOINDEX, NOFOLLOW
description: Geben Sie den vollqualifizierten Domänennamen (FQDN) jeder Computer, den Sie als Front-End-Server in diesem Pool hinzufügen möchten. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Nach der Veröffentlichung der Topologie erfordert das Ändern des vollqualifizierten Domänennamens Löschen des Servers im Topologie-Generator, und klicken Sie dann einen neuen Server mit den neuen FQDN dem Pool hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter Define and Configure a Front End Pool in der Bereitstellungsdokumentation.
ms.openlocfilehash: e1353c84316858282d5b3a78491190f4ea611117
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23262169"
---
# <a name="add-front-end-machine"></a>Hinzufügen eines Front-End-Computers

Geben Sie den vollqualifizierten Domänennamen (FQDN) jeder Computer, den Sie als Front-End-Server in diesem Pool hinzufügen möchten. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Nach der Veröffentlichung der Topologie erfordert das Ändern des vollqualifizierten Domänennamens Löschen des Servers im Topologie-Generator, und klicken Sie dann einen neuen Server mit den neuen FQDN dem Pool hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation.

> [!IMPORTANT]
> Beachten Sie, dass Topologie-Generator gibt an, dass Sie bis zu 20 Front-End-Servern in einem Pool verfügen können. Die maximale unterstützte Anzahl von Servern lautet 12. Sie können bis zu 20 Statefull Server definierten im Fabric, von dem 12 aktiv und online jeweils werden kann.


