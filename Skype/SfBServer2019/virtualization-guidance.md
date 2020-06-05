---
title: 'Unterstützung der Virtualisierung für Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: erfahren Sie mehr über die Unterstützung der Virtualisierung für Skype for Business Server 2019.'
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565954"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Unterstützung der Virtualisierung für Skype for Business Server 2019

Skype for Business Server 2019 wird für die Virtualisierung unterstützt.

Während die Virtualisierung unterstützt wird, gibt es einige wichtige Punkte, die Sie beachten sollten:

- Halten Sie ein 1:1-Verhältnis der virtuellen CPU mit der physischen CPU aufrecht.
- Bewegen Sie einen gastserver nicht, während er in Betrieb ist.
- Die Migration eines Live-Systems und die Portabilität eines virtuellen Computers werden nicht unterstützt.
- Deaktivieren Sie Hyper-Threading auf allen Hosts.
- Konfigurieren Sie keinen dynamischen Arbeitsspeicher auf Hostservern.
- Verwenden Sie feste oder Pass-Through-Datenträger anstelle von dynamischen Datenträgern.
- Ermöglichen Sie den Overhead von 6-10 Prozent für Hypervisoren über das hinaus, was der virtuelle Gast benötigt.

## <a name="supported-hypervisors"></a>Unterstützte Hypervisoren

SFB Server 2019 wird unter Windows Server 2016 und Windows Server 2019 unterstützt.

Für Hypervisoren von Drittanbietern benötigen Sie einen Hypervisor, der das Server Virtualization Validation Program (SVVP)-Test für das entsprechende Betriebssystem bestanden hat.

- Siehe die [Versionen von Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.
- Siehe die [Versionen von Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.
