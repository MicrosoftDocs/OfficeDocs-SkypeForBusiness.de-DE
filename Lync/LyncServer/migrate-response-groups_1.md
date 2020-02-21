---
title: Migrieren von Reaktionsgruppen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204931(v=OCS.15)
ms:contentKeyID: 48184250
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36b37fc6a67a1935c442edb4e2e8ef0d8812315c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Nachdem die Benutzer in lync Server 2013 Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Die Migration von Reaktionsgruppen umfasst das Kopieren von Agentgruppen, Warteschlangen, Workflows und Audiodateien sowie das Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013-Pool. Nachdem Sie Ihre Legacy-Reaktionsgruppen migriert haben, werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im lync Server 2013-Pool verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.

<div>


> [!NOTE]  
> Obwohl Sie Reaktionsgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013 Pool verschieben, wird empfohlen, dass Sie zuerst alle Benutzer verschieben. Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, verfügen erst dann über die vollständige Funktionalität der neuen Features, wenn Sie in den lync Server 2013 Pool verschoben werden.



</div>

Bevor Sie Reaktionsgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der das Reaktionsgruppenanwendung enthält. Das Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert. Sie können sicherstellen, dass der Reaktionsgruppenanwendung durch Ausführen des Cmdlets **Get-CsService – ApplicationServer** installiert wird.

<div>


> [!NOTE]  
> Sie können neue lync Server 2013 Reaktionsgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Vorgänger Reaktionsgruppen migrieren.



</div>

Um Reaktionsgruppen aus einem Legacy Pool in die lync Server 2013 zu migrieren, führen Sie das Cmdlet " **verschieben-CsRgsConfiguration** " aus. Bevor Sie **Move-CsRgsConfiguration** ausführen können, müssen Sie zunächst noch das Schnittstellenpaket für die Abwärtskompatibilität mit Windows Management Instrumentation (WMI) installieren. Führen Sie dazu die Datei "OCSWMIBC.msi" aus. Sie finden diese Datei auf dem Installationsdatenträger im Ordner "Setup".

<div>


> [!IMPORTANT]  
> Das Cmdlet für die Reaktionsgruppen Migration verschiebt die Reaktionsgruppen Konfiguration für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.



</div>

Nachdem Sie die Reaktionsgruppen migriert haben, müssen Sie die URL aktualisieren, mit der formelle Agents sich bei ihren Reaktionsgruppen an-und abmelden, und lync Server-Systemsteuerung-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows verschoben wurden. erfolgreich.

<div>


> [!WARNING]  
> Wenn Sie Reaktionsgruppen migrieren, werden die Office Communications Server 2007 R2 Reaktionsgruppen nicht entfernt. Entfernen Sie Office Communications Server 2007 R2 Reaktionsgruppen nicht. Wenn Sie eine Office Communications Server 2007 R2 Reaktionsgruppe entfernen, werden die Reaktionsgruppen in lync Server 2013 nicht mehr funktionsfähig.



</div>

<div>


> [!IMPORTANT]  
> Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine Office Communications Server 2007 R2 Reaktionsgruppe entfernt wird, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, um wieder lync Server 2013 Reaktionsgruppen auszuführen.



</div>

Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, verbleiben die Agentgruppen, Warteschlangen, Workflows und Audiodateien für mögliche Rollbacks im Vorversionspool. Wenn Sie jedoch keinen Rollback zum Vorversionspool durchführen müssen, müssen Sie das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte wieder in den Vorversionspool zu verschieben.

<div>


> [!IMPORTANT]  
> Warten Sie mit dem Löschen von Reaktionsgruppen aus dem Vorversionspool, bis Sie den Pool außer Betrieb nehmen.



</div>

Bei dem Verfahren, das für die Migration von Reaktionsgruppen Konfigurationen befolgt wird, wird davon ausgegangen, dass Sie eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013 Pools haben. Wenn Sie während der Migration und Bereitstellung Pools konsolidieren oder aufteilen möchten, müssen Sie planen, welche Legacy-Pool-Karten lync Server 2013 Pool zugeordnet werden.

<div>

## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen Konfigurationen

1.  Suchen Sie auf dem Installationsdatenträger die Datei "OCSWMIBC.msi" im Ordner "SetupW", und führen Sie den Installationsvorgang mit der Datei durch.

2.  Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.

3.  Öffnen Sie die Lync Server-Verwaltungsshell.

4.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Beispiel:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Wenn Sie die Registerkarte Reaktionsgruppe für Microsoft Office Communicator 2007 R2 in Ihrer Office Communications Server 2007 R2 Umgebung bereitgestellt haben, entfernen Sie die Registerkarte aus der Datei Office Communicator 2007 R2 Tabs. Xml.
    
    <div>
    

    > [!NOTE]  
    > Formelle Agents verwendeten die Reaktionsgruppen-Registerkarte zur Anmeldung an die entsprechenden Reaktionsgruppen, bevor sie Anrufe empfangen konnten. Wenn Sie die Registerkarte Reaktionsgruppe bereitgestellt haben, haben Sie den Speicherort für die Datei Office Communicator 2007 R2 Tabs. XML ausgewählt, als Sie sie bereitgestellt haben.

    
    </div>

6.  Informieren Sie Benutzer über die aktualisierte URL, die Agents zur An- und Abmeldung bei ihren Reaktionsgruppen benötigen.
    
    <div>
    

    > [!NOTE]  
    > Die URL ist in https://webpoolFQDN/RgsClients/Tab.aspxder Regel, wobei webpoolFQDN der vollqualifizierte Domänenname (FQDN) des webpools ist, der dem Pool zugeordnet ist, den Sie soeben zu lync Server 2013 migriert haben.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist nicht erforderlich, nachdem Benutzer auf lync 2013 aktualisiert haben, da die URL im Menü <STRONG>Extras</STRONG> in lync zur Verfügung steht.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>So überprüfen Sie die Migration von Reaktionsgruppen mithilfe von lync Server-Systemsteuerung

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.

3.  Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

4.  Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

5.  Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentgruppen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>So überprüfen Sie die Migration von Reaktionsgruppen mit Cmdlets

1.  Öffnen Sie die Lync Server-Verwaltungsshell.
    
    Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:
    
        Get-Help <cmdlet name> -Detailed

2.  Geben Sie den folgenden Befehl in der Befehlszeile ein:
    
        Get-CsRgsAgentGroup

3.  Stellen Sie sicher, dass alle Agentengruppen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

4.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsQueue

5.  Stellen Sie sicher, dass alle Warteschlangen in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

6.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsWorkflow

7.  Stellen Sie sicher, dass alle Workflows in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

