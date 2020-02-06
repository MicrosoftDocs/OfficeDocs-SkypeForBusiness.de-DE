---
title: Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Sie veröffentlichen die Topologie, die Sie mit dem Topologie-Generator konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, auf der der Front-End-Server oder der Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Diese Rolle kann nur von einem Front-End-Server oder einem Front-End-Pool zu einem beliebigen Zeitpunkt übernommen werden.
ms.openlocfilehash: cae0f79b9787458ae1dd24077dfdd46689378414
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795416"
---
# <a name="publish-topology-select-cms-page"></a>Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
 
Sie veröffentlichen die Topologie, die Sie mit dem Topologie-Generator konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, auf der der Front-End-Server oder der Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Diese Rolle kann nur von einem Front-End-Server oder einem Front-End-Pool zu einem beliebigen Zeitpunkt übernommen werden. 
  
### <a name="about-the-central-management-server"></a>Informationen zum zentralen Verwaltungs Server
Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Kopie der Datenbank vom Front-End-Server, auf dem sich der zentrale Verwaltungsserver befindet, gelesen/geschrieben wird. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der zentralen Verwaltungsspeicher Daten in der SQL Server-Datenbank (standardmäßig mit dem Namen RTCLOCAL), die während des Setups auf dem Computer installiert sind, und Bereitstellungs. Die lokale Datenbank erhält Replikat Updates über den lync Server Replica Replicator-Agent, der auf allen Computern als Dienst ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht. Auf den Speicherort der Master Datenbank wird in den Active Directory-Domänendiensten von einem Dienst Kontrollpunkt (Service Control Point, SCP) verwiesen. Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und Konfigurieren von lync Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.
  
## <a name="see-also"></a>Siehe auch

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
