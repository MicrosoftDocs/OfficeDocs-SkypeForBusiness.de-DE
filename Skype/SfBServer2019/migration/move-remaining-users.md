---
title: Verschieben der verbleibenden Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Sie können Benutzer über die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell zur neuen Skype for Business Server 2019-Bereitstellung bewegen. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 zu gewährleisten. Details zu den Voraussetzungen für die Durchführung der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Detaillierte Anweisungen zum Verschieben von Benutzern finden Sie unter Phase 4: Verschieben von Testbenutzern in den Pilot Pool.'
ms.openlocfilehash: 67bc2d3b239e65b5b1c83e2dcda81a1610d5a31c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273959"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Verschieben von verbleibenden Benutzern in Skype for Business Server 2019

Sie können Benutzer über die Skype for Business Server Control Panel-oder Skype for Business Server-Verwaltungsshell zur neuen Skype for Business Server 2019-Bereitstellung bewegen. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 zu gewährleisten. Details zu den Voraussetzungen für die Durchführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md). Detaillierte Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Sie können das Snap-in Active Directory-Benutzer und-Computer oder die Legacy-Verwaltungstools nicht verwenden, um Benutzer aus ihrer Legacyumgebung in Skype for Business Server 2019 zu verschieben. 
  
Wenn Sie einen Benutzer in einen Skype for Business Server 2019-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist. 
  
> [!IMPORTANT]
> Dazu gehören die vom Legacy Benutzer erstellten aktiven Besprechungen. Wenn ein älterer Benutzer beispielsweise eine Konferenz für **Meine Besprechung** konfiguriert hat, steht diese Konferenz nach dem Verschieben des Benutzers weiterhin im neuen Skype for Business Server 2019-Pool zur Verfügung. Die Details für den Zugriff auf die Besprechung sind weiterhin dieselbe **Konferenz-URL und Konferenz-ID**. Der einzige Unterschied besteht darin, dass die Konferenz jetzt im Skype for Business Server 2019-Pool und nicht im Legacy Pool gehostet wird. 
  
> [!NOTE]
> Für Homing-Benutzer in Skype for Business Server 2019 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden. Neue Funktionen stehen Benutzern nur zur Verfügung, wenn Sie ein Upgrade auf die neue Client Software durchgeführt haben. 
  
### <a name="post-migration-task"></a>Aufgabe der nach der Migration

1. Nachdem Sie die Benutzer verschoben haben, überprüfen Sie die konferenzrichtlinie, die Ihnen zugewiesen ist. 
    
2. Um sicherzustellen, dass Besprechungen, die von Benutzern verwaltet werden, die sich in Skype for Business Server 2019 befinden, nahtlos mit Verbundbenutzern zusammenarbeiten, die bei der Legacy Installation verwaltet werden, sollten die den migrierten Benutzern zugewiesenen Konferenzrichtlinien anonymen Teilnehmern ermöglichen.
    
3. Konferenzrichtlinien, die anonymen Teilnehmern gestatten, zulassen, dass **Teilnehmer anonyme Benutzer einladen,** die in der Systemsteuerung von Skype for Business Server 2019 ausgewählt sind, und die **AllowAnonymousParticipantsInMeetings** auf " **true** " festgelegt haben Ausgabe aus dem Cmdlet " **Get-CsConferencingPolicy** " in der Skype for Business Server-Verwaltungsshell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

