---
title: Aktivieren oder Deaktivieren des kritischen Modus, um Instant Messaging- und Webkonferenzsitzungen bei Archivierungsfehlern zu blockieren oder zuzulassen
TOCTitle: Aktivieren oder Deaktivieren des kritischen Modus, um Instant Messaging- und Webkonferenzsitzungen bei Archivierungsfehlern zu blockieren oder zuzulassen
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182609(v=OCS.15)
ms:contentKeyID: 49295979
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren oder Deaktivieren des kritischen Modus, um Instant Messaging- und Webkonferenzsitzungen bei Archivierungsfehlern zu blockieren oder zuzulassen

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In Systemsteuerung für Lync Server 2013 verwenden Sie Archivierungskonfigurationen, um den kritischen Modus zu aktivieren bzw. zu deaktivieren. Dies umfasst die folgenden Archivierungskonfigurationen:

  - Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie Lync Server 2013 bereitstellen.

  - Optionale Konfigurationen auf Standort- und auf Benutzerebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Standorte oder Benutzer implementiert wird.

Archivierungskonfigurationen richten Sie zunächst ein, wenn Sie die Archivierung bereitstellen. Sie können Konfigurationen aber nach der Bereitstellung ändern, hinzufügen und löschen. Ausführliche Informationen dazu, wie Archivierungskonfigurationen implementiert werden, z.\&nbsp;B. welche Optionen Sie angeben können und welche Hierarchie für die Archivierungskonfigurationen gilt, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, der Bereitstellungs- oder Betriebsdokumentation.


> [!NOTE]
> Damit Sie die Archivierung nutzen können, müssen Sie Archivierungsrichtlinien konfigurieren, die angeben, ob für unter Lync Server 2013 verwaltete Benutzer die Archivierung für interne Kommunikation, für externe Kommunikation oder für beides aktiviert werden soll. Standardmäßig ist die Archivierung weder für interne noch für externe Kommunikation aktiviert. Bevor Sie die Archivierung in Richtlinien aktivieren, sollten Sie die richtigen Archivierungskonfigurationen für Ihre Bereitstellung und (optional) für bestimmte Standorte und Pools angeben, wie im vorliegenden Abschnitt beschrieben. Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie nach der Bereitstellung der Archivierung beschließen, die Exchange Server-Integration zu verwenden, um Archivierungsdaten und -dateien auf Exchange 2013-Servern zu speichern und alle Benutzer auf den Exchange 2013-Servern verwaltet werden, sollten Sie die SQL Server-Datenbankkonfiguration aus der Topologie entfernen. Dazu müssen Sie den Topologie-Generator verwenden. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013</A> in der Betriebsdokumentation.



## So aktivieren oder deaktivieren Sie die Blockierung von Instant Messaging- und Webkonferenzsitzungen bei Archivierungsfehlern

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten**, dann auf **Details anzeigen**, und führen Sie dann eine der folgenden Aktionen aus:

5.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **Instant Messaging- oder Webkonferenzsitzungen bei Archivierungsfehlern blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.

6.  Klicken Sie auf **Commit**.

## Aktivieren und Deaktivieren des kritischen Modus mithilfe der Lync ServerWindows PowerShell-Cmdlets

Sie können den kritischen Modus mithilfe des **Set-CsArchivingConfiguration**-Cmdlets aktivieren oder deaktivieren. Dieses Cmdlet können Sie entweder in der Verwaltungsshell für Lync Server 2013 ausführen oder in einer Remotesitzung von Windows PowerShell.

## Aktivieren des kritischen Modus

  - Zum Aktivieren des kritischen Modus legen Sie den Wert der **BlockOnArchiveFailure**-Eigenschaft auf **True ($True)** fest. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

## Deaktivieren des kritischen Modus

  - Zum Deaktivieren des kritischen Modus legen Sie den Wert der **BlockOnArchiveFailure**-Eigenschaft auf **False ($False)** fest. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

Weitere Informationen finden Sie im Hilfethema zum [Set-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsArchivingConfiguration)-Cmdlet.

## Siehe auch

#### Aufgaben

[Ändern von Optionen für Archivierungsdatenbanken in Lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  

#### Konzepte

[Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md)  

#### Weitere Ressourcen

[Verwalten von Konfigurationsoptionen für die Archivierung in Lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)

