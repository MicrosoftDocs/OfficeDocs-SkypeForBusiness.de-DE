---
title: Exportieren von archivierten Daten von Lync Server 2013
TOCTitle: Exportieren von archivierten Daten von Lync Server 2013
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204657(v=OCS.15)
ms:contentKeyID: 49293107
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportieren von archivierten Daten von Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die in Archivierungsdatenbanken archivierten Daten liegen nicht in durchsuchbarem oder lesbarem Format vor. Sie können jedoch mit dem Cmdlet "Export-CsArchivingData" Datensätze aus der Datenbank extrahieren und als EML (Outlook Electronic Mail)-Datei speichern. Ausführliche Informationen zum Exportieren archivierter Daten finden Sie in der Betriebsdokumentation unter [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData).

Wenn Sie die Microsoft Exchange-Integration aktivieren, werden Daten in Exchange 2013-Speichern archiviert. In Exchange 2013 archivierte Daten sind durchsuchbar und auffindbar. Ausführliche Informationen zur Unterstützung für integrierte Kommunikation für Exchange 2013 und Lync Server 2013 finden Sie in der Unterstützungsdokumentation unter [Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md). Ausführliche Informationen zum Zugreifen auf in Exchange archivierte Daten finden Sie in der Exchange 2013-Dokumentation.

## Exportieren von Archivierungsdaten mithilfe der Cmdlets der Lync Server-Verwaltungsshell

Archivierungsdaten können mithilfe des Cmdlets "Export-CSArchivingData" exportiert werden. Das Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

**Exportieren von Archivierungsdaten**

  - Mit diesem Befehl werden alle Archivierungsdaten exportiert, die seit dem 1. Juni 2012 in die Archivierungsdatenbank "atl-sql-001.litwareinc.com" geschrieben wurden. Die entsprechende Ausgabedatei wird im Ordner "C:\\ArchivingExports" gespeichert.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Exportieren von Archivierungsdaten für einen einzelnen Benutzer**

  - Mit dem folgenden Befehl werden Archivierungsdaten für einen einzelnen Benutzer exportiert: kenmyer@litwareinc.com. Hierzu wird der Parameter "UserUri" gefolgt von der SIP-Adresse des Benutzers eingefügt. Beispiel:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Weitere Informationen finden Sie im Hilfethema für das [Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)-Cmdlet.

## Siehe auch

#### Konzepte

[Unterstützung der Integration von Exchange Server und SharePoint in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  

#### Weitere Ressourcen

[Export-CsArchivingData](https://docs.microsoft.com/en-us/powershell/module/skype/Export-CsArchivingData)  
[Verwalten der Lync Server 2013-Archivierung](lync-server-2013-managing-archiving.md)

