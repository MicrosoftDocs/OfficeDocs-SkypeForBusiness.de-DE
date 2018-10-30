---
title: Ändern des standardmäßigen Dateiübertragungsfilters
TOCTitle: Ändern des standardmäßigen Dateiübertragungsfilters
ms:assetid: 791774a2-0bb6-4b5b-aeb0-ff69abb170f4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg521017(v=OCS.15)
ms:contentKeyID: 49294479
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern des standardmäßigen Dateiübertragungsfilters

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Lync Server 2013 bietet einen globalen Dateiübertragungsfilter, der bestimmte Dateitypen während der folgenden dateibezogenen Aktivitäten innerhalb Ihrer Lync Server 2013-Bereitstellung blockiert:

  - Dateiübertragungsanforderungen während Sofortnachrichtenunterhaltungen

  - Dateiuploads und -downloads bei Verwendung der Ausdruckfunktion im Office Live Meeting 2007-Client

  - Multimediawiedergabe während Konferenzen

Je nach den Dateitypen, die Sie blockieren oder zulassen möchten, können Sie den globalen Filter mithilfe der Lync Server-Systemsteuerung ändern. Ausführliche Informationen zur Dateiübertragungsfilterung finden Sie unter [Konfigurieren der Dateiübertragung und der URL-Filterung für Chat](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).

## So ändern Sie den standardmäßigen Dateiübertragungsfilter

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Instant Messaging und Anwesenheit** und dann auf **Dateifilter**.

4.  Doppelklicken Sie auf der Seite **Dateifilter** auf den Filter **Global**.

5.  Aktivieren Sie im Abschnitt **Dateifilter bearbeiten** das Kontrollkästchen **Dateifilter aktivieren**.

6.  Klicken Sie im Dropdown-Listenfeld **Dateiübertragung** auf **Alle blockieren** oder **Bestimmte Dateitypen blockieren**.

7.  Wenn Sie die Option **Alle blockieren** aktiviert haben, fahren Sie mit Schritt 9 fort.

8.  Führen Sie eine der folgenden Aktionen aus, wenn Sie auf die Option **Bestimmte Dateitypen blockieren** geklickt haben:
    
    1.  Klicken Sie auf **Auswählen**, um die standardmäßige Liste der Erweiterungen für Dateitypen zu ändern, die blockiert werden sollen.
    
    2.  Wählen Sie im Dialogfeld **Dateityp auswählen** die Dateitypen aus, die Sie blockieren oder zulassen möchten, indem Sie die zugehörigen Erweiterungen aus den Kategorien unter **Dateityperweiterungen** entfernen oder sie hinzufügen.
    
    3.  Wenn die Erweiterung des gewünschten Dateityps nicht aufgeführt wird, geben Sie die Erweiterung in das Textfeld unter **Neue Dateityperweiterungen zur Liste hinzufügen** ein, und klicken Sie anschließend auf **Hinzufügen**.
    
    4.  Klicken Sie auf **OK**.

9.  Klicken Sie auf **Commit**.

## Siehe auch

#### Aufgaben

[Konfigurieren der Dateiübertragung und der URL-Filterung für Chat](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[Erstellen eines neuen Dateiübertragungsfilters für einen bestimmten Standort](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[Erstellen eines neuen URL-Filters für die Verarbeitung von Links in Sofortnachrichtenunterhaltungen](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  

#### Konzepte

[Ändern des URL-Standardfilters](lync-server-2013-modify-the-default-url-filter.md)

