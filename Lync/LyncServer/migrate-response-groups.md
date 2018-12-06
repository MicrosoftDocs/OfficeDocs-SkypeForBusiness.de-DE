---
title: Migrieren von Reaktionsgruppen
TOCTitle: Migrieren von Reaktionsgruppen
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204854(v=OCS.15)
ms:contentKeyID: 49293835
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Reaktionsgruppen

 

_**Letztes Änderungsdatum des Themas:** 2013-09-23_

Nachdem Ihre Benutzer in Lync Server 2013-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Dies beinhaltet das Kopieren von Agent-Gruppen, Warteschlangen, Workflows und Audiodateien sowie das Verschieben von Reaktionsgruppe-Kontaktobjekten aus der Bereitstellung der Vorversion in den Lync Server 2013-Pool. Nach der Migrierung Ihrer Reaktionsgruppen aus der Vorversion, werden Anrufe an den Reaktionsgruppen von der Reaktionsgruppenanwendung im Lync Server 2013-Pool abgewickelt. Der Vorversionspool wickelt keine Anrufe an Reaktionsgruppen mehr ab.


> [!NOTE]
> Sie können Reaktionsgruppen zwar migrieren, bevor Sie alle Benutzer in den Lync Server 2013-Pool verschoben haben, es wird jedoch empfohlen, alle Benutzer zuerst zu verschieben. Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, haben keine vollständige Funktionalität bei neuen Funktionen, bevor sie in den Lync Server 2013-Pool verschoben werden.



Bevor Sie Reaktionsgruppen verschieben, müssen Sie einen Lync Server 2013-Pool bereitstellen, der die Reaktionsgruppenanwendung beinhaltet. Die Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert. Sie können sicherstellen, dass die Reaktionsgruppenanwendung installiert ist, indem Sie das **Get-CsService –ApplicationServer**-Cmdlet ausführen.


> [!NOTE]
> Sie können neue Lync Server 2013-Reaktionsgruppen im Lync Server 2013-Pool erstellen, bevor Sie Ihre Reaktionsgruppen aus der Vorversion migrieren.



Um Reaktionsgruppen aus einem Vorversionspool zum Lync Server 2013 zu migrieren, führen Sie das **Move-CsRgsConfiguration**-Cmdlet aus.


> [!IMPORTANT]
> Das Reaktionsgruppe-Migrations-Cmdlet verschiebt die Reaktionsgruppe-Konfiguration für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.



Nach der Migration der Reaktionsgruppen müssen Sie Lync Server-Systemsteuerung- oder Lync Server-Verwaltungsshell-Cmdlets verwenden, um zu überprüfen, ob alle Vertretergruppen, Warteschlangen und Workflows erfolgreich verschoben wurden.

Wenn Sie Reaktionsgruppen migrieren, werden die Lync Server 2010-Reaktionsgruppen nicht entfernt. Wenn Sie nach der Migration Reaktionsgruppen mithilfe von Lync Server-Systemsteuerung oder Lync Server-Verwaltungsshell verwalten, können Sie sowohl die Lync Server 2010- als auch die Lync Server 2013-Reaktionsgruppen sehen. Sie sollten nur Updates für die Lync Server 2013-Reaktionsgruppen installieren. Die Lync Server 2010-Reaktionsgruppen werden nur zu Wiederherstellungszwecken beibehalten.

> [!CAUTION]  
> Nachdem die Migration abgeschlossen und neue Reaktionsgruppen erstellt wurden, werden in der Lync Server-Systemsteuerung und in der Lync Server-Verwaltungsshell die Lync Server 2010- und Lync Server 2013-Versionen der einzelnen Reaktionsgruppen angezeigt. Verwenden Sie nicht Lync Server-Systemsteuerung oder Lync Server-Verwaltungsshell zum Entfernen der Lync Server 2010-Reaktionsgruppen. Wenn Sie eine Reaktionsgruppe entfernen, stellt die entsprechende Reaktionsgruppe, die während der Migration erstellt wurde, die Arbeit ein. Die Lync Server 2010-Reaktionsgruppen werden entfernt, wenn Sie den Lync Server 2010-Pool außer Betrieb nehmen.



> [!IMPORTANT]
> Es wird empfohlen, keinerlei Daten Ihrer vorigen Bereitstellung zu entfernen, bevor Sie den Pool außer Betrieb setzen. Außerdem wird dringend empfohlen, Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine Lync Server 2010-Reaktionsgruppe gelöscht wird, können Sie Ihre Reaktionsgruppen aus der Sicherung wiederherstellen, damit Lync Server 2013-Reaktionsgruppen wieder funktionieren.



Mit Lync Server 2013 wird eine neue Reaktionsgruppe Funktion namens **Workflowtyp** eingeführt. Der **Workflowtyp** kann **Verwaltet** oder **Nicht veraltet** sein. Alle Reaktionsgruppen werden mit dem **Workflowtyp** **Nicht verwaltet** und mit leerer Manager-Liste migriert.

Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool. Wenn Sie ein Rollback auf den Vorversionspool ausführen müssen, müssen Sie allerdings das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte zurück in den Vorversionspool zu verschieben.

Das folgende Verfahren zum Migrieren von Reaktionsgruppe-Konfigurationen setzt voraus, dass eine 1:1-Beziehung zwischen Ihren Vorversionspools und den Lync Server 2013-Pools besteht. Falls Sie während der Migration und Bereitstellung Pools konsolidieren oder trennen möchten, müssen Sie planen, welcher Vorversionspool welchem Lync Server 2013-Pool zugeordnet wird.

## So migrieren Sie Reaktionsgruppe-Konfigurationen

1.  Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Beispiel:
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  Nach der Migration von Reaktionsgruppen und Agents zum Lync Server 2013-Pool ist die URL, die Agents zur An- und Abmeldung verwenden, eine Lync Server 2013-URL, die im Menü **Extras** zur Verfügung steht. Erinnern Sie Agents daran, sämtliche Referenzen, beispielsweise Lesezeichen, auf die neue URL zu aktualisieren.

## So überprüfen Sie die Reaktionsgruppenmigration mithilfe von Lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen** .

4.  Überprüfen Sie auf der Registerkarte **Workflow** , dass die Liste alle Workflows in Ihrer Lync Server 2010-Umgebung enthält.

5.  Klicken Sie auf die Registerkarte **Warteschlange** , und überprüfen Sie, ob die Liste alle Warteschlangen in Ihrer Lync Server 2010-Umgebung enthält.

6.  Klicken Sie auf die Registerkarte **Gruppe** , und überprüfen Sie, ob die Liste alle Agentgruppen in Ihrer Lync Server 2010-Umgebung enthält.

## So überprüfen Sie die Reaktionsgruppenmigration mithilfe von Lync Server-Verwaltungsshell

1.  Melden Sie sich mit einem Konto am Computer an, das Mitglied der Gruppe "RTCUniversalReadOnlyAdmins" oder mindestens Mitglied der Rolle "CsViewOnlyAdministrator" ist.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.
    
    Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:
    
        Get-Help <cmdlet name> -Detailed

3.  Führen Sie folgenden Befehl aus:
    
        Get-CsRgsAgentGroup

4.  Überprüfen Sie, ob alle Agentgruppen in Ihrer Lync Server 2010-Umgebung in der Liste enthalten sind.

5.  Führen Sie folgenden Befehl aus:
    
        Get-CsRgsQueue

6.  Überprüfen Sie, ob alle Warteschlangen in Ihrer Lync Server 2010-Umgebung in der Liste enthalten sind.

7.  Führen Sie folgenden Befehl aus:
    
        Get-CsRgsWorkflow

8.  Überprüfen Sie, ob alle Workflows in Ihrer Lync Server 2010-Umgebung in der Liste enthalten sind.

