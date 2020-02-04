---
title: Erstellen von Benutzern und Kontakten
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Create Users and Contacts
ms:assetid: 04b24d07-2864-463d-b508-544c2674c4ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945587(v=OCS.15)
ms:contentKeyID: 51541412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1463a7caaad2bcf36996eaac4bd47e2bab25e6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727575"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-users-and-contacts"></a>Erstellen von Benutzern und Kontakten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Sie müssen das lync Server 2013-Benutzer Bereitstellungs Tool (UserProvisioningTool. exe) verwenden, um Benutzer und Kontakte in Vorbereitung auf Stress-und Leistungs Auslastungstests zu erstellen.

Nachfolgend finden Sie eine Liste der Begriffe und Definitionen, die Ihnen bei der Lektüre dieses Themas nützlich sein können.

  - Organisationseinheit – die Organisationseinheit für Active Directory-Domänendienste.

  - Federated/Cross-Pool – Benutzer, die für die Kommunikation mit Benutzern aus anderen Instant Messaging-Diensten (im) wie MSN-Netzwerk von Internet Diensten, AOL® und Yahoo\!-® aktiviert werden.

  - Verteilerlisten – die Objekte in den Active Directory-Domänendiensten, die eine Liste der Benutzer von Active Directory-Domänendiensten enthalten, die zum Starten von Kommunikation mit Personengruppen verwendet werden.

  - Location Info Service – der lync Server 2013-Dienst, der bei aktivierter und konfigurierter Telefonfunktion das Abrufen des physikalischen Standorts für verbesserte 9-1-1 (E9-1-1)-Dienste ermöglicht.

  - US-Telefonnummern – die den Benutzern zugewiesenen Telefonnummern, zusätzlich zu dem SIP-URI, der für das Routing von eingehenden und ausgehenden Anrufen sowie für Reverse Number Lookup (RNL) verwendet wird.

<div>

## <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Erstellen von Benutzern und Kontakten mithilfe von "UserProvisioningTool. exe"

Sie müssen das lync Server-Benutzer Bereitstellungs Tool verwenden, um Benutzer und Kontakte für die Auslastungssimulation zu erstellen. Das lync Server-Bereitstellungstool für Benutzer wird mit dem lync Server Stress and Performance Tool-Paket installiert. Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool. msi) auf dem Front-End-Server oder auf dem Standard Edition-Server ausgeführt wurde. Starten Sie das lync Server-Benutzer Bereitstellungs Tool, indem Sie die Datei UserProvisioningTool. exe (befindet sich bei%\\InstalledDirectory% LyncStressAndPerfTool LyncStress) auf dem Front-End-Server oder auf dem Standard Edition-Server ausführen.

<div>


> [!IMPORTANT]  
> Sie müssen als Mitglied der Sicherheitsgruppe "Domänen-Admins" angemeldet sein, um UserProvisioningTool. exe ausführen zu können. Sie müssen in diesem Kontext ausgeführt werden, da UserProvisioningTool. exe neue Active Directory-Domänendienste-Benutzer erstellt und konfiguriert.



</div>

<div>


> [!NOTE]  
> Wenn Sie eine große Anzahl von Benutzern (10.000 oder mehr) erstellen, führen Sie UserProvisioningTool. exe von einem Highend-Computer aus. Beachten Sie, dass der Domänencontroller auch eine hohe Auslastung aufweisen wird, während die Benutzer erstellt werden.



</div>

Wenn das lync Server-Benutzer Bereitstellungs Tool geöffnet wird, klicken Sie auf **Konfiguration** , und wählen Sie **Konfiguration laden**aus. Wenn Sie mit der Konfiguration von Benutzern und Kontakten beginnen möchten, laden Sie die im Paket enthaltene Standarddatei SampleData. Xml. Dadurch werden die Felder mit Beispieldaten vorab gefüllt, die Sie für Ihr System überarbeiten müssen. Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die bereits angepasste Einstellungen enthält, laden Sie stattdessen die Datei. Füllen Sie die Felder im lync Server-Benutzer Bereitstellungs Tool aus, wie in den folgenden Abschnitten beschrieben.

![Registerkarte "Benutzererstellung"](images/JJ945587.80d3c17b-7482-4818-8381-1eff8717d2fe(OCS.15).jpg "Registerkarte "Benutzererstellung"")

Führen Sie die folgenden Schritte aus, um Serveroptionen zu konfigurieren.

1.  Geben Sie im **Front-End-Pool-FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition-Servers oder-Front-End-Pools ein, in dem Sie die Benutzer hosten möchten.

2.  Geben Sie unter **Benutzer Name-Präfix**ein Präfix ein, das Sie zum Erstellen von Benutzernamen für Testzwecke verwenden möchten.

3.  Geben Sie im Feld **Kennwort**ein Kennwort ein, das für alle Testbenutzerkonten angewendet werden soll.

4.  Geben Sie in **SIP-Domäne**den Domänennamen ein, der für die SIP-URIs von Testbenutzern verwendet werden soll (Uniform Resource Identifiers).

5.  Geben Sie in **Kontodomäne**den Domänennamen Ihrer aktuellen Active Directory-Domänendienst Domäne ein, unter der Sie die Testbenutzer erstellen möchten.

6.  Geben Sie in **Organisationseinheit**den Namen der Active Directory-Domänendienste-ou ein, in der Sie die Benutzerobjekte erstellen möchten. Wenn die Organisationseinheit nicht vorhanden ist, wird Sie erstellt.

7.  Geben Sie in **Telefonvorwahl**die dreistellige Vorwahl ein, die für Testbenutzerkonten verwendet wird. Stellen Sie sicher, dass die Telefonvorwahl keinen Konflikt mit den Ortsnummern anderer Benutzer in den Active Directory-Domänendiensten verursacht.

8.  Aktivieren Sie das Kontrollkästchen **sprachaktiviert** , wenn Sie die Testbenutzer für Enterprise-VoIP aktivieren möchten.

9.  Geben Sie unter **Anzahl der Benutzer**die Gesamtzahl der Testbenutzer an, die Sie erstellen möchten.

10. Geben Sie im **Start Index**die Anfangsnummer an, die als Suffix für das Benutzernamenpräfix verwendet wird.

<div>

## <a name="create-users-button"></a>Schaltfläche "Benutzer erstellen"

Wenn Sie auf die Schaltfläche Benutzer erstellen klicken, werden alle Eingabeparameter überprüft.

  - Wenn es Validierungsfehler gibt, werden Sie aufgefordert, diese Eingabewerte zu korrigieren.

  - Wenn alle Eingabewerte richtig sind, wird das Erstellen von Benutzern in den Active Directory-Domänendiensten gestartet. Am Ende dieses Formulars wird eine Statusleiste angezeigt. Wir empfehlen, dass Sie die Anwendung nicht schließen, während die Statusleiste aktiv ist.

Die Benutzererstellung ist ein langsamer Prozess. Es kann mehrere Minuten dauern. Wenn die Anzahl der Benutzer sehr groß ist, kann der Vorgang sogar einige Stunden dauern. Wenn die Benutzer bereits vorhanden sind, werden Sie mit allen Änderungen aktualisiert. Sie können überprüfen, ob die Benutzer erstellt wurden, indem Sie sich als einer der Benutzer im Bereich anmelden. Verwenden Sie das Benutzerpräfix, die Benutzernummer und @sipDomain als Benutzernamen (beispielsweise LyncUser10@contoso.net) zusammen mit dem angegebenen Kennwort.

</div>

<div>

## <a name="delete-users-button"></a>Schaltfläche "Benutzer löschen"

Wenn Sie auf die Schaltfläche Benutzer löschen klicken, werden alle Eingabeparameter überprüft.

  - Wenn es Validierungsfehler gibt, werden Sie aufgefordert, diese Eingabewerte zu korrigieren.

  - Wenn alle Eingabewerte richtig sind, wird das Deaktivieren und Löschen von Benutzern in den Active Directory-Domänendiensten gestartet. Am Ende dieses Formulars wird eine Statusleiste angezeigt. Wir empfehlen, dass Sie die Anwendung nicht schließen, während die Statusleiste aktiv ist.

<div>


> [!NOTE]  
> <OL>
> <LI>
> <P>Nur US-formatierte Telefonnummern werden unterstützt. Telefonnummern werden immer Benutzern zugewiesen, und alle von UserProvisioningTool. exe erstellten Benutzer sind für Enterprise-VoIP aktiviert. In Szenarien, in denen die Telefonnummer verwendet wird, beispielsweise die automatische Telefonzentrale oder UC-PSTN-Anrufe, verwenden Sie diese Telefonnummer, um Anrufe richtig weiterzuleiten. Aus diesem Grund muss jeder Nutzer eine eindeutige Telefonnummer haben. Wenn Sie Benutzer zweimal erstellen müssen, schlägt der Befehl fehl, es sei denn, Sie verwenden eine andere Ortsvorwahl, oder wenn die vorherigen Benutzer mithilfe des Cmdlets <STRONG>Disable-CsUser</STRONG> deaktiviert wurden.</P>
> <LI>
> <P>Bevor Sie Kontakte erstellen, müssen Sie zuerst die Benutzerreplikation durchführen, die auf der Registerkarte Benutzer ausgeführt wird. Wenn Sie soeben Ihre Benutzer erstellt haben, müssen Sie warten, bis die lync Server-Replikation abgeschlossen ist, und die Benutzerkonten in der Datenbank werden gefüllt. Wenn die Replizierung der Benutzer noch nicht erfolgt ist, wird ein Fehler angezeigt. Sie wissen, wann die Replikation der Benutzer abgeschlossen ist, wenn der lync Server 2013-Front-End-Dienst gestartet wurde, oder dass Sie das Cmdlet " <STRONG>Get-CsUser</STRONG> " für den letzten Benutzer erfolgreich ausgeführt haben.</P></LI></OL>



</div>

</div>

</div>

<div>

## <a name="contacts-creation-tab"></a>Registerkarte "Kontakte erstellen"

Auf der Registerkarte "Kontakte erstellen" können Sie Details zu den Kontakten der Benutzer angeben.

![Registerkarte "Kontakte erstellen"](images/JJ945587.7508726e-83e6-4878-8edd-114543d9af24(OCS.15).jpg "Registerkarte "Kontakte erstellen"")

Führen Sie die folgenden Schritte aus, um die Kontakte der Benutzer zu konfigurieren.

1.  Geben Sie in durchschnittliche Kontakte pro Benutzer die durchschnittliche Anzahl der Kontakte an, die in Kontaktlisten für die einzelnen Benutzer aufgefüllt werden sollen.

2.  Aktivieren Sie das Kontrollkästchen behoben, wenn Sie eine gleiche Anzahl von Kontakten für jeden Benutzer erstellen möchten. Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, deaktivieren Sie das Kontrollkästchen.

3.  Geben Sie in durchschnittliche Kontaktgruppen pro Benutzer die Anzahl der Kontaktgruppen pro Benutzer an. Diese Nummer muss kleiner als durchschnittliche Kontakte pro Nutzer sein.

4.  Geben Sie in Prozent der Föderations-/quer Pool Kontakte eine Zahl zwischen 0 und 100 an. Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.

5.  Geben Sie im Verbund/Pool-Benutzerpräfix den Benutzernamen für Verbundbenutzer an, der den Kontaktlisten lokaler Benutzer hinzugefügt werden soll.

6.  Geben Sie in der SIP-Domäne des Federated/Cross Pool-Benutzers den SIP-Domänennamen der Föderationsbenutzer ein.
    
    <div>
    

    > [!NOTE]  
    > Bei der Erstellung von Kontakten sollte keiner der Benutzer angemeldet sein.

    
    </div>

7.  Überprüfen Sie auf der Registerkarte Benutzererstellung, ob die Parameter richtig sind. Der Bereich der Benutzer, für die Kontakte erstellt werden, wird auf der Registerkarte Benutzererstellung abgerufen.

8.  Klicken Sie auf Kontakte erstellen, um mit der Erstellung des Kontakts zu beginnen. Dieser Vorgang kann mehrere Minuten dauern. Nach Abschluss des Vorgangs wird ein Dialogfeld mit der Meldung "Vorgang wurde erfolgreich abgeschlossen" angezeigt. Sie können die Kontakte, die Sie erstellt haben, überprüfen, indem Sie sich als Benutzer anmelden, der über die Registerkarte Benutzererstellung erstellt wurde.
    
    <div>
    

    > [!NOTE]  
    > Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Ziel Pool neu. Je nachdem, wie viele Kontakte von diesem Vorgang erstellt wurden, dauert es möglicherweise länger (bis zu zwei Stunden), bis die Front-End-Server gestartet werden.

    
    </div>

</div>

<div>

## <a name="distribution-list"></a>Verteilerliste

Eines der Features des lync Server 2013-Tools für Stress und Leistung besteht darin, das Erweiterungsfeature Verteilerliste (DL) in lync 2013 zu simulieren. Wenn Sie die DL-Erweiterung in UserProvisioningTool nicht aktivieren möchten, können Sie diesen Schritt überspringen.

![Registerkarte "Erstellung der Verteilerliste"](images/JJ945587.0a1d681b-2aea-4724-90d8-efa8a526f600(OCS.15).jpg "Registerkarte "Erstellung der Verteilerliste"")

Auf der Registerkarte "Verteilerliste" können Sie DLS erstellen, die vom Tool "Spannung und Leistung" für das Erweiterungsfeature "Verteilerliste" verwendet werden. Vor dem Erstellen von DLS muss lync Server 2013 bereits installiert sein. Sie müssen lync Server 2013 ForestPrep ausgeführt haben. Andernfalls sind die DL-Attribute im Active Directory-Domänendienste-Schema nicht vorhanden, und das Tool kann keine DLS erstellen.

Führen Sie die folgenden Schritte aus, um Verteilerlisten zu konfigurieren.

1.  Geben Sie in Anzahl der Verteilerlisten die Gesamtzahl der DLS an, die Sie erstellen möchten. (Wir empfehlen, dass Sie mit der doppelten Anzahl von Benutzern beginnen). Sie werden von 0 bis n-1 nummeriert.

2.  Geben Sie Unterverteiler Listen Präfix das Präfix an, das die DLS aufweisen soll. Wenn Sie beispielsweise 100-DLS und ein Präfix von testDL angeben, werden die Verteilerlisten mit dem Namen testDL0, testDL1 usw. durch testDL99.

3.  Geben Sie in minimale Mitglieder in einer Vert.-Liste die Mindestanzahl der Benutzer an, die in jeder Verteilerliste hinzugefügt werden sollen.

4.  Geben Sie in maximale Anzahl von Mitgliedern in einer Vert.-Liste die maximale Anzahl der Benutzer an, die in jeder Verteilerliste hinzugefügt werden sollen.

<div>

## <a name="create-distribution-lists-button"></a>Schaltfläche "Verteilerlisten erstellen"

Wenn Sie auf die Schaltfläche Verteilerlisten erstellen klicken, fragt das Tool die Active Directory-Domänendienste ab, um festzustellen, ob Verteilerlisten, die dem Präfix und den Nummern entsprechen, bereits vorhanden sind. Das Tool erstellt nur diejenigen, die noch nicht vorhanden sind. Beim Hinzufügen von Mitgliedern zu diesen neu erstellten Verteilerlisten werden die Benutzer aus dem Bereich ausgewählt, der auf der Registerkarte Benutzererstellung angegeben ist.

</div>

</div>

<div>

## <a name="location-info-service-config-tab"></a>Registerkarte "Standortinformationen für Dienstkonfiguration"

Eines der Features des lync Server 2013-Tools Stress und Leistung besteht darin, Dummy-Konfigurationsdateien für den standortinformationsdienst zu generieren. Der standortinformationsdienst hat in der Regel keine bedeutenden Auswirkungen auf die Leistung der Server.

![Registerkarte "Standortinformationen für Dienstkonfiguration"](images/JJ945587.52ea4e9e-d50a-4dc9-982b-31ee5ace4578(OCS.15).jpg "Registerkarte "Standortinformationen für Dienstkonfiguration"")

Wenn Sie dieses Feature testen möchten, können Sie die im Formular genannten Werte ausfüllen und dann auf die Schaltfläche "LIS-Konfigurationsdateien generieren" klicken. Es werden CSV-Dateien wie "\_LIS Subnet. csv"\_, "LIS Switches\_. csv", "LIS\_Ports. csv" und "LIS WAP. csv" generiert. Sie können diese CSV-Dateien dann in die LIS-Datenbank importieren, indem Sie das Cmdlet " **CsLisSubnet** ", das Cmdlet "Satz- **CsLisSwitch** ", das Cmdlet " **Satz-CsLisPort** " und das Cmdlet "Satz **-CsWirelessAccessPoint** " verwenden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

