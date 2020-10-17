---
title: 'Lync Server 2013: Verwalten von Archivierungs Konfigurationsoptionen für Ihre Organisation, Standorte und Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Archiving configuration options for your organization, sites, and pools
ms:assetid: 377a6f80-5f2b-4bc1-b507-e930a461fb1d
ms:mtpsurl: https://technet.microsoft.com/library/JJ204802(v=OCS.15)
ms:contentKeyID: 48183830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fd9b777f3c7dbfc008f0b985a9c1512aaeb52d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498362"
---
# <a name="managing-archiving-configuration-options-in-lync-server-2013-for-your-organization-sites-and-pools"></a>Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Standorte und Pools

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um anzugeben, wie die Archivierung implementiert wird. Dies schließt die folgenden Archivierungskonfigurationen ein:

  - Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.

  - Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.

Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen. In lync Server 2013 Systemsteuerung können Sie die Seite **Archivierungskonfiguration** der Gruppe **Archivierung und Überwachung** verwenden, um Konfigurationen auf globaler Ebene, auf Standortebene und auf Poolebene zu verwalten. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Für die Verwendung der Archivierung müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für externe Kommunikationen oder für alle Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll. Standardmäßig ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert. Wenn Sie Microsoft Exchange Integration verwenden, müssen Sie Exchange 2013 aktivieren und konfigurieren, um die Archivierung für alle Benutzer zu unterstützen, die in Exchange 2013 verwaltet werden, deren Postfächer In-Place Aufbewahrungsspeicher abgelegt wurden.<BR>Bevor Sie die Archivierung aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional auch für bestimmte Standorte und Pools festlegen, so wie in diesem Abschnitt beschrieben. Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

**So zeigen Sie Informationen zur Archivierungskonfiguration mithilfe von Windows PowerShell-Cmdlets an**

  - Sie können die Informationen zur Archivierungskonfiguration mit Windows PowerShell und dem Cmdlet **Get-CsArchivingConfiguration** anzeigen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .
    
    Verwenden Sie im lync Server-Verwaltungsshell den folgenden Befehl, um Informationen zu allen Archivierungs Konfigurationseinstellungen anzuzeigen:
    
        Get-CsArchivingConfiguration

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Erstellen einer Archivierungskonfiguration in lync Server 2013 zur Verwaltung der Archivierung für bestimmte Standorte oder Pools](lync-server-2013-creating-an-archiving-configuration-to-manage-archiving-for-specific-sites-or-pools.md)

  - [Aktivieren oder Deaktivieren der Archivierung von Chat-oder Konferenzsitzungen in lync Server 2013](lync-server-2013-enabling-or-disabling-archiving-of-im-or-conferencing-sessions.md)

  - [Aktivieren oder Deaktivieren der Löschung archivierter Daten in lync Server 2013](lync-server-2013-enabling-or-disabling-the-purging-of-archived-data.md)

  - [Aktivieren oder Deaktivieren des kritischen Modus in lync Server 2013 zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt](lync-server-2013-enable-disable-critical-mode.md)

  - [Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

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

