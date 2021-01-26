---
title: Benutzerfreundlichkeit bei Poolfehlern in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Erfahren Sie mehr über die Benutzererfahrung, wenn ein Front-End-Pool während der Notfallwiederherstellung in Skype for Business Server ausfällt oder ein Fehler auftritt.
ms.openlocfilehash: 137ad9076febccb272e88e457ee56e6474cff107
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809905"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Benutzerfreundlichkeit bei Poolfehlern in Skype for Business Server
 
Erfahren Sie mehr über die Benutzererfahrung, wenn ein Front-End-Pool während der Notfallwiederherstellung in Skype for Business Server ausfällt oder ein Fehler auftritt.
  
Wenn für einen Pool ein Fehler vor liegt, müssen sich alle Benutzer im betroffenen Pool abmelden und sich dann beim Sicherungspool anmelden. Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus. Im Ausfallsicherheitsmodus können Benutzer keine Aufgaben ausführen, die eine dauerhafte Änderung in Skype for Business Server verursachen würden, z. B. das Hinzufügen eines Kontakts. Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.
  
Alle Anrufe, Besprechungen oder Unterhaltungen, die ein Benutzer hat, wenn der Pool ausfällt, werden unterbrochen, und der Benutzer muss diese Sitzungen nach dem Failover neu einrichten, um fortzufahren.
  
Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Homepool wiederhergestellt wird, kann der Administrator ein Fail back für diese Benutzer ausführen, damit sie von ihrem ursprünglichen Pool, in dem sie noch zu Hause sind, verwendet werden.
  
Beachten Sie, dass die Standortinformationsserverdatenbank nicht in den Sicherungspool repliziert wird. Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.
  
## <a name="user-experience-during-failover"></a>Benutzerfreundlichkeit während des Failovers

Wenn sich ein Benutzer in einem Pool befindet, bei dem ein Fehler auftritt, wird der Benutzer abgemeldet. Jede Peer-zu-Peer-Sitzung, an der der Benutzer teilnimmt, wird beendet, ebenso wie von diesem Benutzer organisierte Konferenzen. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Erst dann kann ein Benutzer neue Sitzungen einrichten oder vorherige Sitzungen 2013 2013 2013 bzw. 2013 2013 25:000 bzw.
  
## <a name="user-experience-during-failback"></a>Benutzerfreundlichkeit beim Failback

Pool-Failbacks können auftreten, während der betroffene Benutzer an einem Sicherungspool angemeldet ist und der Benutzer während des Failbacks weiterhin angemeldet ist und arbeitet. Beachten Sie, dass der Failbackprozess einige Minuten dauert. Zur Orientierung: Erwartungsgemäß dauert ein Pool mit 20.000 Benutzern bis zu 60 Minuten.
  
Die folgenden Tabellen enthalten weitere Details dazu, wie ein Benutzer während und nach einem Failback betroffen ist, und wie Benutzer in anderen Pools einen Benutzer in einem Pool sehen und mit ihm interagieren, für den ein Failback auftritt. 
  
Der Begriff betroffener Benutzer bezieht sich auf sämtliche Benutzer, bei denen beim Home-Pool ein Failover auftrat und die daher vom Sicherungspool verarbeitet werden. Ein Benutzer, der ursprünglich im Sicherungspool gespeichert wurde, ist kein betroffener Benutzer.
  
**Benutzerfreundlichkeit für einen betroffenen Benutzer für einen in einem Failback befindlichen Pool**

|**Benutzerstatus oder -aufgabe**|**Während des Failbacks**|**Nach abgeschlossenem Failback**|
|:-----|:-----|:-----|
|Benutzerstatus des bereits angemeldeten Benutzers  <br/> |Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.  <br/> |Benutzer bleibt angemeldet und wechselt in den regulären Modus.  <br/> |
|Neuer Benutzer meldet sich an  <br/> |Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.  <br/> |Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.  <br/> |
|Vom betroffenen Benutzer organisierte laufende Konferenz  <br/> |Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.  <br/> |Alle Modalitäten funktionieren jetzt. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.  <br/> |
|Vom nicht betroffenen Benutzer organisierte laufende Konferenz  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist darauf beschränkt, was er im Ausfallsicherheitsmodus ausführen kann.  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.  <br/> |
|Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen  <br/> |Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.  <br/> |Für alle Modalitäten verfügbar.  <br/> |
|Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird  <br/> |Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.  <br/> |Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus, und Anwesenheitsänderungen werden nun reflektiert.  <br/> |
|Verfügbarkeit von Kontaktlisten und Adressbuchdienst  <br/> |Nicht verfügbar  <br/> |Available  <br/> |
|Alle Peer-zu-Peer-Sitzungen und -modalitäten  <br/> |Available  <br/> |Available  <br/> |
   
**Benutzerfreundlichkeit für einen in einem nicht betroffenen Pool verwalteten Benutzer während eines Failbacks eines anderen Pools**

|**Benutzeraufgabe**|**Während des Failbacks**|**Nach abgeschlossenem Failback**|
|:-----|:-----|:-----|
|Anwesenheitsinformationen des betroffenen Benutzers anzeigen  <br/> |Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.  <br/> |In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.  <br/> |
|Von betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Alle Modalitäten der Konferenz werden abgebrochen  <br/> |Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.  <br/> |
|Von nicht betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.  <br/> |Die Konferenz wird weiterhin ausgeführt, und der betroffene Benutzer kann in der Konferenz verbleiben, und alle Modalitäten funktionieren.  <br/> |
|Alle Peer-zu-Peer-Sitzungen und -modalitäten  <br/> |Available  <br/> |Available  <br/> |
   

