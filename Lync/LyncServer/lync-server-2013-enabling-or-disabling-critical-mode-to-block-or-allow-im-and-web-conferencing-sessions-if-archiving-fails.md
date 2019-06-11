---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des kritischen Modus zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>Aktivieren oder Deaktivieren des kritischen Modus in lync Server 2013 zum Blockieren oder Zulassen von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um den kritischen Modus zu aktivieren und zu deaktivieren. Dies umfasst die folgenden Archivierungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.

Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellung Dokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll. Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert. Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie nach der Bereitstellung der Archivierung entscheiden, dass Sie die Exchange Server-Integration verwenden möchten, um Archivierungsdaten und Dateien auf Exchange 2013-Servern zu speichern, und alle Ihre Benutzer auf Ihren Exchange 2013-Servern verwaltet werden, sollten Sie die SQL Server-Datenbankkonfiguration von entfernen. Ihre Topologie. Dazu müssen Sie den Topology Builder verwenden. Ausführliche Informationen finden Sie unter Ändern der Optionen für die <A href="lync-server-2013-changing-archiving-database-options.md">Archivierungsdatenbank in lync Server 2013</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>So aktivieren oder deaktivieren Sie die Blockierung von Chat-und Webkonferenz Sitzungen, wenn die Archivierung fehlschlägt

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:

5.  Aktivieren oder deaktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um das Archivierungsverhalten bei einem Fehler festzulegen.

6.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>Aktivieren und Deaktivieren des kritischen Modus mithilfe von Windows PowerShell-Cmdlets

Sie können den kritischen Modus mithilfe des Cmdlets " **festlegen-CsArchivingConfiguration** " aktivieren oder deaktivieren. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-critical-mode"></a>So aktivieren Sie den kritischen Modus

  - Um den kritischen Modus zu aktivieren, legen Sie den Wert der BlockOnArchiveFailure-Eigenschaft auf true ($true) fest. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>So deaktivieren Sie den kritischen Modus

  - Wenn Sie den kritischen Modus deaktivieren möchten, legen Sie den Wert der BlockOnArchiveFailure-Eigenschaft auf false ($false) fest. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern der Optionen für die Archivierungsdatenbank in lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  


[Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

