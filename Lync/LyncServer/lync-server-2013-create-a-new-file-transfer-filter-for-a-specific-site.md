---
title: Erstellen eines neuen Dateiübertragungsfilters für einen bestimmten Standort
TOCTitle: Erstellen eines neuen Dateiübertragungsfilters für einen bestimmten Standort
ms:assetid: d0006487-5217-491c-b730-e6c551cd9825
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182589(v=OCS.15)
ms:contentKeyID: 49295468
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen eines neuen Dateiübertragungsfilters für einen bestimmten Standort

 

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Zusätzlich zur Änderung des globalen Dateiübertragungsfilters können Sie benutzerdefinierte Dateiübertragungsfilter für spezifische Standorte in Ihrer Lync Server 2013-Bereitstellung konfigurieren. Ausführliche Informationen zur Dateiübertragungsfilterung finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chat](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## So erstellen Sie einen Dateiübertragungsfilter für einen spezifischen Standort

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Chat und Anwesenheit** und dann auf **Dateifilter**.

4.  Klicken Sie auf der Seite **Dateifilter** auf **Neu**.

5.  Klicken Sie im Dialogfeld **Standort auswählen** auf den Standort, für den Sie den Dateiübertragungsfilter erstellen möchten, und klicken Sie anschließend auf **OK**.

6.  Aktivieren Sie im Abschnitt **Neuer Dateifilter** das Kontrollkästchen **Dateifilter aktivieren**.

7.  Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alles blockieren** oder **Bestimmte Dateitypen blockieren**.

8.  Wenn Sie auf **Alles blockieren** geklickt haben, fahren Sie mit Schritt 10 fort.

9.  Führen Sie eine der folgenden Aktionen aus, wenn Sie auf die Option **Bestimmte Dateitypen blockieren** geklickt haben:
    
    1.  Klicken Sie auf **Auswählen**, um die standardmäßige Liste der Erweiterungen für Dateitypen zu ändern, die blockiert werden sollen.
    
    2.  Wählen Sie im Dialogfeld **Dateityp auswählen** die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie die zugehörigen Erweiterungen aus den Kategorien unter **Dateityperweiterungen** entfernen oder sie hinzufügen.
    
    3.  Wenn die Erweiterung des gewünschten Dateityps nicht aufgeführt wird, geben Sie die Erweiterung in das Textfeld unter **Dateityperweiterungen der Liste hinzufügen** ein, und klicken Sie anschließend auf **Hinzufügen**.
    
    4.  Klicken Sie auf **OK**.

10. Klicken Sie auf **Commit ausführen**.

## Siehe auch

#### Aufgaben

[Konfigurieren der Dateiübertragung und der URL-Filterung für Chat](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen URL-Filters für die Verarbeitung von Links in Sofortnachrichtenunterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[Ändern des standardmäßigen Dateiübertragungsfilters](lync-server-2013-modify-the-default-file-transfer-filter.md)  

#### Konzepte

[Ändern des URL-Standardfilters](lync-server-2013-modify-the-default-url-filter.md)

