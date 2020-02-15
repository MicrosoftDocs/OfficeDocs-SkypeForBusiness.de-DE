---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren der Löschung archivierter Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Aktivieren oder Deaktivieren der Löschung archivierter Daten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

In lync Server 2013 Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um die Bereinigung zu aktivieren und zu deaktivieren und zu konfigurieren, wie das Löschen implementiert wird. Dies schließt die folgenden Archivierungskonfigurationen ein:

  - Eine globale Konfiguration, die standardmäßig erstellt wird, wenn Sie lync Server 2013 bereitstellen.

  - Optionale Konfigurationen auf Standort- und Poolebene, die Sie zum Angeben der Implementierungsart für spezielle Standorte oder Pools erstellen und verwenden können.

Sie legen Archivierungskonfigurationen anfangs fest, wenn Sie Archivierungen bereitstellen, Sie können jedoch nach der Bereitstellung Konfigurationen ändern, hinzufügen und löschen. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [How Archiving Works in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>


> [!NOTE]  
> Um die Archivierung für Benutzer zu verwenden, die in lync Server 2013 verwaltet werden, müssen Sie Archivierungsrichtlinien konfigurieren, um anzugeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beides aktiviert werden soll. In der Standardeinstellung ist die Archivierung weder für die interne noch für die externe Kommunikation aktiviert. Bevor Sie die Archivierung mithilfe von Richtlinien aktivieren, sollten Sie die entsprechenden Archivierungskonfigurationen für Ihre Bereitstellung und optional auch für bestimmte Standorte und Pools festlegen, so wie in diesem Abschnitt beschrieben. Ausführliche Informationen zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie nach der Bereitstellung der Archivierung, die Sie Microsoft Exchange Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013 Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013 Servern verwaltet werden, entscheiden, sollten Sie die SQL Server Datenbankkonfiguration entfernen. aus Ihrer Topologie. Sie müssen den Topologie-Generator verwenden, um dies zu tun. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-changing-archiving-database-options.md">Ändern von Archivierungsdatenbank Optionen in lync Server 2013</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>So aktivieren oder deaktivieren Sie den Löschvorgang für die Archivierung

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der entsprechenden globalen, Standort- oder Poolkonfiguration. Klicken Sie dann auf **Bearbeiten** und auf **Details anzeigen**, und gehen Sie anschließend folgendermaßen vor.
    
      - Zum Aktivieren des Löschvorgangs aktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**, und führen Sie einen der folgenden Schritte aus:
        
          - Zum Löschen aller Datensätze klicken Sie auf **Exportierte Archivierungsdaten und gespeicherte Archivierungsdaten löschen nach spätestens (Tage)**, und geben Sie die Anzahl der Tage an.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
      - Zum Deaktivieren des Löschvorgangs deaktivieren Sie das Kontrollkästchen **Löschen von Archivierungsdaten aktivieren**.

5.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Löschens von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets

Das Aktivieren und Deaktivieren der automatischen Bereinigung von Archivierungsdaten kann mit Windows PowerShell und dem Cmdlet " **CsArchivingConfiguration** " verwaltet werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>So aktivieren Sie das Löschen aller Archivierungsdaten

  - Um das Löschen aller Archivierungsdaten zu ermöglichen, legen Sie die **"enablepurging"** -Eigenschaft auf true ($true) fest. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Nach dem Ausführen dieses Befehls werden lync Server alle Archivierungsdaten Sätze, die älter sind als der für die **"keeparchivingdatafordays"** -Eigenschaft angegebene Wert, jeden Tag gelöscht.

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>So aktivieren Sie das Löschen von exportierten Archivierungsdaten

  - Zum Begrenzen des Löschvorgangs auf Archivierungsdaten Sätze, die in eine Datendatei exportiert wurden (mithilfe des [Export-CsArchivingData-](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) Cmdlets), müssen Sie auch die "purgeexportedarchivesonly"-Eigenschaft auf true ($true) festlegen. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Nach Ausführung dieses Befehls löscht lync Server nur Archivierungsdaten Sätze, die zwei Kriterien erfüllen: 1) Sie sind älter als der für die **"keeparchivingdatafordays"** -Eigenschaft angegebene Wert; und 2) Sie wurden mit dem **Export-CsArchivingData-** Cmdlet exportiert.

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>So deaktivieren Sie das Löschen aller Archivierungsdaten

  - Wenn Sie das automatische Löschen von Archivierungsdaten Sätzen deaktivieren möchten, legen Sie die **"enablepurging"** -Eigenschaft auf false ($false) fest. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Weitere Informationen, einschließlich zusätzlicher Optionen zum Löschen von Archivierungsdaten, finden Sie im Hilfethema für das Cmdlet " [setCsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) ".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, Standorte und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

