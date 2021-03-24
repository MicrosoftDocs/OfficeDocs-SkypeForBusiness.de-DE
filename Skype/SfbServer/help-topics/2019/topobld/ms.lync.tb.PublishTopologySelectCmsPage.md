---
title: Veröffentlichen der Topologie – Seite "Zentralen Verwaltungsserver auswählen"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Sie veröffentlichen die Topologie, die Sie mit dem Topologie-Generator konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, welcher Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle jederzeit übernehmen.
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096881"
---
# <a name="publish-topology-select-cms-page"></a>Veröffentlichen der Topologie – Seite „Zentralen Verwaltungsserver auswählen“
 
Sie veröffentlichen die Topologie, die Sie mit dem Topologie-Generator konfiguriert haben. Sie werden aufgefordert, aus einer Liste auszuwählen, welcher Front-End-Server oder Front-End-Pool die Rolle des zentralen Verwaltungsspeichers übernimmt. Nur ein Front-End-Server oder Front-End-Pool kann diese Rolle jederzeit übernehmen. 
  
### <a name="about-the-central-management-server"></a>Informationen zum zentralen Verwaltungsserver
Der zentrale Verwaltungsserver ist ein einzelnes Master-/Multiple-Replica-System, in dem die Lese-/Schreibkopie der Datenbank vom Front-End-Server mit dem zentralen Verwaltungsserver gespeichert wird. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server-Datenbank (standardmäßig rtCLOCAL genannt), die während der Einrichtung und Bereitstellung auf dem Computer installiert ist. Die lokale Datenbank empfängt Replikatupdates über den Lync Server Replica Replicator Agent, der als Dienst auf allen Computern ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungsserver und dem lokalen Replikat ist XDS, das aus den Dateien xds.mdf und xds.ldf besteht. Auf den Speicherort der Masterdatenbank wird von einem Dienststeuerungspunkt (Service Control Point, SCP) in Active Directory Domain Services verwiesen. Alle Tools, die den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Lync Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.
  
## <a name="see-also"></a>Siehe auch

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)