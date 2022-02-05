---
title: UCWA-Ereignisse in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
description: 'Zusammenfassung: Erfahren Sie mehr über die Unified Communications Web API (UCWA) in Skype for Business Server.'
---

# <a name="ucwa-events-in-skype-for-business-server"></a>UCWA-Ereignisse in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Unified Communications Web API (UCWA) in Skype for Business Server.
  
Skype for Business Server verwendet die Unified Communications Web API (UCWA) für eine Reihe von Zwecken, vom Zugriff auf Microsoft Exchange für Kontaktsuchen bis zur Aktualisierung der Anwesenheit für mobile Clients.
  
UCWA schreibt Datensätze des Betriebsverhaltens als Ereignistypen Informational, Warning und Error. In der folgenden Tabelle werden die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.
  
|**Ereignis-ID**|**Ereignistyp**|**Zusammenfassung**|**Ursache und Auflösung**|
|:-----|:-----|:-----|:-----|
|20001  <br/> |Zur Information  <br/> |UCWA initialisiert  <br/> |Nicht zutreffend  <br/> N/V  <br/> |
|20002  <br/> |Fehler  <br/> |UCWA ist bei der Initialisierung auf eine unerwartete Ausnahme gestoßen  <br/> |Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.  <br/> Überprüfen Sie die Ausnahmedetails im zugehörigen Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.  <br/> |
|20003  <br/> |Fehler  <br/> |UCWA hat eine ausnahme nicht behandelt  <br/> |Eine unbehandelte Ausnahme ist aufgetreten  <br/> Starten Sie den Server neu. Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20004  <br/> |Fehler  <br/> |Kein Zugriff auf Exchange für HD-Fotos  <br/> |Verbindung mit Exchange ist nicht verfügbar  <br/> Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist.  <br/> |
|20005  <br/> |Zur Information  <br/> |Wiederherstellung nach einem Fehler beim Zugriff auf Exchange für HD-Fotos  <br/> |Nicht zutreffend  <br/> |
|20006  <br/> |Fehler  <br/> |Kein Zugriff auf Exchange für die Kontaktsuche  <br/> |Verbindung mit Exchange ist nicht verfügbar  <br/> Stellen Sie sicher, dass die Verbindung mit Exchange verfügbar ist.  <br/> |
|20007  <br/> |Zur Information  <br/> |Wiederherstellung nach fehlgeschlagener Kontaktsuche in Exchange  <br/> |Nicht zutreffend  <br/> |
|20008  <br/> |Warnung  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Anwendung zu abonnieren  <br/> Überprüfen der Clients auf unnötige Abonnements  <br/> |
|20009  <br/> |Warnung  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren  <br/> |Versuchen Sie, mehr als die zulässigen Anwesenheitsabonnements pro Batch zu abonnieren  <br/> Überprüfen der Clients auf unnötige Abonnements  <br/> |
|20010  <br/> |Fehler  <br/> |Inband-Daten können nicht abgerufen werden  <br/> |Inband-Daten können nicht abgerufen werden  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20011  <br/> |Fehler  <br/> |Anwesenheit kann nicht abonniert werden  <br/> |Anwesenheit kann nicht abonniert werden  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20012  <br/> |Fehler  <br/> |Endpunkt konnte nicht registriert werden  <br/> |Endpunkt konnte nicht registriert werden  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
|20013  <br/> |Fehler  <br/> |CHAT-MCU ist nicht verfügbar  <br/> |CHAT-MCU ist nicht verfügbar  <br/> Überprüfen, ob MCU für Chatnachrichten ausgeführt wird  <br/> |
|20014  <br/> |Zur Information  <br/> |Wiederherstellung nach fehler beim Herstellen einer Verbindung mit DER CHAT-MCU  <br/> |N/V  <br/> |
|20015  <br/> |Fehler  <br/> |AV MCU ist nicht verfügbar  <br/> |AV MCU ist nicht verfügbar  <br/> Überprüfen, ob AV MCU ausgeführt wird  <br/> |
|20016  <br/> |Zur Information  <br/> |Wiederherstellung nach fehlgeschlagener Verbindung mit AV MCU  <br/> |Nicht zutreffend  <br/> |
|20017  <br/> |Fehler  <br/> |AS MCU ist nicht verfügbar  <br/> |AS MCU ist nicht verfügbar  <br/> Überprüfen, ob AS MCU ausgeführt wird  <br/> |
|20018  <br/> |Zur Information  <br/> |Wiederherstellung nach fehlgeschlagener Verbindung mit AS MCU  <br/> |N/V  <br/> |
|20019  <br/> |Fehler  <br/> |Daten-MCU ist nicht verfügbar  <br/> |Daten-MCU ist nicht verfügbar  <br/> Überprüfen, ob Data MCU ausgeführt wird  <br/> |
|20020  <br/> |Zur Information  <br/> |Wiederherstellung nach fehlgeschlagener Verbindung mit Data MCU  <br/> |N/V  <br/> |
|20021  <br/> |Fehler  <br/> |Chat-MCU kann nicht beitreten  <br/> |Chat-MCU kann nicht beitreten  <br/> Überprüfen, ob MCU für Chatnachrichten ausgeführt wird  <br/> |
|20022  <br/> |Fehler  <br/> |Av MCU kann nicht beitreten  <br/> |Av MCU kann nicht beitreten  <br/> Überprüfen, ob AV MCU ausgeführt wird  <br/> |
|20023  <br/> |Fehler  <br/> |As McU kann nicht beitreten  <br/> |As McU kann nicht beitreten  <br/> Überprüfen, ob AS MCU ausgeführt wird  <br/> |
|20024  <br/> |Fehler  <br/> |Daten-MCU kann nicht beitreten  <br/> |Daten-MCU kann nicht beitreten  <br/> Überprüfen, ob Data MCU ausgeführt wird  <br/> |
|20025  <br/> |Fehler  <br/> |Kein Zugriff auf Active Directory für Foto  <br/> |Verbindung mit Active Directory ist nicht verfügbar  <br/> Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.  <br/> |
|20026  <br/> |Zur Information  <br/> |Wiederherstellung nach einem Fehler beim Zugriff auf active directory für Fotos  <br/> |N/V  <br/> |
|20027  <br/> |Warnung  <br/> |Deserialisieren nicht  <br/> |Deserialisieren nicht  <br/> Wenn das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.  <br/> |
   

