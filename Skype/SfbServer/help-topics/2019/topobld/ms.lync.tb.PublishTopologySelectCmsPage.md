---
title: Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Sie veröffentlichen die Topologie, die Sie mithilfe des Topologie-Generators konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, welcher Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle zu einem bestimmten Zeitpunkt übernehmen.
ms.openlocfilehash: 435b13109e573116734ae3a688abd07044199509
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771023"
---
# <a name="publish-topology-select-cms-page"></a>Veröffentlichen der Topologie – Seite „Zentralen Verwaltungsserver auswählen“
 
Sie veröffentlichen die Topologie, die Sie mithilfe des Topologie-Generators konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, welcher Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle zu einem bestimmten Zeitpunkt übernehmen. 
  
### <a name="about-the-central-management-server"></a>Informationen zum zentralen Verwaltungsserver
Der zentrale Verwaltungsserver ist ein einzelnes Master-/Mehrfachreplikatsystem, in dem sich die Kopie der Datenbank mit Lese-/Schreibzugriff auf dem Front-End-Server befindet, der den zentralen Verwaltungsserver enthält. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server-Datenbank (standardmäßig RTCLOCAL genannt), die während des Setups und der Bereitstellung auf dem Computer installiert ist. Die lokale Datenbank empfängt Replikatupdates über den Lync Server-Replikatreplikationsdienst-Agent, der als Dienst auf allen Computern ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungsserver und das lokale Replikat ist XDS, das aus den Dateien "xds.mdf" und "xds.ldf" besteht. Auf den Speicherort der Masterdatenbank wird von einem Dienststeuerungspunkt (Service Control Point, SCP) in Active Directory Domain Services verwiesen. Alle Tools, die den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Lync Server verwenden, verwenden die SCP, um den zentralen Verwaltungsspeicher zu suchen.
  
## <a name="see-also"></a>Weitere Informationen

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)