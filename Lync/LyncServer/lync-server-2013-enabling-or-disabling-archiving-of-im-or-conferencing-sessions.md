---
title: Aktivieren oder Deaktivieren der Archivierung von Instant Messaging- oder Konferenzsitzungen
TOCTitle: Aktivieren oder Deaktivieren der Archivierung von Instant Messaging- oder Konferenzsitzungen
ms:assetid: aa4b5983-dbe1-4d64-8a18-fe2c33994e94
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182567(v=OCS.15)
ms:contentKeyID: 49295039
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren der Archivierung von Instant Messaging- oder Konferenzsitzungen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-10_

In der Systemsteuerung für Lync Server 2013 verwenden Sie Archivierungskonfigurationen zum Aktivieren und Deaktivieren der Archivierung von Sofortnachrichten und/oder Konferenzsitzungen. Dies schließt die folgenden Archivierungskonfigurationen ein:

  - Ein globale Konfiguration, die standardmäßig beim Bereitstellen von Lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.

Die Archivierungskonfigurationen werden erstmalig beim Bereitstellen der Archivierung eingerichtet. Sie können die Konfigurationen jedoch nach der Bereitstellung ändern, hinzufügen und löschen. Ausführliche Informationen zur Implementierung der Archivierungskonfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie von Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder Betriebsdokumentation.


> [!NOTE]
> Für die Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, mit deren Hilfe angegeben wird, ob die Archivierung für die interne Kommunikation und/oder externe Kommunikation von Benutzern aktiviert wird, die in Lync Server 2013 verwaltet werden. Standardmäßig ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert. Bevor Sie die Archivierung in Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional für spezielle Standorte und Pools angeben, wie in diesem Abschnitt beschrieben. Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie sich nach der Bereitstellung der Archivierung für die Verwendung der Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und -dateien auf Exchange 2013-Servern entscheiden und alle Benutzer auf den Exchange 2013-Servern verwaltet werden, sollten Sie die SQL Server-Datenbankkonfiguration aus der Topologie entfernen. Dazu müssen Sie den Topologie-Generator verwenden. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013</A> in der Betriebsdokumentation.



## So aktivieren oder deaktivieren Sie die Archivierung von IM- oder Konferenzsitzungen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Wählen Sie in der Liste der Archivierungskonfigurationen die entsprechende globale Konfiguration, Standortkonfiguration oder Poolkonfiguration aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Details anzeigen**, und führen Sie dann die folgenden Aktionen aus:
    
      - Klicken Sie auf **IM-Sitzungen archivieren**, um die Archivierung ausschließlich für IM-Sitzungen (Instant Messaging, Sofortnachrichten) zu aktivieren.
    
      - Klicken Sie auf **IM- und Konferenzsitzungen archivieren**, um sowohl IM-Sitzungen als auch Konferenzen zu archivieren.
    
      - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.

5.  Klicken Sie auf **Commit**.

## Siehe auch

#### Weitere Ressourcen

[Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
[Konfigurieren und Zuweisen von Archivierungsrichtlinien](lync-server-2013-configuring-and-assigning-archiving-policies.md)

