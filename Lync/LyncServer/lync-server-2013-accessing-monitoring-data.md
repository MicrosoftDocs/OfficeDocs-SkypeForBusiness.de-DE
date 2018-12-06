---
title: Zugreifen auf Überwachungsdaten in Lync Server 2013
TOCTitle: Zugreifen auf Überwachungsdaten in Lync Server 2013
ms:assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688116(v=OCS.15)
ms:contentKeyID: 49890821
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zugreifen auf Überwachungsdaten in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Überwachungsdaten werden paarweise in SQL Server-Datenbanken gespeichert: Datenbank "LcsCdr" für Kommunikationsdatensätze und "QoEMetrics" für QoE-Daten (Quality of Experience). Zu diesen beiden Datenbanken gibt es nichts Spezielles, d. h., dass auf die in diesen Datenbanken gespeicherten Daten mit allen Tools zugegriffen werden kann, die normalerweise zum Zugriff auf die SQL Server-Daten und zur Analyse verwendet werden.

Ein Tool, das für den Zugriff auf und die Analyse von Überwachungsdaten berücksichtigt werden sollte sind die Lync Server Monitoring-Berichte. Monitoring-Berichte enthalten einen Satz Standardberichte, die von Microsoft SQL Server Reporting Service veröffentlicht werden. Diese Berichte, auf die über einen Webbrowser zugegriffen werden kann, liefern Informationen zu Nutzung, Anrufdiagnose und Medienqualität basierend auf den KDS- und QoE-Datensätzen in den KDS- und QoE-Datenbanken. Monitoring-Berichte gehören zum Lieferumfang von Lync Server 2013 und können mit dem Bereitstellungs-Assistenten von Lync Server nach der Installation von Lync Server installiert werden. Der Monitoring Server wurde somit konfiguriert.

Wie bereits an früherer Stelle angemerkt, ist bei den Monitoring-Berichten SQL Server Reporting Service erforderlich. SQL Server Reporting Service kann gleichzeitig mit SQL Server installiert werden oder auch nach der Installation von SQL Server installiert werden.

Weitere Informationen finden Sie im Thema [Installieren von Lync Server 2013-Überwachungsberichten](lync-server-2013-installing-lync-server-2013-monitoring-reports.md) im Lync Server 2013 Bereitstellungshandbuch.

