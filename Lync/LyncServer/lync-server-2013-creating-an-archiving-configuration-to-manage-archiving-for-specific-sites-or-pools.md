---
title: 'Lync Server 2013: Erstellen einer Archivierungskonfiguration zum Verwalten der Archivierung für bestimmte Websites oder Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39ff0add99f41e31ad585b58112146a7f52cc1b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832769"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>Erstellen einer Archivierungskonfiguration in lync Server 2013 zum Verwalten der Archivierung für bestimmte Websites oder Pools

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

In der lync Server 2013-Systemsteuerung verwenden Sie Archivierungs Konfigurationen, um zu steuern, wie die Archivierung in Ihrer Bereitstellung implementiert wird. Dies umfasst die folgenden Archivierungs Konfigurationen:

  - Eine globale Konfiguration, die standardmäßig beim Bereitstellen von lync Server 2013 erstellt wird.

  - Optionale Konfigurationen auf Websiteebene und auf Poolebene, die Sie erstellen und verwenden können, um anzugeben, wie die Archivierung für bestimmte Websites oder Pools implementiert werden soll.

Sie haben zunächst Archivierungs Konfigurationen eingerichtet, wenn Sie die Archivierung bereitstellen, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [wie funktioniert die Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellung Dokumentation oder Betriebsdokumentation.

<div>


> [!NOTE]  
> Um die Archivierung verwenden zu können, müssen Sie Archivierungsrichtlinien so konfigurieren, dass Sie angeben, ob die Archivierung für die interne Kommunikation, für die externe Kommunikation oder für Benutzer, die in lync Server 2013 verwaltet werden, aktiviert werden soll. Standardmäßig ist die Archivierung für die interne oder externe Kommunikation nicht aktiviert. Bevor Sie die Archivierung in einer beliebigen Richtlinie aktivieren, sollten Sie die geeigneten Archivierungs Konfigurationen für Ihre Bereitstellung und optional für bestimmte Websites und Pools angeben, wie in diesem Abschnitt beschrieben. Details zum Aktivieren der Archivierung finden Sie unter <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Konfigurieren und Zuweisen von Archivierungsrichtlinien in lync Server 2013</A> in der Bereitstellungsdokumentation.<BR>Wenn Sie nach der Bereitstellung der Archivierung entscheiden, dass Sie die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013-Servern verwenden möchten und alle Ihre Benutzer auf Ihren Exchange 2013-Servern gespeichert sind, sollten Sie die SQL Server-Datenbankkonfiguration entfernen. aus Ihrer Topologie. Dazu müssen Sie den Topology Builder verwenden. Ausführliche Informationen finden Sie unter Ändern der Optionen für die <A href="lync-server-2013-changing-archiving-database-options.md">Archivierungsdatenbank in lync Server 2013</A> in der Betriebsdokumentation.



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>So erstellen Sie eine Archivierungskonfiguration für eine Website oder einen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie auf der Seite **Archivierungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
      - Wenn Sie eine Website Archivierungskonfiguration erstellen möchten, klicken Sie auf **Websitekonfiguration** , und wählen Sie dann unter **Website auswählen**die Website aus, die für die Archivierung konfiguriert werden soll.
    
      - Wenn Sie eine Pool Archivierungskonfiguration erstellen möchten, klicken Sie auf **Poolkonfiguration** , und wählen Sie dann in **Pool auswählen**den Pool aus, der für die Archivierung konfiguriert werden soll.

5.  Führen Sie unter **Neue Archivierungseinstellung** im Dropdown-Listenfeld **Archivierungseinstellung** eine der folgenden Aktionen aus:
    
      - Klicken Sie auf **Chatsitzungen archivieren**, um die Archivierung ausschließlich für Chatsitzungen zu aktivieren.
    
      - Klicken Sie auf **Chat- und Webkonferenzsitzungen archivieren**, um sowohl Chatsitzungen als auch Konferenzen zu archivieren.
    
      - Klicken Sie auf **Archivierung deaktivieren**, um die Archivierung für die Richtlinie zu deaktivieren.

6.  Führen Sie außerdem in **Neue Archivierungseinstellung** die folgenden Aktionen aus:
    
      - Aktivieren Sie das Kontrollkästchen **Bei Archivierungsfehler Chat- oder Webkonferenzsitzungen blockieren**, um Aktivitäten zu blockieren, wenn die Archivierung nicht verfügbar ist.
    
      - Wenn Sie Microsoft Exchange Server zum Speichern von Archivierungsdaten verwenden möchten, klicken Sie auf das Kontrollkästchen **Microsoft Exchange-Integration** .
    
      - Zum Aktivieren des Löschvorgangs für Daten aktivieren Sie das Kontrollkästchen **Bereinigungsfunktion für alle Archivierungsdaten aktivieren** und führen Sie einen der folgenden Schritte aus:
        
          - Klicken Sie auf **Löschen von exportierten und gespeicherten Archivierungsdaten nach einer Höchstdauer von (Tage)** und geben Sie eine Anzahl von Tagen an, um die archivierten Inhalte nach einer bestimmten Anzahl von Tagen zu löschen.
        
          - Klicken Sie auf **Nur exportierte Archivierungsdaten löschen**, um nur die exportierten Daten zu löschen.

7.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von Archivierungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet New-CsArchivingConfiguration erstellt werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>So erstellen Sie eine neue Sammlung von Archivierungs Konfigurationseinstellungen für eine Website

  - Mit dem folgenden Befehl wird eine neue Auflistung von Archivierungskonfigurationseinstellungen für den Standort „Redmond“ erstellt:
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>So erstellen Sie eine neue Sammlung von Archivierungs Konfigurationseinstellungen, die nur die Chat Archivierung zulassen

  - Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet. Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Sammlung von Archivierungs Konfigurationseinstellungen erstellen möchten, die standardmäßig die Archivierung von Instant Messaging-Sitzungen zulassen, verwenden Sie nur einen Befehl wie den folgenden:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>So geben Sie beim Erstellen von Archivierungs Konfigurationseinstellungen mehrere Eigenschaftswerte an

  - Mehrere Eigenschaftswerte können geändert werden, indem Sie mehrere Parameter angeben. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Chatsitzungen archiviert werden und Chats blockiert werden, falls der Archivierungsdienst nicht verfügbar ist:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Verwalten von Archivierungs Konfigurationsoptionen in lync Server 2013 für Ihre Organisation, ihre Websites und Pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

