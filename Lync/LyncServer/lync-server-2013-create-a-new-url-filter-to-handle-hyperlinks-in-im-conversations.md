---
title: Erstellen eines neuen URL-Filters für die Verarbeitung von Links in Sofortnachrichtenunterhaltungen
TOCTitle: Erstellen eines neuen URL-Filters für die Verarbeitung von Links in Sofortnachrichtenunterhaltungen
ms:assetid: d0ee01e5-f039-4a34-ac9d-659fe4e9e879
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182590(v=OCS.15)
ms:contentKeyID: 49295478
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen eines neuen URL-Filters für die Verarbeitung von Links in Sofortnachrichtenunterhaltungen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Zusätzlich zur Änderung des globalen URL-Filters können Sie benutzerdefinierte URL-Filter für einzelne Standorte in Ihrer Lync Server 2013-Bereitstellung konfigurieren. Ausführliche Informationen zur URL-Filterung finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chat](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## So erstellen Sie einen neuen URL-Filter

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** und dann auf **URL-Filter**.

4.  Klicken Sie auf der Seite **URL-Filter** auf **Neu**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, für den Sie den URL-Filter erstellen möchten, und klicken Sie anschließend auf **OK**.

6.  Aktivieren Sie im Dialogfeld **Neuer URL-Filter** das Kontrollkästchen **URL-Filter aktivieren**, um die URL-Filterung für den Standort zu aktivieren.

7.  Wenn Sie alle aktiven URLs blockieren möchten, die eine Datei mit einer der unter **Dateityperweiterungen, die blockiert werden sollen** aufgeführten Erweiterungen enthalten, aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **URLs mit Dateierweiterung blockieren**.

8.  Klicken Sie im Dropdown-Listenfeld **Linkpräfix** auf die gewünschte Option zur Verarbeitung von URLs in Sofortnachrichtenunterhaltungen.
    
    Über die Option **Nachricht zulassen** wird dem Benutzer beim Senden eines zulässigen Links eine Warnmeldung angezeigt.

9.  Klicken Sie auf **Commit ausführen**.

## Siehe auch

#### Aufgaben

[Konfigurieren der Dateiübertragung und der URL-Filterung für Chat](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen Dateiübertragungsfilters für einen bestimmten Standort](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Ändern des standardmäßigen Dateiübertragungsfilters](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### Konzepte

[Ändern des URL-Standardfilters](lync-server-2013-modify-the-default-url-filter.md)

