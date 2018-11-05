---
title: Konfigurieren von Archivierungsoptionen für einen Standort
TOCTitle: Konfigurieren von Archivierungsoptionen für einen Standort
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204930(v=OCS.15)
ms:contentKeyID: 49294097
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Archivierungsoptionen für einen Standort

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Sie können Archivierungsoptionen für bestimmte Standorte angeben, indem Sie entsprechende Optionen in einer Archivierungskonfiguration für die betreffenden Standorte erstellen und konfigurieren. Eine Standortkonfiguration überschreibt die globale Konfiguration. Dies gilt jedoch nur für den in der Standortkonfiguration angegebenen Standort. Standortkonfigurationen werden von Poolkonfigurationen überschrieben.

Nähere Informationen zur Funktionsweise von Archivierungskonfigurationen, einschließlich der Hierarchie für Konfigurationen auf globaler Ebene sowie auf Standort- und Poolebene, finden Sie in der Planungs-, in der Bereitstellungs- oder in der Betriebsdokumentation unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md).


> [!NOTE]
> Es wird empfohlen, alle erforderlichen Optionen in den Archivierungskonfigurationen festzulegen, bevor Sie die Archivierung aktivieren.




> [!IMPORTANT]
> Zum Aktivieren der Archivierung müssen Archivierungsrichtlinien angegeben werden, um die Archivierung der internen und externen Kommunikation auf globaler Ebene zu steuern. Gegebenenfalls können auch Richtlinien auf Standort- und Benutzerebene angegeben werden. Wenn Sie Richtlinien auf Benutzerebene konfigurieren, müssen Sie die Benutzerrichtlinien bestimmten Benutzern zuweisen. Ausführliche Informationen zum Erstellen und Konfigurieren von Archivierungsrichtlinien finden Sie in der Betriebsdokumentation unter <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Verwalten der Archivierung von interner und externer Kommunikation in Lync Server 2013</A>.



## So konfigurieren Sie die Archivierungsoptionen auf Standortebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die CsArchivingAdministrator- oder die CsAdministrator-Rolle zugewiesen wurde, bei einem Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Systemsteuerung für Lync Server 2013 zu öffnen. Nähere Informationen über die verschiedenen Methoden zum Starten von Systemsteuerung für Lync Server 2013 finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und dann auf **Standortkonfiguration**.

5.  Wählen Sie unter **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.

6.  Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
      - Um nur Sofortnachrichtensitzungen zu archivieren, klicken Sie auf **Sofortnachrichtensitzungen archivieren**.
    
      - Um sowohl Sofortnachrichtensitzungen als auch Konferenzen zu archivieren, klicken Sie auf **Sofortnachrichten- und Webkonferenzsitzungen archivieren**.
    
      - Um die Archivierung für die Richtlinie zu deaktivieren, klicken Sie auf **Archivierung deaktivieren**.

7.  Gehen Sie unter **Neue Archivierungseinstellung** wie folgt vor:
    
      - Aktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um die Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Um Archivierungsdaten mit Microsoft Exchange Server zu speichern, aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration**.
    
      - Zum Aktivieren des Datenlöschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie eine der folgenden Aktionen aus:
        
          - Klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

8.  Klicken Sie auf **Commit**.

