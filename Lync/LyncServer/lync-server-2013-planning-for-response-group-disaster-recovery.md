---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3a196a258198fe0bc65b533841544decd96aa2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a>Planen der Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In diesem Abschnitt werden einige Möglichkeiten beschrieben, wie Sie Reaktionsgruppen für die Disaster Recovery vorbereiten und eine Übersicht über den Disaster Recovery-Prozess erhalten.

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a>Vorbereiten der Disaster Recovery einer Reaktionsgruppe

Beachten Sie bei der Vorbereitung und Durchführung von Disaster Recovery-Verfahren Folgendes:

<div>


> [!NOTE]  
> In einer Koexistenz-Umgebung werden nur die lync Server 2013-Reaktionsgruppen für die in diesem Dokument beschriebenen Disaster Recovery-Verfahren unterstützt.



</div>

  - Planen Sie die Disaster Recovery, wenn Sie Ihre Kapazitätsplanung durchführen. Für die Disaster Recovery-Kapazität sollten alle Pools in einem gekoppelten Pool in der Lage sein, die Arbeitslasten aller Reaktionsgruppen in beiden Pools zu verarbeiten. Details zur Kapazitätsplanung der Reaktionsgruppe finden Sie unter [Kapazitätsplanung für die Reaktionsgruppe in lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Nehmen Sie regelmäßige Sicherungskopien aller Reaktionsgruppen Konfigurationen in allen Front-End-Pools auf, in denen Sie die Antwortgruppen Anwendung mithilfe des in diesem Dokument beschriebenen Exportvorgangs bereitgestellt haben. Ausführliche Informationen finden Sie unter [Disaster Recovery-Verfahren für die Reaktionsgruppe in lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Bewahren Sie die Sicherungskopien an einem sicheren Ort auf.

  - Bewahren Sie eine separate Sicherungskopie aller Original-Audiodateien auf, die Sie für die reaktionsgruppenanwendung verwendet haben, einschließlich Aufnahmen und Musik-in-halten-Dateien. Bewahren Sie die Sicherungsdateien an einem sicheren Ort auf.

  - Bei der Disaster-Wiederherstellung in lync Server 2013 müssen alle Einstellungen für die Reaktionsgruppe eindeutige Namen für Ihre Bereitstellung aufweisen. Diese Anforderung gilt für Workflows, Warteschlangen, Agentengruppen, Feiertagssätze und Geschäftsstunden. Überprüfen Sie, ob diese Anforderung erfüllt ist, wenn die primären und die Sicherungs Pools noch aktiv sind, und bevor Sie eine Failover-Prozedur initiieren müssen. Wenn beim Importieren von Antwortgruppen Daten in den Sicherungspool Namenskonflikte auftreten, schlägt der Import fehl. Um das Import-und FailoverVerfahren abzuschließen, müssen Sie die Namenskonflikte lösen, indem Sie das Reaktionsgruppen Objekt im Sicherungspool umbenennen oder das Cmdlet " **Import-CsRgsConfiguration** " mit dem Parameter "– ResolveNameConflicts" verwenden, um den Konflikt automatisch zu beheben, indem Sie eine eindeutige identifizierende Nummer an das Antwortgruppen Objekt anfügen.

  - Im Allgemeinen empfehlen wir, dass Sie tägliche Sicherungen durchführen, aber wenn Sie über eine große Anzahl von Änderungen verfügen, möchten Sie möglicherweise häufigere Sicherungen planen. Die Menge der Informationen, die Sie bei einem Notfall verlieren können, hängt von der Häufigkeit Ihrer Sicherungen sowie von Häufigkeit und Umfang der Änderungen ab.

  - Es ist möglich, Antwortgruppen in einen Backup-Pool zu importieren, bevor ein Notfall-oder Failover-Vorgang stattfindet. Wenn Sie Reaktionsgruppen im Voraus importieren, verringert sich die Ausfallzeit, da der lync Server Response Group-Dienst im Sicherungspool wiederhergestellt werden kann, sobald Anrufe an den Sicherungspool weitergeleitet werden.
    
    <div>
    

    > [!NOTE]  
    > Die reaktionsgruppenanwendung kann keine Agents erreichen, die in einem inaktiven Pool verwaltet werden, bis das Failover abgeschlossen ist. Während dieser Zeit verarbeitet die reaktionsgruppenanwendung Anrufe, als ob diese Agents nicht verfügbar sind.

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a>Disaster Recovery-Prozess der Reaktionsgruppe

Im Fall eines Notfalls können Sie Reaktionsgruppen mithilfe einer der folgenden Wiederherstellungsmethoden wiederherstellen:

  - Führen Sie einen Failover zu einem Sicherungspool durch, und führen Sie dann einen Fehler zurück zum ursprünglichen Pool aus.

  - Führen Sie einen Failover zu einem Sicherungspool durch, erstellen Sie einen neuen Pool mit einem anderen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN), und importieren Sie dann die Antwortgruppen in den neuen Pool.

Während der Failover-Phase der Disaster Recovery befinden sich die Reaktionsgruppen in mehreren Pools: im primären Pool (der nicht verfügbar ist) und im Sicherungspool. Die Antwortgruppen in beiden Pools haben denselben Namen und denselben Besitzer (den primären Pool), haben aber unterschiedliche übergeordnete Elemente.

Wenn Sie eine Wiederherstellung durch Erstellen eines neuen Pools mit einem anderen FQDN durchführen, müssen Sie den neuen Pool als Besitzer der Antwortgruppen zuweisen, wenn Sie ihn importieren. Der Besitz von Reaktionsgruppen verbleibt mit dem ursprünglichen Pool, es sei denn, dass Sie den Besitz mithilfe des-OverwriteOwner-Parameters mit dem **Import-CsRgsConfiguration-** Cmdlet explizit neu zuweisen.

<div>


> [!NOTE]  
> Sie müssen auch den – OverwriteOwner-Parameter verwenden, wenn Sie den Pool während der Wiederherstellung neu erstellt haben (also die Antwortgruppen Datenbank leer ist), unabhängig davon, ob Sie den gleichen FQDN verwenden oder nicht. Sie müssen den-OverwriteOwner-Parameter nicht verwenden, wenn Sie den Pool nicht neu erstellt haben, es jedoch zulässig ist, diesen Parameter immer dann zu verwenden, wenn Sie Antwortgruppen wieder in den primären Pool importieren.



</div>

Pro Pool können Sie nur einen Satz von Reaktionsgruppen-Konfigurationseinstellungen auf Anwendungsebene definieren. Zu diesen Einstellungen gehören die standardmäßige Musik-in-halten-Konfiguration, die standardmäßige Musik-in-halten-Audiodatei, die Kulanzzeit für den Agenten-Rückruf und die Kontextkonfiguration des Anrufs. Führen Sie das Cmdlet " **Get-CsRgsConfiguration** " aus, um diese Konfigurationseinstellungen anzuzeigen. Details zum Cmdlet **Get-CsRgsConfiguration** finden Sie unter [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Sie können diese Einstellungen auf Anwendungsebene von einem Pool zu einem anderen übertragen, indem Sie das Cmdlet " **Import-CsRgsConfiguration** " mit dem Parameter "– ReplaceExistingSettings" verwenden, aber dadurch werden die Einstellungen im Ziel Pool überschrieben.

<div>


> [!IMPORTANT]  
> Diese Einschränkung beim Übertragen von Einstellungen in einen anderen Pool gilt nur für die Einstellungen auf Anwendungsebene und die standardmäßige Musik-in-Halt-Audiodatei. Sie gilt nicht für Agentengruppen, Warteschlangen, Workflows, Geschäftszeiten und Feiertagssätze.



</div>

Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool während eines Notfalls nicht ersetzen möchten und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen auf Anwendungsebene des primären Pools verloren. Wenn Sie einen neuen Pool erstellen müssen, um den primären Pool während der Wiederherstellung zu ersetzen, entweder mit demselben FQDN oder mit einem anderen FQDN, können Sie die ursprünglichen Einstellungen auf Anwendungsebene nicht wiederherstellen. In diesem Fall müssen Sie den neuen Pool mit diesen Einstellungen konfigurieren und die Musik-in-Halt-Audiodatei aufnehmen.

Wenn Sie sich entscheiden, das Cmdlet " **Import-CsRgsConfiguration** " zu verwenden, um während eines Notfalls Einstellungen auf Anwendungsebene aus dem primären Pool in den Sicherungspool zu übertragen, können Sie die Einstellungen während der Wiederherstellung auf die gleiche Weise aus dem Sicherungspool in den neuen Pool übertragen, wie Sie Sie vom primären Pool an den Sicherungspool übertragen haben.

Die folgende Tabelle enthält eine Übersicht über die Schritte, die beim erneuten Herstellen von Reaktionsgruppen erforderlich sind.

Ausführliche Informationen zum Ausführen dieser Schritte finden Sie unter [Disaster Recovery-Verfahren für die Reaktionsgruppe in lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### <a name="response-group-disaster-recovery-steps"></a>Notfall Wiederherstellungsschritte für die Reaktionsgruppe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Erforderliche Gruppen und Rollen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vor einem Ausfall</p></td>
<td><p>Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> routinemäßig aus, um Sicherungen aller Reaktionsgruppen Konfigurationen in allen Front-End-Pools zu erstellen, in denen die Antwortgruppen Anwendung bereitgestellt wird.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Bei einem Ausfall</p></td>
<td><p>Führen Sie das Cmdlet " <strong>Import-CsRgsConfiguration</strong> " aus, um die gesicherte Konfiguration des lync Server-Reaktionsgruppendiensts aus dem primären Pool in den Sicherungspool zu importieren.</p>
<div>

> [!NOTE]  
> Verwenden Sie den Parameter – ReplaceExistingSettings, wenn Sie die Einstellungen für die Reaktionsgruppe auf Anwendungsebene im Sicherungspool durch die Einstellungen des primären Pools ersetzen möchten. Wenn Sie die Einstellungen auf Anwendungsebene nicht vom primären Pool in den Sicherungspool übertragen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen des primären Pools verloren.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Nach dem Import</p></td>
<td><p>Führen Sie die Cmdlets für die Reaktionsgruppe mit dem Parameter – ShowAll (zum Anzeigen aller Antwortgruppen) oder des Parameters "– Owner" aus, um zu überprüfen, ob alle Reaktionsgruppen Konfigurationen in den Sicherungspool importiert wurden.</p>
<div>

> [!IMPORTANT]  
> Wenn Sie weder den-ShowAll-Parameter noch den – owner-Parameter verwenden, werden die Reaktionsgruppen, die Sie in den Sicherungspool importiert haben, nicht in den Ergebnissen aufgelistet, die von den Cmdlets zurückgegeben werden.


</div>
<p>Führen Sie die folgenden Cmdlets aus:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Nach dem Failover</p></td>
<td><ul>
<li><p>Setzen Sie einen Testanruf an eine Reaktionsgruppe, die in den Sicherungspool importiert wurde, und überprüfen Sie, ob der Anruf richtig gehandhabt wird.</p></li>
<li><p>Alle formellen Agents müssen sich bei ihren formalen Gruppen im Sicherungspool erneut anmelden.</p></li>
<li><p>Verwalten von Konfigurationsänderungen:</p>
<p>Reaktionsgruppen im Sicherungspool, ob Sie in den Backup-Pool importiert oder im Besitz des Sicherungs Pools sind, können während des Ausfalls wie gewohnt geändert werden.</p>
<div>

> [!IMPORTANT]  
> Sie müssen die lync Server-Verwaltungsshell zum Verwalten der Reaktionsgruppen verwenden, die Sie in den Sicherungspool importiert haben. Sie können die lync Server-Systemsteuerung nicht verwenden, um diese Reaktionsgruppen zu verwalten, während Sie sich im Sicherungspool befinden.


</div></li>
</ul></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p>Nach der Wiederherstellung vor dem Failback</p></td>
<td><p>Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> aus, indem Sie den-source-Parameter als Backup-Pool und den Parameter-Owner als primären Pool angeben, um die Reaktionsgruppen zu exportieren, die im Besitz des primären Pools aus dem Sicherungspool sind.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Nach dem Failback</p></td>
<td><ul>
<li><p>Führen Sie das Cmdlet " <strong>Import-CsRgsConfiguration</strong> " aus, um die Reaktionsgruppen wieder in den primären Pool zu importieren.</p>
<div>

> [!NOTE]  
> Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool zum Ersetzen bereitstellen, verwenden Sie den Parameter – ReplaceExistingSettings, um die Einstellungen auf Anwendungsebene aus dem Sicherungspool in den neuen Pool zu übertragen. Wenn Sie die Einstellungen nicht aus dem Sicherungspool übertragen, verwendet der neue Pool die Standardeinstellungen.


</div></li>
<li><p>Führen Sie die folgenden Cmdlets mit dem-ShowAll-Parameter (zum Anzeigen aller Antwortgruppen) oder des – Owner-Parameters (zum Anzeigen nur importierter Antwortgruppen) aus, um zu überprüfen, ob alle Reaktionsgruppen Konfigurationen erfolgreich wieder in den primären Pool importiert wurden:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Setzen Sie einen Testanruf an eine Reaktionsgruppe, die zurück in den primären Pool importiert wurde, und überprüfen Sie, ob der Anruf richtig gehandhabt wird.</p></li>
<li><p>Führen Sie optional das Cmdlet <strong>Export-CsRgsConfiguration</strong> im Sicherungspool mit dem Parameter – RemoveExportedConfiguration aus, um die Reaktionsgruppen zu entfernen, die im Besitz des primären Pools des Sicherungs Pools sind.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

