---
title: 'Lync Server 2013: Vorbereiten des Active Directory Schemas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d98f7ba4ac0f2efe8a78ebcaacdc966ac5fdf3a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Vorbereiten des Active Directory Schemas in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-27_

Bevor Sie mit der Vorbereitung Active Directory-Domänendienste beginnen, können Sie die Schemadateien mithilfe eines Text-Editors wie Windows Notepad öffnen oder sich [Active Directory Schemaerweiterungen, Klassen und Attribute ansehen, die von lync Server 2013 verwendet](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) werden, um alle Active Directory-Domänendienste Schemaerweiterungen zu überprüfen, die für lync Server 2013 geändert werden. Lync Server verwendet vier Schemadateien:

  - ExternalSchema. ldf, die für die Interoperabilität mit Exchange Server verwendet wird

  - ServerSchema. ldf, bei dem es sich um die primäre lync Server 2013 Schemadatei handelt

  - BackCompatSchema.ldf, verwendet zur Interoperabilität mit allen Komponenten aus vorherigen Versionen

  - VersionSchema.ldf, verwendet für Versionsinformationen des vorbereiteten Schemas

Alle LDF-Dateien werden während der Schemavorbereitung installiert – unabhängig davon, ob Sie eine Migration von einer vorherigen Version oder eine Neuinstallation durchführen. Diese Schemadateien werden in der in der obigen Liste aufgeführten Reihenfolge installiert und befinden sich im \\Ordner\\Support Schema auf dem Installationsmedium.

Die lync Server Schemaerweiterungen werden in allen Domänen repliziert, was sich auf den Netzwerkdatenverkehr auswirkt. Führen Sie die Schemavorbereitung zu einem Zeitpunkt aus, zu dem die Netzwerkauslastung möglichst gering ist.

<div>


> [!NOTE]  
> Wenn Sie Unterstützung für Microsoft® Office Communicator Mobile 2007 R2 für Java und Microsoft® Office Communicator Mobile für Nokia 1,0 Mobile Clients zu ihrer lync Server 2013-Bereitstellung hinzufügen müssen, müssen Sie das Active Directory-Schema für Microsoft Office vorbereiten. Communications Server 2007 R2 bei der Installation von lync Server 2013. Die erforderliche Software und Dokumentation finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>.



</div>

<div>

## <a name="adsi-edit"></a>ADSI-Editor

Der ADSI-Editor (Active Directory Services Interfaces Editor) ist ein AD DS-Verwaltungstool, mit dem Sie die Schemavorbereitung und -replikation überprüfen können.

Die ADSI-Bearbeitung wird standardmäßig installiert, wenn Sie die AD DS Rolle installieren, um einen Server als Domänencontroller zu erstellen. Für Windows Server 2008 und Windows Server 2008 R2 ist ADSI Edit (AdsiEdit. msc) in den Remote Server-Verwaltungs Tools enthalten. Sie können die Remote Dienstprogrammsoftware auch auf Domänenmitgliedsservern oder eigenständigen Servern installieren. Das Remote dienstprogrammor-Paket wird bei der Installation von Windows standardmäßig auf diese Server kopiert, wird jedoch nicht standardmäßig installiert. Sie installieren einzelne Tools mithilfe des Server-Managers. ADSI-Bearbeitung ist unter **Rollenverwaltungstools**, **Active Directory-Domänendienste Tools**, **Active Directory Domänen Controller Tools**enthalten.

Für Windows Server 2003 ist die ADSI-Bearbeitung in den Support Tools enthalten. Die Support Tools stehen auf der Windows Server 2003-CD im Ordner \\Support\\Tools zur Verfügung, oder Sie können Sie unter "Windows Server 2003 Service Pack 2 32-Bit Support Tools" [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)unter herunterladen. Anleitungen zum Installieren der Support Tools auf der Produkt-CD finden Sie unter "Install Windows Support Tools" [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)unter. Adsiedit. dll wird automatisch registriert, wenn Sie die Support Tools installieren. Wenn Sie die Dateien jedoch auf Ihren Computer kopiert haben, müssen Sie den Befehl " **regsvr32** " ausführen, um die Datei "Adsiedit. dll" zu registrieren, bevor Sie das Tool ausführen können.

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Durchführen Active Directory Schemavorbereitung in lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Überprüfen Active Directory Schemareplikation in lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Vorbereiten der Gesamtstruktur auf lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Vorbereiten von Domänen für lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

