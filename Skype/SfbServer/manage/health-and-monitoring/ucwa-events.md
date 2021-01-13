---
title: UCWA-Ereignisse in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Zusammenfassung: Erfahren Sie mehr über die Unified Communications Web API (UCWA) in Skype for Business Server.'
ms.openlocfilehash: d8426418bf01954137a1bbed25d5fef93443dc5c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816665"
---
# <a name="ucwa-events-in-skype-for-business-server"></a>UCWA-Ereignisse in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server verwendet die Unified Communications Web API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontaktsuchen bis zum Aktualisieren der Anwesenheit für mobile Clients.
  
UCWA schreibt Aufzeichnungen des Betriebsverhaltens als Ereignistypen "Informational", "Warning" und "Error". In der folgenden Tabelle werden die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.
  
|**Ereignis-ID**|**Ereignistyp**|**Zusammenfassung**|**Ursache und Lösung**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Informational  <br/> |UCWA initialisiert  <br/> |Nicht zutreffend  <br/> Nicht zutreffend  <br/> |
|20002  <br/> |Error  <br/> |Bei UCWA ist während der Initialisierung eine unerwartete Ausnahme aufgetreten  <br/> |Bei der Initialisierung ist ein unerwarteter Fehler aufgetreten.  <br/> Untersuchen Sie die Ausnahmedetails im zugehörigen Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.  <br/> |
|20003  <br/> |Error  <br/> |Ausnahmefehler bei UCWA  <br/> |Eine nicht behandelte Ausnahme ist eingetreten.  <br/> Starten Sie den Server neu. Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20004  <br/> |Error  <br/> |Zugriff auf Exchange für HD-Foto nicht möglich  <br/> |Verbindung mit Exchange ist nicht verfügbar  <br/> Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist.  <br/> |
|20005  <br/> |Informational  <br/> |Wiederherstellung nach fehler beim Zugriff auf Exchange für HD-Foto  <br/> |Nicht zutreffend  <br/> |
|20006  <br/> |Error  <br/> |Zugriff auf Exchange für Kontaktsuche nicht möglich  <br/> |Verbindung mit Exchange ist nicht verfügbar  <br/> Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist  <br/> |
|20007  <br/> |Informational  <br/> |Wiederherstellung nach fehlerhaftem Suchen des Kontakts in Exchange  <br/> |Nicht zutreffend  <br/> |
|20008  <br/> |Warnung  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren  <br/> Überprüfen der Clients auf nicht benötigte Abonnements  <br/> |
|20009  <br/> |Warnung  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren  <br/> Überprüfen der Clients auf nicht benötigte Abonnements  <br/> |
|20010  <br/> |Error  <br/> |Inbanddaten können nicht abgerufen werden  <br/> |Inbanddaten können nicht abgerufen werden  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20011  <br/> |Error  <br/> |Anwesenheit kann nicht abonniert werden  <br/> |Anwesenheit kann nicht abonniert werden  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20012  <br/> |Error  <br/> |Endpunkt konnte nicht registriert werden  <br/> |Endpunkt konnte nicht registriert werden  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20013  <br/> |Error  <br/> |IM MCU ist nicht verfügbar  <br/> |IM MCU ist nicht verfügbar  <br/> Überprüfen, ob IM MCU ausgeführt wird  <br/> |
|20014  <br/> |Informational  <br/> |Wiederherstellung nach fehler beim Herstellen einer Verbindung mit IM MCU  <br/> |Nicht zutreffend  <br/> |
|20015  <br/> |Error  <br/> |AV MCU ist nicht verfügbar  <br/> |AV MCU ist nicht verfügbar  <br/> Überprüfen, ob AV MCU ausgeführt wird  <br/> |
|20016  <br/> |Informational  <br/> |Wiederherstellung nach fehler beim Herstellen einer Verbindung mit AV MCU  <br/> |Nicht zutreffend  <br/> |
|20017  <br/> |Error  <br/> |AS MCU ist nicht verfügbar  <br/> |AS MCU ist nicht verfügbar  <br/> Überprüfen, ob AS MCU ausgeführt wird  <br/> |
|20018  <br/> |Informational  <br/> |Wiederherstellung nach fehler beim Herstellen einer Verbindung mit AS MCU  <br/> |Nicht zutreffend  <br/> |
|20019  <br/> |Error  <br/> |Daten-MCU ist nicht verfügbar  <br/> |Daten-MCU ist nicht verfügbar  <br/> Überprüfen, ob Data MCU ausgeführt wird  <br/> |
|20020  <br/> |Informational  <br/> |Wiederherstellung nach fehler beim Herstellen einer Verbindung mit Data MCU  <br/> |Nicht zutreffend  <br/> |
|20021  <br/> |Error  <br/> |Teilnahme an IM MCU nicht möglich  <br/> |Teilnahme an IM MCU nicht möglich  <br/> Überprüfen, ob IM MCU ausgeführt wird  <br/> |
|20022  <br/> |Error  <br/> |Beitritt zu AV MCU nicht möglich  <br/> |Beitritt zu AV MCU nicht möglich  <br/> Überprüfen, ob AV MCU ausgeführt wird  <br/> |
|20023  <br/> |Error  <br/> |As MCU kann nicht beitreten  <br/> |As MCU kann nicht beitreten  <br/> Überprüfen, ob AS MCU ausgeführt wird  <br/> |
|20024  <br/> |Error  <br/> |Daten-MCU kann nicht beitreten  <br/> |Daten-MCU kann nicht beitreten  <br/> Überprüfen, ob Data MCU ausgeführt wird  <br/> |
|20025  <br/> |Error  <br/> |Zugriff auf Active Directory für Foto nicht möglich  <br/> |Verbindung mit Active Directory ist nicht verfügbar  <br/> Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.  <br/> |
|20026  <br/> |Informational  <br/> |Wiederherstellung nach fehler beim Zugriff auf Active Directory für Foto  <br/> |Nicht zutreffend  <br/> |
|20027  <br/> |Warnung  <br/> |Deserialisierung nicht möglich  <br/> |Deserialisierung nicht möglich  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
   

