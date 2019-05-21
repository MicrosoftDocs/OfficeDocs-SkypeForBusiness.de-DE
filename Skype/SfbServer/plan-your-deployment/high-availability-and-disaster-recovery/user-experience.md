---
title: Benutzerfreundlichkeit während eines Pool Fehlers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Informieren Sie sich, welche Benutzer beim Failover eines Front-End-Pools oder bei einer Wiederherstellung des notfalls in Skype for Business Server auftreten.
ms.openlocfilehash: cc8ea8c51bebcffdbf0873f2f1a355cd648b6df0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297232"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Benutzerfreundlichkeit während eines Pool Fehlers in Skype for Business Server
 
Informieren Sie sich, welche Benutzer beim Failover eines Front-End-Pools oder bei einer Wiederherstellung des notfalls in Skype for Business Server auftreten.
  
Wenn für einen Pool ein Failover vorgenommen wurde, werden alle Benutzer im betroffenen Pool gezwungen, sich abzumelden und sich beim Sicherungspool anzumelden. Für einen kurzen Zeitraum befinden sich die Benutzer, die sich am Sicherungspool anmelden, möglicherweise im Ausfallsicherheitsmodus. Im Resilienz-Modus können Benutzer keine Aufgaben ausführen, die zu einer dauerhaften Änderung auf Skype for Business Server führen, wie etwa das Hinzufügen eines Kontakts. Nachdem das Failover abgeschlossen wurde, können alle Benutzer alle Dienste vom Sicherungspool beziehen.
  
Sämtliche Anrufe, Besprechungen oder Gespräche, über die ein Benutzer verfügt, während ein Pool ausfällt, werden unterbrochen, und der Benutzer muss diese Sitzungen wiederherstellen, um nach dem Failover fortzufahren.
  
Benutzer werden während eines Failovers oder Failbacks nicht verlagert. Benutzer, die auf einem ausfallenden Pool verwaltet werden, werden temporär durch den Sicherungspool verarbeitet. Wenn der Home-Pool wiederhergestellt wird, kann der Administrator über ein Failback diese Benutzer wieder über ihren ursprünglichen Pool verarbeiten, dem sie noch zugeordnet sind.
  
Hinweis: Die Location Information Server-Datenbank wird nicht in den Sicherungspool repliziert. Als bewährte Vorgehensweise sollte der Administrator die LIS-Datenbank regelmäßig sichern und die neueste Sicherungskopie verwenden, um die LIS-Datenbank im Sicherungspool nach dem Failover wiederherzustellen.
  
## <a name="user-experience-during-failover"></a>Benutzerfreundlichkeit während des Failovers

Wenn sich ein Benutzer in einem ausfallenden Pool befindet, wird er abgemeldet. Sämtliche Peer-zu-Peer-Sitzungen, an denen der Benutzer teilgenommen hat, werden beendet, ebenso die von ihm organisierten Konferenzen. Der Benutzer kann sich nicht wieder anmelden, bis entweder der Registrierungsausfallsicherheits-Zeitgeber abläuft oder der Administrator Failoverprozeduren initiiert, was auch immer zuerst eintritt. Wenn sich Benutzer wieder anmelden, werden sie im Sicherungspool angemeldet. Wenn sie sich vor Abschluss des Failovers anmelden, befinden sie sich im Ausfallsicherheitsmodus, bis das Failover abgeschlossen ist. Nur dann kann ein Benutzer neue Sitzungen erstellen oder vorherige Sitzungen wiederherstellen.
  
## <a name="user-experience-during-failback"></a>Benutzerfreundlichkeit während des Failbacks

Pool-Failbacks können auftreten, wenn der betroffene Benutzer während des Failbacks weiterhin an einem Sicherungspool angemeldet ist und arbeitet. Hinweis: Es dauert mehrere Minuten, bis der Failback-Prozess abgeschlossen ist. Zur Orientierung: Erwartungsgemäß dauert dies bei einem Pool mit 20.000 Benutzern bis zu 60 Minuten.
  
In den folgenden Tabellen finden Sie genauere Informationen darüber, wie ein Benutzer bei und nach einem Failback betroffen ist und auch wie Benutzer in anderen Pools einen Benutzer, für dessen Pool ein Failback ausgeführt wird, sehen und mit diesem interagieren. 
  
Der Begriff betroffener Benutzer bezieht sich auf sämtliche Benutzer, bei denen ein Failover im Home-Pool aufgetreten ist und die daher vom Sicherungspool verarbeitet werden. Sämtliche Benutzer, die ursprünglich auf dem Sicherungspool verwaltet wurden, sind keine betroffenen Benutzer.
  
**Benutzererfahrung eines betroffenen Benutzers bei einem Pool in Failback**

|**Benutzerstatus oder -aufgabe**|**Während des Failbacks**|**Nach abgeschlossenem Failback**|
|:-----|:-----|:-----|
|Benutzerstatus des bereits angemeldeten Benutzers  <br/> |Benutzer bleibt angemeldet und mit dem Sicherungspool verbunden. Zu einem gewissen Punkt wird der Benutzer abgemeldet und wieder im ursprünglichen Home-Pool angemeldet, und zwar im Ausfallsicherheitsmodus.  <br/> |Benutzer bleibt angemeldet und wechselt in den regulären Modus.  <br/> |
|Neuer Benutzer meldet sich an.  <br/> |Benutzer können sich am Home-Pool im Ausfallsicherheitsmodus anmelden.  <br/> |Benutzer können sich am ursprünglichen Home-Pool im regulären Modus anmelden.  <br/> |
|Von betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Alle Modalitäten der Konferenz werden abgebrochen. Die Schaltfläche zum erneuten Teilnehmen wird angezeigt. Benutzer können jedoch nicht erneut teilnehmen, während sich der betroffene Benutzer im Ausfallsicherheitsmodus befindet.  <br/> |Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.  <br/> |
|Von nicht betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Der betroffene Benutzer ist auf die Aktionen beschränkt, die er im Ausfallsicherheitsmodus ausführen kann.  <br/> |Die Konferenz wird weiterhin ausgeführt und der betroffene Benutzer kann in der Konferenz verbleiben. Zudem funktionieren alle Modalitäten, nachdem der Benutzer den Ausfallsicherheitsmodus verlassen hat.  <br/> |
|Planen oder Ändern von geplanten Änderungen, Erstellen von Ad-hoc-Konferenzen  <br/> |Nicht möglich, während sich der Benutzer im Ausfallsicherheitsmodus befindet.  <br/> |Für alle Modalitäten verfügbar.  <br/> |
|Anwesenheit, wie sie von anderen Benutzern im selben Pool gesehen wird  <br/> |Die Anwesenheit ist unbekannt, während der Benutzer am Sicherungspool während des Ausfallsicherheitsmodus angemeldet ist.  <br/> |Zeigt den letzten vom Benutzer festgelegten Anwesenheitsstatus. Anwesenheitsänderungen werden nun reflektiert.  <br/> |
|Verfügbarkeit von Kontaktlisten und Adressbuchdienst  <br/> |Nicht verfügbar  <br/> |Verfügbar  <br/> |
|Alle Peer-zu-Peer-Sitzungen und -modalitäten  <br/> |Verfügbar  <br/> |Verfügbar  <br/> |
   
**Benutzererfahrung mit einem verwalteten Benutzer in einem nicht betroffenen Pool während eines Failbacks eines anderen Pools**

|**Benutzeraufgabe**|**Während des Failbacks**|**Nach abgeschlossenem Failback**|
|:-----|:-----|:-----|
|Anwesenheitsinformationen des betroffenen Benutzers anzeigen  <br/> |Zeigt den letzten vom betroffenen Benutzer festgelegten Anwesenheitsstatus an.  <br/> |In Bearbeitung. Nicht betroffene Benutzer sehen Updates, die von betroffenen Benutzern vorgenommen wurden.  <br/> |
|Von betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Alle Modalitäten der Konferenz werden abgebrochen  <br/> |Alle Modalitäten funktionieren nun. Jeder Teilnehmer muss klicken, um wieder an der Konferenz teilzunehmen.  <br/> |
|Von nicht betroffenen Benutzern organisierte laufende Konferenzen  <br/> |Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.  <br/> |Die Konferenz wird weiterhin ausgeführt, der betroffene Benutzer kann in der Konferenz verbleiben und alle Modalitäten funktionieren.  <br/> |
|Alle Peer-zu-Peer-Sitzungen und -modalitäten  <br/> |Verfügbar  <br/> |Verfügbar  <br/> |
   

