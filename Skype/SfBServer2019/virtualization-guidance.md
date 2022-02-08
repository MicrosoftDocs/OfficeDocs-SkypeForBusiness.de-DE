---
title: 'Virtualisierungsunterstützung für Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 'Zusammenfassung: Erfahren Sie mehr über die Virtualisierungsunterstützung für Skype for Business Server 2019.'
ms.openlocfilehash: 87263c4204cddbcd5e64cfeb6709b88bb94c2a60
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392257"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a>Virtualisierungsunterstützung für Skype for Business Server 2019

Skype for Business Server 2019 wird für die Virtualisierung unterstützt.

Während die Virtualisierung unterstützt wird, gibt es einige wichtige Punkte, die Sie beachten sollten:

- Behalten Sie ein 1:1-Verhältnis zwischen virtueller CPU und physischer CPU bei.
- Verschieben Sie einen Gastserver während des Betriebs nicht.
- Die Migration eines Livesystems und die Portabilität eines virtuellen Computers werden nicht unterstützt.
- Deaktivieren Sie Hyperthreading auf allen Hosts.
- Konfigurieren Sie dynamischen Speicher nicht auf Hostservern.
- Verwenden Sie feste oder Pass-Through-Datenträger anstelle dynamischer Datenträger.
- Lassen Sie einen Mehraufwand von 6 bis 10 Prozent für Hypervisoren zu, der über die Anforderungen des virtuellen Gasts hinausgeht.

## <a name="supported-hypervisors"></a>Unterstützte Hypervisoren

SfB Server 2019 wird auf Windows Server 2016 und Windows Server 2019 unterstützt.

Für Hypervisoren von Drittanbietern benötigen Sie einen Hypervisor, der das Server Virtualization Validation Program (SVVP)-Test für das entsprechende Betriebssystem bestanden hat.

- Siehe [die Windows Server 2016 Versionen](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.
- Siehe [die Versionen Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.

## <a name="stress-and-performance-tool"></a>Stress- und Leistungstool

Das Skype for Business Server 2019 Stress and Performance Tool enthält Tools, die die Kapazitätsplanung für Skype for Business Server 2019 vereinfachen. Das Skype for Business Server 2019 Stress and Performance Tool hilft Ihnen dabei:

- Vereinfachen der Hardwareplanung für Skype for Business Server 2019
- Bereitstellen von mehr Wissen und bewährten Methoden für die Leistungsoptimierung
- Messen der Leistung Ihrer beabsichtigten Skype for Business Server 2019-Bereitstellungen
 
Sie können das [Tool hier herunterladen](https://www.microsoft.com/download/details.aspx?id=101447).
