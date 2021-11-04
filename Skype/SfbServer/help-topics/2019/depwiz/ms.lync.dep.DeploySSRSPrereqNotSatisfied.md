---
title: SQL Server Reporting Services (Voraussetzungen nicht erfüllt)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.
ms.openlocfilehash: 5ed5a84c5ac9b6da5b662f607ba3706d60ca2c97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755206"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Voraussetzungen nicht erfüllt)

Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.

Um dieses Problem zu beheben, stellen Sie sicher, dass Ein Überwachungsserver mit der Domäne verknüpft ist, dass er im Topologie-Generator definiert ist und dass die Topologie veröffentlicht wurde. SQL Server Reporting Services müssen auch auf dem SQL Server verfügbar sein und als Feature in der Monitoring Server-Datenbank auf dem SQL Server installiert sein.

Ausführliche Informationen finden Sie unter [Installieren von Überwachungsberichten in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) und Bereitstellen der [Überwachung.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)