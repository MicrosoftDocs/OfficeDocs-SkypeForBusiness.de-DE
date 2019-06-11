---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren des Bereinigens von archivierten Daten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28eba32895ca928b40e42a04d8d701c7257f1e43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Aktivieren oder Deaktivieren des Bereinigens archivierter Daten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um das Bereinigen zu aktivieren und zu deaktivieren und die Implementierung der Bereinigung zu konfigurieren. Dies umfasst die folgenden Archivierungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.

Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellung Dokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie die Archivierung für Benutzer verwenden möchten, die in lync Server 2013 verwaltet werden, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für beide aktiviert werden soll. Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert. Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie nach der Bereitstellung der Archivierung entscheiden, dass Sie die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013-Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013-Servern gespeichert sind, sollten Sie die SQL Server-Datenbankkonfiguration entfernen. aus Ihrer Topologie. Dazu müssen Sie den Topology Builder verwenden. Ausführliche Informationen finden Sie unter Ändern der Optionen für die <A href="lync-server-2013-changing-archiving-database-options.md">Archivierungsdatenbank in lync Server 2013</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>So aktivieren oder deaktivieren Sie die Bereinigung für die Archivierung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf den Namen der betreffenden Konfiguration auf globaler, Standort- oder Poolebene. Klicken Sie auf **Bearbeiten** und auf **Details anzeigen** und führen Sie dann eine der folgenden Aktionen aus:
    
      - Aktivieren Sie zum Starten des Löschvorgangs das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
        
          - Wenn Sie alle Datensätze löschen möchten, klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie die Anzahl der Tage an.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.
    
      - Deaktivieren Sie zum Beenden des Löschvorgangs das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren**.

5.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Aktivieren oder Deaktivieren des Löschens von Archivierungsdaten mithilfe von Windows PowerShell-Cmdlets

Das Aktivieren und Deaktivieren der automatischen Bereinigung von Archivierungsdaten kann mithilfe von Windows PowerShell und dem Cmdlet " **CsArchivingConfiguration** " verwaltet werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>So aktivieren Sie das Löschen aller Archivierungsdaten

  - Um das Löschen aller Archivierungsdaten zu aktivieren, muss die **EnablePurging** -Eigenschaft auf true ($true) festgelegt werden. Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Nachdem dieser Befehl ausgeführt wurde, löscht lync Server jeden Tag alle Archivierungsdaten Sätze, die älter als der für die **"keeparchivingdatafordays"** -Eigenschaft angegebene Wert sind.

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>So aktivieren Sie das Bereinigen der exportierten Archivierungsdaten

  - Um das Löschen auf das Archivieren von Datensätzen zu begrenzen, die in eine Datendatei exportiert wurden (mithilfe des Cmdlets [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), müssen Sie auch die PurgeExportedArchivesOnly-Eigenschaft auf true festlegen ($true). Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Nachdem dieser Befehl ausgeführt wurde, löscht lync Server nur Archivierungsdaten Sätze, die zwei Kriterien erfüllen: 1) Sie sind älter als der für die **"keeparchivingdatafordays"** -Eigenschaft angegebene Wert; und 2) Sie wurden mit dem Cmdlet **Export-CsArchivingData** exportiert.

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>So deaktivieren Sie das Löschen aller Archivierungsdaten

  - Um das automatisierte Löschen von Archivierungsdaten Sätzen zu deaktivieren, setzen Sie die **EnablePurging** -Eigenschaft auf false ($false). Beispiel:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Weitere Informationen, einschließlich zusätzlicher Optionen zum Bereinigen von Archivierungsdaten, finden Sie im Hilfethema [](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) zum Cmdlet "setCsArchivingConfiguration".

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

