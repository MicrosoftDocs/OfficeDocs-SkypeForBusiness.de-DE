---
title: Installieren von SQL Server Reporting Services
TOCTitle: Installieren von SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204957(v=OCS.15)
ms:contentKeyID: 49294203
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von SQL Server Reporting Services

 

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Wenn Sie beabsichtigen, Microsoft Lync Server 2013-Monitoring-Berichte zu verwenden (mehr dazu im nächsten Abschnitt in dieser Dokumentation), müssen Sie zuvor SQL Server Reporting Services installieren. Diese können gleichzeitig mit Microsoft SQL Server oder jederzeit danach installiert werden. Wenn Sie SQL Server nicht installiert haben, folgen Sie den an einer früheren Stelle in dieser Dokumentation aufgeführten Anweisungen. Bei der Installation von SQL Server müssen Sie darauf achten, dass Sie auf der Seite "Featureauswahl" die Option "Reporting Services" auswählen. Dadurch werden die SQL Server Reporting Services installiert.

Wenn Sie SQL Server ohne SQL Server Reporting Services installiert haben, können Sie dieses Feature gemäß der entsprechenden Vorgehensweise für SQL Server 2008 R2 bzw. SQL Server 2012 installieren.

Wenn Sie überprüfen möchten, ob die Reporting Services ordnungsgemäß installiert sind, gehen Sie wie folgt vor:

1.  Wenn bei Ihnen Microsoft SQL Server 2008 R2 ausgeführt wird, klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2008 R2**, **Konfigurationstools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.
    
    Bei Microsoft SQL Server 2012 klicken Sie auf **Start**, **Alle Programme**, **Microsoft SQL Server 2012**, **Konfigurationstools**, und klicken Sie dann auf **Konfigurations-Manager für Reporting Services**.

2.  Überprüfen Sie im Dialogfeld **Konfigurationsverbindung für Reporting Services**, ob im Feld **Servername** der Name Ihres Servers und im Feld **Berichtsserverinstanz** der Name der SQL Server-Instanz, die Ihre Überwachungsdaten speichert, angezeigt werden. Klicken Sie auf **Verbinden**.

Im Konfigurations-Manager für Reporting Services sollte im Bereich "Berichtsserverstatus" erkennbar sein, dass SQL Server Reporting Services installiert ist und dass die Reporting Services aktuell ausgeführt werden: Der "Berichtsserverstatus" sollte **Gestartet** lauten, und die Schaltfläche **Starten** sollte ausgegraut und nicht verfügbar sein. Wenn der Berichterstellungsdienst nicht ausgeführt wird, klicken Sie auf **Start**, um den Dienst zu starten.

Wenn neben "Berichtsserver-Datenbankname" keine Datenbank aufgeführt ist, führen Sie Folgendes durch:

1.  Klicken Sie im Konfigurations-Manager für Reporting Services auf **Datenbank**.

2.  Klicken Sie im Bereich "Berichtsserver-Datenbank" auf **Datenbank ändern**.

3.  Aktivieren Sie im Assistenten zum Konfigurieren der Berichtsserver-Datenbank im Bereich "Aktion" den Punkt **Neue Berichtsserver-Datenbank erstellen**, und klicken Sie dann auf **Weiter**.

4.  Überprüfen Sie im Bereich "Datenbankserver", ob die Angaben in den Feldern **Servername**, **Authentifizierungstyp** und **Benutzername** korrekt sind. Klicken Sie auf **Verbindung testen**, um zu überprüfen, ob eine Verbindung zu dem Datenbankserver hergestellt werden kann, und klicken Sie dann auf **Weiter**.

5.  Akzeptieren Sie im Bereich "Datenbank" die Standardwerte für **Datenbankname**, **Sprache** und **Berichtsservermodus**, und klicken Sie dann auf **Weiter**.

6.  Überprüfen Sie, ob im Bereich "Anmeldeinformationen" in der Dropdownliste **Authentifizierungstyp** und in den Feldern **Benutzername** und **Kennwort** die korrekten Informationen aufgeführt sind, und klicken Sie dann auf **Weiter**.

7.  Klicken Sie im Bereich "Zusammenfassung" auf **Weiter**.

8.  Klicken Sie im Bereich "Fortsetzen und Fertigstellen" auf **Fertigstellen**.

Klicken Sie auf **Webdienst-URL**, um zu überprüfen, ob die Berichtsdienst-URLs konfiguriert sind. Unter **URLs für Berichtsserver-Webdienst** sollte mindestens eine URL aufgeführt sein. Klicken Sie auf die einzelnen URLs, um zu überprüfen, ob Sie damit die Startseite für die lokale Installation von SQL Server Reporting Services erreichen.

