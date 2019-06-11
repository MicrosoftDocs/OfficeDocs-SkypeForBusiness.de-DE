---
title: 'Lync Server 2013: Verwalten von Archivierungs Konfigurationsoptionen für Ihre Organisation, ihre Websites und Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10efbf23a503364de7034651d94ced43a8d7b750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung durchgeführt wird. Dies umfasst die folgenden Archivierungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.

Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. In der lync Server 2013-Systemsteuerung können Sie auf **** der Seite Archivierungs-und Überwachungsgruppe auf der Seite Archivierungs **-und Überwachungs** Einstellungen Konfigurationen auf globaler Ebene, Websiteebene und Poolebene verwalten. Ausführliche Informationen dazu, wie Archivierungs Konfigurationen implementiert werden, einschließlich der Optionen, die Sie angeben können, und die Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellung Dokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für alle Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll. Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert. Wenn Sie die Microsoft Exchange-Integration verwenden, müssen Sie Exchange 2013 aktivieren und konfigurieren, um die Archivierung für alle Benutzer zu unterstützen, die sich in Exchange 2013 befinden und deren Postfächer in-situ-Speicher abgelegt wurden.<BR>Vor der Aktivierung der Archivierung sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

**So zeigen Sie Informationen zur Archivierungskonfiguration mithilfe von Windows PowerShell-Cmdlets an**

  - Sie können die Informationen zur Archivierungskonfiguration mithilfe von Windows PowerShell und dem Cmdlet **Get-CsArchivingConfiguration** anzeigen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.
    
    Verwenden Sie in der lync Server-Verwaltungsshell den folgenden Befehl, um Informationen zu allen Archivierungs Konfigurationseinstellungen anzuzeigen:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen einer Archivierungskonfiguration in lync Server 2013 zum Verwalten der Archivierung für bestimmte Websites oder Pools](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Aktivieren oder Deaktivieren der Archivierung von Chat-oder Konferenzsitzungen in lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Aktivieren oder Deaktivieren des Bereinigens archivierter Daten in lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Aktivieren oder Deaktivieren des kritischen Modus in lync Server 2013 zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt](lync-server-2013-enabling-or-disabling-critical-mode-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails.md)

  - [Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Aktivieren oder Deaktivieren der Integration von lync Server 2013 mit Exchange-Speicher](lync-server-2013-enabling-or-disabling-integration-with-exchange-storage.md)

  - [Löschen einer Archivierungskonfiguration in lync Server 2013](lync-server-2013-deleting-an-archiving-configuration.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der Lync Server 2013-Archivierung](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

