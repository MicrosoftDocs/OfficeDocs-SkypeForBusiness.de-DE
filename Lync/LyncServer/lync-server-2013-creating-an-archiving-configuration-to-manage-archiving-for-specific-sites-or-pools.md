---
title: Erstellen einer Archivierungskonfiguration zum Verwalten der Archivierung für bestimmte Standorte oder Pools
TOCTitle: Erstellen einer Archivierungskonfiguration zum Verwalten der Archivierung für bestimmte Standorte oder Pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205251(v=OCS.15)
ms:contentKeyID: 49295345
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer Archivierungskonfiguration zum Verwalten der Archivierung für bestimmte Standorte oder Pools

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der Systemsteuerung für Lync Server 2013 bestimmen Sie mithilfe von Archivierungskonfigurationen, wie die Archivierung in Ihrer Bereitstellung implementiert wird. Dies beinhaltet die folgenden Archivierungskonfigurationen:

  - Eine globale Konfiguration, die beim Bereitstellen von Lync Server 2013 standardmäßig erstellt wird.

  - Optionale Konfigurationen auf Standard- und Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Standorte oder Pools implementiert wird.

Archivierungskonfigurationen richten Sie ursprünglich beim Bereitstellen der Archivierung ein. Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen. Ausführliche Informationen zur Implementierung der Archivierungskonfigurationen, einschließlich der zulässigen Optionen und der Hierarchie der Archivierungskonfigurationen, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.


> [!NOTE]
> Zur Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für Benutzer, die in Lync Server 2013 verwaltet werden, für die interne Kommunikation und/oder für die externe Kommunikation aktiviert werden soll. In der Standardeinstellung ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert. Vor der Aktivierung der Archivierung in Richtlinien sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional wie in diesem Abschnitt beschrieben für bestimmte Standorte und Pools angeben. Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.<BR>Falls Sie nach der Bereitstellung der Archivierung die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und -dateien auf Exchange 2013-Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013-Servern verwaltet werden, sollten Sie die SQL Server-Datenbankkonfiguration aus Ihrer Topologie entfernen. Hierfür müssen Sie den Topologie-Generator verwenden. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013</A> in der Betriebsdokumentation.



## So erstellen Sie eine Archivierungskonfiguration für einen Standort oder einen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu**, und führen Sie eine der folgenden Aktionen aus:
    
      - Um eine Standortarchivierungskonfiguration zu erstellen, klicken Sie auf **Standortkonfiguration**, und wählen Sie dann in **Standort auswählen** den Standort aus, der für die Archivierung konfiguriert werden soll.
    
      - Um eine Poolarchivierungskonfiguration zu erstellen, klicken Sie auf **Poolkonfiguration**, und wählen Sie dann in **Pool auswählen** den Pool aus, der für die Archivierung konfiguriert werden soll.

5.  Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.
    
      - Klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**, um sowohl Chatsitzungen als auch Konferenzen zu archivieren.
    
      - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.

6.  Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivität zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Aktivieren Sie das Kontrollkästchen **Microsoft Exchange-Integration**, um Microsoft Exchange Server zum Speichern von Archivierungsdaten zu verwenden.
    
      - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)**, und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

7.  Klicken Sie auf **Commit ausführen**.

## Erstellen von Archivierungskonfigurationseinstellungen mithilfe der Lync Server-Cmdlets

Archivierungskonfigurationseinstellungen können auch mit Windows PowerShell und dem New-CsArchivingConfiguration-Cmdlet erstellt werden. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Erstellen einer neuen Auflistung von Archivierungskonfigurationseinstellungen für einen Standort

  - Mit dem folgenden Befehl wird eine neue Auflistung von Archivierungskonfigurationseinstellungen für den Standort "Redmond" erstellt:
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

## Erstellen einer neuen Auflistung von Archivierungskonfigurationseinstellungen, die nur die Chatnachrichtenarchivierung erlauben

  - Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet. Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von Archivierungskonfigurationseinstellungen erstellen möchten, die standardmäßig die Archivierung von Chatsitzungen erlauben, verwenden Sie den folgenden Befehl:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

## Angeben mehrerer Eigenschaftswerte beim Erstellen von Archivierungskonfigurationseinstellungen

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Chatsitzungen archiviert werden und Chats blockiert werden, falls der Archivierungsdienst nicht verfügbar ist:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

Weitere Informationen finden Sie im Hilfethema für das [New-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsArchivingConfiguration)-Cmdlet.

## Siehe auch

#### Konzepte

[Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Weitere Ressourcen

[Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

