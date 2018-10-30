---
title: 'Lync Server 2013: Vorbereiten des Active Directory-Schemas'
TOCTitle: Vorbereiten des Active Directory-Schemas
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398119(v=OCS.15)
ms:contentKeyID: 49293063
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vorbereiten des Active Directory-Schemas in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bevor Sie mit der Vorbereitung von Active Directory-Domänendienste beginnen, können Sie die Schemadateien mit einem Texteditor öffnen (z. B. mit Windows Editor) oder in der [Active Directory-Schemaerweiterungen, -Klassen und -Attribute, die von Lync Server 2013 verwendet werden](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) alle Active Directory-Domänendienste-Schemaerweiterungen durchsehen, die für Lync Server 2013 geändert werden. In Lync Server werden vier Schemadateien verwendet:

  - ExternalSchema.ldf, verwendet zur Interoperabilität mit Microsoft Exchange Server

  - "ServerSchema.ldf", die primäre Lync Server 2013-Schemadatei

  - BackCompatSchema.ldf, verwendet zur Interoperabilität mit allen Komponenten aus vorherigen Versionen

  - VersionSchema.ldf, verwendet für Versionsinformationen des vorbereiteten Schemas

Alle LDF-Dateien werden während der Schemavorbereitung installiert – unabhängig davon, ob Sie eine Migration von einer vorherigen Version oder eine Neuinstallation durchführen. Diese Schemadateien werden in der Reihenfolge installiert, in der sie in der vorstehenden Liste aufgeführt werden, und befinden sich im Ordner "\\Support\\schema" auf dem Installationsmedium.

Die Lync Server-Schemaerweiterungen werden in allen Domänen repliziert, was sich auf den Netzwerkdatenverkehr auswirkt. Führen Sie die Schemavorbereitung zu einem Zeitpunkt aus, zu dem die Netzwerkauslastung möglichst gering ist.


> [!NOTE]
> Wenn in Ihrer Lync Server 2013-Bereitstellung mobile Clients mit Microsoft®&nbsp;Office Communicator Mobile&nbsp;2007&nbsp;R2 für Java und Microsoft®&nbsp;Office Communicator Mobile für Nokia&nbsp;1.0 unterstützt werden sollen, müssen Sie das Active Directory-Schema für Microsoft Office Communications Server 2007 R2 während der Installation von Lync Server 2013 vorbereiten. Die erforderliche Software und Begleitdokumentation finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.



## ADSI-Editor

Der ADSI-Editor (Active Directory Services Interfaces Editor) ist ein AD DS-Verwaltungstool, mit dem Sie die Schemavorbereitung und -replikation überprüfen können.

Der ADSI-Editor wird standardmäßig installiert, wenn Sie die AD DS-Rolle installieren, um einen Server als Domänencontroller einzusetzen. Bei Windows Server 2008 und Windows Server 2008 R2 ist der ADSI-Editor (adsiedit.msc) in den Remoteserver-Verwaltungstools (Remote Server Administration Tools, RSAT) enthalten. Sie können die Remoteserver-Verwaltungstools auch auf Domänenmitgliedsservern oder eigenständigen Servern installieren. Das RSAT-Paket wird standardmäßig auf diese Server kopiert, wenn Sie Windows installieren. Es wird standardmäßig jedoch nicht installiert. Sie installieren einzelne Tools über den Server-Manager. Sie finden den ADSI-Editor unter **Rollenverwaltungstools** , **Tools für die Active Directory-Domänendienste** , **Tools für Active Directory-Domänencontroller** .

Bei Windows Server 2003 ist der ADSI-Editor in den Supporttools enthalten. Die Supporttools befinden sich auf der Windows Server 2003-CD im Ordner "\\SUPPORT\\TOOLS". Sie können die Tools auch auf der Seite "Supporttools für Windows Server 2003 Service Pack 2 (32 Bit)" unter folgendem Link herunterladen: [http://go.microsoft.com/fwlink/p/?linkId=207172](http://go.microsoft.com/fwlink/p/?linkid=207172). Anweisungen zur Installation der Supporttools von der Produkt-CD finden Sie auf der Seite "Installieren der Windows-Supporttools" unter <http://go.microsoft.com/fwlink/?linkid=125771>. Die Datei "adsiedit.dll" wird automatisch registriert, wenn Sie die Supporttools installieren. Falls Sie die Dateien jedoch auf Ihren Computer kopiert haben, müssen Sie den Befehl **regsvr32** ausführen, um **adsiedit.dll** zu registrieren, bevor Sie das Tool ausführen können.

## In diesem Abschnitt

  - [Ausführen der Active Directory-Schemavorbereitung in Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Überprüfen der Active Directory-Schemareplikation in Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

## Siehe auch

#### Weitere Ressourcen

[Vorbereiten der Gesamtstruktur für Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Vorbereiten von Domänen für Lync Server 2013](lync-server-2013-preparing-domains.md)

