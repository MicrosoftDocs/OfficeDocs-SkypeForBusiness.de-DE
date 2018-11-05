---
title: Migrieren von Reaktionsgruppen
TOCTitle: Migrieren von Reaktionsgruppen
ms:assetid: 5c07bf4b-ad8a-4b83-b970-7d933bb7c4ef
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204931(v=OCS.15)
ms:contentKeyID: 49294125
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Migrieren von Reaktionsgruppen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Nachdem die Benutzer in die Lync Server 2013-Pools verschoben wurden, können Sie Ihre Reaktionsgruppen migrieren. Das Migrieren der Reaktionsgruppen schließt das Kopieren von Agentgruppen, Warteschlangen, Workflows und Audiodateien sowie das Verschieben von Reaktionsgruppe-Kontaktobjekten von der Vorversionsbereitstellung in den Lync Server 2013-Pool ein. Nach der Migration der Vorversionsreaktionsgruppen werden Anrufe an die Reaktionsgruppen von der Reaktionsgruppenanwendung im Lync Server 2013 verarbeitet. Anrufe für Reaktionsgruppen werden nicht mehr vom Vorversionspool verarbeitet.


> [!NOTE]
> Sie können Reaktionsgruppen zwar migrieren, bevor Sie alle Benutzer in den Lync Server 2013-Pool verschoben haben, es wird jedoch empfohlen, alle Benutzer zuerst zu verschieben. Insbesondere Benutzer, die Reaktionsgruppen-Agents sind, haben keine vollständige Funktionalität bei neuen Funktionen, bevor sie in den Lync Server 2013-Pool verschoben werden.



Bevor Sie Reaktionsgruppen verschieben, müssen Sie einen Lync Server 2013-Pool bereitstellen, der die Reaktionsgruppenanwendung beinhaltet. Die Reaktionsgruppenanwendung wird bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert und aktiviert. Sie können sicherstellen, dass die Reaktionsgruppenanwendung installiert ist, indem Sie das **Get-CsService–ApplicationServer**-Cmdlet ausführen.


> [!NOTE]
> Sie können neue Lync Server 2013-Reaktionsgruppen im Lync Server 2013-Pool erstellen, bevor Sie Ihre Reaktionsgruppen aus der Vorversion migrieren.



Um Reaktionsgruppen aus einem Vorversionspool zu Lync Server 2013 zu migrieren, führen Sie das **Move-CsRgsConfiguration**-Cmdlet aus. Bevor Sie **Move-CsRgsConfiguration** ausführen können, müssen Sie zunächst noch das Schnittstellenpaket für die Abwärtskompatibilität mit Windows Management Instrumentation (WMI) installieren. Führen Sie dazu die Datei "OCSWMIBC.msi" aus. Sie finden diese Datei auf dem Installationsdatenträger im Ordner "Setup".


> [!IMPORTANT]
> Das Reaktionsgruppe-Migrations-Cmdlet verschiebt die Reaktionsgruppe-Konfiguration für den gesamten Pool. Die Auswahl bestimmter Gruppen, Warteschlangen oder Workflows zum Migrieren ist nicht möglich.



Im Anschluss an die Migration der Reaktionsgruppen müssen Sie die URL aktualisieren, die von formellen Agents zum An- und Abmelden bei Reaktionsgruppen verwendet wird. Außerdem müssen Sie mit dem Lync Server-Systemsteuerung- oder mit dem Lync Server-Verwaltungsshell-Cmdlet überprüfen, ob alle Agentgruppen, Warteschlangen und Workflows erfolgreich verschoben wurden.

> [!CAUTION]  
> Bei der Migration von Reaktionsgruppen werden die Office Communications Server 2007 R2-Reaktionsgruppen nicht entfernt. Es wird auch nicht empfohlen, die Office Communications Server 2007 R2-Reaktionsgruppen zu entfernen. Wenn Sie eine Office Communications Server 2007 R2-Reaktionsgruppe entfernen, können die Reaktionsgruppen in Lync Server 2013 nicht mehr verwendet werden.



> [!IMPORTANT]
> Warten Sie mit dem Entfernen von Daten aus früheren Bereitstellungen, bis Sie den Pool außer Betrieb nehmen. Darüber hinaus wird dringend empfohlen, die Reaktionsgruppen unmittelbar nach der Migration zu exportieren. Wenn eine Office Communications Server 2007 R2-Reaktionsgruppe entfernt wird, können Sie die Reaktionsgruppen aus der Sicherung wiederherstellen, damit die Lync Server 2013-Reaktionsgruppen wieder verwendet werden können.



Wenn Sie das **Move-CsRgsConfiguration**-Cmdlet ausführen, bleiben die Agent-Gruppen, Warteschlangen, Workflows und Audiodateien zu Wiederherstellungszwecken im Vorversionspool. Wenn Sie ein Rollback auf den Vorversionspool ausführen müssen, müssen Sie allerdings das **Move-CsApplicationEndpoint**-Cmdlet ausführen, um Kontaktobjekte zurück in den Vorversionspool zu verschieben.


> [!IMPORTANT]
> Warten Sie mit dem Löschen von Reaktionsgruppen aus dem Vorversionspool, bis Sie den Pool außer Betrieb nehmen.



Im folgenden Verfahren zum Migrieren von Reaktionsgruppe-Konfigurationen wird davon ausgegangen, dass eine 1:1-Beziehung zwischen den Vorversionspools und den Lync Server 2013-Pools besteht. Wenn Sie im Rahmen der Migration und der Bereitstellung Pools verbinden oder aufteilen möchten, müssen Sie überlegen, welcher Vorversionspool welchem Lync Server 2013-Pool zugeordnet ist.

## So migrieren Sie Reaktionsgruppe-Konfigurationen

1.  Suchen Sie auf dem Installationsdatenträger die Datei "OCSWMIBC.msi" im Ordner "SetupW", und führen Sie den Installationsvorgang mit der Datei durch.

2.  Melden Sie sich auf dem Computer über ein Konto an, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist oder über entsprechende Administratorrechte und -berechtigungen verfügt.

3.  Öffnen Sie die Lync Server-Verwaltungsshell.

4.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    Beispiel:
    
        Move-CsRgsConfiguration -Source pool01.contoso.net -Destination pool02.contoso.net

5.  Wenn Sie die Registerkarte "Reaktionsgruppe" für Microsoft Office Communicator 2007 R2 in Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben, entfernen Sie die Registerkarte aus der Office Communicator 2007 R2-Datei "tabs.xml".
    

    > [!NOTE]
    > Formelle Agents verwendeten die Reaktionsgruppen-Registerkarte zur Anmeldung an die entsprechenden Reaktionsgruppen, bevor sie Anrufe empfangen konnten. Wenn Sie die Registerkarte "Reaktionsgruppe" bereitgestellt haben, haben Sie den Speicherort der Office Communicator 2007 R2-Datei "tabs.xml" vor der Bereitstellung ausgewählt.



6.  Informieren Sie Benutzer über die aktualisierte URL, die Agents zur An- und Abmeldung bei ihren Reaktionsgruppen benötigen.
    

    > [!NOTE]
    > In der Regel lautet die URL "https://webpoolFQDN/RgsClients/Tab.aspx", wobei <EM>webpoolFQDN</EM> für den vollqualifizierten Domänenname (FQDN) des Webpools steht, der dem Pool zugeordnet ist, den Sie eben nach Lync Server 2013 verschoben haben.

    

    > [!NOTE]
    > Dieser Schritt ist nicht mehr erforderlich, nachdem Benutzer auf Lync 2013 aktualisiert haben, da die URL im Menü <STRONG>Tools</STRONG> in Lync verfügbar ist.



## So überprüfen Sie die Migration von Reaktionsgruppen mit Lync Server-Systemsteuerung

1.  Öffnen Sie die Lync Server-Systemsteuerung.

2.  Klicken Sie im linken Navigationsbereich auf **Reaktionsgruppen** .

3.  Überprüfen Sie auf der Registerkarte **Workflow** , dass die Liste alle Workflows in Ihrer Office Communications Server 2007 R2-Umgebung enthält.

4.  Klicken Sie auf die Registerkarte **Warteschlange** und überprüfen Sie, ob die Liste alle Warteschlangen in Ihrer Office Communications Server 2007 R2-Umgebung enthält.

5.  Klicken Sie auf die Registerkarte **Gruppe** und überprüfen Sie, ob die Liste alle Agentgruppen in Ihrer Office Communications Server 2007 R2-Umgebung enthält.

## So überprüfen Sie die Migration von Reaktionsgruppen mit Cmdlets

1.  Öffnen Sie die Lync Server-Verwaltungsshell.
    
    Führen Sie Folgendes aus, um nähere Informationen zu den folgenden Cmdlets zu erhalten:
    
        Get-Help <cmdlet name> -Detailed

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsAgentGroup

3.  Überprüfen Sie, ob alle Agentgruppen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

4.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsQueue

5.  Überprüfen Sie, ob alle Warteschlangen in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

6.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsRgsWorkflow

7.  Überprüfen Sie, ob alle Workflows in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.

