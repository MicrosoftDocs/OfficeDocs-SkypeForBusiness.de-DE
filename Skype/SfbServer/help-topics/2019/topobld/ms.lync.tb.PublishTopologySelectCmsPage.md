---
title: Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Sie veröffentlichen die Topologie, die Sie mithilfe des Topologie-Generators konfiguriert haben. Sie werden aufgefordert, aus einer Liste Wählen Sie die Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers halten übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle zu einem bestimmten Zeitpunkt enthalten.
ms.openlocfilehash: e649629650bfa1fe168698984e3e8b0aaa5d2df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888758"
---
# <a name="publish-topology-select-cms-page"></a>Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
 
Sie veröffentlichen die Topologie, die Sie mithilfe des Topologie-Generators konfiguriert haben. Sie werden aufgefordert, aus einer Liste Wählen Sie die Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers halten übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle zu einem bestimmten Zeitpunkt enthalten. 
  
### <a name="about-the-central-management-server"></a>Informationen zu den zentralen Verwaltungsserver
Den zentralen Verwaltungsserver ist ein einzelnes Master/mehreren Replikat System, auf dem wird die Lese-Schreib-Kopie der Datenbank vom Front-End-Server gespeichert, der den zentralen Verwaltungsserver enthält. Auf jedem Computer in der Topologie, einschließlich der Front-End-Server, der den zentralen Verwaltungsserver enthält ist eine schreibgeschützte Kopie der zentralen Speicherdaten in SQL Server-Datenbank (namens RTCLOCAL standardmäßig) auf dem Computer während des Setups installiert und Einsatz. Die lokale Datenbank empfängt Replikat Updates über die Lync Server Replikat Replicator-Agent, der als Dienst auf allen Computern ausgeführt wird. Der Name der aktuellen Datenbank auf den zentralen Verwaltungsserver und dem lokalen Replikat ist XDS, die der Dateien xds.mdf und xds.ldf besteht. Einen Dienststeuerungspunkt (SCP) in Active Directory Domain Services verweist auf der Speicherort der master-Datenbank. Alle Tools, die verwenden den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Lync Server, mithilfe des Dienstverbindungspunkts um den zentralen Verwaltungsspeicher zu suchen.
  
## <a name="see-also"></a>Siehe auch

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
