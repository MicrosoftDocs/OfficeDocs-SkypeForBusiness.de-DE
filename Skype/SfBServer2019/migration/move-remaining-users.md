---
title: Verschieben der verbleibenden Benutzer
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Sie können Benutzer in der neuen Skype für Business Server 2019 Bereitstellung verschieben, unter Verwendung von entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell. Sie müssen einige Anforderungen um einen reibungslosen Übergang zur Skype für Business Server 2019 sicherzustellen erfüllen. Ausführliche Informationen zu den erforderlichen Komponenten bis zum Abschluss der Verfahren in diesem Thema finden Sie unter Konfigurieren von Clients für die Migration. Ausführliche Schritte zum Verschieben von Benutzern, finden Sie unter Phase 4: Verschieben von Testbenutzern in den pilotpool.'
ms.openlocfilehash: 9f984b7fac919decce521c6dafc587a4ac86de50
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878324"
---
# <a name="move-remaining-users-to-skype-for-business-server-2019"></a>Verschieben der restlichen Benutzer zu Skype für Business Server 2019

Sie können Benutzer in der neuen Skype für Business Server 2019 Bereitstellung verschieben, unter Verwendung von entweder Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell. Sie müssen einige Anforderungen um einen reibungslosen Übergang zur Skype für Business Server 2019 sicherzustellen erfüllen. Ausführliche Informationen zu den erforderlichen Komponenten bis zum Abschluss der Verfahren in diesem Thema finden Sie unter [Konfigurieren von Clients für die Migration](configure-clients-for-migration.md). Ausführliche Schritte zum Verschieben von Benutzern finden Sie unter [Phase 4: Verschieben von Testbenutzern in den pilotpool](phase-4-move-test-users-to-the-pilot-pool.md).
  
> [!IMPORTANT]
> Sie können nicht das Snap-in Active Directory-Benutzer und-Computer oder die Vorversion Verwaltungstools verwenden, um Benutzer aus der vorgängerumgebung nach Skype für Business Server 2019 verschieben. 
  
Wenn Sie einen Benutzer in einen Skype für Business Server 2019 Pool verschieben, werden die Daten für den Benutzer mit der Back-End-Datenbank verschoben, die den neuen Pool zugeordnet ist. 
  
> [!IMPORTANT]
> Dazu gehören die aktiven Besprechungen vom legacy Benutzer erstellt. Beispielsweise wenn ein älterer Benutzer eine Konferenz **meiner Besprechung** konfiguriert hat, werden der Konferenz in die neue Skype für Business Server 2019 Pool verfügbar, nachdem der Benutzer verschoben wurde. Die Details zum Zugriff auf diese Besprechung werden die gleichen **Konferenz-URL und Konferenz-ID**. Der einzige Unterschied ist, dass die Konferenz jetzt in die Skype für Business Server 2019 Pool und nicht im Pool Vorgängerversion gehostet wird. 
  
> [!NOTE]
> Das Verwalten von Benutzern in Skype für Business Server 2019 nicht erfordert, dass Sie aktualisierte Clients zur selben Zeit bereitstellen. Neuer Funktionen werden für Benutzer verfügbar, nur, wenn sie auf die neue Clientsoftware aktualisiert haben. 
  
### <a name="post-migration-task"></a>Aufgaben nach der migration

1. Nachdem Sie Benutzer verschieben möchten, überprüfen Sie die konferenzrichtlinie, die ihnen zugewiesen ist. 
    
2. Um sicherzustellen, dass Benutzer organisierte Besprechungen in Skype für die Arbeit mit partnerverbundbenutzern Business Server 2019 verwaltet, die in älteren Install verwaltet werden, sollte die den migrierten Benutzern zugeordnete konferenzrichtlinie anonyme Teilnehmer zulassen.
    
3. Legen Sie konferenzrichtlinien, anonyme Teilnehmer haben **anonyme Benutzer einladen von Teilnehmern gestatten** für Business Server 2019 Control Panel in Skype ausgewählt und **AllowAnonymousParticipantsInMeetings** auf **true fest,** in der Ausgabe des Cmdlets **Get-CsConferencingPolicy** in der Skype für Business Server-Verwaltungsshell. 
    
<!-- 4. For details about configuring conferencing policy by using Skype for Business Server Management Shell, see 
 [Set-CsConferencingPolicy](../../lync-server-management-shell/lync-server-2013-cmdlets-by-category/set-csconferencingpolicy.md) in the Skype for Business Server Management Shell documentation.  -->
    

