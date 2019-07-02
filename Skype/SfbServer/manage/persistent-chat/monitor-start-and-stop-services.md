---
title: Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6b28595-f702-4ecf-8115-e4104b87da89
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die beständigen Chat Dienste in Skype for Business Server 2015 starten, beenden und überwachen.'
ms.openlocfilehash: 9d2edf0e05a6efcd6e9354696cceade8265abbac
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418691"
---
# <a name="monitor-start-and-stop-the-persistent-chat-services-in-skype-for-business-server-2015"></a>Überwachen, Starten und Beenden der Dienste für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie die beständigen Chat Dienste in Skype for Business Server 2015 starten, beenden und überwachen können.
  
Die beständigen Chat Dienste und die beständigen Chat-Konformitäts Dienste sind Teil der Skype for Business Server-Topologie und können daher mithilfe der folgenden Cmdlets überwacht, gestoppt und gestartet werden:
  
|||
|:-----|:-----|
|get-CsWindowsService  <br/> |Gibt detaillierte Informationen zu den Skype for Business Server 2015-Komponenten zurück, die als Windows-Dienste ausgeführt werden.  <br/> |
|start-CsWindowsService  <br/> |Startet den Dienst.  <br/> |
|stop-CsWindowsService  <br/> |Beendet den Dienst.  <br/> |
   
> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 

Weitere Informationen zur Verwendung dieser Cmdlets finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

