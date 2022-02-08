---
title: Benutzerfreundlichkeit bei Poolfehlern in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Erfahren Sie, welche Benutzer auftreten, wenn ein Front-End-Pool während der Notfallwiederherstellung in Skype for Business Server ausfällt.
ms.openlocfilehash: 19533d855c8aeee453808873746609e2508b0b2f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390007"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Benutzerfreundlichkeit bei Poolfehlern in Skype for Business Server
 
Erfahren Sie, welche Benutzer auftreten, wenn ein Front-End-Pool während der Notfallwiederherstellung in Skype for Business Server ausfällt.
  
Wenn ein Pool fehlgeschlagen ist, werden alle Benutzer im betroffenen Pool gezwungen, sich ab- und dann beim Sicherungspool anzumelden. Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus. Im Ausfallsicherheitsmodus können Benutzer keine Aufgaben ausführen, die eine dauerhafte Änderung an Skype for Business Server verursachen würden, z. B. das Hinzufügen eines Kontakts. Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.
  
Alle Anrufe, Besprechungen oder Unterhaltungen, die ein Benutzer hat, wenn der Pool fehlschlägt, werden unterbrochen, und der Benutzer muss diese Sitzungen nach dem Failover erneut einrichten, um fortzufahren.
  
Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Startpool wiederhergestellt wird, kann der Administrator ein Failback für diese Benutzer ausführen, um von ihrem ursprünglichen Pool bedient zu werden, in dem sie noch verwaltet werden.
  
Beachten Sie, dass die Location Information Server-Datenbank nicht in den Sicherungspool repliziert wird. Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.
  
## <a name="user-experience-during-failover"></a>Benutzerfreundlichkeit während des Failovers

Wenn sich ein Benutzer in einem Pool befindet, der fehlschlägt, wird der Benutzer abgemeldet. Jede Peer-to-Peer-Sitzung, an der der Benutzer teilgenommen hat, wird beendet, ebenso wie die von diesem Benutzer organisierten Konferenzen. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Nur dann kann ein Benutzer neue Sitzungen einrichten oder vorherige Sitzungen erneut einrichten.
  
## <a name="user-experience-during-failback"></a>Benutzererfahrung während des Failbacks

Pool-Failbacks können auftreten, während der betroffene Benutzer an einem Sicherungspool angemeldet ist und der Benutzer während des Failbacks weiterhin angemeldet ist und arbeitet. Beachten Sie, dass der Failbackvorgang mehrere Minuten dauert. Zur Orientierung: Erwartungsgemäß dauert ein Pool mit 20.000 Benutzern bis zu 60 Minuten.
  
Die folgenden Tabellen enthalten weitere Details dazu, wie ein Benutzer während und nach einem Failback betroffen ist und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit diesem interagieren, bei dem ein Fehler aufgetreten ist. 
  
Der Begriff betroffener Benutzer bezieht sich auf sämtliche Benutzer, bei denen beim Home-Pool ein Failover auftrat und die daher vom Sicherungspool verarbeitet werden. Ein Benutzer, der ursprünglich im Sicherungspool verwaltet wurde, ist kein betroffener Benutzer.
  
**Benutzerfreundlichkeit für einen betroffenen Benutzer für einen in einem Failback befindlichen Pool**

|**Benutzerstatus oder -aufgabe**|**Während des Failbacks**|**Nach abgeschlossenem Failback**|
|:-----|:-----|:-----|
|Benutzerstatus des bereits angemeldeten Benutzers  <br/> |Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.  <br/> |Benutzer bleibt angemeldet und wechselt in den regulären Modus.  <br/> |
|Neuer Benutzer meldet sich an  <br/> |Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.  <br/> |Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.  <br/> |
|Vom betroffenen Benutzer organisierte laufende Konferenz  <br/> |Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.  <br/> |Alle Modalitäten funktionieren jetzt. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.  <br/> |
|Vom nicht betroffenen Benutzer organisierte laufende Konferenz  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist darauf beschränkt, was er im Ausfallsicherheitsmodus ausführen kann.  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.  <br/> |
|Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen  <br/> |Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.  <br/> |Für alle Modalitäten verfügbar.  <br/> |
|Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird  <br/> |Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.  <br/> |Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus, und Anwesenheitsänderungen werden nun reflektiert.  <br/> |
|Verfügbarkeit von Kontaktlisten und Adressbuchdienst  <br/> |Nicht verfügbar  <br/> |Verfügbar  <br/> |
|Alle Peer-zu-Peer-Sitzungen und -modalitäten  <br/> |Verfügbar  <br/> |Verfügbar  <br/> |
   
**Benutzerfreundlichkeit für einen in einem nicht betroffenen Pool verwalteten Benutzer während eines Failbacks eines anderen Pools**

|**Benutzeraufgabe**|**Während des Failbacks**|**Nach abgeschlossenem Failback**|
|:-----|:-----|:-----|
|Anwesenheitsinformationen des betroffenen Benutzers anzeigen  <br/> |Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.  <br/> |In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.  <br/> |
|Von betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Alle Modalitäten der Konferenz werden abgebrochen  <br/> |Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.  <br/> |
|Von nicht betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.  <br/> |
|Alle Peer-zu-Peer-Sitzungen und -modalitäten  <br/> |Verfügbar  <br/> |Verfügbar  <br/> |
   

