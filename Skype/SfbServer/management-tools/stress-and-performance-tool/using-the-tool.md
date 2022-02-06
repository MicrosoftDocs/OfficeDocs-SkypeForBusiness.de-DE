---
title: Verwenden des Tools Skype for Business Server 2015 Stress and Performance
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: 'Um das Skype for Business Server 2015 Stress and Performance Tool auszuführen, müssen Sie in der Lage sein, sowohl Benutzer, Kontakte als auch Benutzerprofile zu verwalten, das Tool für die Ausführung zu konfigurieren und dann die Ausgabe oder Ergebnisse zu überprüfen, die vom Tool erstellt werden.'
---

# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Verwenden des Tools Skype for Business Server 2015 Stress and Performance
 
Um das Skype for Business Server 2015 Stress and Performance Tool auszuführen, müssen Sie in der Lage sein, sowohl Benutzer, Kontakte als auch Benutzerprofile zu verwalten, das Tool für die Ausführung zu konfigurieren und dann die Ausgabe oder Ergebnisse zu überprüfen, die vom Tool erstellt werden.
  
Es gibt vier Bereiche, in denen das Skype for Business Server 2015 Stress and Performance Tool ausgeführt wird (die ausführbare Datei ist LyncPerfTool.exe):
  
- [Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Konfigurieren des Benutzerprofils](using-the-tool.md#BKMK_UserProfile)
    
- [Ausführen von LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretieren der Ergebnisse](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Erstellen von Benutzern und Kontakten
<a name="BKMK_CreateUsersAndContacts"> </a>

Sie müssen das Benutzerbereitstellungstool Skype for Business Server 2015 (SB 2015) (UserProvisioningTool.exe) verwenden, um Benutzer und Kontakte für Ihre Stress- und Leistungstests zu erstellen.
  
Dies ist eine Liste hilfreicher Begriffe, die beim Lesen der Themen hilfreich sein können:
  
- **Organisationseinheit** – Die Organisationseinheit (Organizational Unit, OE) von Active Directory Domain Services (AD DS).
    
- **Verbund/Poolübergreifend** : Benutzer, die mit Benutzern aus anderen Chatdiensten kommunizieren können.
    
- **Verteilerlisten** – oder DLs. Dies sind Objekte in AD DS, die eine Liste von AD DS-Benutzern enthalten. Sie werden verwendet, um die Kommunikation zwischen Gruppen von Personen zu vereinfachen.
    
- **Standortinformationsdienst** – Der Skype for Business Server 2015-Dienst, der, wenn er pro Telefon aktiviert und konfiguriert ist, den Abruf des physischen Standorts für Erweiterte 911 -Dienste (E911) ermöglicht.
    
- **U.S. Telefon Numbers** – Telefon Nummern, die dem Benutzer zusätzlich zu dem SIP-URI zugewiesen sind, der für das Routing von eingehenden und ausgehenden Anrufen in der Reverse Number Lookup (RNL) verwendet wird.
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Erstellen von Benutzern und Kontakten mithilfe von UserProvisioningTool.exe

> [!NOTE]
> Bevor Sie überhaupt beginnen, stellen Sie sicher, dass Sie als Mitglied der Sicherheitsgruppe "Domänenadministratoren" angemeldet sind, um dieses Tool auszuführen. Sie müssen dies tun, da Sie Active Directory-Benutzer erstellen werden. 
  
Sie müssen das Skype for Business Server Benutzerbereitstellungstool verwenden, um Benutzer und Kontakte für die Lastsimulation zu erstellen.
  
Das **Skype for Business Server Benutzerbereitstellungstool** wird mit dem **Paket Skype for Business Server Stress and Performance Tool** installiert. Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool.msi) auf dem Front-End-Server oder dem Standard Edition Server ausgeführt wurde, den Sie testen möchten.
  
Sie können das Skype for Business Server Benutzerbereitstellungstool starten, indem Sie die Datei UserProvisioningTool.exe (unter %InstalledDirectory%LyncStressAndPerfTool\LyncStress) auf dem Front-End-Server oder auf dem Standard Edition-Server ausführen.
  
> [!IMPORTANT]
> Wenn Sie eine große Anzahl von Benutzern erstellen (z. B. 10.000 oder mehr), führen Sie die UserProvisioningTool.exe aus. Sie müssen dies tun, da das Tool  *neue*  AD-Benutzer erstellt und konfiguriert.
  
Wenn das Benutzerbereitstellungstool geöffnet wird, klicken Sie auf "Konfiguration", und wählen Sie die Ladekonfiguration aus. 
  
Laden Sie die im Paket enthaltene Standarddatei mit dem Namen "SampleData.xml", um mit dem Konfigurieren von Benutzern und Kontakten zu beginnen. Dadurch werden Felder vorab mit Beispieldaten aufgefüllt, die Sie ändern müssen, um sie für Ihre Bereitstellung relevant zu machen.
  
Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die ihre benutzerdefinierten Einstellungen bereits enthält, können Sie diese Datei stattdessen laden. Füllen Sie die Felder im Benutzerbereitstellungstool aus, wie in den folgenden Abschnitten beschrieben.
  
### <a name="to-configure-server-options"></a>So konfigurieren Sie Serveroptionen:

1. Geben Sie im **FQDN-Feld des Front-End-Pools** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition Servers oder den Front-End-Pool ein, in dem Sie die Benutzer hosten möchten.
    
2. Geben Sie im Feld **"Präfix des Benutzernamens** " ein Präfix ein, das Sie verwenden möchten, um Ihre Benutzernamen zu Testzwecken zu kürzen (z. B. "TestUser").
    
3. Geben Sie im Feld **"Kennwort"** ein Kennwort ein, das für alle Testbenutzerkonten verwendet wird.
    
4. Geben Sie im Feld **"Kontodomäne** " den Domänennamen Ihrer aktuellen AD-Domäne ein (die Domäne, in der Sie Ihre Testbenutzer erstellen möchten).
    
5. Geben Sie im Feld **"Organisationseinheit** " den Namen der AD-Domäne ein, in der Sie diese Testbenutzer erstellen möchten. (Wenn die OE noch nicht vorhanden ist, wird sie für Sie erstellt).
    
6. Geben Sie im **Feld Telefon Vorwahl** die dreistellige Vorwahl ein, die für alle Testbenutzerkonten verwendet werden soll. Stellen Sie sicher, dass die von Ihnen gewählte Vorwahl nicht mit den Vorwahlen anderer Benutzer in AD in Konflikt gerät.
    
7. Aktivieren Sie das Kontrollkästchen "**Sprach aktiviert**", wenn Sie die Testbenutzer für Enterprise-VoIP aktivieren möchten.
    
8. Geben Sie im Feld **"Anzahl der Benutzer"** die Gesamtzahl der Testbenutzer an, die Sie erstellen möchten.
    
9. Geben Sie im **Feld Startindex** die Startnummer an, die als Suffix für das Präfix des Benutzernamens verwendet wird (z. B. lautet das Präfix "TestUser", und der Vorname endet im folgenden Beispiel mit "0".)
    
     ![Benutzerbereitstellungstool mit der Registerkarte "Benutzererstellung".](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Schaltfläche "Benutzer erstellen"

Wenn Sie auf die Schaltfläche " **Benutzer erstellen** " klicken, werden die eingegebenen Eingabeparameter überprüft. Wenn Validierungsfehler auftreten, werden Sie aufgefordert, diese zu beheben. Wenn alle Werte korrekt sind, werden benutzer in AD angezeigt (unabhängig davon, welche OU Sie angegeben haben). Während der Ausführung des Tools wird am unteren Rand des Tools eine Statusanzeige angezeigt. Schließen Sie die Anwendung nicht, während die Statusanzeige aktiv ist.
  
Die Erstellung des Benutzers nimmt Zeit in Anspruch. Planen Sie daher bitte entsprechend. Dieser Vorgang kann zwischen mehreren Minuten für einige Benutzer und ein paar Stunden für eine große Anzahl von Benutzern dauern.
  
Wenn Sie in Ihrer Testumgebung keinen Zugriff auf den AD-Domänencontroller haben, können Sie dennoch die Benutzererstellung überprüfen, indem Sie sich als einer der Benutzer im Bereich der Benutzer anmelden, die Sie erstellt haben. Denken Sie daran, das Präfix und das Suffix zusammen mit dem @sipDomain als Benutzernamen zu verwenden. Hier ist ein Beispiel:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Wenn die Benutzer bereits vorhanden sind, werden sie durch Klicken auf die Schaltfläche "Benutzer erstellen" mit konfigurationsänderungen aktualisiert. 
  
#### <a name="delete-users-button"></a>Schaltfläche "Benutzer löschen"

Wenn Sie auf die Schaltfläche " **Benutzer löschen** " klicken, werden die Eingabeparameter der Registerkarte überprüft. Wenn Überprüfungsfehler auftreten, werden Sie aufgefordert, diese zu beheben. Wenn die Eingabewerte korrekt sind, werden die angegebenen Testbenutzer deaktiviert und aus Active Directory gelöscht. Auch hier wird unten auf dieser Registerkarte eine Statusanzeige angezeigt, und Sie sollten die Anwendung nicht schließen, während die Statusleiste aktiv ist.
  
> [!NOTE]
> Es werden nur US-formatierte Telefonnummern unterstützt. Telefon Nummern werden benutzern immer zugewiesen, und alle von UserProvisioningTool.exe erstellten Benutzer sind standardmäßig für Enterprise-VoIP aktiviert. Alle Szenarien, in denen die Telefonnummer verwendet wird, z. B. automatische Konferenztelefonzentralen oder UC-PSTN-Anrufe, verwenden diese Telefonnummer, um Anrufe ordnungsgemäß weiterzuleiten. Aus diesem Grund muss  *jeder Benutzer*  über eine *eindeutige Telefonnummer verfügen*  .
  
> [!NOTE]
> **Wenn Sie Benutzer zweimal erstellen müssen, schlägt der Befehl fehl, es sei denn, Sie verwenden eine andere Vorwahl oder wenn die vorherigen Benutzer mithilfe des Cmdlets Disable-CsUser deaktiviert wurden.**
  
> [!IMPORTANT]
> Bevor Sie Kontakte erstellen, müssen Sie zunächst die Benutzerreplikation abschließen (dies erfolgt über die Registerkarte "Benutzer"). 
  
> [!IMPORTANT]
> Wenn Sie ihre Benutzer gerade erstellt haben, müssen Sie warten, bis Skype for Business Server Replikation abgeschlossen ist, und die Benutzerkonten in der Datenbank auffüllen. **Wenn die Replikation der Benutzer noch nicht abgeschlossen ist, wird ein Fehler angezeigt.** Sie wissen, wann Benutzer die Replikation abgeschlossen haben, wenn der Skype for Business Server 2015-Front-End-Dienst gestartet wurde, oder indem Sie das Cmdlet Get-CsUser auf dem letzten Benutzer der Gesamtzahl, die Sie angegeben haben, erfolgreich ausführen.
  
#### <a name="contacts-creation-tab"></a>Registerkarte "Kontakteerstellung"

Auf dieser Registerkarte können Sie die Kontaktdetails der Benutzer für Ihre Tests bereitstellen.
  
![Benutzerbereitstellungstool mit der Registerkarte "Inhaltserstellung".](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Gehen Sie folgendermaßen vor, um die Kontakte der Benutzer zu konfigurieren:

1. Geben Sie im Feld **"Durchschnittliche Kontakte pro Benutzer** " die durchschnittliche Anzahl von Kontakten ein, die in Kontaktlisten für jeden Benutzer aufgefüllt werden sollen.
    
2. Aktivieren Sie das Kontrollkästchen **Fixiert** , wenn Sie für jeden Benutzer eine gleiche Anzahl von Kontakten erstellen möchten. Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, deaktivieren Sie dieses Kontrollkästchen.
    
3. Geben Sie im Feld **"Durchschnittliche Kontaktgruppen pro Benutzer** " die Anzahl der Kontaktgruppen pro Benutzer ein. Diese Zahl muss kleiner als **die durchschnittlichen Kontakte pro Benutzer** sein.
    
4. Geben Sie im **Prozentfeld "Partnerkontakte/Poolübergreifende Kontakte"** eine Zahl zwischen 0 und 100 an. Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.
    
5. Geben Sie im **Benutzerpräfixfeld "Partnerverbund/Poolübergreifender Pool** " den Benutzernamen für Verbundbenutzer an, der den Kontaktlisten lokaler Benutzer hinzugefügt wird.
    
6. Geben Sie im Feld " **Sip-Domäne für Partnerbenutzer/Poolübergreifende Benutzer** " den SIP-Domänennamen der Verbundbenutzer an.
    
7. Stellen Sie auf der Registerkarte " **Benutzererstellung** " sicher, dass die Informationen korrekt sind. Ihre Kontakte werden anhand von Werten auf der Registerkarte "Benutzererstellung" erstellt.
    
8. Klicken Sie auf **Kontakte erstellen** , um mit der Erstellung des Kontakts zu beginnen. Dieser Vorgang kann mehrere Minuten dauern. Nach Abschluss dieses Vorgangs wird ein Dialogfeld mit der Meldung "Vorgang wurde erfolgreich abgeschlossen" angezeigt. Sie können die erstellten Kontakte überprüfen, indem Sie sich als Benutzer anmelden, der über die Registerkarte "Benutzererstellung" erstellt wurde.
    
    > [!NOTE]
    > Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Zielpool neu. Es kann länger (bis zu 2 Stunden) dauern, bis die Front-End-Server gestartet werden, je nachdem, wie viele Kontakte durch diesen Vorgang erstellt wurden. 
  
#### <a name="distribution-list"></a>Verteilerliste

Das Tool Skype for Business Server 2015 Stress and Performance kann das Verteilerlistenerweiterungsfeature (Distribution List, DL) im Skype for Business 2015-Client simulieren. Sie können diesen Schritt überspringen, wenn Sie nicht beabsichtigen, die DL-Erweiterung im Benutzerbereitstellungstool zu aktivieren.
  
![Benutzerbereitstellungstool mit der Registerkarte "Erstellung von Verteilerlisten".](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
Auf der Registerkarte "Verteilerliste" können Sie DLs erstellen, die das Stress and Performance Tool für das Feature "Verteilerlistenerweiterung" verwendet. Vor dem Erstellen von DLs muss Skype for Business Server 2015 bereitgestellt werden, einschließlich der Ausführung von ForestPrep. Wenn dies nicht erfolgt, sind die DL-Attribute nicht im AD-Schema vorhanden, sodass das Tool keine DLs erstellen kann.
  
### <a name="to-configure-distribution-lists"></a>So konfigurieren Sie Verteilerlisten:

1. In the **Number of Distribution Lists** field, give the total number of DLs you want to create (The recommendation here is that you start with a value that is double the number of users you have.).
    
2. Geben Sie in das Feld **Verteilerlistenpräfix** ein Präfix ein, das alle erstellten DLs aufweisen, z. B. *testDL*  . Das bedeutet, dass Ihre DL-Namen bei 100 DLs wie folgt aussehen: testDL0, testDL1, bis testDL99.
    
3. In the **Minimum Members in a Dist. List** field, enter the minimum number of users to put in each DL.
    
4. In the **Maximum Members in a Dist. List** field, enter the maximum number of users to add in each DL.
    
#### <a name="create-distribution-lists-button"></a>Schaltfläche "Verteilerlisten erstellen"

Wenn Sie auf die Schaltfläche "Verteilerlisten erstellen" klicken, fragt das Tool Active Directory ab, um festzustellen, ob Verteilerlisten vorhanden sind, die mit dem Präfix und den Nummern übereinstimmen. Das Tool erstellt alle DLs, die noch nicht vorhanden sind. Wenn Mitglieder zu diesen neu erstellten Verteilerlisten hinzugefügt werden, werden die Benutzer aus dem Bereich ausgewählt, der auf der Registerkarte "Benutzererstellung" angegeben ist.
  
#### <a name="location-info-service-config-tab"></a>Registerkarte "Location Info Service Config"

Das Skype for Business Server 2015 Stress and Performance Tool kann auch Pseudokonfigurationsdateien für den Standortinformationsdienst generieren. Beachten Sie, dass der Standortinformationsdienst in der Regel keine signifikanten Auswirkungen auf die Leistung auf den Servern hat. 
  
![Benutzerbereitstellungstool mit der Registerkarte "Location Info Service Config".](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Wenn Sie dieses Feature testen möchten, füllen Sie die Werte im Formular aus, und klicken Sie auf die Schaltfläche "LIS-Konfigurationsdateien generieren", die .CSV aufgerufenen Dateien erstellt:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Verwenden Sie die folgenden PowerShell-Cmdlets, um diese Dateien in die LIS-Datenbank zu importieren:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Konfigurieren des Benutzerprofils
<a name="BKMK_UserProfile"> </a>

Nachdem Ihre Benutzer erstellt wurden (über das Benutzererstellungstool), können Sie Benutzerprofile mit dem Skype for Business Server 2015 Load Configuration Tool (UserProfileGenerator.exe) konfigurieren.
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ausführen des Tools für die Skype for Business Server 2015-Lastkonfiguration

Starten Sie das Tool "Ladekonfiguration" (UserProfileGenerator.exe), und füllen Sie die Registerkarten aus. Dieses Tool erstellt ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen ihrer Simulationen benötigen. Jedes Clientverzeichnis enthält ein Skript zum Starten des Tools Skype for Business Server 2015 Stress and Performance (LyncPerfTool.exe). In den folgenden Abschnitten finden Sie Beispiele für das Ausfüllen der Felder auf den einzelnen Registerkarten des Tools Skype for Business Server 2015 Load Configuration.
  
> [!IMPORTANT]
> Die im Tool "Lastenkonfiguration" (UserProfileGenerator.exe) verwendeten benutzerspezifischen Werte müssen mit den Im Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) für den Pool angegebenen Werten übereinstimmen. 
  
#### <a name="common-configuration-tab"></a>Registerkarte "Allgemeine Konfiguration"

Die Registerkarte **"Allgemeine Konfiguration** " des Ladekonfigurationstools wird unten angezeigt. Füllen Sie die Felder der Registerkarte "Allgemeine Konfiguration" aus, wie in den folgenden Schritten beschrieben.
  
![Die Registerkarte "Benutzerbereitstellung" mit der Registerkarte "Allgemeine Konfiguration".](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Geben Sie im Feld **"Anzahl der verfügbaren Computer** " die Anzahl der Computer ein, die Sie zum Ausführen des Stress and Performance-Tools (LyncPerfTool.exe) verwenden möchten. Es wird empfohlen, dass Sie einen Computer für alle 4500 Benutzer haben, die Sie simulieren möchten. Diese Anzahl kann jedoch variieren, wenn Sie die Ladestufe reduzieren oder nur eine Teilmenge der verfügbaren Features des Tools verwenden (Ladestufen werden auf der Registerkarte "Allgemeine Szenarien" festgelegt).
    
2. Geben Sie im Feld **"Präfix für Benutzernamen** " ein Präfix für das Benutzernamenfeld aller Benutzer ein. Zum Anmelden des Uniform Resource Identifier (URI) wird: *UserPrefix[User Start Index... (Anzahl der Benutzer-1)] @User Domäne*  , z. B. myUser009@Contoso.com.
    
3. Geben Sie im Feld **"Kennwort für alle Benutzer"** das Kennwort ein, das bei der Erstellung der Benutzer verwendet wurde. Wenn Sie dieses Feld leer lassen, wird der Benutzername als Kennwort festgelegt.
    
4. Geben Sie im Feld **"Benutzeranfangsindex** " den Index des ersten zu konfigurierenden Benutzers ein. Sie können unterschiedliche Bereiche für unterschiedliche Arten oder Laststufen konfigurieren, aber Sie müssen das Lastkonfigurationstool (UserProfileGenerator.exe) einmal pro bereich ausführen, den Sie konfigurieren möchten.
    
5. Geben Sie im Feld **"Anzahl der Benutzer"** die Gesamtzahl der Benutzer ein, die Sie konfigurieren möchten.
    
6. Geben Sie im Feld " **Benutzerdomäne** " die für den SIP-URI verwendete Domäne ein. Dies wird verwendet, um den SIP-URI jedes Benutzers zu erstellen, um sich beim Skype for Business Server 2015 Front-End-Server oder Standard Edition-Server anzumelden, und unterscheidet sich möglicherweise von der Kontodomäne.
    
7. Geben Sie im Feld **"Kontodomäne** " die AD DS-Domänenanmeldung ein.
    
8. Geben Sie im Feld **MPOP Percentage** (Multiple Point of Presence Percentage) einen Wert für den Prozentsatz der Benutzer an, die von mehreren Computern oder Geräten angemeldet sind, z. B. 10 %.
    
9. Geben Sie die maximale Anzahl gleichzeitiger Endpunkte in das Feld **"Pro Sekunde (pro Instanz) anmelden"** ein. Dies ist die maximale Anzahl von Anmeldungen für Ihre Benutzer, und die Empfehlung ist eine Rate von weniger als/gleich 2 pro Sekunde (<=2).
    
10. Geben Sie im Feld **"Zugriffsproxy" oder "Pool-FQDN** " den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen sollen. Wenn sich die Benutzer extern anmelden, müssen Sie den Zugriffsproxy eingeben. Wenn die Benutzer intern sind, geben Sie den FQDN ihres Enterprise Pools oder Standard Edition Servers an.
    
11. Geben Sie im **Feld "Port** " den Port ein, den Benutzer für SIP verwenden sollen (hier ist der Standardwert 5061).
    
12. Geben Sie für das Feld **"Externer Netzwerkserver Einstellungen**" den FQDN des Zugriffsproxys oder Pools und erneut den **Port an**. Diese Einstellungen werden nur für die Lastsimulation externer Endpunkte verwendet.
    
#### <a name="general-scenarios-tab"></a>Registerkarte "Allgemeine Szenarien"

![Lastkonfigurationstool mit der Registerkarte "Allgemeine Szenarien".](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Sie können die Ladestufen und Parameter für die einzelnen allgemeinen Szenarien konfigurieren, indem Sie bestimmen, was Ausgeführt oder deaktiviert werden soll. Hier sind Ihre allgemeinen Optionen:
  
> [!NOTE]
> Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**. Wenn Sie eine Einstellung auswählen, die jedoch deaktiviert ist, werden Konfigurationen für jeden Client generiert. Hohe Ergebnisse in der maximalen unterstützten Auslastung auf dem Server; Mittel ist 60 % der hohen Last; niedrig ist 30 %. 
  
- **Chat –** Dazu gehören Peer-to-Peer und Konferenzen. wählen Sie den entsprechenden Wert für die Ladestufe aus.
    
- **Audiokonferenzen –** Wählen Sie eine Ladestufe *nur*  für Audiokonferenzen aus. Peer-to-Peer-Anrufe werden etwas später im Abschnitt " **VoIP-Szenarien"** behandelt. Öffnen Sie die Registerkarte **"Erweitert** ", um MultiView zu aktivieren.
    
- **Anwendungsfreigabe –** Wählen Sie eine Ladestufe für die Anwendungsfreigabe aus.
    
- **Datenzusammenarbeit –** Wählen Sie eine Ladestufe für die Datenzusammenarbeit aus, einschließlich Datenkonferenzen.
    
- **Verteilerlistenerweiterung –** Klicken Sie auf die Schaltfläche **"Erweitert",** und füllen Sie das Feld mit den gleichen Werten aus, die auf der Registerkarte "DL" des Benutzererstellungstools (UserProvisioningTool.exe) konfiguriert sind. Wählen Sie eine Ladestufe aus.
    
- **Adressbuch-Webabfrage –** Dies ist der Adressbuch-Nachschlagedienst anstelle des Adressbuchdateidownloads. Wenn Sie dies für Adressbuchdateidownloads aktivieren möchten, klicken Sie auf die Schaltfläche **"Erweitert** ", und legen **Sie "EnableABSDownload** " auf "True" fest. Geben Sie einen Wert für die Ladestufe an.
    
- **Reaktionsgruppendienst –** Klicken Sie auf die Schaltfläche **"Erweitert",** und geben Sie die URIs der Reaktionsgruppen an, die Sie bereits erstellt haben, als Sie Reaktionsgruppendienst Agents bereitgestellt haben. Sie müssen mindestens eine Reaktionsgruppe auswählen. Um mehr zu verwenden, trennen Sie die Reaktionsgruppen durch Semikolons. Aktualisieren Sie **RGSUriSuffixStartIndex** und **RGSUriSuffixEndIndex** auf die tatsächlichen Werte. Wählen Sie eine Ladestufe aus.
    
- **Standortinformationsdienste –** Wählen Sie die Ladestufe "Aktiviert" oder "Deaktiviert" aus.
    
> [!NOTE]
> Jedes Szenario verfügt über eine Schaltfläche "Erweitert" und eine Reihe von Kontrollkästchen, die Variationen zur Standardeinstellung ermöglichen. 
  
- Die Auswahl von  *Ad-hoc*  ermöglicht es dem Tool, die Simulation von Konferenzen zu generieren, die während der Stunde erstellt werden.
    
- Wenn Sie  *"Große Conf*  " auswählen, wird ein Szenario für große Konferenzen simuliert.
    
-  *Extern*  weist das Tool an, auch externe Benutzer zu simulieren.
    
Diese Schaltflächen und Kontrollkästchen sind für jedes Szenario spezifische zusätzliche Werte und ändern das Verhalten des Stress- und Leistungstools und ermöglichen Anpassungen.
  
Wenn der Wert der Ladestufe **"Benutzerdefiniert**" ist, wird für jedes Szenario auf der Registerkarte "Allgemeine Szenarien" (mit Ausnahme von Standortinformationsdiensten) die Unterhaltungsrate mithilfe des entsprechenden Felds im Dialogfeld "Erweitert" berechnet. Der Feldname kann je nach Szenario unterschiedlich sein, aber die Feldbeschreibung gibt  *an: HINWEIS Diese Nummer wird nur verwendet, wenn "Benutzerdefiniert" im Dropdownmenü ausgewählt ist*  .
  
Die Werte **"Hoch**", " **Mittel**" und " **Niedrig**" ändern die Unterhaltungsraten pro Modalität entsprechend dem Benutzermodell, das eine Balance aller Szenarien darstellt. Wenn die Ladestufe pro Modalität aufgrund eines Unterschieds bei der erwarteten Nutzung geändert werden muss, verwenden Sie eine benutzerdefinierte Unterhaltungsrate.
  
#### <a name="voice-scenarios-tab"></a>Registerkarte "VoIP-Szenarien"

Dies ist die Registerkarte für die Konfiguration aller VoIP-bezogenen Szenarien.
  
![Registerkarte "VoIP-Szenarien für das Ladekonfigurationstool".](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Folgende Optionen sind verfügbar:
  
- **VoIP –** Klicken Sie auf die Schaltfläche **"Erweitert",** und fügen Sie Werte für die Felder PhoneAreaCode und LocationProfile (Wählplan) hinzu. Sie geben auch einen Wert für die Ladestufe an. Wenn Sie eine Ladestufe für VoIP oder UC/PSTN-Gateway auswählen, wird eine Konfigurationsdatei für pstn-telefonbasierte Telefonverbindungen (Public Switched Telephone Network, PSTN) zu Unified Communications (UC) generiert, um externe Anrufe zu simulieren.
    
- **UC/PSTN-Gateway –** Sie müssen einen Load Level-Wert auswählen, und wenn Sie etwas anderes als "Deaktiviert" auswählen, müssen Sie auch einen Wert für die PSTN-Vorwahl angeben, indem Sie auf die Schaltfläche **"Erweitert** " klicken. Klicken Sie unter dem Vermittlungsserver und pstn auf **"Hinzufügen** ". Stellen Sie sicher, dass Sie eine Route für die Vorwahl konfiguriert haben.
    
    > [!TIP]
    > Sie können entweder die Skype for Business Systemsteuerung oder Skype for Business Verwaltungsshell verwenden, um die VoIP-Routenkonfiguration zu überprüfen. 
  
- **Konferenzzentrale –** Geben Sie einen Wert für die Ladestufe an. Any value other than Disabled will enable the **Telephone Number** field. Geben Sie die Telefonnummer der automatischen Telefonzentrale ein, die Sie verwenden möchten. Click **Advanced** and give a value for the **LocationProfile** field.
    
- **Service zum Parken von Anrufen –** Geben Sie hier eine Ladestufe an.
    
- **Vermittlungsserver und PSTN –** Jeder Vermittlungsserver, den Sie verwenden möchten, benötigt einen eigenen PSTN-Simulator. Nachdem Sie festgelegt haben, welchen Client Sie für den Simulator verwenden möchten, konfigurieren Sie Ihren Vermittlungsserver so, dass Anrufe an diesen Computer auf dem von Ihnen konfigurierten PSTN-Simulator weitergeleitet werden. Klicken Sie auf die Schaltfläche " **Hinzufügen** ", um einen Wert für den Vermittlungsserver zu konfigurieren.
    
    > [!NOTE]
    > Jedes Szenario verfügt über eine Schaltfläche "Erweitert", die sich daneben befindet. Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Einstellungen, die das Verhalten des Stress and Performance Tools ändern und anpassungsfähigen. > Für jedes Szenario auf der Registerkarte "VoIP-Szenarien" wird die Unterhaltungsrate mithilfe des entsprechenden Felds im Dialogfeld "Erweitert" berechnet, wenn der Wert der Ladestufe **"Benutzerdefiniert**" lautet. Der Feldname kann je nach Szenario unterschiedlich sein, aber die Feldbeschreibung gibt  *an: HINWEIS Diese Nummer wird nur verwendet, wenn "Benutzerdefiniert" im Dropdownmenü ausgewählt ist*  .
  
#### <a name="web-app-tab"></a>Registerkarte "Web-App"

![Tool zum Laden der Konfiguration, Registerkarte "Web-App".](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App unterstützt Konferenzszenarien über den Unified Communications Web API (UCWA)-Server, der auf einem Front-End-Server installiert ist. Verwenden Sie die Registerkarte "Web App", um alle Web-App-bezogenen Szenarien zu konfigurieren. Mögliche Optionen sind:
  
- **Allgemeine Web App-Einstellungen –** Klicken Sie auf die Schaltfläche **"Zusätzliche Einstellungen**", und legen Sie **reachTargetServerUrl** auf die virtuelle IP (VIP) des Verzeichnispools der VIP des Front-End-Pools fest.
    
- **Anwendungsfreigabe –** Wählen Sie einen Wert für Load Level aus.
    
- **Datenzusammenarbeit –** Wählen Sie einen Wert für Load Level aus.
    
- **Chat –** Wählen Sie einen Wert für Load Level aus.
    
- **VoIP-Konferenzen –** Wählen Sie einen Wert für Load Level aus.
    
> [!NOTE]
> Jedes Szenario verfügt über eine **Schaltfläche "Erweitert** ", die sich daneben befindet. Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Stress and Performance Tools ändern und anpassungsfähigen.> Für jedes Web App-Szenario wird der im **Feld ConversationsPerHour** angegebene Wert anstelle der Standardeinstellung verwendet, wenn die Ladestufe **"Benutzerdefiniert**" ist.
  
#### <a name="mobility-tab"></a>Registerkarte "Mobilität"

Verwenden Sie diese Registerkarte, um alle Mobilitätsszenarien zu konfigurieren.
  
![Registerkarte "Ladekonfigurationstool Mobilität".](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Die folgenden Optionen sind verfügbar:
  
- **Allgemeine Mobilität Einstellungen –** Klicken Sie auf **zusätzliche Einstellungen**, und legen Sie das Feld "UcwaTargetServerUrl" auf die virtuelle IP (VIP) des Directorpools oder die VIP des Front-End-Pools fest.
    
- **Anwesenheits- und P2P-Chat/Audio –** Wählen Sie einen Wert für "Ladestufe" aus, um die Mobilitätssimulation zu aktivieren.
    
> [!NOTE]
> Jedes Szenario verfügt über eine **Schaltfläche "Erweitert** ", die sich daneben befindet. Erweiterte Dialogfelder enthalten spezifische Werte für jedes Szenario, die das Verhalten des Stress- und Leistungstools ändern und anpassungsfähigen.> Für jedes Mobilitätsszenario wird der im **Feld ConversationsPerHour** angegebene Wert anstelle der Standardeinstellung verwendet, wenn die Ladestufe **"Benutzerdefiniert**" ist.
  
#### <a name="summary-tab"></a>Registerkarte "Zusammenfassung"

Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen.
  
![Registerkarte "Zusammenfassung des Ladekonfigurationstools".](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen. 
  
Sie können Benutzernummernbereiche manuell konfigurieren, indem Sie das Kontrollkästchen **"Benutzerdefinierte Benutzerbereichsgenerierung aktivieren** " aktivieren und dann in der Tabelle mit dem Benutzerbereich, den Sie anpassen möchten, auf das Szenario doppelklicken.
  
Überprüfen Sie **(RunClient.bat) beim Starten die Anmeldeverzögerung** , um Verzögerungen in den generierten Batchdateien einzuschließen, damit sie der Anmelderate entsprechen. Dies ist hilfreich, um zu verhindern, dass serverüberlastet wird, wenn eine große Anzahl von Benutzern angemeldet wird.
  
Klicken Sie auf **"Dateien generieren** ", und wählen Sie den Ordner aus, in dem Sie die Konfiguration generieren möchten. Wenn Ihre Dateien erfolgreich erstellt wurden, wird ein Dialogfeld angezeigt.
  
![Das Meldungsfeld "Erfolgreich generierte Konfigurationsdateien laden". Klicken Sie einfach auf "OK".](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ausführen von LyncPerfTool
<a name="BKMK_RunTool"> </a>

Sie müssen Benutzer, Kontakte und Szenarien erstellen, bevor Sie das Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) ausführen. Ausführliche Informationen zur Verwendung der Tools zum Ausführen dieser Aktionen finden Sie unter ["Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts) " und ["Konfigurieren von Benutzerprofilen](using-the-tool.md#BKMK_UserProfile) " weiter oben in diesem Artikel. Beim Ausführen dieser Tools wird auch eine Datei generiert, die mit dem Stress and Performance-Tool als Teil einer Batchdatei mit den erforderlichen Parametern ausgeführt wird.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ausführen des Tools Skype for Business Server 2015 Stress and Performance

Das Tool "Lastenkonfiguration" (UserProfileGenerator.exe) erstellt eine Batchdatei, mit der Sie das Stress and Performance-Tool (LyncPerfTool.exe) ausführen können, indem Sie Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden. Die Batchdatei führt eine Instanz von LyncPerfTool.exe pro Konfigurationsdatei aus. Gehen Sie folgendermaßen vor, um die Batchdatei auszuführen:
  
### <a name="run-the-stress-and-performance-test"></a>Ausführen des Belastungs- und Leistungstests

1. Kopieren Sie den Ordner mit den Konfigurationsordnern und Dateien in das Verzeichnis, in dem LyncPerfTool.exe auf jedem Clientcomputer vorhanden ist. (Wenn Sie beispielsweise die Konfigurationsdateien im Ordner 1.28_13.16.16 generiert haben, kopieren Sie diesen Ordner in den Ordner mit LyncPerfTool.exe darin. Führen Sie dies auf jedem Client aus.)
    
2. Navigieren Sie zum Clientordner, und führen **Sie das RunClient-Batchskript** aus. Sie können im Windows Explorer auf die Batchdatei doppelklicken und alle Konfigurationsdateien für diesen Client ausführen. Sie können das Skript auch in einem Clientordner ausführen, indem Sie die folgende Syntax verwenden:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Um das Stress and Performance-Tool direkt auszuführen, öffnen Sie eine Eingabeaufforderung, und geben Sie den folgenden Befehl an der Befehlszeile ein (und achten Sie bei der ersten Ausführung darauf, die Leistungsindikatoren  `regsvr32 /i /n /s LyncPerfToolPerf.dll`zu registrieren, wie in der Notiz weiter unten in diesem Thema dargestellt):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Damit das Tool die Werte in der Konfigurationsdatei anzeigt, fügen Sie den  `/displayfile` Parameter in den vorherigen Befehl ein, damit er wie folgt aussieht:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Drücken Sie STRG+C, um den Vorgang zu  *beenden*  .
  
> [!NOTE]
> Bevor Sie das Tool Stress and Performance direkt ausführen, müssen Sie die Leistungsindikatoren über den folgenden Befehl registrieren:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Jede Instanz des Stress and Performance-Tools, das Sie starten, beginnt sofort mit der Anmeldung von Benutzern, in der Regel mit einer Rate von einem Benutzer pro Sekunde. 
  
Die spitzen Benutzeranmeldungsrate für den Pool beträgt ca. 12 pro Sekunde. Dies bedeutet, dass Sie nicht mehr als 12 LyncPerfTool.exe Instanzen gleichzeitig starten sollten, während sich benutzer noch anmelden. 1.000 Benutzer benötigen ca. 20 Minuten, um sich bei einer pro Sekunde vollständig anzumelden.
  
## <a name="interpreting-the-results"></a>Interpretieren der Ergebnisse
<a name="BKMK_Interpret"> </a>

Das Skype for Business Server 2015 Stress and Performance Tool verfügt über viele Leistungsindikatoren, die Ihnen helfen zu verstehen, was der Client macht und ob Probleme auftreten.
  
### <a name="client-counters"></a>Clientzähler

Jede Instanz von LyncPerfTool.exe ausgeführt wird, verfügt über eine separate Instanz der Leistungsindikatoren. Jede Instanz wird anhand ihrer Prozess-ID benannt. Wenn Clients überlastet sind, können andere Probleme auftreten. So verhindern Sie diese Probleme:
  
- Überwachen sie die CPU- und Speicherauslastung auf den Clientcomputern. Wenn die CPU konsistent über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.
    
- Wenn der Speicherbedarf hoch ist, treten möglicherweise Probleme auf, wenn die Seitendatei nicht mehr genügend Speicherplatz hat. Stellen Sie sicher, dass der Commit-Betrag nicht den Grenzwert auf dem Computer erreicht. Wenn Speicherbeschränkungen gelten, sollten Sie die Größe der Seitendatei erhöhen oder die Anzahl der Benutzer verringern.
    
Hier ist eine Liste der wichtigsten Leistungsindikatoren:
  
**Allgemeine Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|In Minuten aufgewendete Zeit  <br/> |Zeit, die seit dem Starten des Prozesses aufgewendet wurde.  <br/> |
|Aktive Endpunkte  <br/> |Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.  <br/> |
|Fehlgeschlagene Anmeldungen  <br/> |Gesamtzahl der Endpunkt-Anmeldefehler.  <br/> |
|Anmeldeversuche  <br/> |Gesamtzahl der Endpunkt-Anmeldeversuche.  <br/> |
|Getrennte Endpunkte  <br/> |Gesamtzahl der Endpunkte, die getrennt wurden.  <br/> |
   
**Anwesenheitsinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|SetPresence-Aufrufe  <br/> |Gesamtzahl der Anwesenheitsänderungsversuche. Informationen zu verschiedenen Arten von Anwesenheitsänderungen finden Sie unter "SetPresence (Presence Type) Calls Performance Counter".  <br/> |
|NNN-Antworten für SetPresence  <br/> |Gesamtzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|GetPresence-Anrufe  <br/> |Gesamtzahl der Versuche, Anwesenheitsanfragen abzurufen.  <br/> |
|NNN-Antworten für GetPresence  <br/> |Gesamtzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
   
**Adressbuchdienstinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|ABS Full/Delta-Dateidownloads versucht  <br/> |Gesamtanzahl der versuchten vollständigen oder Delta-Dateidownloadanforderungen.  <br/> |
|ABS Full/Delta-Dateidownloads erfolgreich  <br/> |Gesamtanzahl der versuchten vollständigen oder Delta-Dateidownloadanforderungen.  <br/> |
|Mit dem Adressbuchwebabfragedienst zusammenhängende Leistungsindikatoren  <br/> |Adressbuchdatei-Download-bezogene Leistungsindikatoren.  <br/> |
|Abs WS Calls attempted  <br/> |Gesamtanzahl der versuchten Webdienstanforderungen für Adressbuchabfragen.  <br/> |
|ABS-WS-Aufrufe erfolgreich  <br/> |Gesamtanzahl der Webdienstanforderungen des Adressbuchwebs, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|ABS-WS-Aufrufe fehlgeschlagen  <br/> |Gesamtanzahl der Webdienstanforderungen des Adressbuchwebs, die einen Fehlerantwortcode zurückgegeben haben.  <br/> |
   
> [!NOTE]
> Diese Kategorie enthält Indikatoren, die zum Überwachen von ABS-Dateidownloads (Address Book Service) und Webdienstanforderungen für Adressbuch verwendet werden. 
  
**Verteilerlisteninformationen (DL)**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Versuchte Anrufe  <br/> |Gesamtzahl der versuchten DLX-Webdienstanforderungen (Distribution List Expansion).  <br/> |
|Erfolgreiche Aufrufe  <br/> |Gesamtzahl der DLX-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|Anrufe fehlgeschlagen  <br/> |Gesamtzahl der DLX-Webdienstanforderungen, die einen Fehlerantwortcode zurückgegeben haben.  <br/> |
   

  
> [!NOTE]
> Die unten aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Anrufe an den Vermittlungsserver, den A/V-Konferenzserver, den Edgeserver, die Reaktionsgruppenanwendung und die automatische Konferenzzentrale, wenn diese Szenarien aktiviert sind. 
  
**VoIP-Basisinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der derzeit laufenden eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Beendete Anrufe  <br/> |Gesamtzahl der bereits beendeten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Abgelehnte Anrufe  <br/> |Gesamtzahl der abgelehnten eingehenden Sprachanrufe.  <br/> |
|Es wurde versucht, eingehende/ausgehende Anrufe zu tätigen.  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Eingerichtete eingehende/ausgehende Anrufe  <br/> |Gesamtzahl der eingerichteten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Empfangene Anrufe NNN  <br/> |Gesamtzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|VoIP-Passrate (%)  <br/> |Gesamtzahl der eingerichteten Anrufe/Gesamtzahl der versuchten Anrufe.  <br/> |
   
**Anrufinformationen des Reaktionsgruppendiensts**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der aktiven Anrufe an die Reaktionsgruppenanwendung.  <br/> |
|Versuchte Anrufe  <br/> |Gesamtzahl der versuchten Anrufe.  <br/> |
   
**Chatanrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der laufenden eingehenden/ausgehenden Chatanrufe.  <br/> |
|Beendete Anrufe  <br/> |Die Gesamtzahl der eingehenden/ausgehenden Chatanrufe, die bereits beendet wurden.  <br/> |
|Empfangene Anrufe NNN  <br/> |Gesamtzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|Empfangene/gesendete Chatnachrichten  <br/> |Gesamtanzahl der empfangenen oder gesendeten Nachrichten für alle Sitzungen.  <br/> |
|Es wurde versucht, eingehende/ausgehende Anrufe zu tätigen.  <br/> |Gesamtzahl der versuchten eingehenden/ausgehenden Chatanrufe.  <br/> |
|Eingerichtete eingehende/ausgehende Anrufe  <br/> |Gesamtzahl der eingehenden/ausgehenden Chatanrufe, die eingerichtet wurden.  <br/> |
   
**Anrufinformationen zur App-Freigabe**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Beendete Anrufe  <br/> |Gesamtanzahl der bereits beendeten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Empfangene Anrufe NNN  <br/> |Gesamtzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|Es wurde versucht, eingehende/ausgehende Anrufe zu tätigen.  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Eingerichtete eingehende/ausgehende Anrufe  <br/> |Gesamtzahl der eingerichteten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
   
**CAA-Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der derzeit laufenden eingehenden/ausgehenden PsTN-Anrufe (Public Switched Telephone Network).  <br/> |
|Beendete Anrufe  <br/> |Gesamtanzahl der eingehenden/ausgehenden PSTN-Anrufe, die bereits beendet wurden.  <br/> |
|Es wurde versucht, eingehende/ausgehende Anrufe zu tätigen.  <br/> |Gesamtzahl der versuchten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
|Eingerichtete eingehende/ausgehende Anrufe  <br/> |Gesamtzahl der eingerichteten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
   
**Konferenzinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Chatkonferenzen  <br/> |Gesamtzahl der laufenden Chatkonferenzen.  <br/> |
|Aktive Audio-/Videokonferenzen  <br/> |Gesamtzahl der laufenden Audio-/Videokonferenzen (A/V).  <br/> |
|Aktive Konferenzen für die Anwendungsfreigabe  <br/> |Gesamtzahl der laufenden Konferenzen zur Anwendungsfreigabe.  <br/> |
|Anzahl der Teilnehmer  <br/> |Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.  <br/> |
|Konferenzplanfehler  <br/> |Gesamtanzahl der Fehler beim Planen einer Konferenz.  <br/> |
|Teilnahme an Konferenzfehler  <br/> |Gesamtanzahl der Fehler beim Versuch, eine Verbindung mit einer Konferenz herzustellen.  <br/> |
   
**UCWA-Clientzähler**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Gesamtzahl der erfolgreichen IMMCU-Verknüpfungen  <br/> |Gesamtzahl der Chatkonferenzen, die beigetreten sind.  <br/> |
|Gesamtzahl der erfolgreichen DMCU-Verknüpfungen  <br/> |Gesamtzahl der beigetretenen A/V-Konferenzen.  <br/> |
   

