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
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.
ms.openlocfilehash: 792c9d3b6e7c398d517549eb55aaf85086badb64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100011"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Voraussetzungen nicht erfüllt)

Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.

Um dieses Problem zu beheben, stellen Sie sicher, dass ein Monitoring Server der Domäne beigetreten ist, dass er im Topologie-Generator definiert ist und dass die Topologie veröffentlicht wurde. SQL Server Reporting Services muss auch auf der SQL Server verfügbar sein und als Feature in der Monitoring Server-Datenbank auf der SQL Server.

Weitere Informationen finden Sie [unter Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) und [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).