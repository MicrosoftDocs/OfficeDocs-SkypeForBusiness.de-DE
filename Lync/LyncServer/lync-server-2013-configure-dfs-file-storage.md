---
title: 'Lync Server 2013: Konfigurieren des Dateispeichers'
TOCTitle: Konfigurieren des Dateispeichers
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205150(v=OCS.15)
ms:contentKeyID: 49295037
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren des Dateispeichers für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server 2013 unterstützt die Verwendung von Dateifreigaben auf einem DFS (Distributed File System). Ausführliche Informationen zu DFS für Windows Server 2008 finden Sie in der Schritt-für-Schritt-Anleitung für Windows Server 2008 unter [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835). Für die DFS-Verwendung ist für Lync Server 2013 Folgendes erforderlich:

  - Namespaces sind domänenbasiert

  - Auf allen Namespace-Servern wird mindestens Windows 2008 ausgeführt

Für die Einrichtung von Lync Server 2013 ist es erforderlich, dass die Berechtigungen für den freigegebenen Ordner dem Administrator den vollständigen Zugriff ermöglichen. Lync Server 2013 verwendet dann die NTFS-Dateiberechtigungen für die Zugriffssteuerungsliste der Ordner. Zum Einschränken des Zugriffs werden keine geerbten DFS-Freigabeberechtigungen verwendet.

Ausführlichere Informationen zu den Dateifreigabeanforderungen finden Sie unter [Dateispeicherunterstützung in Lync Server 2013](lync-server-2013-file-storage-support.md) in der Unterstützungsdokumentation.

Im folgenden Verfahren wird die ordnungsgemäße Konfiguration von Berechtigungen für freigegebene Ordner mithilfe des DFS-Namespace-Assistenten beschrieben (siehe Beschreibung in der Anleitung zur DFS-Einrichtung).

## So konfigurieren Sie Berechtigungen für freigegebene Ordner

1.  Klicken Sie auf **Start** , zeigen Sie auf **Alle Programme** und auf **Verwaltung** , und klicken Sie dann auf **DFS-Verwaltung** .

2.  Klicken Sie in der Konsolenstruktur des DFS-Verwaltungs-Snap-Ins mit der rechten Maustaste auf den Namespace-Server (z. B. "filesrv1.contoso.com"), und klicken Sie dann auf **Einstellungen bearbeiten** .

3.  Wählen Sie **Berechtigungen für freigegebene Ordner** aus.

4.  Wählen Sie **Benutzerdefinierte Berechtigungen verwenden** aus.

5.  Wählen Sie für die Administratorgruppe unter **Zulassen** Folgendes aus:
    
      - **Vollzugriff**
    
      - **Ändern**
    
      - **Lesen**

6.  Klicken Sie auf **Übernehmen** und dann auf **OK** .

