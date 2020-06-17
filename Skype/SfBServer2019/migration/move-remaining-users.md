---
title: Verschieben der restlichen Benutzer
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Sie können Benutzer in die neue Skype for Business Server 2019-Bereitstellung über Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell migrieren. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter Phase 4: Verschieben von Testbenutzern in den Pilot Pool.'
ms.openlocfilehash: 0c4135ed8c3eaae25e57e6af1c67a18eb933b190
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753713"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Verschiebe verbleibenden Benutzer auf Skype for Business Server 2019

Sie können Benutzer in die neue Skype for Business Server 2019-Bereitstellung über Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell migrieren. Sie müssen einige Voraussetzungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen für die Ausführung der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md). Ausführliche Anweisungen zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den Pilot Pool](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Sie können nicht das Snap-in Active Directory Benutzer und Computer oder die Legacy-Verwaltungstools verwenden, um Benutzer aus ihrer Legacyumgebung in Skype for Business Server 2019 zu migrieren. 
  
Wenn Sie einen Benutzer in einen Skype for Business Server 2019-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist. 
  
> [!IMPORTANT]
> Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat. Wenn beispielsweise ein älterer Benutzer eine " **Meine Besprechung** "-Konferenz konfiguriert hat, ist diese Konferenz weiterhin im neuen Skype for Business Server 2019-Pool verfügbar, nachdem der Benutzer verschoben wurde. Die Details für den Zugriff auf diese Besprechung sind die gleiche **Konferenz-URL und Konferenz-ID** wie vorher. Der einzige Unterschied besteht darin, dass die Konferenz nun im Pool Skype for Business Server 2019 und nicht im Legacy Pool gehostet wird. 
  
> [!NOTE]
> Für das Homing von Benutzern in Skype for Business Server 2019 müssen keine aktualisierten Clients gleichzeitig bereitgestellt werden. Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben. 
  
### <a name="post-migration-task"></a>Aufgaben nach der Migration

1. Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie. 
    
2. Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die in Skype for Business Server 2019 verwaltet werden, nahtlos mit Verbundbenutzern zusammenarbeiten, die in einer Legacy Installation verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.
    
3. Konferenzrichtlinien, die anonymen Teilnehmern erlauben, **ermöglichen Teilnehmern das einladen anonymer Benutzer** in Skype for Business Server 2019-Systemsteuerung und haben in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der Skype for Business Server Verwaltungsshell **AllowAnonymousParticipantsInMeetings** auf **true** festgelegt. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

