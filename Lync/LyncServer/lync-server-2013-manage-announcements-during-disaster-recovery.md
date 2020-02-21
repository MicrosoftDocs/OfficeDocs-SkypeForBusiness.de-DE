---
title: 'Lync Server 2013: Verwalten von Ankündigungen während der Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 164c58859a6e92abfbb50b79c12b587c3b65c1a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Verwalten von Ankündigungen während der Notfallwiederherstellung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Lync Server 2013 unterstützt Ankündigungen für Anrufe bei nicht zugewiesenen Nummern während Ausfällen. Die Wiederherstellung der Ansagefunktionalität bei einem Ausfall ist optional. Wenn Sie sich dafür entscheiden, Ansagen bei einem Ausfall wiederherzustellen, müssen Sie die Ansagekonfiguration im Sicherungspool erneut erstellen. In diesem Abschnitt wird die Vorgehensweise beschrieben, falls Sie Ansagen bei einer Notfallwiederherstellung wiederherstellen möchten.

Dieser Abschnitt bezieht sich auf nicht zugewiesene Nummernbereiche, die das Ankündigungsanwendung verwenden. Für nicht zugewiesene Nummernbereiche, die die automatische Telefonzentrale von Exchange Unified Messaging (UM) verwenden, ist dieser Abschnitt nicht zutreffend.

<div>

## <a name="before-an-outage"></a>Vor einem Ausfall

Unabhängig davon, ob Sie Ankündigungen während Ausfällen verwenden, sollten Sie separate Sicherungen aller benutzerdefinierten Audiodateien durchführen, die Sie für die Ankündigungsanwendung konfiguriert haben. Benutzerdefinierte Ankündigungen werden im Rahmen des lync Server Notfall Wiederherstellungsprozesses nicht gesichert. Wenn Sie keine separaten Backups der Dateien erstellen und die auf den Server oder in den Pool hochgeladenen Dateien beschädigt, infiziert oder gelöscht werden, sind die Dateien verloren.

Wenn Sie keine Sicherungskopien von benutzerdefinierten Audiodateien haben und die ursprünglichen Audiodateien nicht mehr verfügbar sind, finden Sie die Audiodateien, die Sie für eine Ankündigungsanwendung konfiguriert haben, indem Sie in der Dateispeicher für den Server oder Pool suchen, in dem Sie ursprünglich die Dateien wurden importiert. Sie können alle Audiodateien, die Sie für den Ankündigungsanwendung konfiguriert haben, aus dem Dateispeicher kopieren.

**So kopieren Sie Audiodateien aus dem Dateispeicher**

1.  Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Beispiel:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Dabei steht X-ApplicationServer-X für die Dienst-ID des Anwendungsservers des Pools (z. B. 1-ApplicationServer-1).


</div>

<div>

## <a name="during-an-outage"></a>Bei einem Ausfall

Wenn Sie die Ankündigungsanwendung während eines Ausfalls verwenden möchten, müssen Sie die Ankündigungs Konfiguration im Sicherungspool durch Ausführen der in diesem Abschnitt beschriebenen Aufgaben neu erstellen.

<div>


> [!NOTE]  
> Es wird empfohlen, diese Schritte nach dem Failover auf den Sicherungspool auszuführen. Sobald Sie nämlich Schritt 2 ausführen, wird der Sicherungspool zum Besitzer der nicht zugewiesenen Nummernbereiche.



</div>

<div>


> [!NOTE]  
> Für Nummernbereiche, die eine Exchange UM-Rufnummer der automatischen Telefonzentrale verwenden, sind diese Schritte nicht erforderlich.



</div>

**So erstellen Sie die Ankündigungs Konfiguration im Sicherungspool neu**

1.  Führen Sie die folgenden Aktionen aus, um die Ansagen, die Sie im primären Pool erstellt haben, im Sicherungspool erneut zu erstellen:
    
    1.  Importieren Sie alle im primären Pool verwendeten Audiodateien in den Sicherungspool, indem Sie das Cmdlet **Import-CsAnnouncementFile** verwenden und den Sicherungspool für den Parameter Parent angeben.
    
    2.  Erstellen Sie jede Ansage mit dem **New-CsAnnouncement-Cmdlet neu** , und geben Sie den Sicherungspool für den Parameter Parent an.
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen zur Verwendung dieser Parameter zum Erstellen von Ankündigungen im Sicherungspool finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Create a Announcement in lync Server 2013</A>.

    
    </div>

2.  Nachdem Sie alle Ansagen im Sicherungspool erneut erstellt haben, leiten Sie alle nicht zugewiesenen Nummernbereiche, die Ansagen im primären Pool verwenden, an die erneut erstellten Ansagen im Sicherungspool um.
    
    Für jeden nicht zugewiesenen Nummernbereich, der eine Ansage im primären Pool verwendet, führen Sie folgenden Befehl aus:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Nach einem Ausfall

Wenn der primäre Pool nicht mehr verfügbar ist, müssen Sie die nicht zugewiesenen Nummernbereiche, die Sie für den Ausfall geändert haben, wieder an den primären Pool umleiten.

<div>


> [!NOTE]  
> Für Nummernbereiche, die eine Exchange UM-Rufnummer der automatischen Telefonzentrale verwenden, sind diese Schritte nicht erforderlich.



</div>

**So stellen Sie Ankündigungen im primären Pool wieder her**

1.  Wenn Sie den primären Pool während der Wiederherstellung erneut erstellen mussten, müssen Sie die Ansagen im primären Pool erneut erstellen. Dazu importieren Sie die Audiodateien und erstellen Ankündigungen, so wie das beim Sicherungspool der Fall war, außer dass Sie den primären Pool für den Parent-Parameter angeben. Weitere Informationen hierzu finden Sie unter "Bei einem Ausfall" weiter oben in diesem Thema.

2.  Für jeden nicht zugewiesenen Nummernbereich, den Sie für den Ausfall geändert haben, führen Sie folgenden Befehl aus:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Entfernen Sie optional die Ansagen, die Sie im Sicherungspool erneut erstellt haben. Hier erhalten Sie eine Liste der Ankündigungen für den Sicherungspool Ankündigungsanwendung. Führen Sie an der Eingabeaufforderung Folgendes aus:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Beispiel:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Suchen Sie in der zurückgegebenen Liste die Ansagen, die Sie entfernen möchten, und kopieren Sie die GUIDs. Führen Sie für jede Ansage, die Sie entfernen möchten, Folgendes aus:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Beispiel:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

