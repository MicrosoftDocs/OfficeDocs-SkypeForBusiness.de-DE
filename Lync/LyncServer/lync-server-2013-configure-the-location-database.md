---
title: Konfigurieren der Standortdatenbank in Lync Server 2013
TOCTitle: Konfigurieren der Standortdatenbank in Lync Server 2013
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398679(v=OCS.15)
ms:contentKeyID: 49294631
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Standortdatenbank in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-17_

Sie müssen zunächst die Standortdatenbank konfigurieren, um Clients für die automatische Ermittlung ihres Standorts innerhalb eines Netzwerks zu aktivieren. Wenn Sie keine Standortdatenbank konfigurieren und **Standort erforderlich** in der Ortungsrichtlinie auf **Ja** oder **Haftungsausschluss** festgelegt ist, wird der Benutzer zur manuellen Eingabe eines Standorts aufgefordert.

Zur Konfiguration der Standortdatenbank führen Sie die folgenden Aufgaben aus:

1.  Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) verwenden, müssen Sie diese ELIN in das Feld "CompanyName" eingeben.

2.  Überprüfen Sie die Adressen anhand der MSAG-Daten (Master Street Address Guide), die vom Dienstanbieter für E9-1-1 verwaltet werden.

3.  Veröffentlichen Sie die aktualisierte Datenbank.


> [!NOTE]
> Alternativ können Sie eine sekundäre Standortdatenbank definieren, die anstelle der Standortdatenbank verwendet wird. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren eines sekundären Standortinformationsdiensts in Lync Server 2013</A>.



## In diesem Abschnitt

  - [Auffüllen der Standortdatenbank](lync-server-2013-populate-the-location-database.md)

  - [Überprüfen von Adressen](lync-server-2013-validate-addresses.md)

  - [Veröffentlichen der Standortdatenbank von Lync Server 2013](lync-server-2013-publish-the-location-database.md)

