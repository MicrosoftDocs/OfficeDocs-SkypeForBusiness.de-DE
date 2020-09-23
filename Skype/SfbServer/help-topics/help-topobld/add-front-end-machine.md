---
title: Hinzufügen von Front-End-Computern
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
- ms.lync.tb.AddFrontEndMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7fe2522-1bd2-416a-9dbb-51cacea9c6e0
description: Geben Sie den vollqualifizierten Domänennamen jedes Computers an, der diesem Pool als Front-End-Server hinzugefügt werden soll. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Wenn Sie den vollqualifizierten Domänennamen nach dem Veröffentlichen der Topologie ändern möchten, müssen Sie den Server im Topologie-Generator löschen und dem Pool anschließend einen neuen Server mit dem neuen vollqualifizierten Domänennamen hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter Definieren und Konfigurieren eines Front-End-Pools in der Bereitstellungsdokumentation.
ms.openlocfilehash: 69837016022f30453a287b6264936e20ec4883ca
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218316"
---
# <a name="add-front-end-machine"></a>Hinzufügen von Front-End-Computern

Geben Sie den vollqualifizierten Domänennamen jedes Computers an, der diesem Pool als Front-End-Server hinzugefügt werden soll. Nach dem Hinzufügen eines Computers zur Liste können Sie den vollqualifizierten Domänennamen des Computers zu einem beliebigen Zeitpunkt vor der Veröffentlichung der Topologie aktualisieren oder aus dem Pool entfernen. Wenn Sie den vollqualifizierten Domänennamen nach dem Veröffentlichen der Topologie ändern möchten, müssen Sie den Server im Topologie-Generator löschen und dem Pool anschließend einen neuen Server mit dem neuen vollqualifizierten Domänennamen hinzufügen. Ausführliche Informationen zum Hinzufügen eines Front-End-Pools zur Topologie finden Sie unter [Definieren und Konfigurieren eines Front-End-Pools](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in der Bereitstellungsdokumentation.

> [!IMPORTANT]
> Beachten Sie, dass der Topologie-Generator angibt, dass Sie bis zu 20 Front-End-Server in einem Pool haben können. Die maximal unterstützte Anzahl von Servern ist 12. Im Fabric können bis zu 20 statefull-Server definiert sein, von denen 12 gleichzeitig aktiv sein und online sein können.


