---
title: 'Lync Server 2013: Verwalten von Ansagen während der Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65627e68b31e23908e9fd5258a69862f7ea15b79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Verwalten von Ansagen während der Notfallwiederherstellung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Lync Server 2013 unterstützt Ankündigungen für Anrufe an nicht zugewiesene Nummern während Ausfällen. Das Wiederherstellen der Ankündigungsfunktion während eines Ausfalls ist optional. Wenn Sie Ankündigungen während eines Ausfalls wiederherstellen möchten, müssen Sie Ihre Ankündigungs Konfiguration im Sicherungspool erneut erstellen. In diesem Abschnitt wird beschrieben, was Sie tun müssen, wenn Sie Ankündigungen während der Disaster Recovery wiederherstellen möchten.

Dieser Abschnitt gilt für nicht zugewiesene Nummernbereiche, in denen die Ankündigungs Anwendung verwendet wird. Dieser Abschnitt gilt nicht für nicht zugewiesene Nummernbereiche, die die automatische UM-Telefonzentrale (Exchange Unified Messaging) verwenden.

<div>

## <a name="before-an-outage"></a>Vor einem Ausfall

Unabhängig davon, ob Sie Ankündigungen während Ausfällen verwenden, sollten Sie separate Sicherungen aller angepassten Audiodateien vornehmen, die Sie für die Ankündigungs Anwendung konfiguriert haben. Angepasste Ankündigungen werden im Rahmen des lync Server Disaster Recovery-Prozesses nicht gesichert. Wenn Sie keine separaten Sicherungen der Dateien vornehmen und die Dateien, die Sie auf den Server oder Pool hochgeladen haben, beschädigt, beschädigt oder gelöscht sind, gehen die Dateien verloren.

Wenn Sie keine Sicherungskopien von angepassten Audiodateien haben und die ursprünglichen Audiodateien nicht mehr zur Verfügung stehen, können Sie die Audiodateien finden, die Sie für eine Ankündigungs Anwendung konfiguriert haben, indem Sie im Dateispeicher nach dem Server oder Pool suchen, in dem Sie ursprünglich die Dateien wurden importiert. Sie können alle Audiodateien kopieren, die Sie für die Ankündigungs Anwendung konfiguriert haben, aus dem Dateispeicher.

**So kopieren Sie Audiodateien aus dem Dateispeicher**

1.  Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Beispiel:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Wobei x-ApplicationServer-x auf die Dienst-ID des Anwendungsservers des Pools verweist (beispielsweise 1-ApplicationServer-1 ")


</div>

<div>

## <a name="during-an-outage"></a>Bei einem Ausfall

Wenn Sie die Ankündigungs Anwendung während eines Ausfalls verwenden möchten, müssen Sie die Ankündigungs Konfiguration im Sicherungspool neu erstellen, indem Sie die in diesem Abschnitt beschriebenen Aufgaben ausführen.

<div>


> [!NOTE]  
> Wir empfehlen, dass Sie diese Aufgaben ausführen, nachdem Sie das Failover für den Sicherungspool durchgeführt haben, denn sobald Sie Schritt 2 ausführen, übernimmt der Sicherungspool den Besitz der nicht zugewiesenen Nummernbereiche.



</div>

<div>


> [!NOTE]  
> Diese Schritte sind für Nummernbereiche, die eine Telefonnummer der automatischen Exchange UM-Telefonzentrale verwenden, nicht erforderlich.



</div>

**So erstellen Sie die Ankündigungs Konfiguration im Sicherungspool erneut**

1.  Erstellen Sie die Ankündigungen, die Sie im primären Pool im Sicherungspool bereitgestellt haben, wie folgt neu:
    
    1.  Importieren Sie alle im primären Pool verwendeten Audiodateien in den Sicherungspool mithilfe des Cmdlets " **Import-CsAnnouncementFile** ", und geben Sie den Sicherungspool für den übergeordneten Parameter an.
    
    2.  Erstellen Sie die einzelnen Ankündigungen neu, indem Sie das Cmdlet **New-CsAnnouncement** verwenden und den Sicherungspool für den übergeordneten Parameter angeben.
    
    <div>
    

    > [!NOTE]  
    > Details zur Verwendung dieser Parameter zum Erstellen von Ankündigungen im Sicherungspool finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Erstellen einer Ankündigung in lync Server 2013</A>.

    
    </div>

2.  Nachdem alle Ankündigungen im Sicherungspool neu erstellt wurden, leiten Sie alle nicht zugewiesenen Nummernbereiche, die Ankündigungen im primären Pool verwenden, auf die neu erstellten Ankündigungen im Sicherungspool um.
    
    Führen Sie für jeden nicht zugewiesenen Nummernbereich, der eine Ankündigung im primären Pool verwendet, die folgenden Aktionen aus:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Nach dem Ausfall

Wenn der primäre Pool verfügbar wird, müssen Sie die nicht zugewiesenen Nummernbereiche, die Sie für den Ausfall geändert haben, wieder in den primären Pool umleiten.

<div>


> [!NOTE]  
> Diese Schritte sind für Nummernbereiche, die eine Telefonnummer der automatischen Exchange UM-Telefonzentrale verwenden, nicht erforderlich.



</div>

**So stellen Sie Ankündigungen im primären Pool wieder her**

1.  Wenn Sie den primären Pool während der Wiederherstellung wiederherstellen mussten, müssen Sie die Ankündigungen im primären Pool neu erstellen, indem Sie die Audiodateien importieren und Ankündigungen erstellen, genau wie im Sicherungspool, mit der Ausnahme, dass Sie den primären Pool für das übergeordnete Element angeben. Parameter. Ausführliche Informationen finden Sie unter "während eines Ausfalls" weiter oben in diesem Thema.

2.  Führen Sie für jeden nicht zugewiesenen Nummernbereich, den Sie für den Ausfall geändert haben, die folgenden Aktionen aus:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Optional können Sie die im Sicherungspool neu erstellten Ankündigungen entfernen. Rufen Sie eine Liste der Ankündigungen für die APP für die Backup-Pool Ankündigung ab. Führen Sie an der Eingabeaufforderung folgenden Befehl aus:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Beispiel:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Suchen Sie in der resultierenden Liste die Ankündigungen, die Sie entfernen möchten, und kopieren Sie die GUIDs. Führen Sie für jede Ankündigung, die Sie entfernen möchten, Folgendes aus:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Beispiel:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

