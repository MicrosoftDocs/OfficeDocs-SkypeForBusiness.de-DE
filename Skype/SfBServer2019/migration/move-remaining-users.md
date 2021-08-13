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
description: 'Sie können Benutzer in die neue Skype for Business Server 2019-Bereitstellung verschieben, indem Sie entweder Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell verwenden. Sie müssen einige Anforderungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen zum Abschließen der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Ausführliche Schritte zum Verschieben von Benutzern finden Sie in Phase 4: Verschieben von Testbenutzern in den Pilotpool.'
ms.openlocfilehash: a2742acf32899aca71c28da733c723640a8c1e9200f26f793a918eac04714f15
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300631"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Verschieben der verbleibenden Benutzer zu Skype for Business Server 2019

Sie können Benutzer in die neue Skype for Business Server 2019-Bereitstellung verschieben, indem Sie entweder Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell verwenden. Sie müssen einige Anforderungen erfüllen, um einen reibungslosen Übergang zu Skype for Business Server 2019 sicherzustellen. Ausführliche Informationen zu den Voraussetzungen zum Abschließen der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration.](configure-clients-for-migration.md) Ausführliche Schritte zum Verschieben von Benutzern finden Sie in [Phase 4: Verschieben von Testbenutzern in den Pilotpool.](phase-4-move-test-users-to-the-pilot-pool.md)
  
> [!IMPORTANT]
> Sie können das Snap-In "Active Directory-Benutzer und -Computer" oder die älteren Verwaltungstools nicht verwenden, um Benutzer aus Ihrer älteren Umgebung in Skype for Business Server 2019 zu verschieben. 
  
Wenn Sie einen Benutzer in einen Skype for Business Server 2019-Pool verschieben, werden die Daten für den Benutzer in die Back-End-Datenbank verschoben, die dem neuen Pool zugeordnet ist. 
  
> [!IMPORTANT]
> Hierzu gehören die aktiven Besprechungen, die der Benutzer der Vorgängerversion erstellt hat. Wenn beispielsweise ein Legacybenutzer eine **Besprechungskonferenz** konfiguriert hat, ist diese Konferenz auch nach dem Verschieben des Benutzers weiterhin im neuen Pool Skype for Business Server 2019 verfügbar. Die Details für den Zugriff auf diese Besprechung sind die gleiche **Konferenz-URL und Konferenz-ID** wie vorher. Der einzige Unterschied besteht darin, dass die Konferenz jetzt im Skype for Business Server 2019-Pool und nicht im Legacypool gehostet wird. 
  
> [!NOTE]
> Für das Aufrufen von Benutzern auf Skype for Business Server 2019 ist es nicht erforderlich, dass Sie aktualisierte Clients gleichzeitig bereitstellen. Neue Funktionen stehen den Benutzern nur dann zur Verfügung, wenn sie ein Upgrade auf die neue Clientsoftware durchgeführt haben. 
  
### <a name="post-migration-task"></a>Aufgabe nach der Migration

1. Überprüfen Sie nach dem Verschieben der Benutzer die ihnen zugeordnete Konferenzrichtlinie. 
    
2. Um sicherzustellen, dass Besprechungen, die von Benutzern organisiert werden, die am Skype for Business Server 2019 verwaltet werden, nahtlos mit Verbundbenutzern funktionieren, die bei der Legacyinstallation verwaltet werden, sollte die konferenzrichtlinie, die den migrierten Benutzern zugewiesen ist, anonyme Teilnehmer zulassen.
    
3. Konferenzrichtlinien, die anonymen Teilnehmern erlauben, dass **Teilnehmer anonyme Benutzer einladen** können, die in Skype for Business Server 2019-Systemsteuerung ausgewählt wurden, und **AllowAnonymousParticipantsInMeetings** in der Ausgabe des Cmdlets **"Get-CsConferencingPolicy"** in der Skype for Business Server-Verwaltungsshell auf **"True"** festgelegt haben. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

