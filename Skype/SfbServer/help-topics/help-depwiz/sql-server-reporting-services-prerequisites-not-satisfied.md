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
ms.openlocfilehash: 6c87bc180923442bfd1f32b6836a6d41256261d3fe3233b0f347071f6bf9e884
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304077"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Voraussetzungen nicht erfüllt)

Diese Seite wird angezeigt, wenn in Ihrer Infrastruktur keine Monitoring Server bereitgestellt sind. Dies bedeutet, dass die Mindestanforderung für die Bereitstellung von Monitoring Server-Berichten noch nicht erfüllt sind.

Um dieses Problem zu beheben, stellen Sie sicher, dass Ein Überwachungsserver mit der Domäne verknüpft ist, dass er im Topologie-Generator definiert ist und dass die Topologie veröffentlicht wurde. SQL Server Reporting Services muss auch auf dem SQL Server verfügbar sein und als Feature in der Monitoring Server-Datenbank auf dem SQL Server installiert sein.

Ausführliche Informationen finden Sie unter [Installieren von Überwachungsberichten in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) und [Bereitstellen der Überwachung.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)