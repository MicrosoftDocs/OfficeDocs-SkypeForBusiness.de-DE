---
title: Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Dienste für beständigen Chat in Skype for Business Server 2015 starten, beenden und überwachen.'
ms.openlocfilehash: f2b2c964659b3de5045d414736bc5c1e5ddadd28
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766483"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Dienste für beständigen Chat in Skype for Business Server 2015 starten, beenden und überwachen.
  
Die Dienste für beständigen Chat und die Kompatibilitätsdienste für beständigen Chat sind Teil der Skype for Business Server Topologie und können daher mithilfe der folgenden Cmdlets überwacht, beendet und gestartet werden:
  
|Cmdlet|Funktion|
|:-----|:-----|
|get-CsWindowsService  <br/> |Gibt detaillierte Informationen zu Skype for Business Server 2015-Komponenten zurück, die als Windows-Dienste ausgeführt werden.  <br/> |
|start-CsWindowsService  <br/> |Startet den Dienst.  <br/> |
|stop-CsWindowsService  <br/> |Beendet den Dienst.  <br/> |
   
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 

Ausführliche Informationen zur Verwendung der Cmdlets finden Sie unter [Skype for Business Server 2015-Verwaltungsshell.](../management-shell.md)
  

