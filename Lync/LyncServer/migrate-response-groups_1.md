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
ms.openlocfilehash: 9c01ec246ba99d2a2f71a16179d839409e6b57b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a>Migrieren von Reaktionsgruppen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Nachdem die Benutzer in die lync Server 2013-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Zum Migrieren von Reaktionsgruppen gehören das Kopieren von Agentengruppen, Warteschlangen, Workflows und Audiodateien sowie das Verschieben von Kontaktobjekten der Reaktionsgruppe aus der Legacy Bereitstellung in den lync Server 2013-Pool. Nachdem Sie Ihre Legacy Antwortgruppen migriert haben, werden die Anrufe an die Reaktionsgruppen von der Antwortgruppen Anwendung im lync Server 2013-Pool verarbeitet. Anrufe an Reaktionsgruppen werden nicht mehr vom Legacy Pool verarbeitet.

<div>


> [!NOTE]  
> Obwohl Sie Antwortgruppen migrieren können, bevor Sie alle Benutzer in den lync Server 2013-Pool verschieben, empfiehlt es sich, zuerst alle Benutzer zu verschieben. Insbesondere haben Benutzer, die Reaktionsgruppen-Agents sind, nicht die vollständige Funktionalität der neuen Features, bis Sie in den lync Server 2013-Pool verschoben werden.



</div>

Bevor Sie Antwortgruppen migrieren, müssen Sie einen lync Server 2013-Pool bereitgestellt haben, der die reaktionsgruppenanwendung enthält. Die reaktionsgruppenanwendung wird standardmäßig installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen. Sie können sicherstellen, dass die reaktionsgruppenanwendung installiert ist, indem Sie das Cmdlet " **Get-CsService – ApplicationServer** " ausführen.

<div>


> [!NOTE]  
> Sie können neue lync Server 2013-Antwortgruppen im lync Server 2013-Pool erstellen, bevor Sie Ihre Legacy Antwortgruppen migrieren.



</div>

Führen Sie das Cmdlet **Move-CsRgsConfiguration** aus, um Reaktionsgruppen aus einem Legacy Pool auf den lync Server 2013 zu migrieren. Bevor Sie **Move-CsRgsConfiguration**ausführen können, müssen Sie zuerst das Windows-Verwaltungs Instrumentations Paket (WMI)-abwärts Kompatibilitäts Schnittstellen installieren. Installieren Sie diese Anwendung, indem Sie OCSWMIBC. msi ausführen. Sie können OCSWMIBC. msi auf dem Installationsmedium im Setup-Ordner finden.

<div>


> [!IMPORTANT]  
> Mit dem Cmdlet "Migration der Reaktionsgruppe" wird die Reaktionsgruppen Konfiguration für den gesamten Pool verschoben. Sie können keine bestimmten Gruppen, Warteschlangen oder Workflows auswählen, die migriert werden sollen.



</div>

Nachdem Sie die Antwortgruppen migriert haben, müssen Sie die URL aktualisieren, mit der sich die formellen Agents bei ihren Antwortgruppen an-und abmelden und die lync Server Control Panel-oder lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Agentengruppen,-Warteschlangen und-Workflows verschoben wurden. erfolgreich.

<div>


> [!WARNING]  
> Wenn Sie Antwortgruppen migrieren, werden die Office Communications Server 2007 R2-Antwortgruppen nicht entfernt. Entfernen Sie keine Office Communications Server 2007 R2-Antwortgruppen. Wenn Sie eine Office Communications Server 2007 R2-Reaktionsgruppe entfernen, funktionieren die Antwortgruppen in lync Server 2013 nicht mehr.



</div>

<div>


> [!IMPORTANT]  
> Wir empfehlen, dass Sie keine Daten aus Ihrer vorherigen Bereitstellung entfernen, bevor Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, dass Sie Reaktionsgruppen unmittelbar nach der Migration exportieren. Wenn eine Office Communications Server 2007 R2-Reaktionsgruppe entfernt wird, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit die lync Server 2013-Reaktionsgruppen erneut ausgeführt werden.



</div>

Wenn Sie das Cmdlet **Move-CsRgsConfiguration** ausführen, verbleiben die Agentengruppen,-Warteschlangen,-Workflows und-Audiodateien im Legacy Pool für Rollback-Zwecke. Wenn Sie jedoch einen Rollback zum Legacy Pool durchführen müssen, müssen Sie das Cmdlet **Move-CsApplicationEndpoint** ausführen, um die Kontaktobjekte wieder in den Legacy Pool zu verschieben.

<div>


> [!IMPORTANT]  
> Wir empfehlen, dass Sie keine Antwortgruppen Daten aus dem Legacy Pool löschen, bis Sie den Pool außer Betrieb nehmen.



</div>

Bei der folgenden Vorgehensweise für die Migration von Reaktionsgruppen Konfigurationen wird davon ausgegangen, dass Sie über eine 1:1-Beziehung zwischen Ihren Legacy Pools und den lync Server 2013-Pools verfügen. Wenn Sie beabsichtigen, Pools während ihrer Migration und Bereitstellung zu konsolidieren oder aufzuteilen, müssen Sie planen, welche Legacy Pool-Zuordnungen dem lync Server 2013-Pool zugeordnet werden.

<div>

## <a name="to-migrate-response-group-configurations"></a>So migrieren Sie Reaktionsgruppen Konfigurationen

1.  Suchen Sie OCSWMIBC. msi im Setup-Ordner des Installationsmediums, und installieren Sie es.

2.  Melden Sie sich bei dem Computer mit einem Konto an, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über entsprechende Administratorrechte und-Berechtigungen verfügt.

3.  Öffnen Sie die lync Server-Verwaltungsshell.

4.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Beispiel:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Wenn Sie die Registerkarte Reaktionsgruppe für Microsoft Office Communicator 2007 R2 in Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben, entfernen Sie die Registerkarte aus der Office Communicator 2007 R2-Datei "Tabs. xml".
    
    <div>
    

    > [!NOTE]  
    > Formale Agents verwendeten die Registerkarte Reaktionsgruppe, um sich bei ihren Reaktionsgruppen anzumeldeten, bevor Sie Anrufe empfangen konnten. Wenn Sie die Registerkarte Reaktionsgruppe bereitgestellt haben, haben Sie beim Bereitstellen den Speicherort für die Office Communicator 2007 R2-Datei "Tabs. xml" ausgewählt.

    
    </div>

6.  Stellen Sie den Benutzern die aktualisierte URL zur Verfügung, die die Agents bei ihren Antwortgruppen anmelden müssen.
    
    <div>
    

    > [!NOTE]  
    > Die URL ist in https://webpoolFQDN/RgsClients/Tab.aspxder Regel, wobei webpoolFQDN der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des webpools ist, der dem Pool zugeordnet ist, der gerade zu lync Server 2013 migriert wurde.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Dieser Schritt ist nicht erforderlich, nachdem Benutzer auf lync 2013 aktualisiert haben, da die URL über das Menü <STRONG>Extras</STRONG> in lync zur Verfügung steht.

    
    </div>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a>So überprüfen Sie die Migration der Reaktionsgruppen mithilfe der lync Server-Systemsteuerung

1.  Öffnen Sie die lync Server-Systemsteuerung.

2.  Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen**.

3.  Überprüfen Sie auf der Registerkarte **Workflow** , ob alle Workflows in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

4.  Klicken Sie auf die Registerkarte **Warteschlange** , und stellen Sie sicher, dass alle Warteschlangen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

5.  Klicken Sie auf die Registerkarte **Gruppe** , und stellen Sie sicher, dass alle Agentengruppen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-cmdlets"></a>So überprüfen Sie die Migration der Reaktionsgruppe mithilfe von Cmdlets

1.  Öffnen Sie die lync Server-Verwaltungsshell.
    
    Ausführliche Informationen zu den folgenden Cmdlets finden Sie unter:
    
        Get-Help <cmdlet name> -Detailed

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsAgentGroup

3.  Überprüfen Sie, ob alle Agentengruppen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

4.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsQueue

5.  Überprüfen Sie, ob alle Warteschlangen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

6.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsWorkflow

7.  Überprüfen Sie, ob alle Workflows in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

