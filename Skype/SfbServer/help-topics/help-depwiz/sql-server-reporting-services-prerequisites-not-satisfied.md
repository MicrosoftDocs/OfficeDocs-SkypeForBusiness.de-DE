---
title: SQL Server Reporting Services (Voraussetzungen nicht erfüllt)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.
ms.openlocfilehash: 235dec8ce462a6aafe7a1c4746cdb01d5169d4b3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615971"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Voraussetzungen nicht erfüllt)

Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.

Um dieses Problem zu beheben, stellen Sie sicher, dass Ein Überwachungsserver mit der Domäne verknüpft ist, dass er im Topologie-Generator definiert ist und dass die Topologie veröffentlicht wurde. SQL Server Reporting Services muss auch im SQL Server verfügbar sein und als Feature in der Monitoring Server-Datenbank auf dem SQL Server installiert sein.

Ausführliche Informationen finden Sie unter [Installieren von Überwachungsberichten in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) und [Bereitstellen der Überwachung.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)