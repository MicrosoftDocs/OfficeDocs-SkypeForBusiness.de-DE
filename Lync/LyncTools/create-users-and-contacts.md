---
title: Erstellen von Benutzern und Kontakten
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a911124af0ac4dc57eca01e0ef6e2a801a61caa5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505222"
---
# <a name="create-users-and-contacts"></a>Erstellen von Benutzern und Kontakten

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Sie müssen das lync Server 2013-Benutzer Bereitstellungs Tool (UserProvisioningTool.exe) verwenden, um Benutzer und Kontakte in Vorbereitung auf Stress-und Leistungs Auslastungstests zu erstellen.

Im folgenden finden Sie eine Liste von Begriffen und Definitionen, die Sie beim Durchlesen dieses Themas hilfreich finden.

  - Organisationseinheit – die Active Directory-Domänendienste Organisationseinheit (Organizational Unit, OU).

  - Verbund/Cross-Pool – Benutzer, die für die Kommunikation mit Benutzern von anderen Chat Diensten (Instant Messaging) wie MSN-Netzwerk mit Internet Diensten, AOL® und Yahoo-® aktiviert werden \! .

  - Verteilerlisten – die Objekte in Active Directory-Domänendienste, die eine Liste der Active Directory-Domänendienste-Benutzer enthalten, die zum Starten der Kommunikation mit Personengruppen verwendet werden.

  - Location Info Service – der lync Server 2013 Dienst, der bei Aktivierung und Konfiguration pro Telefon den Abruf des physischen Speicherorts für erweiterte 9-1-1-Dienste (E9-1-1) ermöglicht.

  - US-Telefonnummern – die Telefonnummern, die Benutzern zugewiesen sind, zusätzlich zu dem SIP-URI, der zum Weiterleiten von eingehenden und ausgehenden Anrufen und Reverse Number Lookup (können) verwendet wird.

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Erstellen von Benutzern und Kontakten mithilfe von UserProvisioningTool.exe

Zum Erstellen von Benutzern und Kontakten für die Auslastungssimulation müssen Sie das lync Server Benutzer prodienste-Tool verwenden. Das lync Server-Benutzer Prothesen-Tool wird mit dem lync Server Stress and Performance Tool Package installiert. Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool.msi) auf dem Front-End-Server oder dem Standard Edition-Server ausgeführt wurde. Starten Sie das lync Server Benutzer Bereitstellung-Tool, indem Sie die Datei UserProvisioningTool.exe (befindet sich unter% InstalledDirectory% LyncStressAndPerfTool \\ LyncStress) auf der Front-End-Server oder auf dem Standard Edition-Server.

<div>


> [!IMPORTANT]  
> Sie müssen als Mitglied der Sicherheitsgruppe "Domänen-Admins" angemeldet sein, um UserProvisioningTool.exe ausführen zu können. Sie müssen in diesem Kontext ausgeführt werden, da UserProvisioningTool.exe neue Active Directory-Domänendienste Benutzer erstellen und konfigurieren.



</div>

<div>


> [!NOTE]  
> Wenn Sie eine große Anzahl von Benutzern (10.000 oder mehr) erstellen, führen Sie UserProvisioningTool.exe von einem High-End-Computer aus. Beachten Sie, dass der Domänencontroller auch bei der Erstellung der Benutzer eine hohe Auslastung erfahren wird.



</div>

Wenn das lync Server Benutzer ProTools geöffnet wird, klicken Sie auf **Konfiguration** und dann auf Konfiguration **Laden**. Laden Sie die Standarddatei, die im Paket enthalten ist, SampleData.xml, um mit der Konfiguration von Benutzern und Kontakten zu beginnen. Dadurch werden die Felder mit Beispieldaten vorab gefüllt, die Sie für Ihr System überarbeiten müssen. Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die bereits angepasste Einstellungen enthält, laden Sie diese Datei stattdessen. Füllen Sie die Felder im lync Server Benutzer protoolieren aus, wie in den folgenden Abschnitten beschrieben.

![Registerkarte "Benutzererstellung".](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Registerkarte "Benutzererstellung".")

Führen Sie die folgenden Schritte aus, um Serveroptionen zu konfigurieren.

1.  Geben Sie im **Front-End-Pool-FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition-Server oder Front-End-Pool, in dem die Benutzer gehostet werden sollen.

2.  Geben Sie unter **Benutzer Name Präfix**ein Präfix ein, das Sie zum Erstellen von Benutzernamen zu Testzwecken verwenden möchten.

3.  Geben Sie unter **Kennwort**ein Kennwort an, das auf alle Testbenutzerkonten angewendet wird.

4.  Geben Sie in **SIP-Domäne**den Domänennamen ein, der für SIP-URIs der Testbenutzer (Uniform Resource Identifiers) verwendet werden soll.

5.  Geben Sie in **Kontodomäne**den Domänennamen Ihrer aktuellen Active Directory-Domänendienste Domäne ein, unter der Sie die Testbenutzer erstellen möchten.

6.  Geben Sie in **Organisationseinheit**den Namen der Active Directory-Domänendienste ou ein, in der Sie die Benutzerobjekte erstellen möchten. Wenn die Organisationseinheit nicht vorhanden ist, wird Sie erstellt.

7.  Geben Sie unter **Telefonvorwahl**den dreistelligen Vorwahlcode ein, der für Testbenutzerkonten verwendet wird. Stellen Sie sicher, dass die Telefonvorwahl nicht mit den Gebietscodes anderer Benutzer in Active Directory-Domänendienste in Konflikt steht.

8.  Aktivieren Sie das Kontrollkästchen **sprachaktiviert** , wenn Sie die Testbenutzer für Enterprise-VoIP aktivieren möchten.

9.  Geben Sie unter **Anzahl der Benutzer**die Gesamtzahl der Testbenutzer an, die Sie erstellen möchten.

10. Geben Sie unter **Start Index**die Startnummer an, die als Suffix für das Benutzernamenpräfix verwendet wird.

<div>

## <a name="create-users-button"></a>Schaltfläche "Benutzer erstellen"

Wenn Sie auf die Schaltfläche Benutzer erstellen klicken, werden alle Eingabeparameter überprüft.

  - Wenn Validierungsfehler vorliegen, werden Sie aufgefordert, diese Eingabewerte zu korrigieren.

  - Wenn alle Eingabewerte korrekt sind, wird mit dem Erstellen von Benutzern in Active Directory-Domänendienste begonnen. Unten in diesem Formular wird eine Statusleiste angezeigt. Es wird empfohlen, die Anwendung nicht zu schließen, während die Statusanzeige aktiv ist.

Die Erstellung des Benutzers ist ein langsamer Prozess. Es kann mehrere Minuten dauern. Wenn die Anzahl der Benutzer sehr groß ist, kann der Vorgang sogar einige Stunden dauern. Wenn die Benutzer bereits vorhanden sind, werden Sie mit allen Änderungen aktualisiert. Sie können überprüfen, ob die Benutzer erstellt wurden, indem Sie sich als einer der Benutzer im Bereich anmelden. Verwenden Sie das Benutzerpräfix, die Benutzernummer und @sipDomain als Benutzername (beispielsweise LyncUser10@contoso.net) zusammen mit dem angegebenen Kennwort.

</div>

<div>

## <a name="delete-users-button"></a>Schaltfläche "Benutzer löschen"

Wenn Sie auf die Schaltfläche Benutzer löschen klicken, werden alle Eingabeparameter überprüft.

  - Wenn Validierungsfehler vorliegen, werden Sie aufgefordert, diese Eingabewerte zu korrigieren.

  - Wenn alle Eingabewerte korrekt sind, wird das Deaktivieren und Löschen von Benutzern in Active Directory-Domänendienste gestartet. Unten in diesem Formular wird eine Statusleiste angezeigt. Es wird empfohlen, die Anwendung nicht zu schließen, während die Statusanzeige aktiv ist.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Nur US-formatierte Telefonnummern werden unterstützt. Telefonnummern werden immer Benutzern zugewiesen, und alle von UserProvisioningTool.exe erstellten Benutzer sind für Enterprise-VoIP aktiviert. Alle Szenarien, die die Telefonnummer wie automatische Telefonzentrale für Konferenzen oder UC-PSTN-Anrufe verwenden, verwenden diese Telefonnummer, um Anrufe ordnungsgemäß weiterzuleiten. Aus diesem Grund muss jeder Benutzer eine eindeutige Telefonnummer haben. Wenn Sie Benutzer zweimal erstellen müssen, tritt beim Ausführen des Befehls ein Fehler auf, es sei denn, Sie verwenden eine andere Vorwahl oder wenn die vorherigen Benutzer mithilfe des Cmdlets <STRONG>Disable-CsUser</STRONG> deaktiviert wurden.</P>
> <LI>
> <P>Bevor Sie Kontakte erstellen, müssen Sie zuerst die Benutzerreplikation ausführen, die auf der Registerkarte Benutzer ausgeführt wird. Wenn Sie Ihre Benutzer soeben erstellt haben, müssen Sie warten, bis lync Server Replikation abgeschlossen ist und die Benutzerkonten in der Datenbank auffüllen. Wenn die Replikation der Benutzer noch nicht abgeschlossen ist, wird ein Fehler angezeigt. Sie wissen, wann Benutzer die Replikation abgeschlossen haben, wenn lync Server 2013 Front-End-Dienst gestartet wurde, oder indem Sie das Cmdlet <STRONG>Get-CsUser</STRONG> für den letzten Benutzer erfolgreich ausführen.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Registerkarte "Kontakte erstellen"

Auf der Registerkarte Kontakte Erstellung können Sie Details für die Kontakte von Benutzern angeben.

![Registerkarte Kontakte erstellen.](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Registerkarte Kontakte erstellen.")

Führen Sie die folgenden Schritte aus, um die Kontakte der Benutzer zu konfigurieren.

1.  Geben Sie in durchschnittliche Kontakte pro Benutzer die durchschnittliche Anzahl von Kontakten an, die in Kontaktlisten für jeden Benutzer aufgefüllt werden sollen.

2.  Aktivieren Sie das Kontrollkästchen fixiert, wenn Sie für jeden Benutzer eine gleiche Anzahl von Kontakten erstellen möchten. Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, deaktivieren Sie das Kontrollkästchen.

3.  Geben Sie in durchschnittliche Kontaktgruppen pro Benutzer die Anzahl der Kontaktgruppen pro Benutzer an. Diese Nummer muss kleiner sein als durchschnittliche Kontakte pro Benutzer.

4.  Geben Sie in Prozent für Verbund-/Pool Kontakte eine Zahl zwischen 0 und 100 an. Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.

5.  Geben Sie unter Benutzerpräfix für Verbund/Cross-Pool den Benutzernamen für Verbundbenutzer an, der den Kontaktlisten lokaler Benutzer hinzugefügt wird.

6.  Geben Sie in Pool-SIP-Domäne des Verbund Pools den SIP-Domänennamen der Verbundbenutzer an.
    
    <div>
    

    > [!NOTE]  
    > Keiner der Benutzer sollte beim Erstellen von Kontakten angemeldet sein.

    
    </div>

7.  Überprüfen Sie auf der Registerkarte Benutzererstellung, ob die Parameter richtig sind. Der Bereich der Benutzer, für die Kontakte erstellt werden, wird auf der Registerkarte Benutzererstellung abgerufen.

8.  Klicken Sie auf Kontakte erstellen, um mit der Erstellung des Kontakts zu beginnen. Dieser Vorgang kann mehrere Minuten dauern. Nachdem er abgeschlossen wurde, wird ein Dialogfeld mit der Meldung angezeigt, dass der Vorgang erfolgreich abgeschlossen wurde. Sie können die Kontakte, die erstellt wurden, überprüfen, indem Sie sich als ein Benutzer anmelden, der auf der Registerkarte Benutzererstellung erstellt wurde.
    
    <div>
    

    > [!NOTE]  
    > Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Ziel Pool neu. Je nachdem, wie viele Kontakte durch diesen Vorgang erstellt wurden, kann es länger dauern (bis zu 2 Stunden), bis die Front-End-Server gestartet wurden.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Verteilerliste

Eines der Features des lync Server 2013 Stress-und Leistungstools besteht darin, das Erweiterungsfeature Verteilerliste (DL) in lync 2013 zu simulieren. Wenn Sie die DL-Erweiterung in UserProvisioningTool nicht aktivieren, können Sie diesen Schritt überspringen.

![Registerkarte "Erstellung von Verteilerlisten".](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Registerkarte "Erstellung von Verteilerlisten".")

Auf der Registerkarte Verteilerliste können Sie DLS erstellen, die das Belastungs-und Leistungs Tool für das Erweiterungsfeature "Verteilerlisten" verwenden wird. Vor dem Erstellen von Verteilerlisten müssen lync Server 2013 bereits installiert sein. Sie müssen lync Server 2013 ForestPrep ausgeführt haben. Andernfalls sind die DL-Attribute im Active Directory-Domänendienste-Schema nicht vorhanden, und das Tool kann keine Verteilerlisten erstellen.

Führen Sie die folgenden Schritte aus, um Verteilerlisten zu konfigurieren.

1.  Geben Sie unter Anzahl der Verteilerlisten die Gesamtzahl der DLS an, die Sie erstellen möchten. (Es wird empfohlen, mit der doppelten Anzahl von Benutzern zu beginnen). Sie werden von 0 bis n-1 nummeriert.

2.  Geben Sie Unterverteiler Listen Präfix das Präfix an, das die DLS aufweisen soll. Wenn Sie beispielsweise 100 DLS und ein Präfix für testDL angeben, werden die DLS mit testDL0, testDL1 usw. über testDL99.

3.  Geben Sie in mindestmember in einer Dist. List die minimale Anzahl von Benutzern an, die in jeder Verteilerliste hinzugefügt werden sollen.

4.  Geben Sie in maximale Mitgliederzahl in einer Dist. List die maximale Anzahl von Benutzern an, die in jeder Verteilerliste hinzugefügt werden soll.

<div>

## <a name="create-distribution-lists-button"></a>Schaltfläche "Verteilerlisten erstellen"

Wenn Sie auf die Schaltfläche Verteilerlisten erstellen klicken, fragt das Tool Active Directory-Domänendienste ab, um zu sehen, ob Verteilerlisten, die mit den Präfixen und Nummern übereinstimmen, bereits vorhanden sind. Mit dem Tool werden nur diejenigen erstellt, die noch nicht vorhanden sind. Beim Hinzufügen von Mitgliedern zu diesen neu erstellten Verteilerlisten werden die Benutzer aus dem Bereich ausgewählt, der auf der Registerkarte Benutzererstellung angegeben ist.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Registerkarte "Location Info Service config"

Eines der Features des Tools lync Server 2013 Stress und Leistung ist das Generieren von Dummy-Konfigurationsdateien für den standortinformationsdienst. Der standortinformationsdienst hat in der Regel keine nennenswerten Auswirkungen auf die Leistung der Server.

![Registerkarte "Location Info Service config".](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Registerkarte "Location Info Service config".")

Wenn Sie dieses Feature testen möchten, können Sie die im Formular genannten Werte eingeben und dann auf die Schaltfläche "LIS-Konfigurationsdateien generieren" klicken. Es generiert CSV-Dateien, die als LIS \_ -Subnet.csv, LIS- \_Switches.csv, LIS- \_Ports.csv und Lis-WAP.csv bezeichnet werden \_ . Anschließend können Sie diese CSV-Dateien mithilfe des Cmdlets " **CsLisSubnet** ", des Cmdlets " **setCsLisSwitch** ", des Cmdlets " **setCsLisPort** " und des Cmdlets "Sets- **CsWirelessAccessPoint** " in die LIS-Datenbank importieren.

</div>

</div>

<span> </span>

</div>

</div>

</div>

