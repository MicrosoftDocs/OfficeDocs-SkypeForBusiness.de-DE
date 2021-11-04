---
title: 'Virtualisierungsunterstützung für Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 850bfc0ae19aa8391baca6c9a8b6f1dde85cde2d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767103"
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
 
Sie können das Tool [hier](https://www.microsoft.com/download/details.aspx?id=101447)herunterladen.
