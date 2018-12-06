---
title: Konfigurieren von Archivierungsoptionen auf globaler Ebene
TOCTitle: Konfigurieren von Archivierungsoptionen auf globaler Ebene
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205233(v=OCS.15)
ms:contentKeyID: 49295280
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Archivierungsoptionen auf globaler Ebene

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

Wenn Sie Ihrer Topologie die Archivierung hinzufügen und die Topologie veröffentlichen, erstellt Lync Server eine globale Konfiguration für die Archivierung. Standardmäßig sind für die globale Konfiguration keine Archivierungsoptionen aktiviert. Die globale Konfiguration bestimmt, welche Optionen für Ihre gesamte Bereitstellung aktiviert werden, außer Sie richten Standort- oder Poolkonfigurationen ein, die die globale Konfiguration außer Kraft setzen.

Ausführliche Informationen zur Funktionsweise der Archivierungskonfigurationen, einschließlich der Hierarchie für globale, Standort- und Poolkonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.


> [!NOTE]
> Sie sollten alle entsprechenden Optionen für die Archivierungskonfigurationen angeben, bevor Sie die Archivierung aktivieren.



## So konfigurieren Sie Archivierungsoptionen auf globaler Ebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Systemsteuerung für Lync Server 2013 zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden zum Starten der Systemsteuerung für Lync Server 2013 finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Global**, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details einblenden**.

5.  Wählen Sie unter **Archivierungseinstellung bearbeiten – Global** in der Dropdownliste **Archivierungseinstellung** eine der folgenden Archivierungsoptionen aus:
    
      - **Archivierung deaktivieren**
    
      - **Chatsitzungen archivieren**
    
      - **Chat- und Webkonferenzsitzungen archivieren**

6.  Führen Sie außerdem auf der Seite **Archivierungseinstellung bearbeiten – Global** die folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration**, um Microsoft Exchange Server zum Speichern von Archivierungsdaten zu verwenden.
    
      - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

7.  Klicken Sie auf **Commit ausführen**.

