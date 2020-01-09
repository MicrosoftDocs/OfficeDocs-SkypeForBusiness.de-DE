---
title: Verwenden des Skype for Business Server 2015 Stress-und Leistungstools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Wenn Sie das Stress-und Leistungstool für Skype for Business Server 2015 ausführen möchten, müssen Sie in der Lage sein, Benutzer, Kontakte und Benutzerprofile zu verwalten, das Tool für die Ausführung zu konfigurieren und dann die vom Tool erstellte Ausgabe oder Ergebnisse zu überprüfen.
ms.openlocfilehash: af4d0dcb1cc4196f98941799c61dcf29510ba795
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992482"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Verwenden des Skype for Business Server 2015 Stress-und Leistungstools
 
Wenn Sie das Stress-und Leistungstool für Skype for Business Server 2015 ausführen möchten, müssen Sie in der Lage sein, Benutzer, Kontakte und Benutzerprofile zu verwalten, das Tool für die Ausführung zu konfigurieren und dann die vom Tool erstellte Ausgabe oder Ergebnisse zu überprüfen.
  
Es gibt vier Bereiche, in denen das Ausführen des Stress-und Leistungstools von Skype for Business Server 2015 (die ausführbare Datei ist "LyncPerfTool. exe"):
  
- [Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Benutzerprofil konfigurieren](using-the-tool.md#BKMK_UserProfile)
    
- [Ausführen von LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretieren der Ergebnisse](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Erstellen von Benutzern und Kontakten
<a name="BKMK_CreateUsersAndContacts"> </a>

Sie müssen das Benutzer Bereitstellungs Tool (UserProvisioningTool. exe) von Skype for Business Server 2015 (SB 2015) verwenden, um Benutzer und Kontakte für Ihre Belastungs-und Leistungstests zu erstellen.
  
Dies ist eine Liste hilfreicher Begriffe, die beim Lesen der Themen hilfreich sein können:
  
- **Organisationseinheit** – die Active Directory-Domänendienste (AD DS)-Organisationseinheit (OU).
    
- **Federated/Cross-Pool** – Benutzer, die mit Benutzern aus anderen Instant Messaging-Diensten (im) kommunizieren können.
    
- **Verteilerlisten** -oder DLS. Hierbei handelt es sich um Objekte in AD DS, die eine Liste der AD DS-Benutzer enthalten. Sie werden verwendet, um die Kommunikation zwischen Gruppen von Personen zu vereinfachen.
    
- **Location Info Service** – der Skype for Business Server 2015-Dienst, der, wenn er pro Telefon aktiviert und konfiguriert ist, den Abruf des physikalischen Standorts für verbesserte 911-Dienste (E911) ermöglicht.
    
- **US-Telefonnummern** : dem Benutzer zugewiesene Telefonnummern zusätzlich zum SIP-URI, der für das Routing von eingehenden und ausgehenden Anrufen in Reverse Number Lookup (RNL) verwendet wird.
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Erstellen von Benutzern und Kontakten mithilfe von "UserProvisioningTool. exe"

> [!NOTE]
> Bevor Sie beginnen, müssen Sie unbedingt sicherstellen, dass Sie als Mitglied der Sicherheitsgruppe "Domänen-Admins" angemeldet sind, um dieses Tool ausführen zu können. Sie müssen dies tun, weil Sie Active Directory-Benutzer erstellen werden. 
  
Sie müssen das Benutzer Bereitstellungs Tool für Skype for Business Server verwenden, um Benutzer und Kontakte für die Auslastungssimulation zu erstellen.
  
Das **Skype for Business Server-Bereitstellungstool für Benutzer** wird mit dem **Skype for Business Server Stress-und Leistungstool-** Paket installiert. Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool. msi) auf dem Front-End-Server oder auf dem Standard Edition-Server ausgeführt wurde, den Sie testen möchten.
  
Sie können das Benutzer Bereitstellungs Tool für Skype for Business Server starten, indem Sie die Datei UserProvisioningTool. exe (befindet sich unter% InstalledDirectory% LyncStressAndPerfTool \ LyncStress) auf dem Front-End-Server oder auf dem Standard Edition-Server ausführen.
  
> [!IMPORTANT]
> Wenn Sie eine große Anzahl von Benutzern erstellen (beispielsweise 10.000 oder mehr), führen Sie die UserProvisioningTool. exe aus. Dies ist erforderlich, da das Tool *neue* anzeigen Benutzer erstellt und konfiguriert.
  
Wenn das Benutzer Bereitstellungs Tool geöffnet wird, klicken Sie auf Konfiguration, und wählen Sie die Load-Konfiguration aus. 
  
Wenn Sie mit der Konfiguration von Benutzern und Kontakten beginnen möchten, laden Sie die im Paket enthaltene Standarddatei mit dem Namen "sampledata. xml". Damit werden Felder mit Beispieldaten vorab gefüllt, die Sie ändern müssen, damit Sie für Ihre Bereitstellung relevant sind.
  
Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die bereits Ihre angepassten Einstellungen enthält, können Sie diese Datei stattdessen laden. Füllen Sie die Felder im Benutzer Bereitstellungs Tool aus, wie in den folgenden Abschnitten beschrieben.
  
### <a name="to-configure-server-options"></a>So konfigurieren Sie Serveroptionen:

1. Geben Sie im Feld **FQDN des Front-End-Pools** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition-Servers oder den Front-End-Pool ein, in dem Sie die Benutzer hosten möchten.
    
2. Geben Sie im Feld **Benutzer Name-Präfix** ein Präfix ein, das Sie verwenden möchten, um Ihre Benutzernamen zu Testzwecken zu überschreiben (beispielsweise "testuser").
    
3. Geben Sie im Feld **Kennwort** ein Kennwort ein, das für alle Testbenutzerkonten verwendet wird.
    
4. Geben Sie im Feld **Kontodomäne** den Domänennamen der aktuellen AD-Domäne ein (in der Sie die Testbenutzer erstellen möchten).
    
5. Geben Sie im Feld **Organisationseinheit** den Namen der anzeigen Domäne ein, in der Sie diese Testbenutzer erstellen möchten. (Wenn die Organisationseinheit noch nicht vorhanden ist, wird Sie für Sie erstellt).
    
6. Geben Sie im Feld **Telefonvorwahl** die dreistellige Vorwahl ein, die in allen Testbenutzerkonten verwendet werden soll. Stellen Sie sicher, dass die von Ihnen gewählte Vorwahl nicht in Konflikt mit den Ortsvorwahl anderer Benutzer in AD steht.
    
7. Aktivieren Sie das Kontrollkästchen **sprachaktiviert** , wenn Sie die Testbenutzer für Enterprise-VoIP aktivieren möchten.
    
8. Geben Sie im Feld **Anzahl der Benutzer** die Gesamtzahl der Testbenutzer ein, die Sie erstellen möchten.
    
9. Geben Sie im Feld **Start Index** die Anfangszahl ein, die dem Benutzernamenpräfix als Suffix verwendet werden soll (beispielsweise ist das Präfix "testuser", und der Vorname endet im folgenden Beispiel mit "0").
    
     ![Benutzerbereitstellungstool mit der Registerkarte für die Erstellung von Benutzern](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Schaltfläche "Benutzer erstellen"

Wenn Sie auf die Schaltfläche **Benutzer erstellen** klicken, werden die von Ihnen eingegebenen Eingabeparameter überprüft. Wenn es Validierungsfehler gibt, werden Sie aufgefordert, diese zu beheben. Oder, wenn alle Werte richtig sind, werden die Benutzer in Anzeige (in der von Ihnen angegebenen OU) angezeigt. Im unteren Bereich des Tools wird eine Statusleiste angezeigt. Schließen Sie die Anwendung nicht, während die Statusleiste aktiv ist.
  
Die Benutzererstellung benötigt Zeit, daher sollten Sie dies entsprechend planen. Dieser Vorgang kann mehrere Minuten für einige Benutzer und für eine große Anzahl von Benutzern auf einige Stunden dauern.
  
Wenn Sie keinen Zugriff auf den AD-Domänen Controller in Ihrer Testumgebung haben, können Sie die Benutzererstellung weiterhin überprüfen, indem Sie sich als einer der Benutzer in dem von Ihnen angegebenen Bereich der Benutzer anmelden. Denken Sie daran, das Präfix und das Suffix zusammen mit dem @sipDomain als username zu verwenden. Hier ist ein Beispiel: <em>TestUser20@contoso.net</em> .
  
> [!NOTE]
> Wenn die Benutzer bereits vorhanden sind, werden Sie durch Klicken auf die Schaltfläche Benutzer erstellen mit Konfigurationsänderungen aktualisiert. 
  
#### <a name="delete-users-button"></a>Schaltfläche "Benutzer löschen"

Wenn Sie auf die Schaltfläche **Benutzer löschen** klicken, werden die Eingabeparameter der Registerkarte überprüft. Wenn es Validierungsfehler gibt, werden Sie aufgefordert, diese zu beheben, und wenn die Eingabewerte richtig sind, werden die angegebenen Testbenutzer deaktiviert und aus Active Directory gelöscht. Wieder wird eine Statusleiste am unteren Rand dieser Registerkarte angezeigt, und Sie sollten die Anwendung nicht schließen, während die Statusleiste aktiv ist.
  
> [!NOTE]
> Nur US-formatierte Telefonnummern werden unterstützt. Telefonnummern werden immer Benutzern zugewiesen, und alle von UserProvisioningTool. exe erstellten Benutzer sind standardmäßig für Enterprise-VoIP aktiviert. In Szenarien, in denen die Telefonnummer verwendet wird, beispielsweise die automatische Telefonzentrale oder UC-PSTN-Anrufe, verwenden Sie diese Telefonnummer, um Anrufe richtig weiterzuleiten. Aus diesem Grund muss *jeder Nutzer* eine *eindeutige Telefonnummer* haben.
  
> [!NOTE]
> **Wenn Sie Benutzer zweimal erstellen müssen, schlägt der Befehl fehl, es sei denn, Sie verwenden eine andere Ortsvorwahl, oder wenn die vorherigen Benutzer mithilfe des Cmdlets Disable-CsUser deaktiviert wurden.**
  
> [!IMPORTANT]
> Bevor Sie Kontakte erstellen, müssen Sie zuerst die Benutzerreplikation durchführen (Dies erfolgt über die Registerkarte Benutzer). 
  
> [!IMPORTANT]
> Wenn Sie soeben Ihre Benutzer erstellt haben, müssen Sie warten, bis die Skype for Business Server-Replikation abgeschlossen ist, und die Benutzerkonten in der Datenbank aufgefüllt. **Wenn die Replizierung der Benutzer noch nicht erfolgt ist, wird ein Fehler angezeigt.** Sie wissen, wann die Replikation der Benutzer abgeschlossen ist, wenn der Skype for Business Server 2015-Front-End-Dienst gestartet wurde, oder dass Sie das Cmdlet "Get-CsUser" für den letzten Benutzer der angegebenen Gesamtzahl erfolgreich ausgeführt haben.
  
#### <a name="contacts-creation-tab"></a>Registerkarte "Kontakte erstellen"

Auf dieser Registerkarte können Sie die Kontaktdetails der Benutzer für Ihre Tests angeben.
  
![Das Benutzerbereitstellungstool zeigt die Registerkarte für die Erstellung von Inhalten.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Gehen Sie wie folgt vor, um die Kontakte der Benutzer zu konfigurieren:

1. Geben Sie im Feld **durchschnittliche Kontakte pro Benutzer** die durchschnittliche Anzahl der Kontakte ein, die in Kontaktlisten für jeden Benutzer eingetragen werden sollen.
    
2. Aktivieren Sie das Kontrollkästchen **behoben** , wenn Sie eine gleiche Anzahl von Kontakten für jeden Benutzer erstellen möchten. Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, deaktivieren Sie das Kontrollkästchen.
    
3. Geben Sie im Feld **durchschnittliche Kontaktgruppen pro Benutzer** die Anzahl der Kontaktgruppen pro Benutzer ein. Diese Nummer muss kleiner als **durchschnittliche Kontakte pro Nutzer**sein.
    
4. Geben Sie im Feld **Federated/Cross Pool Contacts Percentage** eine Zahl zwischen 0 und 100 ein. Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.
    
5. Geben Sie im Feld **Benutzerpräfix für Federated/Cross-Pool** den Benutzernamen für Federated-Benutzer an, der den Kontaktlisten lokaler Benutzer hinzugefügt werden soll.
    
6. Geben Sie im Feld **Federated/Cross Pool User SIP Domain** den SIP-Domänennamen der Federated-Benutzer ein.
    
7. Überprüfen Sie auf der Registerkarte **Benutzererstellung** , ob die Informationen richtig sind. Ihre Kontakte werden auf der Registerkarte Benutzererstellung aus Werten erstellt.
    
8. Klicken Sie auf **Kontakte erstellen** , um mit der Erstellung des Kontakts zu beginnen. Dieser Vorgang kann mehrere Minuten dauern. Nach Abschluss des Vorgangs wird ein Dialogfeld mit der Meldung "Vorgang wurde erfolgreich abgeschlossen" angezeigt. Sie können die Kontakte, die Sie erstellt haben, überprüfen, indem Sie sich als Benutzer anmelden, der über die Registerkarte Benutzererstellung erstellt wurde.
    
> [!NOTE]
> Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Ziel Pool neu. Je nachdem, wie viele Kontakte von diesem Vorgang erstellt wurden, dauert es möglicherweise länger (bis zu zwei Stunden), bis die Front-End-Server gestartet werden. 
  
#### <a name="distribution-list"></a>Verteilerliste

Das Stress-und Leistungs Tool von Skype for Business Server 2015 kann das Erweiterungsfeature Verteilerliste (DL) im Skype for Business 2015-Client simulieren. Sie können diesen Schritt überspringen, wenn Sie nicht beabsichtigen, die DL-Erweiterung im Benutzer Bereitstellungstool zu aktivieren.
  
![Benutzerbereitstellungstool zeigt Registerkarte für die Erstellung von Verteilerlisten](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
Auf der Registerkarte "Verteilerliste" können Sie DLS erstellen, die vom Tool "Spannung und Leistung" für das Erweiterungsfeature "Verteilerliste" verwendet werden. Vor dem Erstellen von DLS muss Skype for Business Server 2015 bereitgestellt werden, einschließlich der Ausführung von ForestPrep. Wenn dies nicht der Fall ist, sind die DL-Attribute im AD-Schema nicht vorhanden, sodass das Tool keine DLS erstellen kann.
  
### <a name="to-configure-distribution-lists"></a>So konfigurieren Sie Verteilerlisten:

1. Geben Sie im Feld **Anzahl der Verteilerlisten** die Gesamtzahl der DLS ein, die Sie erstellen möchten (hier wird empfohlen, dass Sie mit einem Wert beginnen, der die doppelte Anzahl der Benutzer hat.).
    
2. Geben Sie im Feld **Verteilerliste-Präfix** ein Präfix ein, das alle von Ihnen erstellten Verteilerlisten, beispielsweise *testDL* , enthalten soll. Das bedeutet, dass Ihre DL-Namen bei 100 DLS wie folgt aussehen: testDL0, testDL1, bis zu testDL99.
    
3. Geben Sie im Feld **mindestmember in einem Vert. List** -Feld die Mindestanzahl der Benutzer ein, die in jeder Verteilerliste abgelegt werden sollen.
    
4. Geben Sie im Feld Maximale Anzahl von **Mitgliedern in einem Vert.-Listen** Feld die maximale Anzahl der Benutzer ein, die in jeder Verteilerliste hinzugefügt werden sollen.
    
#### <a name="create-distribution-lists-button"></a>Schaltfläche "Verteilerlisten erstellen"

Wenn Sie auf die Schaltfläche Verteilerlisten erstellen klicken, fragt das Tool Active Directory ab, um festzustellen, ob Verteilerlisten, die mit dem Präfix und den Nummern übereinstimmen, bereits vorhanden sind. Das Tool erstellt alle Verteilerlisten, die noch nicht vorhanden sind. Beim Hinzufügen von Mitgliedern zu diesen neu erstellten Verteilerlisten werden die Benutzer aus dem Bereich ausgewählt, der auf der Registerkarte Benutzererstellung angegeben ist.
  
#### <a name="location-info-service-config-tab"></a>Registerkarte "Standortinformationen für Dienstkonfiguration"

Das Stress-und Leistungs Tool von Skype for Business Server 2015 kann auch Dummy-Konfigurationsdateien für den standortinformationsdienst generieren. Beachten Sie, dass der standortinformationsdienst in der Regel keine bedeutenden Auswirkungen auf die Leistung der Server hat. 
  
![Benutzerbereitstellungstool zeigt die Registerkarte für die Konfiguration des Standortinformationsdiensts](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Wenn Sie dieses Feature testen möchten, geben Sie die Werte in das Formular ein, und klicken Sie auf die Schaltfläche "LIS-Konfigurationsdateien generieren", die erstellt wird. CSV-Dateien mit dem Namen:
  
- LIS_Subnet. CSV
    
- LIS_Switches. CSV
    
- LIS_Ports. CSV
    
- LIS_WAP. CSV
    
Verwenden Sie diese PowerShell-Cmdlets, um diese Dateien in die LIS-Datenbank zu importieren:
  
- Satz-CsLisSubnet
    
- Satz-CsLisSwitch
    
- Satz-CsLisPort
    
- Satz-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Benutzerprofil konfigurieren
<a name="BKMK_UserProfile"> </a>

Nachdem Ihre Benutzer erstellt wurden (über das Tool zum Erstellen von Benutzern), können Sie Benutzerprofile mit dem Skype for Business Server 2015 Load Configuration Tool (UserProfileGenerator. exe) konfigurieren.
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ausführen des Load Configuration Tools für Skype for Business Server 2015

Starten Sie das Load Configuration Tool (UserProfileGenerator. exe), und füllen Sie die Registerkarten aus. Dieses Tool erstellt ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen ihrer Simulationen benötigen. Jedes Clientverzeichnis enthält ein Skript zum Starten des Skype for Business Server 2015-Stress-und-Leistungstools (LyncPerfTool. exe). In den folgenden Abschnitten finden Sie Beispiele für das Ausfüllen der Felder auf jeder Registerkarte des Skype for Business Server 2015 Load Configuration-Tools.
  
> [!IMPORTANT]
> Die benutzerspezifischen Werte, die im Load Configuration Tool (UserProfileGenerator. exe) verwendet werden, müssen den im Skype for Business Server 2015-Benutzer Erstellungstool (UserProvisioningTool. exe) für den Pool angegebenen Werten entsprechen. 
  
#### <a name="common-configuration-tab"></a>Registerkarte "Allgemeine Konfiguration"

Die Registerkarte " **Allgemeine Konfiguration** " des Tools "Load Configuration" ist unten dargestellt. Füllen Sie die Felder auf der Registerkarte Allgemeine Konfiguration aus, wie in den folgenden Schritten beschrieben.
  
![Die Registerkarte „Benutzerbereitstellung“ zeigt die Registerkarte für die allgemeine Konfiguration.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Geben Sie im Feld **Anzahl der verfügbaren** Computer die Anzahl der Computer ein, die Sie zum Ausführen des Stress-und Leistungstools (LyncPerfTool. exe) verwenden möchten. Wir empfehlen, dass Sie über einen Computer für alle 4500-Benutzer verfügen, die Sie simulieren werden, diese Zahl kann jedoch variieren, wenn Sie den Ladebereich verringern oder nur einen Teil der verfügbaren Features des Tools verwenden (die Ladestufen werden auf der Registerkarte Allgemeine Szenarien festgesetzt).
    
2. Geben Sie im Feld **Präfix für Benutzernamen** für alle Benutzer ein Präfix für das Feld Benutzername ein. So melden Sie sich beim Uniform Resource Identifier (URI) an: *UserPrefix [User Start Index... (Anzahl der Benutzer-1)] @User Domäne* , beispielsweise myUser009@contoso.com.
    
3. Geben Sie im Feld **Kennwort für alle Benutzer** das Kennwort ein, das beim Erstellen der Benutzer verwendet wurde. Wenn Sie dieses Feld leer lassen, wird der Nutzername als Kennwort gesetzt.
    
4. Geben Sie im Feld **Start Index des Benutzers** den Index des ersten Benutzers ein, der konfiguriert werden soll. Sie können verschiedene Bereiche für verschiedene Typen oder lade Ebenen konfigurieren, aber Sie müssen das Load Configuration Tool (UserProfileGenerator. exe) einmal pro Bereich ausführen, den Sie konfigurieren möchten.
    
5. Geben Sie im Feld **Anzahl der Benutzer** die Gesamtzahl der Benutzer ein, die Sie konfigurieren möchten.
    
6. Geben Sie im Feld **Benutzerdomäne** die Domäne ein, die für den SIP-URI verwendet wird. Diese wird verwendet, um den SIP-URI jedes Benutzers zu erstellen, der sich beim Skype for Business Server 2015-Front-End-Server oder Standard Edition-Server anmeldet und sich möglicherweise von der Kontodomäne unterscheidet.
    
7. Geben Sie im Feld **Kontodomäne** die Active Directory-Domänenanmeldung ein.
    
8. Geben Sie im Feld **mpop-Prozent** Satz (mehrfacher Punkt des Anwesenheits Prozentsatzes) einen Wert für den Prozentsatz der Benutzer ein, die von mehreren Computern oder Geräten angemeldet sind, beispielsweise 10 Prozent.
    
9. Geben Sie die maximale Anzahl von gleichzeitigen Endpunkten im Feld **Anmeldung pro Sekunde (pro Instanz)** ein. Hierbei handelt es sich um die maximale Anzahl von Protokoll-ins für Ihre Benutzer, und die Empfehlung ist eine Rate von kleiner als/gleich 2 pro Sekunde (<= 2).
    
10. Geben Sie im Feld **Zugriffs Proxy oder Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen sollen. Wenn sich die Benutzer extern anmelden, müssen Sie den Zugriffsproxy eingeben. Wenn die Benutzer intern sind, geben Sie den FQDN Ihres Enterprise-Pools oder Standard Edition-Servers ein.
    
11. Geben Sie im Feld **Port** den Port ein, den Benutzer für SIP verwenden sollen (die Standardeinstellung lautet 5061).
    
12. Geben Sie für das Feld **externe Netzwerk Server Einstellungen** den Zugriffs Proxy-oder Pool-FQDN und erneut den **Port**an. Diese Einstellungen werden nur für die Auslastungssimulation externer Endpunkte verwendet.
    
#### <a name="general-scenarios-tab"></a>Registerkarte "allgemeine Szenarien"

![Lastkonfigurationstool zeigt Registerkarte „Allgemeine Szenarien“](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Sie können die Auslastungsgrade und Parameter für die einzelnen allgemeinen Szenarien konfigurieren, indem Sie festlegen, was ausgeführt werden soll oder ob Sie deaktiviert bleiben möchten. Hier sind die allgemeinen Optionen:
  
> [!NOTE]
> Werte für Load Level für alle Felder, aber lokale Informationsdienste sind **deaktiviert**, **gering**, **Mittel**, **hoch**oder **Benutzerdefiniert**. Wenn Sie eine Einstellung, aber deaktiviert auswählen, werden für jeden Clientkonfigurationen generiert. Hohe Ergebnisse bei maximaler unterstützter Auslastung auf dem Server; Medium ist 60% der großen Last; niedriger ist 30%. 
  
- **Instant Messaging –** Dazu gehören Peer-to-Peer und Konferenzen; Wählen Sie den entsprechenden Wert für Load Level aus.
    
- **Audio-Conferencing-** Wählen Sie *nur* eine Auslastungsstufe für Audiokonferenzen aus. Peer-zu-Peer-Anrufe werden etwas später im Abschnitt **VoIP-Szenarien** behandelt. Öffnen Sie die Registerkarte **erweitert** , um MultiView zu aktivieren.
    
- **Anwendungsfreigabe –** Wählen Sie eine Auslastungsstufe für die Anwendungsfreigabe aus.
    
- **Datenzusammenarbeit –** Wählen Sie eine Auslastungsstufe für die Datenzusammenarbeit aus, die Datenkonferenzen umfasst.
    
- **Erweiterung der Verteilerliste –** Klicken Sie auf die Schaltfläche **erweitert** , und füllen Sie das Feld mit den gleichen Werten aus, die auf der Registerkarte DL des Benutzer Erstellungstools (UserProvisioningTool. exe) konfiguriert sind. Wählen Sie eine Auslastungsstufe aus.
    
- **Adressbuch-Webabfrage –** Hierbei handelt es sich um den Adressbuch-Suchdienst anstelle des Adressbuchdatei Downloads. Wenn Sie dies für Adressbuchdatei Downloads aktivieren möchten, klicken Sie auf die Schaltfläche **erweitert** , und legen Sie **EnableABSDownload** auf true fest. Geben Sie einen Wert für Load Level an.
    
- **Reaktionsgruppendienst –** Klicken Sie auf die Schaltfläche **erweitert** , und geben Sie die URIs der Reaktionsgruppen an, die Sie bereits beim Bereitstellen von Reaktionsgruppen-Service-Agents erstellt haben. Sie müssen mindestens eine Reaktionsgruppe auswählen. Wenn Sie mehr verwenden möchten, trennen Sie die Antwortgruppen durch Semikolons. Aktualisieren Sie **RGSUriSuffixStartIndex** und **RGSUriSuffixEndIndex** auf die tatsächlichen Werte. Wählen Sie eine Auslastungsstufe aus.
    
- **Standort Informationsdienste –** Wählen Sie eine Auslastungsstufe entweder aktiviert oder deaktiviert aus.
    
> [!NOTE]
> In jedem der Szenarien befindet sich neben der Schaltfläche "Erweitert" und eine Reihe von Kontrollkästchen, die Variationen der Standardeinstellung ermöglichen. 
  
- Wenn Sie *Ad-hoc* auswählen, kann das Tool die Simulation von Konferenzen generieren, die während der gesamten Stunde erstellt werden.
    
- Wenn Sie eine *große conf* auswählen, wird ein großes Konferenz Szenario simuliert.
    
-  *Extern* weist das Tool an, auch externe Benutzer zu simulieren.
    
Diese Schaltflächen und Kontrollkästchen sind zusätzliche Werte, die für jedes Szenario spezifisch sind, und ändern das Verhalten des Tools Stress und Leistung und ermöglichen eine Anpassung.
  
Bei jedem Szenario auf der Registerkarte Allgemeine Szenarien (mit Ausnahme von Standort Informationsdiensten) wird die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld erweitert berechnet, wenn der Wert der Auslastungsstufe **Benutzerdefiniert**ist. Der Feldname kann je nach Szenario unterschiedlich sein, aber die Feld Beschreibung gibt an: *Hinweis Diese Nummer wird nur verwendet, wenn im Dropdownmenü die Option Benutzerdefiniert ausgewählt ist* .
  
Mit den Werten " **hoch**", " **Mittel**" und " **tief**" werden die Konversations Raten pro Modalwert entsprechend dem Benutzermodell geändert, bei dem es sich um ein Gleichgewicht aller Szenarien handelt. Verwenden Sie eine benutzerdefinierte Unterhaltungs Rate, wenn der Auslastungsgrad pro Modalwert aufgrund einer unterschiedlichen erwarteten Nutzung geändert werden muss.
  
#### <a name="voice-scenarios-tab"></a>Registerkarte "Sprachszenarien"

Dies ist die Registerkarte für die Konfiguration aller sprachbezogenen Szenarien.
  
![Lastkonfigurationstool, Registerkarte für VoIP-Szenarien](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Ihre Optionen sind:
  
- **VoIP-** Klicken Sie auf die Schaltfläche **erweitert** , und fügen Sie Werte für die Felder PhoneAreaCode und LocationProfile (Wählplan) hinzu. Außerdem geben Sie einen Wert für Load Level an. Wenn Sie eine Auslastungsstufe für VoIP oder UC/PSTN-Gateway aktiviert haben, wird eine Public-Switched Telephone Network (PSTN) zur Unified Communications (UC)-Konfigurationsdatei generiert, um externe Anrufe zu simulieren.
    
- **UC/PSTN-Gateway –** Sie müssen einen Wert für die Auslastungsstufe auswählen, und wenn Sie etwas anderes als deaktiviert auswählen, müssen Sie auch einen Wert für die PSTN-Vorwahl angeben, indem Sie auf die Schaltfläche **erweitert** klicken. Klicken Sie unter dem Vermittlungs Server und PSTN auf **Hinzufügen** . Stellen Sie sicher, dass für die Ortsvorwahl eine Route konfiguriert ist.
    
    > [!TIP]
    > Sie können entweder das Skype Control Panel für Unternehmen oder die Skype for Business-Verwaltungsshell verwenden, um Ihre VoIP-Routen Konfiguration zu überprüfen. 
  
- **Konferenzzentrale –** Geben Sie einen Wert für Load Level an. Mit einem anderen Wert als "deaktiviert" wird das Feld " **Telefonnummer** " aktiviert. Geben Sie die Telefonnummer der automatischen Telefonzentrale ein, die Sie verwenden möchten. Klicken Sie auf **erweitert** , und geben Sie einen Wert für das **LocationProfile** -Feld ein.
    
- **Parken-Service anrufen-** Geben Sie hier einen Ladebereich ein.
    
- **Vermittlungs Server und PSTN –** Jeder Vermittlungs Server, den Sie verwenden möchten, benötigt einen eigenen PSTN-Simulator. Nachdem Sie festgestellt haben, welchen Client Sie für den Simulator verwenden werden, konfigurieren Sie den Vermittlungs Server so, dass Anrufe an diesen Computer im von Ihnen konfigurierten PSTN-Simulator weitergeleitet werden. Klicken Sie auf die Schaltfläche **Hinzufügen** , um einen Wert für den Vermittlungs Server zu konfigurieren.
    
    > [!NOTE]
    > In jedem Szenario befindet sich daneben eine Schaltfläche "Erweitert". Erweiterte Dialogfelder enthalten spezifische Einstellungen für jedes Szenario, die das Verhalten des Stress-und Leistungstools ändern und die Anpassung aktivieren. > für jedes Szenario auf der Registerkarte VoIP-Szenarien, wenn der Wert der Ladeebene **Benutzerdefiniert**ist, wird die Konversations Rate mithilfe des entsprechenden Felds im Dialogfeld erweitert berechnet. Der Feldname kann je nach Szenario unterschiedlich sein, aber die Feld Beschreibung gibt an: *Hinweis Diese Nummer wird nur verwendet, wenn im Dropdownmenü die Option Benutzerdefiniert ausgewählt ist* .
  
#### <a name="web-app-tab"></a>Web App-Registerkarte

![Lastkonfigurationstool, Registerkarte „Web App“](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App unterstützt Konferenzszenarien über den Unified Communications Web API-Server (UCWA), der auf einem Front-End-Server installiert ist. Verwenden Sie die Registerkarte Web App, um alle Web App-bezogenen Szenarien zu konfigurieren. Folgende Optionen stehen zur Auswahl:
  
- **Allgemeine Web App-Einstellungen –** Klicken Sie auf die Schaltfläche **zusätzliche Einstellungen** , und legen Sie die **ReachTargetServerUrl** auf die virtuelle IP-Adresse (VIP) des Front-End-Pool-VIP-Pools.
    
- **Anwendungsfreigabe –** Wählen Sie einen Wert für Load Level aus.
    
- **Datenzusammenarbeit –** Wählen Sie einen Wert für Load Level aus.
    
- **Instant Messaging –** Wählen Sie einen Wert für Load Level aus.
    
- **Sprachkonferenzen –** Wählen Sie einen Wert für Load Level aus.
    
> [!NOTE]
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " **erweitert** ". Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Stress-und Leistungstools ändern und die Anpassung ermöglichen. #a0 für jedes der Web-App-Szenarien wird, wenn die Auslastungsstufe **Benutzerdefiniert**ist, der im Feld **ConversationsPerHour** angegebene Wert anstelle des Standardwerts verwendet.
  
#### <a name="mobility-tab"></a>Reiter "Mobilität"

Auf dieser Registerkarte können Sie alle mobilitätsbezogenen Szenarien konfigurieren.
  
![Lastkonfigurationstool, Registerkarte für Mobilität](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Die folgenden Optionen sind verfügbar:
  
- **Allgemeine Mobilitätseinstellungen –** Klicken Sie auf **Weitere Einstellungen** , und legen Sie das Feld UcwaTargetServerUrl auf den Director Pool Virtual IP (VIP) oder den Front-End-Pool VIP.
    
- **Anwesenheits-und P2P-Instant Messaging/-Audio –** Wählen Sie einen Wert für Load Level aus, um die Mobilitäts Simulation zu aktivieren.
    
> [!NOTE]
> In jedem der Szenarien befindet sich daneben eine Schaltfläche " **erweitert** ". Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Stress-und Leistungstools ändern und die Anpassung aktivieren. #a0 für jedes Mobilitäts Szenario wird, wenn die Auslastungsstufe **Benutzerdefiniert**ist, der im Feld **ConversationsPerHour** angegebene Wert anstelle des Standardwerts verwendet.
  
#### <a name="summary-tab"></a>Registerkarte "Zusammenfassung"

Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen.
  
![Lastkonfigurationstool, Registerkarte „Zusammenfassung“](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen. 
  
Es ist möglich, Benutzernummern Bereiche manuell zu konfigurieren, indem Sie das Kontrollkästchen Benutzer **definierte Benutzerbereichs Generierung aktivieren** auswählen und dann in der Tabelle mit dem Benutzerbereich, den Sie anpassen möchten, auf das Szenario doppelklicken.
  
Überprüfen **(RunClient. bat) fügen Sie beim Starten eine Anmelde Verzögerung hinzu** , um Verzögerungen in den generierten Batchdateien einzubeziehen, damit Sie der Anmelderate entsprechen. Dies ist nützlich, um eine Serverüberlastung zu verhindern, wenn eine große Anzahl von Benutzern signiert wird.
  
Klicken Sie auf **Dateien generieren** , und wählen Sie den Ordner aus, in dem Sie die Konfiguration generieren möchten. Wenn Ihre Dateien erfolgreich erstellt wurden, wird ein Dialogfeld angezeigt.
  
![Das Nachrichtenfeld „Lastkonfigurationsdateien erfolgreich erstellt“. Klicken Sie einfach auf „OK“.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ausführen von LyncPerfTool
<a name="BKMK_RunTool"> </a>

Sie müssen Benutzer, Kontakte und Szenarien erstellen, bevor Sie das Stress-und Leistungs Tool für Skype for Business Server 2015 (LyncPerfTool. exe) ausführen. Details zum Verwenden der Tools zum Ausführen dieser Aktionen finden Sie unter [Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts) und [Konfigurieren des Benutzerprofils](using-the-tool.md#BKMK_UserProfile) zuvor in diesem Artikel. Wenn Sie diese Tools ausführen, wird auch eine Datei generiert, die mit dem Belastungs-und Leistungstool als Teil einer Batchdatei mit den erforderlichen Parametern ausgeführt wird.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ausführen des Stress-und Leistungstools von Skype for Business Server 2015

Das Load Configuration Tool (UserProfileGenerator. exe) erstellt eine Batchdatei, mit der Sie das Belastungs-und Leistungstool (LyncPerfTool. exe) ausführen können, indem Sie Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden. Die Batchdatei führt eine Instanz von LyncPerfTool. exe pro Konfigurationsdatei aus. Führen Sie die folgenden Schritte aus, um die Batchdatei auszuführen:
  
### <a name="run-the-stress-and-performance-test"></a>Führen Sie den Belastungs-und Leistungstest aus.

1. Kopieren Sie den Ordner mit den Konfigurationsordnern und-Dateien in das Verzeichnis, in dem sich LyncPerfTool. exe auf jedem Clientcomputer befindet. (Wenn Sie beispielsweise die Konfigurationsdateien im Ordner "1.28 _ 13.16.16" erstellt haben, kopieren Sie diesen Ordner in den Ordner mit "LyncPerfTool. exe". Tun Sie dies auf jedem Client.)
    
2. Navigieren Sie zum Clientordner, und führen Sie das **RunClient** -Batchskript aus. Sie können in Windows-Explorer auf die Batchdatei doppelklicken, und alle Konfigurationsdateien für diesen Client werden ausgeführt. Sie können das Skript auch über einen Clientordner ausführen, indem Sie die folgende Syntax verwenden:
    
   ```PowerShell
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Wenn Sie das Tool für die Spannungs-und Leistungsfähigkeit direkt ausführen möchten, öffnen Sie eine Eingabeaufforderung, und geben Sie den folgenden Befehl in der Befehlszeile ein (und wenn Sie dies zum ersten `regsvr32 /i /n /s LyncPerfToolPerf.dll`Mal tun, müssen Sie die Leistungsindikatoren registrieren, wie in der Notiz weiter unten in diesem Thema dargestellt):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Damit das Tool die Werte in der Konfigurationsdatei anzeigt, fügen Sie den `/displayfile` Parameter für den vorhergehenden Befehl ein, damit er wie folgt aussieht:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Drücken Sie STRG + C, um den Vorgang zu *Beenden* .
  
> [!NOTE]
> Bevor Sie das Belastungs-und Leistungstool direkt ausführen können, müssen Sie die Leistungsindikatoren über den folgenden Befehl registrieren:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Jede Instanz des von Ihnen gestarteten Druck-und Leistungstools beginnt sofort mit der Anmeldung bei Benutzern, in der Regel mit einer Rate von einem Benutzer pro Sekunde. 
  
Die Höchstzahl der Benutzeranmelde Rate für den Pool beträgt ca. 12 pro Sekunde. Das bedeutet, dass Sie nicht mehr als 12 LyncPerfTool. exe-Instanzen gleichzeitig starten sollten, während sich die Benutzer noch anmelden. 1000-Benutzer benötigen ca. 20 Minuten, um sich vollständig mit einer pro Sekunde anzumeldet.
  
## <a name="interpreting-the-results"></a>Interpretieren der Ergebnisse
<a name="BKMK_Interpret"> </a>

Das Stress-und Leistungs Tool von Skype for Business Server 2015 bietet zahlreiche Leistungsindikatoren, die Ihnen helfen, zu verstehen, was der Client tut, und ob Probleme auftreten.
  
### <a name="client-counters"></a>Client-Leistungsindikatoren

Jede Instanz von LyncPerfTool. exe verfügt über eine separate Instanz der Leistungsindikatoren. Jede Instanz wird durch ihre Prozess-ID benannt. Wenn Clients überladen sind, können andere Probleme auftreten. So verhindern Sie diese Probleme:
  
- Überwachen der CPU-und Speicherauslastung auf den Clientcomputern Wenn die CPU konstant über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.
    
- Wenn der Speicherbedarf sehr groß ist, können Probleme auftreten, wenn die Auslagerungsdatei nicht mehr genügend Speicherplatz aufweist. Überprüfen Sie, ob die Commit-Belastung auf dem Computer nicht auf das Limit trifft. Wenn Sie Speichergrenzwerte verwenden, können Sie die Größe der Auslagerungsdatei erhöhen oder die Anzahl der Benutzer reduzieren.
    
Nachfolgend finden Sie eine Liste der wichtigsten Leistungsindikatoren:
  
**Allgemeine Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|In Minuten verbrachte Zeit  <br/> |Die Zeit, die seit dem Start des Prozesses aufgewendet wurde.  <br/> |
|Aktive Endpunkte  <br/> |Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.  <br/> |
|Fehlgeschlagene Anmeldungen  <br/> |Die Gesamtzahl der Endpunkt Anmeldungsfehler.  <br/> |
|Anmeldeversuche  <br/> |Die Gesamtzahl der Endpunkt Anmeldeversuche.  <br/> |
|Endpunkte getrennt  <br/> |Die Gesamtzahl der Endpunkte, die getrennt wurden.  <br/> |
   
**Anwesenheitsinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|SetPresence-Anrufe  <br/> |Die Gesamtzahl der Anwesenheits Änderungsversuche. Informationen zu unterschiedlichen Arten von Anwesenheitsänderungen finden Sie im Leistungsindikator SetPresence (Presence Type) Calls.  <br/> |
|NNN-Antworten für SetPresence  <br/> |Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|GetPresence-Anrufe  <br/> |Die Gesamtzahl der Versuche, Anwesenheits Anfragen abzurufen.  <br/> |
|NNN-Antworten für GetPresence  <br/> |Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
   
**Informationen zum Adressbuchdienst**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Vollständige/Delta-Datei Downloads versucht  <br/> |Die Gesamtzahl der vollständigen oder Deltadatei Downloadanforderungen wurde versucht.  <br/> |
|Vollständige/Delta-Datei Downloads erfolgreich  <br/> |Die Gesamtzahl der vollständigen oder Deltadatei Downloadanforderungen wurde versucht.  <br/> |
|Verwandte Leistungsindikatoren des Adressbuch-Webabfrage Diensts  <br/> |Verwandte Leistungsindikatoren für Adressbuchdateien herunterladen.  <br/> |
|Versuchter ABS WS-Anruf  <br/> |Die Gesamtzahl der versuchten Adressbuch-Webabfrage Dienstanforderungen.  <br/> |
|ABS WS-Aufrufe erfolgreich  <br/> |Die Gesamtzahl der Adressbuch-Webabfrage Dienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|ABS WS-Anrufe nicht möglich  <br/> |Die Gesamtzahl der Adressbuch-Webabfrage Dienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.  <br/> |
   
> [!NOTE]
> Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Dateidownloads für den Adressbuchdienst (ABS) und für Adressbuch-Webabfrage Dienstanforderungen verwendet werden. 
  
**Informationen zur Verteilerliste (DL)**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Anrufversuche  <br/> |Gesamtzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung (dlx).  <br/> |
|Anrufe erfolgreich  <br/> |Die Gesamtzahl der dlx-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|Anruf fehlgeschlagen  <br/> |Die Gesamtzahl der dlx-Webdienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.  <br/> |
   

  
> [!NOTE]
> Die nachstehend aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Anrufe an den Vermittlungsserver, A/V-Konferenzserver, den Edgeserver, die Antwortgruppen Anwendung und die automatische Konferenzzentrale, wenn diese Szenarien aktiviert sind. 
  
**VoIP-Grundinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die derzeit ausgeführt werden.  <br/> |
|Anrufe beendet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe wurde bereits beendet.  <br/> |
|Anrufe abgelehnt  <br/> |Die Gesamtzahl der eingehenden Sprachanrufe wurde abgelehnt.  <br/> |
|Ein-und ausgehende Anrufe wurden versucht  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe wurde versucht.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Gesamtzahl der festgelegten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Empfangene Anrufe nnn  <br/> |Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|VoIP-Durchlauf Rate (%)  <br/> |Gesamtzahl der eingestellten Anrufe/Gesamtzahl der Anrufe.  <br/> |
   
**Informationen zum Reaktionsgruppendienst**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl aktiver Anrufe an die reaktionsgruppenanwendung.  <br/> |
|Anrufversuche  <br/> |Gesamtzahl der versuchten Anrufe.  <br/> |
   
**Sofortnachrichten (im)-Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der laufenden eingehenden/ausgehenden Sofortnachrichten.  <br/> |
|Anrufe beendet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Instant Messaging-Anrufe wurde bereits beendet.  <br/> |
|Empfangene Anrufe nnn  <br/> |Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|Empfangene/Gesendete Chatnachrichten  <br/> |Die Gesamtzahl der Nachrichten, die für alle Sitzungen empfangen oder gesendet wurden.  <br/> |
|Ein-und ausgehende Anrufe wurden versucht  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe wurde versucht.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe wurde eingerichtet.  <br/> |
   
**App-Freigabe-Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabe Anrufe.  <br/> |
|Anrufe beendet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde bereits beendet.  <br/> |
|Empfangene Anrufe nnn  <br/> |Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|Ein-und ausgehende Anrufe wurden versucht  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Aufrufe wurde versucht.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde eingerichtet.  <br/> |
   
**CAA-Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe (Public Switched Telephone Network), die derzeit ausgeführt werden.  <br/> |
|Anrufe beendet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde bereits beendet.  <br/> |
|Ein-und ausgehende Anrufe wurden versucht  <br/> |Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde versucht.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Gesamtzahl der festgelegten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
   
**Konferenz Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Instant Messaging-Konferenzen  <br/> |Gesamtzahl der laufenden Instant Messaging-Konferenzen.  <br/> |
|Aktive Audio/Video Konferenzen  <br/> |Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).  <br/> |
|Aktive Anwendungsfreigabe Konferenzen  <br/> |Gesamtzahl der laufenden Konferenz zur Anwendungsfreigabe.  <br/> |
|Anzahl der Teilnehmer  <br/> |Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.  <br/> |
|Konferenzplan Fehler  <br/> |Die Gesamtzahl der Fehler bei dem Versuch, eine Konferenz zu planen.  <br/> |
|Konferenz Fehler teilnehmen  <br/> |Die Gesamtzahl der Fehler bei dem Versuch, eine Verbindung mit einer Konferenz herzustellen.  <br/> |
   
**UCWA-Client-Leistungsindikatoren**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Gesamtzahl der IMMCU-Joins erfolgreich  <br/> |Die Gesamtzahl der Teilnahmen an Instant Messaging-Konferenzen.  <br/> |
|Gesamtzahl der DMCU-Joins erfolgreich  <br/> |Die Gesamtzahl der A/V-Konferenzen, die beigetreten sind.  <br/> |
   

