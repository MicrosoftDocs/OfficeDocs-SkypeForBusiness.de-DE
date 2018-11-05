---
title: Aktivieren oder Deaktivieren der Löschung von archivierten Daten
TOCTitle: Aktivieren oder Deaktivieren der Löschung von archivierten Daten
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520968(v=OCS.15)
ms:contentKeyID: 49293496
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren der Löschung von archivierten Daten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In Systemsteuerung für Lync Server 2013 verwenden Sie Archivierungskonfigurationen, um den Löschvorgang für die Archivierung zu aktivieren oder zu deaktivieren und um zu konfigurieren, wie der Löschvorgang implementiert wird. Hierzu gehören folgende Archivierungskonfigurationen:

  - Eine globale Konfiguration, die bei der Bereitstellung von Lync Server 2013 standardmäßig implementiert wird.

  - Optionale Konfigurationen auf Standort- und Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Standorte oder Pools implementiert wird.

Die Archivierungskonfigurationen werden anfänglich bei der Bereitstellung der Archivierung eingerichtet. Nach der Bereitstellung können Sie aber Konfigurationen ändern, hinzufügen und löschen. Detaillierte Informationen darüber, wie Archivierungskonfigurationen implementiert werden, einschließlich verfügbarer Optionen und Hierarchie der Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.


> [!NOTE]
> Um die Archivierung für Benutzer zu verwenden, die in Lync Server 2013 verwaltet werden, müssen Sie mithilfe von Archivierungsrichtlinien angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beides aktiviert wird. In der Standardeinstellung ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert. Bevor Sie die Archivierung mithilfe von Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional auch für bestimmte Standorte und Pools festlegen, so wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie sich nach der Bereitstellung der Archivierung entscheiden, die Microsoft Exchange-Integration zu verwenden, um Archivierungsdaten und -dateien auf Exchange 2013-Servern zu speichern, und alle Benutzer auf Exchange 2013-Servern verwaltet werden, sollten Sie die SQL Server-Datenbankkonfiguration aus der Topologie entfernen. Hierzu müssen Sie den Topologie-Generator verwenden. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013</A> in der Betriebsdokumentation.



## So aktivieren oder deaktivieren Sie den Löschvorgang für die Archivierung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration. Klicken Sie dann auf **Bearbeiten** und auf **Details anzeigen**, und gehen Sie anschließend folgendermaßen vor.
    
      - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Zum Löschen aller Datensätze klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie die Anzahl der Tage an.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
      - Zum Deaktivieren des Löschvorgangs deaktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**.

5.  Klicken Sie auf **Commit**.

## Aktivieren und Deaktivieren des Löschens von Archivierungsdaten mit den Lync Server-Verwaltungsshell-Cmdlets

Die Aktivierung und Deaktivierung des automatischen Löschens von Archivierungsdaten kann auch mit Windows PowerShell und dem Cmdlet **Set-CsArchivingConfiguration** verwaltet werden. Dieses Cmdlet kann auch über die Verwaltungsshell für Lync Server 2013 oder eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Aktivieren der Löschung aller archivierten Daten

  - Setzen Sie zum Aktivieren der Löschung aller archivierten Daten die Eigenschaft **EnablePurging** auf **True** (**$True**). Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Nachdem Sie diesen Befehl ausgeführt haben, werden von Lync Server alle archivierten Datensätze gelöscht, die älter sind als der für die Eigenschaft **KeepArchivingDataForDays** angegebene Wert.

## Aktivieren der Löschung ausschließlich für exportierte Archivierungsdaten

  - Um das Löschen auf Archivierungsdatensätze zu beschränken, die in eine Datendatei exportiert wurden (mit dem Cmdlet [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)), müssen Sie auch die Eigenschaft **PurgeExportedArchivesOnly** auf **True** (**$True**) setzen. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Nachdem Sie diesen Befehl ausgeführt haben, werden von Lync Server nur die archivierten Datensätze gelöscht, auf die folgende Kriterien zutreffen: 1) sie sind älter als der für die Eigenschaft **KeepArchivingDataForDays** angegebene Wert; und 2) sie wurden mit dem Cmdlet **Export-CsArchivingData** exportiert.

## Deaktivieren der Löschung aller archivierten Daten

  - Setzen Sie zum Deaktivieren der automatischen Löschung von Archivierungsdatensätzen die Eigenschaft **EnablePurging** auf **False** (**$False**). Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

Weitere Informationen, einschließlich zusätzlicher Optionen zum Löschen archivierter Daten, finden Sie im Hilfethema für das Cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration).

## Siehe auch

#### Konzepte

[Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Weitere Ressourcen

[Konfigurieren und Zuweisen von Archivierungsrichtlinien](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

