---
title: Importieren von Richtlinien und Einstellungen
TOCTitle: Importieren von Richtlinien und Einstellungen
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205178(v=OCS.15)
ms:contentKeyID: 49295129
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importieren von Richtlinien und Einstellungen

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Nachdem Sie Ihre Office Communications Server 2007 R2-Topologieinformationen mit Ihrem Lync Server 2013-Pilotpool zusammengeführt haben, müssen Sie ein Lync Server 2013-Verwaltungsshell-Cmdlet ausführen, um Ihre Office Communications Server 2007 R2-Richtlinien und -Konfigurationseinstellungen zu Ihrem Lync Server 2013-Pilotpool zu migrieren.

Das Cmdlet **Import-CsLegacyConfiguration** importiert Richtlinien, VoIP-Routen, Wählpläne, Communicator Web Access-URLs und Zugriffsnummern für Einwahlkonferenzen in Lync Server 2013.

## Migrieren von Richtlinien und Einstellungen

1.  Starten Sie auf dem Lync Server 2013-Front-End-Server die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Import-CsLegacyConfiguration
    
    Nachdem die Richtlinien importiert wurden, verwenden Sie folgende Verfahren, um die importierten Richtlinien in der Lync Server-Systemsteuerung anzuzeigen.

## Anzeigen importierter Richtlinien

1.  Öffnen Sie die Lync Server 2013-Systemsteuerung.

2.  Klicken Sie auf **VoIP-Routing** , und zeigen Sie die importierten Richtlinien an.

3.  Klicken Sie auf **Konferenzen** , und zeigen Sie die importierten Richtlinien an.

4.  Klicken Sie auf die Option für Partnerverbund und externen Zugriff , und zeigen Sie die importierten Richtlinien an.

5.  Klicken Sie auf **Überwachung und Archivierung** , und zeigen Sie die importierten Richtlinien an.

