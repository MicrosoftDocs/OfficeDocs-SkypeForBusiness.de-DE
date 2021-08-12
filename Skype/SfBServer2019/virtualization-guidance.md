---
title: 'Virtualisierungsunterstützung für Skype for Business Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Erfahren Sie mehr über die Virtualisierungsunterstützung für Skype for Business Server 2019.'
ms.openlocfilehash: 61b54a7e2d8fc170fe63137f637246f56dcce2a01dc7af0b41ea6dc5c5c56099
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334557"
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

- Sehen Sie sich die [Windows Server 2016 Versionen](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste an.
- Siehe [die Versionen Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in der SVVP-Liste.

## <a name="stress-and-performance-tool"></a>Stress- und Leistungstool

Das Skype for Business Server 2019 Stress and Performance Tool enthält Tools, die die Kapazitätsplanung für Skype for Business Server 2019 vereinfachen. Das Skype for Business Server 2019 Stress and Performance Tool hilft Ihnen dabei:

- Vereinfachen der Hardwareplanung für Skype for Business Server 2019
- Bereitstellen von mehr Wissen und bewährten Methoden für die Leistungsoptimierung
- Messen der Leistung Ihrer vorgesehenen Skype for Business Server 2019-Bereitstellungen
 
Sie können das Tool [hier](https://www.microsoft.com/download/details.aspx?id=101447)herunterladen.
