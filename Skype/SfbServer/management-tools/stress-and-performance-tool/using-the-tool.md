---
title: Verwenden des Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
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
description: Um das Skype for Business Server 2015-Tool für Stress und Leistung ausführen zu können, müssen Sie sowohl Benutzer, Kontakte als auch Benutzerprofile verwalten, das Tool für die Ausführung konfigurieren und dann die Ausgabe oder ergebnisse überprüfen können, die vom Tool erstellt werden.
ms.openlocfilehash: 300da4109ddbdbf06f6dcfbe241cc45c83ec82ca
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675727"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Verwenden des Skype for Business Server 2015 Stress and Performance Tool
 
Um das Skype for Business Server 2015-Tool für Stress und Leistung ausführen zu können, müssen Sie sowohl Benutzer, Kontakte als auch Benutzerprofile verwalten, das Tool für die Ausführung konfigurieren und dann die Ausgabe oder ergebnisse überprüfen können, die vom Tool erstellt werden.
  
Es gibt vier Bereiche, in denen das Skype for Business Server 2015 Stress and Performance Tool ausgeführt wird (die ausführbare Datei ist LyncPerfTool.exe):
  
- [Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Benutzerprofil konfigurieren](using-the-tool.md#BKMK_UserProfile)
    
- [Ausführen von LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretieren der Ergebnisse](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Erstellen von Benutzern und Kontakten
<a name="BKMK_CreateUsersAndContacts"> </a>

Sie müssen das Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) verwenden, um Benutzer und Kontakte für Ihre Stress- und Leistungstests zu erstellen.
  
Dies ist eine Liste hilfreicher Begriffe, die beim Lesen der Themen hilfreich sein können:
  
- **Organisationseinheit** – Die Active Directory Domain Services (AD DS) Organisationseinheit (OU).
    
- **Verbund/Poolübergreifender Pool** – Benutzer, die mit Benutzern aus anderen Chatdiensten kommunizieren können.
    
- **Verteilerlisten** – oder DLs. Dies sind Objekte in AD DS, die eine Liste von AD DS-Benutzern enthalten. Sie werden verwendet, um die Kommunikation über Gruppen von Personen hinweg zu erleichtern.
    
- **Standortinformationsdienst** – Der Skype for Business Server 2015-Dienst, der, wenn er pro Telefon aktiviert und konfiguriert ist, das Abrufen des physischen Standorts für E911-Dienste (Enhanced 911) ermöglicht.
    
- **US-Telefon Nummern** – Telefon Nummern, die dem Benutzer zusätzlich zum SIP-URI zugewiesen sind, der für das Routing eingehender und ausgehender Anrufe in der Umgekehrten Nummernsuche (Reverse Number Lookup, RNL) verwendet wird.
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Erstellen von Benutzern und Kontakten mithilfe von UserProvisioningTool.exe

> [!NOTE]
> Bevor Sie überhaupt beginnen, stellen Sie sicher, dass Sie als Mitglied der Sicherheitsgruppe "Domänenadministratoren" angemeldet sind, um dieses Tool auszuführen. Sie müssen dies tun, da Sie Active Directory-Benutzer erstellen werden. 
  
Sie müssen das Skype for Business Server-Benutzerbereitstellungstool verwenden, um Benutzer und Kontakte für die Lastsimulation zu erstellen.
  
Das **Skype for Business Server-Benutzerbereitstellungstool** wird mit dem **Paket Skype for Business Server Stress and Performance Tool** installiert. Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool.msi) auf dem Front-End-Server oder Standard Edition Server ausgeführt wurde, den Sie testen möchten.
  
Sie können das Skype for Business Server-Benutzerbereitstellungstool starten, indem Sie die Datei UserProvisioningTool.exe (befindet sich unter %InstalledDirectory%LyncStressAndPerfTool\LyncStress) auf dem Front-End-Server oder auf dem Standard Edition Server ausführen.
  
> [!IMPORTANT]
> Wenn Sie eine große Anzahl von Benutzern erstellen (z. B. 10.000 oder mehr), führen Sie die UserProvisioningTool.exe aus. Sie müssen dies tun, da das Tool  *neue*  AD-Benutzer erstellt und konfiguriert.
  
Wenn das Benutzerbereitstellungstool geöffnet wird, klicken Sie auf "Konfiguration", und wählen Sie "Konfiguration laden" aus. 
  
Um mit der Konfiguration von Benutzern und Kontakten zu beginnen, laden Sie die im Paket enthaltene Standarddatei mit dem Namen "SampleData.xml". Dadurch werden Felder mit Beispieldaten vorab ausgefüllt, die Sie ändern müssen, um sie für Ihre Bereitstellung relevant zu machen.
  
Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die bereits Ihre angepassten Einstellungen enthält, können Sie diese Datei stattdessen laden. Füllen Sie die Felder im Benutzerbereitstellungstool aus, wie in den folgenden Abschnitten beschrieben.
  
### <a name="to-configure-server-options"></a>So konfigurieren Sie Serveroptionen:

1. Geben Sie im **FQDN-Feld des Front-End-Pools** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition Servers oder den Front-End-Pool ein, in dem Sie die Benutzer hosten möchten.
    
2. Geben Sie im Feld **"Benutzernamenpräfix** " ein Präfix ein, das Sie verwenden möchten, um Ihre Benutzernamen zu Testzwecken zu überschreiben (z. B. "TestUser").
    
3. Geben Sie im Feld **"Kennwort"** ein Kennwort ein, das für alle Testbenutzerkonten verwendet wird.
    
4. Geben Sie im Feld **"Kontodomäne"** den Domänennamen Ihrer aktuellen AD-Domäne ein (die Domäne, in der Sie Ihre Testbenutzer erstellen möchten).
    
5. Geben Sie im Feld **"Organisationseinheit** " den Namen der AD-Domäne ein, in der Sie diese Testbenutzer erstellen möchten. (Wenn die OE noch nicht vorhanden ist, wird sie für Sie erstellt).)
    
6. Geben Sie im Feld **Telefon Vorwahl** die dreistellige Vorwahl ein, die für alle Testbenutzerkonten verwendet werden soll. Stellen Sie sicher, dass die von Ihnen ausgewählte Vorwahl nicht mit den Vorwahlen anderer Benutzer in AD in Konflikt gesetzt wird.
    
7. Aktivieren Sie das Kontrollkästchen "**VoIP-aktiviert**", wenn Sie die Testbenutzer für Enterprise-VoIP aktivieren möchten.
    
8. Geben Sie im Feld **"Anzahl der Benutzer** " die Gesamtanzahl der Testbenutzer an, die Sie erstellen möchten.
    
9. Geben Sie im Feld " **Startindex** " die Startnummer an, die als Suffix für das Benutzernamenpräfix verwendet wird (z. B. lautet das Präfix "TestUser", und der Vorname endet im folgenden Beispiel mit "0").)
    
     ![Benutzerbereitstellungstool mit der Registerkarte "Benutzererstellung".](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Schaltfläche "Benutzer erstellen"

Wenn Sie auf die Schaltfläche " **Benutzer erstellen** " klicken, werden die eingegebenen Eingabeparameter überprüft. Wenn Überprüfungsfehler auftreten, werden Sie aufgefordert, sie zu beheben. Oder, wenn alle Werte korrekt sind, werden Benutzer in AD angezeigt (in der von Ihnen angegebenen ORGANISATIONSEINHEIT). Während der Ausführung des Tools wird am unteren Rand des Tools eine Statusanzeige angezeigt. Schließen Sie die Anwendung nicht, während die Statusanzeige aktiv ist.
  
Die Erstellung des Benutzers nimmt Zeit in Anspruch. Planen Sie daher bitte entsprechend. Dieser Vorgang kann von mehreren Minuten für einige Benutzer bis hin zu einigen Stunden für eine große Anzahl von Benutzern dauern.
  
Wenn Sie in Ihrer Testumgebung keinen Zugriff auf den AD-Domänencontroller haben, können Sie die Benutzererstellung dennoch überprüfen, indem Sie sich als einer der Benutzer in dem Von Ihnen angegebenen Benutzerbereich anmelden. Denken Sie daran, das Präfix und das Suffix zusammen mit dem @sipDomain als Benutzernamen zu verwenden. Hier ist ein Beispiel:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Wenn die Benutzer bereits vorhanden sind, werden sie durch Klicken auf die Schaltfläche "Benutzer erstellen" mit konfigurationsänderungen aktualisiert. 
  
#### <a name="delete-users-button"></a>Schaltfläche "Benutzer löschen"

Wenn Sie auf die Schaltfläche " **Benutzer löschen** " klicken, werden die Eingabeparameter der Registerkarte überprüft. Wenn Überprüfungsfehler auftreten, werden Sie aufgefordert, sie zu beheben, und wenn die Eingabewerte richtig sind, werden die angegebenen Testbenutzer deaktiviert und aus Active Directory gelöscht. Auch hier wird unten auf dieser Registerkarte eine Statusanzeige angezeigt, und Sie sollten die Anwendung nicht schließen, während die Statusanzeige aktiv ist.
  
> [!NOTE]
> Es werden nur us-formatierte Telefonnummern unterstützt. Telefon Nummern werden benutzern immer zugewiesen, und alle von UserProvisioningTool.exe erstellten Benutzer sind standardmäßig für Enterprise-VoIP aktiviert. Alle Szenarien, in denen die Telefonnummer verwendet wird, z. B. die automatische Konferenzzentrale oder UC-PSTN-Anrufe, verwenden diese Telefonnummer, um Anrufe ordnungsgemäß weiterzuleiten. Aus diesem Grund muss  *jeder Benutzer*  über eine *eindeutige Telefonnummer verfügen*  .
  
> [!NOTE]
> **Wenn Sie Benutzer zweimal erstellen müssen, schlägt der Befehl fehl, es sei denn, Sie verwenden eine andere Vorwahl oder wurden die vorherigen Benutzer mithilfe des cmdlets Disable-CsUser deaktiviert.**
  
> [!IMPORTANT]
> Bevor Sie Kontakte erstellen, müssen Sie zuerst die Benutzerreplikation durchführen (dies erfolgt über die Registerkarte "Benutzer"). 
  
> [!IMPORTANT]
> Wenn Sie gerade Ihre Benutzer erstellt haben, müssen Sie warten, bis Skype for Business Server Replikation abgeschlossen ist und die Benutzerkonten in der Datenbank aufgefüllt werden. **Wenn die Replikation für die Benutzer noch nicht abgeschlossen ist, wird eine Fehlermeldung angezeigt.** Sie wissen, wann Benutzer die Replikation abgeschlossen haben, wenn der Front-End-Dienst Skype for Business Server 2015 gestartet wurde, oder indem Sie das cmdlet Get-CsUser für den letzten Benutzer der angegebenen Gesamtzahl erfolgreich ausführen.
  
#### <a name="contacts-creation-tab"></a>Registerkarte "Kontakte erstellen"

Auf dieser Registerkarte können Sie den Kontakten der Benutzer Details zu Ihren Tests geben.
  
![Benutzerbereitstellungstool mit der Registerkarte "Inhaltserstellung".](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Gehen Sie wie folgt vor, um die Kontakte der Benutzer zu konfigurieren:

1. Geben Sie im Feld **"Durchschnittliche Kontakte pro Benutzer** " die durchschnittliche Anzahl von Kontakten ein, die in Kontaktlisten für jeden Benutzer aufgefüllt werden sollen.
    
2. Aktivieren Sie das Kontrollkästchen " **Behoben** ", wenn Sie für jeden Benutzer eine gleiche Anzahl von Kontakten erstellen möchten. Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, deaktivieren Sie dieses Kontrollkästchen.
    
3. Geben Sie im Feld **"Durchschnittliche Kontaktgruppen pro Benutzer** " die Anzahl der Kontaktgruppen pro Benutzer ein. Diese Zahl muss kleiner als die **durchschnittlichen Kontakte pro Benutzer** sein.
    
4. Geben Sie im Feld **"Partnerverbund/Poolübergreifender Kontaktprozentsatz"** eine Zahl zwischen 0 und 100 ein. Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.
    
5. Geben Sie im Feld **"Verbundbenutzerpräfix/Poolübergreifendes Benutzerpräfix** " den Benutzernamen für Verbundbenutzer an, der den Kontaktlisten der lokalen Benutzer hinzugefügt wird.
    
6. Geben Sie im Feld **"Partnerverbund-/Poolbenutzer-SIP-Domäne** " den SIP-Domänennamen der Verbundbenutzer an.
    
7. Stellen Sie auf der Registerkarte " **Benutzererstellung** " sicher, dass die Informationen korrekt sind. Ihre Kontakte werden anhand von Werten auf der Registerkarte "Benutzererstellung" erstellt.
    
8. Klicken Sie auf **"Kontakte erstellen** ", um mit der Erstellung des Kontakts zu beginnen. Dieser Vorgang kann mehrere Minuten dauern. Nach Abschluss des Vorgangs wird ein Dialogfeld mit der Meldung "Vorgang erfolgreich abgeschlossen" angezeigt. Sie können die Kontakte überprüfen, die erstellt wurden, indem Sie sich als Benutzer anmelden, der über die Registerkarte "Benutzererstellung" erstellt wurde.
    
    > [!NOTE]
    > Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Zielpool neu. Es kann länger (bis zu 2 Stunden) dauern, bis die Front-End-Server gestartet wurden, je nachdem, wie viele Kontakte durch diesen Vorgang erstellt wurden. 
  
#### <a name="distribution-list"></a>Verteilerliste

Das Skype for Business Server 2015 Stress and Performance Tool kann das Erweiterungsfeature für Verteilerlisten (DL) im Skype for Business 2015-Client simulieren. Sie können diesen Schritt überspringen, wenn Sie nicht beabsichtigen, die DL-Erweiterung im Benutzerbereitstellungstool zu aktivieren.
  
![Benutzerbereitstellungstool mit der Registerkarte "Erstellung von Verteilerlisten".](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
Auf der Registerkarte "Verteilerliste" können Sie DLs erstellen, die vom Stress- und Leistungstool für die Erweiterung von Verteilerlisten verwendet werden. Vor dem Erstellen von DLs muss Skype for Business Server 2015 bereitgestellt werden, einschließlich der Ausführung von ForestPrep. Wenn dies nicht erfolgt, sind die DL-Attribute nicht im AD-Schema vorhanden, sodass das Tool keine DLs erstellen kann.
  
### <a name="to-configure-distribution-lists"></a>So konfigurieren Sie Verteilerlisten:

1. Geben Sie im Feld **"Anzahl der Verteilerlisten** " die Gesamtanzahl der zu erstellenden DLs an (Es wird empfohlen, mit einem Wert zu beginnen, der doppelt so viele Benutzer wie sie haben.)
    
2. Geben Sie im Feld " **Präfix für Verteilerliste** " ein Präfix ein, das alle von Ihnen erstellten DLs aufweisen, z. B. *testDL*  . Das bedeutet, dass Ihre DL-Namen bei 100 DLs wie folgt aussehen: testDL0, testDL1 bis testDL99.
    
3. Geben Sie **im Feld "Mindestelemente" in einem Feld "Dist. Liste** " die Mindestanzahl von Benutzern ein, die in jede DL eingefügt werden sollen.
    
4. Geben Sie **im Feld "Maximale Mitglieder" in einem** Listenfeld die maximale Anzahl von Benutzern ein, die in jeder DL hinzugefügt werden sollen.
    
#### <a name="create-distribution-lists-button"></a>Schaltfläche "Verteilerlisten erstellen"

Wenn Sie auf die Schaltfläche "Verteilerlisten erstellen" klicken, fragt das Tool Active Directory ab, um festzustellen, ob bereits Verteilerlisten vorhanden sind, die dem Präfix und den Nummern entsprechen. Das Tool erstellt alle noch nicht vorhandenen DLs. Wenn Mitglieder zu diesen neu erstellten Verteilerlisten hinzugefügt werden, werden die Benutzer aus dem Bereich ausgewählt, der auf der Registerkarte "Benutzererstellung" angegeben ist.
  
#### <a name="location-info-service-config-tab"></a>Registerkarte "Konfiguration des Standortinformationsdiensts"

Das Skype for Business Server 2015 Stress and Performance Tool kann auch Dummy-Konfigurationsdateien für den Standortinformationsdienst generieren. Beachten Sie, dass der Standortinformationsdienst in der Regel keine erheblichen Auswirkungen auf die Leistung auf den Servern hat. 
  
![Das Tool für die Benutzerbereitstellung mit der Registerkarte "Konfiguration des Standortinformationsdiensts".](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Wenn Sie dieses Feature testen möchten, geben Sie die Werte im Formular ein, und klicken Sie auf die Schaltfläche "LIS-Konfigurationsdateien generieren", wodurch .CSV Dateien mit dem Namen ":
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Verwenden Sie die folgenden PowerShell-Cmdlets, um diese Dateien in die LIS-Datenbank zu importieren:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Benutzerprofil konfigurieren
<a name="BKMK_UserProfile"> </a>

Nachdem Ihre Benutzer erstellt wurden (über das Benutzererstellungstool), können Sie Benutzerprofile mit dem Skype for Business Server 2015 Load Configuration Tool (UserProfileGenerator.exe) konfigurieren.
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ausführen des Ladekonfigurationstools für Skype for Business Server 2015

Starten Sie das Ladekonfigurationstool (UserProfileGenerator.exe), und füllen Sie die Registerkarten aus. Dieses Tool erstellt ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen Ihrer Simulationen benötigen. Jedes Clientverzeichnis enthält ein Skript zum Starten des Tools für stress- und leistungsgesteuerte Skype for Business Server 2015 (LyncPerfTool.exe). In den folgenden Abschnitten finden Sie Beispiele zum Ausfüllen der Felder auf jeder Registerkarte des Skype for Business Server 2015 Load Configuration Tool.
  
> [!IMPORTANT]
> Die im Ladekonfigurationstool (UserProfileGenerator.exe) verwendeten benutzerspezifischen Werte müssen mit den Werten übereinstimmen, die im Skype for Business Server 2015-Benutzererstellungstool (UserProvisioningTool.exe) für den Pool angegeben sind. 
  
#### <a name="common-configuration-tab"></a>Registerkarte "Allgemeine Konfiguration"

Die Registerkarte " **Allgemeine Konfiguration** " des Ladekonfigurationstools ist unten dargestellt. Füllen Sie die Felder der Registerkarte "Allgemeine Konfiguration" aus, wie in den folgenden Schritten beschrieben.
  
![Die Registerkarte "Benutzerbereitstellung" mit der Registerkarte "Allgemeine Konfiguration".](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Geben Sie im Feld **"Anzahl der verfügbaren Computer** " die Anzahl der Computer ein, die Sie zum Ausführen des Tools "Stress and Performance" (LyncPerfTool.exe) verwenden möchten. Es wird empfohlen, einen Computer für alle 4500 Benutzer zu verwenden, die Sie simulieren werden. Diese Anzahl kann jedoch variieren, wenn Sie den Ladegrad verringern oder nur eine Teilmenge der verfügbaren Features des Tools verwenden (Ladeebenen werden auf der Registerkarte "Allgemeine Szenarien" festgelegt).
    
2. Geben Sie im Feld **"Präfix für Benutzernamen** " ein Präfix für das Benutzernamenfeld aller Benutzer ein. Die Anmeldung des URI (Uniform Resource Identifier) erfolgt wie folgt: *UserPrefix[User Start Index... (Anzahl der Benutzer-1)] @User Domäne*  beispielsweise myUser009@Contoso.com.
    
3. Geben Sie im Feld **"Kennwort für alle Benutzer** " das Kennwort ein, das bei der Erstellung der Benutzer verwendet wird. Wenn Sie dieses Feld leer lassen, wird der Benutzername als Kennwort festgelegt.
    
4. Geben Sie im Feld **"Benutzeranfangsindex** " den Index des ersten zu konfigurierenden Benutzers ein. Sie können unterschiedliche Bereiche für unterschiedliche Typen oder Ladeebenen konfigurieren, aber Sie müssen das Ladekonfigurationstool (UserProfileGenerator.exe) einmal pro bereich ausführen, den Sie konfigurieren möchten.
    
5. Geben Sie im Feld **"Anzahl der Benutzer** " die Gesamtzahl der Benutzer ein, die Sie konfigurieren möchten.
    
6. Geben Sie im Feld **"Benutzerdomäne** " die Domäne ein, die für den SIP-URI verwendet wird. Dies wird verwendet, um den SIP-URI jedes Benutzers zu erstellen, um sich beim front-End-Server Skype for Business Server 2015 oder Standard Edition-Server anzumelden, und kann sich von der Kontodomäne unterscheiden.
    
7. Geben Sie im Feld **"Kontodomäne"** die AD DS-Domänenanmeldung ein.
    
8. Geben Sie im Feld **MPOP-Prozentsatz** (Prozentsatz mehrerer Anwesenheitspunkte) einen Wert für den Prozentsatz der Benutzer an, die von mehreren Computern oder Geräten angemeldet sind, z. B. 10 Prozent.
    
9. Geben Sie die maximale Anzahl gleichzeitiger Endpunkte in das Feld **"Anmelden pro Sekunde (pro Instanz)"** ein. Dies ist die maximale Anzahl von Anmeldungen für Ihre Benutzer, und die Empfehlung ist eine Rate von weniger als/gleich 2 pro Sekunde (<=2).
    
10. Geben Sie im **FQDN-Feld "Zugriffsproxy" oder "Pool** " den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen sollen. Wenn sich die Benutzer extern anmelden, müssen Sie den Zugriffsproxy eingeben. Wenn die Benutzer intern sind, geben Sie den FQDN ihres Enterprise Pools oder Standard Edition Servers an.
    
11. Geben Sie im Feld **"Port** " den Port ein, den Benutzer für SIP verwenden möchten (der Standardwert hier ist 5061).
    
12. Geben Sie für das Feld **"Externer Netzwerkserver Einstellungen**" den Zugriffsproxy- oder Pool-FQDN und erneut den **Port** an. Diese Einstellungen werden nur für die Lastsimulation externer Endpunkte verwendet.
    
#### <a name="general-scenarios-tab"></a>Registerkarte "Allgemeine Szenarien"

![Load Configuration Tool showing the General Scenarios tab.](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Sie können die Ladeebenen und Parameter für jedes der allgemeinen Szenarien konfigurieren, indem Sie bestimmen, was Sie ausführen oder deaktiviert lassen möchten. Hier sind Ihre allgemeinen Optionen:
  
> [!NOTE]
> Lastebenenwerte für alle Felder, aber lokale Informationsdienste sind **deaktiviert**, **niedrig**, **mittel**, **hoch** oder **benutzerdefiniert**. Wenn Sie eine Einstellung außer "Deaktiviert" auswählen, werden konfigurationen für jeden Client generiert. Hohe Ergebnisse bei der maximal unterstützten Last auf dem Server; Mittel ist 60% der hohen Last; niedrig ist 30%. 
  
- **Instant Messaging –** Dazu gehören Peer-to-Peer- und Konferenzen; wählen Sie den entsprechenden Wert für "Load Level" aus.
    
- **Audiokonferenz –** Wählen Sie einen Ladegrad *nur* für Audiokonferenzen aus. Peer-to-Peer-Anrufe werden etwas später im Abschnitt **"VoIP-Szenarien** " behandelt. Öffnen Sie die Registerkarte " **Erweitert** ", um MultiView zu aktivieren.
    
- **Anwendungsfreigabe –** Wählen Sie eine Ladeebene für die Anwendungsfreigabe aus.
    
- **Datenzusammenarbeit –** Wählen Sie eine Ladeebene für die Datenzusammenarbeit aus, einschließlich Datenkonferenzen.
    
- **Verteilerlistenerweiterung -** Klicken Sie auf die Schaltfläche " **Erweitert",** und füllen Sie das Feld mit den gleichen Werten aus, die auf der Registerkarte "DL" des Benutzererstellungstools (UserProvisioningTool.exe) konfiguriert sind. Wählen Sie einen Ladegrad aus.
    
- **Adressbuch-Webabfrage –** Dies ist der Adressbuch-Nachschlagedienst anstelle des Adressbuchdateidownloads. Wenn Sie dies für Adressbuchdateidownloads aktivieren möchten, klicken Sie auf die Schaltfläche " **Erweitert** ", und legen Sie **"EnableABSDownload** " auf "True" fest. Geben Sie einen Wert für den Ladegrad an.
    
- **Reaktionsgruppendienst –** Klicken Sie auf die Schaltfläche " **Erweitert",** und geben Sie die URIs der Reaktionsgruppen an, die Sie bereits bei der Bereitstellung von Reaktionsgruppendienst-Agents erstellt haben. Sie müssen mindestens eine Reaktionsgruppe auswählen. Wenn Sie mehr verwenden möchten, trennen Sie die Reaktionsgruppen durch Semikolons. Aktualisieren Sie **RGSUriSuffixStartIndex** und **RGSUriSuffixEndIndex** auf die tatsächlichen Werte. Wählen Sie einen Ladegrad aus.
    
- **Standortinformationsdienste –** Wählen Sie eine Ladeebene von "Aktiviert" oder "Deaktiviert" aus.
    
> [!NOTE]
> Jedes der Szenarien verfügt über eine Schaltfläche "Erweitert" daneben und eine Reihe von Kontrollkästchen, die Variationen der Standardeinstellung ermöglichen. 
  
- Die Auswahl von  *Ad-hoc*  ermöglicht es dem Tool, Simulationen von Konferenzen zu generieren, die während der gesamten Stunde erstellt werden.
    
- Wenn Sie  *"Große Konferenzen*  " auswählen, wird ein Szenario für große Konferenzen simuliert.
    
-  *Extern*  weist das Tool an, auch externe Benutzer zu simulieren.
    
Diese Schaltflächen und Kontrollkästchen sind zusätzliche Werte, die für jedes Szenario spezifisch sind, und ändern das Verhalten des Tools für Stress und Leistung und ermöglichen die Anpassung.
  
Wenn für jedes Szenario auf der Registerkarte "Allgemeine Szenarien" (mit Ausnahme von Positionsinformationsdiensten) der Wert " **Ladeebene" "Benutzerdefiniert**" ist, wird die Unterhaltungsrate mithilfe des entsprechenden Felds im Dialogfeld "Erweitert" berechnet. Der Feldname kann je nach Szenario unterschiedlich sein, in der Feldbeschreibung wird jedoch folgendes angegeben:  *HINWEIS Diese Zahl wird nur verwendet, wenn "Benutzerdefiniert" aus dem Dropdownmenü ausgewählt ist*  .
  
Die Werte **"Hoch**", " **Mittel"** und " **Niedrig**" ändern die Unterhaltungsraten pro Modalität entsprechend dem Benutzermodell, das ein Gleichgewicht aller Szenarien darstellt. Wenn der Ladegrad pro Modalität aufgrund eines Unterschieds bei der erwarteten Nutzung geändert werden muss, verwenden Sie eine benutzerdefinierte Unterhaltungsrate.
  
#### <a name="voice-scenarios-tab"></a>Registerkarte "VoIP-Szenarien"

Dies ist die Registerkarte für die Konfiguration aller Sprachszenarien.
  
![Registerkarte "Sprachszenarien" des Konfigurationstools laden.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Folgende Optionen sind verfügbar:
  
- **VoIP -** Klicken Sie auf die Schaltfläche " **Erweitert",** und fügen Sie Werte für die Felder "PhoneAreaCode" und "LocationProfile" (Wählplan) hinzu. Sie geben auch einen Wert für "Load Level" an. Wenn Sie einen Ladegrad für voIP oder UC/PSTN-Gateway aktiviert wählen, wird ein PSTN-Konfigurationsdatei (Public Switched Telephone Network) zu Unified Communications (UC) generiert, um externe Anrufe zu simulieren.
    
- **UC/PSTN-Gateway –** Sie müssen einen Wert für den Ladegrad auswählen, und wenn Sie einen anderen Wert als "Deaktiviert" auswählen, müssen Sie auch einen Wert für die PSTN-Vorwahl angeben, indem Sie auf die Schaltfläche " **Erweitert** " klicken. Klicken Sie unter vermittlungsserver und PSTN auf **"Hinzufügen"** . Stellen Sie sicher, dass Sie eine Route für die Vorwahl konfiguriert haben.
    
    > [!TIP]
    > Sie können entweder die Skype for Business Systemsteuerung- oder Skype for Business-Verwaltungsshell verwenden, um Ihre VoIP-Routenkonfiguration zu überprüfen. 
  
- **Konferenzzentrale –** Geben Sie einen Wert für "Load Level" an. Mit einem anderen Wert als "Deaktiviert" wird das Feld **"Telefonnummer** " aktiviert. Geben Sie die Telefonnummer der automatischen Telefonzentrale ein, die Sie verwenden möchten. Klicken Sie auf **"Erweitert** ", und geben Sie einen Wert für das **Feld "LocationProfile** " ein.
    
- **Call Parking Service -** Geben Sie hier einen Ladegrad an.
    
- **Vermittlungsserver und PSTN –** Jeder Vermittlungsserver, den Sie verwenden möchten, benötigt einen eigenen PSTN-Simulator. Nachdem Sie ermittelt haben, welchen Client Sie für den Simulator verwenden möchten, konfigurieren Sie Ihren Vermittlungsserver so, dass Anrufe an diesen Computer im von Ihnen konfigurierten PSTN-Simulator weitergeleitet werden. Klicken Sie auf die Schaltfläche **"Hinzufügen** ", um einen Wert für den Vermittlungsserver zu konfigurieren.
    
    > [!NOTE]
    > Jedes Szenario verfügt über eine Schaltfläche "Erweitert" daneben. Erweiterte Dialogfelder enthalten spezifische Einstellungen für jedes Szenario, die das Verhalten des Tools für Stress und Leistung ändern und Anpassungen ermöglichen. > Für jedes Szenario auf der Registerkarte "Sprachszenarien" wird die Unterhaltungsrate mithilfe des entsprechenden Felds im Dialogfeld "Erweitert" berechnet, wenn der Wert für "Ladeebene **" "Benutzerdefiniert**" ist. Der Feldname kann je nach Szenario unterschiedlich sein, in der Feldbeschreibung wird jedoch folgendes angegeben:  *HINWEIS Diese Zahl wird nur verwendet, wenn "Benutzerdefiniert" aus dem Dropdownmenü ausgewählt ist*  .
  
#### <a name="web-app-tab"></a>Registerkarte "Web App"

![Tool "Konfiguration laden", Registerkarte "Web-App".](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App unterstützt Konferenzszenarien über den Unified Communications Web API (UCWA)-Server, der auf einem Front-End-Server installiert ist. Verwenden Sie die Registerkarte "Web App", um alle Web-App-bezogenen Szenarien zu konfigurieren. Mögliche Optionen sind:
  
- **Allgemeine Web App-Einstellungen –** Klicken Sie auf die Schaltfläche "**Zusätzliche Einstellungen**", und legen Sie "**ReachTargetServerUrl**" auf die virtuelle IP(VIP) des Verzeichnispools der VIP des Front-End-Pools fest.
    
- **Anwendungsfreigabe –** Wählen Sie einen Wert für "Load Level" aus.
    
- **Datenzusammenarbeit –** Wählen Sie einen Wert für "Load Level" aus.
    
- **Instant Messaging –** Wählen Sie einen Wert für "Load Level" aus.
    
- **Sprachkonferenzen –** Wählen Sie einen Wert für "Load Level" aus.
    
> [!NOTE]
> In jedem Szenario befindet sich daneben eine Schaltfläche " **Erweitert** ". Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Tools für Stress und Leistung ändern und customization.> Wenn der Ladegrad für jedes Web App-Szenario **benutzerdefiniert** ist, wird der im Feld **"ConversationsPerHour** " angegebene Wert anstelle des Standardwerts verwendet.
  
#### <a name="mobility-tab"></a>Registerkarte "Mobilität"

Verwenden Sie diese Registerkarte, um alle Mobilitätsszenarien zu konfigurieren.
  
![Registerkarte "Mobilität" des Konfigurationstools laden.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Die folgenden Optionen stehen zur Auswahl:
  
- **General Mobility Einstellungen –** Klicken Sie auf **"Zusätzliche Einstellungen**", und legen Sie das Feld "UcwaTargetServerUrl" auf die virtuelle IP(VIP) des Directorpools oder die VIP des Front-End-Pools fest.
    
- **Anwesenheit und P2P-Chat/Audio –** Wählen Sie einen Wert für "Lastgrad" aus, um die Mobilitätssimulation zu aktivieren.
    
> [!NOTE]
> In jedem Szenario befindet sich daneben eine Schaltfläche " **Erweitert** ". Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Tools für Stress und Leistung ändern und "customization.> Für jedes Mobilitätsszenario, wenn der Ladegrad **benutzerdefiniert** ist, wird der im Feld **"ConversationsPerHour** " angegebene Wert anstelle des Standardwerts verwendet.
  
#### <a name="summary-tab"></a>Registerkarte "Zusammenfassung"

Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen.
  
![Registerkarte "Zusammenfassung des Konfigurationstools laden".](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für die einzelnen Szenarien verwendet werden sollen. 
  
Es ist möglich, Benutzernummernbereiche manuell zu konfigurieren, indem Sie das Kontrollkästchen **"Benutzerdefinierte Benutzerbereichsgenerierung aktivieren** " aktivieren und dann in der Tabelle mit dem Benutzerbereich, den Sie anpassen möchten, auf das Szenario doppelklicken.
  
Check **(RunClient.bat) Add sign-in delay when starting** in order to include delays in the generated batch files to correspond to the sign-in rate. Dies ist nützlich, um eine Serverüberlastung zu verhindern, wenn Sie sich bei einer großen Anzahl von Benutzern anmelden.
  
Klicken Sie auf **"Dateien generieren** ", und wählen Sie den Ordner aus, in dem Sie die Konfiguration generieren möchten. Wenn Ihre Dateien erfolgreich erstellt wurden, wird ein Dialogfeld angezeigt.
  
![Das Meldungsfeld "Erfolgreich generierte Konfigurationsdateien laden". Klicken Sie einfach auf "OK".](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ausführen von LyncPerfTool
<a name="BKMK_RunTool"> </a>

Sie müssen Benutzer, Kontakte und Szenarien erstellen, bevor Sie das Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) ausführen. Ausführliche Informationen zur Verwendung der Tools zum Ausführen dieser Aktionen finden [Sie unter "Benutzer und Kontakte erstellen](using-the-tool.md#BKMK_CreateUsersAndContacts) " und ["Benutzerprofil konfigurieren](using-the-tool.md#BKMK_UserProfile) " weiter oben in diesem Artikel. Wenn Sie diese Tools ausführen, wird auch eine Datei generiert, die mit dem Stress- und Leistungstool als Teil einer Batchdatei mit den erforderlichen Parametern ausgeführt wird.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ausführen des Tools für Stress und Leistung Skype for Business Server 2015

Das Ladekonfigurationstool (UserProfileGenerator.exe) erstellt eine Batchdatei, mit der Sie das Stress and Performance-Tool (LyncPerfTool.exe) ausführen können, indem Sie Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden. Die Batchdatei führt eine Instanz von LyncPerfTool.exe pro Konfigurationsdatei aus. Führen Sie die folgenden Schritte aus, um die Batchdatei auszuführen:
  
### <a name="run-the-stress-and-performance-test"></a>Ausführen des Stress- und Leistungstests

1. Kopieren Sie den Ordner mit den Konfigurationsordnern und -dateien in das Verzeichnis, das auf jedem Clientcomputer LyncPerfTool.exe hat. (Wenn Sie beispielsweise die Konfigurationsdateien im Ordner 1.28_13.16.16 generiert haben, kopieren Sie diesen Ordner mit LyncPerfTool.exe in den Ordner. Führen Sie dies auf jedem Client aus.)
    
2. Navigieren Sie zum Clientordner, und führen **Sie das RunClient-Batchskript** aus. Sie können im Windows Explorer auf die Batchdatei doppelklicken, und alle Konfigurationsdateien für diesen Client werden ausgeführt. Sie können das Skript auch aus einem Clientordner ausführen, indem Sie die folgende Syntax verwenden:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Um das Tool "Stress and Performance" direkt auszuführen, öffnen Sie eine Eingabeaufforderung, und geben Sie den folgenden Befehl an der Befehlszeile ein (und wenn Sie dies zum ersten Mal tun, müssen Sie die Leistungsindikatoren  `regsvr32 /i /n /s LyncPerfToolPerf.dll`registrieren, wie in der Notiz weiter unten in diesem Thema gezeigt):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Damit das Tool die Werte in der Konfigurationsdatei anzeigt, fügen Sie den  `/displayfile` Parameter in den vorherigen Befehl ein, damit er wie folgt aussieht:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Drücken Sie STRG+C, um den Vorgang zu  *beenden*  .
  
> [!NOTE]
> Bevor Sie das Stress- und Leistungstool direkt ausführen, müssen Sie die Leistungsindikatoren über den folgenden Befehl registrieren:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Jede Instanz des Tools für Stress und Leistung, das Sie starten, beginnt sofort mit der Anmeldung von Benutzern, in der Regel mit einer Rate von einem Benutzer pro Sekunde. 
  
Die maximale Benutzeranmeldungsrate für den Pool beträgt etwa 12 pro Sekunde. Dies bedeutet, dass Sie nicht mehr als 12 LyncPerfTool.exe Instanzen gleichzeitig starten sollten, während sich Benutzer noch anmelden. Eintausend Benutzer brauchen etwa 20 Minuten, um sich mit einer pro Sekunde vollständig anzumelden.
  
## <a name="interpreting-the-results"></a>Interpretieren der Ergebnisse
<a name="BKMK_Interpret"> </a>

Das Skype for Business Server 2015 Stress and Performance Tool verfügt über viele Leistungsindikatoren, die Ihnen helfen können, zu verstehen, was der Client tut und ob Probleme auftreten.
  
### <a name="client-counters"></a>Clientzähler

Jede Instanz der ausgeführten LyncPerfTool.exe verfügt über eine separate Instanz der Leistungsindikatoren. Jede Instanz wird anhand ihrer Prozess-ID benannt. Wenn Clients überlastet sind, können andere Probleme auftreten. So verhindern Sie diese Probleme:
  
- Überwachen der CPU- und Speicherauslastung auf den Clientcomputern. Wenn die CPU konsistent über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.
    
- Wenn der Speicherbedarf hoch ist, treten möglicherweise Probleme auf, wenn der Speicherplatz für die Seitendatei nicht mehr ausreicht. Stellen Sie sicher, dass die Commit-Gebühr nicht den Grenzwert auf dem Computer erreicht. Wenn Speichergrenzwerte auftreten, sollten Sie die Größe der Seitendatei erhöhen oder die Anzahl der Benutzer verringern.
    
Hier ist eine Liste der wichtigsten Leistungsindikatoren:
  
**Allgemeine Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Zeitaufwand in Minuten  <br/> |Die Zeit, die seit dem Start des Prozesses aufgewendet wurde.  <br/> |
|Aktive Endpunkte  <br/> |Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.  <br/> |
|Fehlgeschlagene Anmeldungen  <br/> |Gesamtanzahl der Endpunkt-Anmeldefehler.  <br/> |
|Anmeldeversuche  <br/> |Gesamtanzahl der Endpunkt-Anmeldeversuche.  <br/> |
|Endpunkte getrennt  <br/> |Gesamtanzahl der Endpunkte, die getrennt wurden.  <br/> |
   
**Anwesenheitsinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|SetPresence-Aufrufe  <br/> |Gesamtanzahl der Anwesenheitsänderungsversuche. Informationen zu verschiedenen Arten von Anwesenheitsänderungen finden Sie unter "SetPresence (Presence Type) Calls Performance Counter".  <br/> |
|NNN-Antworten für SetPresence  <br/> |Gesamtanzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|GetPresence-Aufrufe  <br/> |Die Gesamtanzahl der Versuche zum Abrufen von Anwesenheitsanforderungen.  <br/> |
|NNN-Antworten für GetPresence  <br/> |Gesamtanzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
   
**Adressbuch-Dienstinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Abs Full/Delta Dateidownloads versucht  <br/> |Gesamtanzahl der versuchten Downloadanforderungen für vollständige oder Delta-Dateien.  <br/> |
|Abs Full/Delta Dateidownloads erfolgreich  <br/> |Gesamtanzahl der versuchten Downloadanforderungen für vollständige oder Delta-Dateien.  <br/> |
|Adressbuch-Webabfragedienstbezogene Leistungsindikatoren  <br/> |Adressbuchdatei herunterladen bezogene Leistungsindikatoren.  <br/> |
|ABS WS-Aufrufe versucht  <br/> |Gesamtanzahl der versuchten Adressbuch-Webabfragedienstanforderungen.  <br/> |
|ABS WS-Aufrufe erfolgreich  <br/> |Gesamtanzahl der Adressbuch-Webabfragedienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|ABS WS-Aufrufe fehlgeschlagen  <br/> |Gesamtanzahl der Adressbuch-Webabfragedienstanforderungen, die einen Fehlerantwortcode zurückgegeben haben.  <br/> |
   
> [!NOTE]
> Diese Kategorie enthält Indikatoren, die zum Überwachen von ABS-Dateidownloads (Address Book Service) und Adressbuch-Webabfragedienstanforderungen verwendet werden. 
  
**Informationen zur Verteilerliste (Verteilerliste, DL)**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Versuchter Aufruf  <br/> |Gesamtanzahl der versuchten DLX-Webdienstanforderungen (Verteilerlistenerweiterung).  <br/> |
|Anrufe erfolgreich  <br/> |Gesamtanzahl der DLX-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|Fehler bei Anrufen  <br/> |Gesamtanzahl der DLX-Webdienstanforderungen, die einen Fehlerantwortcode zurückgegeben haben.  <br/> |
   

  
> [!NOTE]
> Die unten aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Anrufen an den Vermittlungsserver, den A/V-Konferenzserver, den Edgeserver, die Reaktionsgruppenanwendung und die automatische Konferenzzentrale, wenn diese Szenarien aktiviert sind. 
  
**Grundlegende Informationen zu VoIP**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der derzeit laufenden eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Beendete Anrufe  <br/> |Die Gesamtzahl der bereits beendeten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Anrufe abgelehnt  <br/> |Die Gesamtzahl der eingehenden Sprachanrufe wurde abgelehnt.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Gesamtanzahl der eingerichteten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Anrufe empfangen NNN  <br/> |Gesamtanzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|VoIP Pass Rate (%)  <br/> |Gesamtanzahl der eingerichteten Anrufe/Versuchter Gesamtaufrufe.  <br/> |
   
**Anrufinformationen des Reaktionsgruppendiensts**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der aktiven Aufrufe an die Reaktionsgruppenanwendung.  <br/> |
|Versuchter Aufruf  <br/> |Die Gesamtzahl der versuchten Anrufe.  <br/> |
   
**Anrufinformationen für Chatnachrichten**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der laufenden eingehenden/ausgehenden Chatanrufe.  <br/> |
|Beendete Anrufe  <br/> |Die Gesamtzahl der bereits beendeten eingehenden/ausgehenden Chatanrufe.  <br/> |
|Anrufe empfangen NNN  <br/> |Gesamtanzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|Empfangene/gesendete Chatnachrichten  <br/> |Gesamtanzahl der empfangenen oder gesendeten Nachrichten für alle Sitzungen.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Chatanrufe.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Die Gesamtanzahl der eingerichteten eingehenden/ausgehenden Chatnachrichtenanrufe.  <br/> |
   
**Anrufinformationen für die App-Freigabe**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Beendete Anrufe  <br/> |Die Gesamtzahl der bereits beendeten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Anrufe empfangen NNN  <br/> |Gesamtanzahl der vom Server empfangenen nnn-Antwortcodes.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Gesamtanzahl der eingerichteten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
   
**CAA-Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der derzeit laufenden PSTN-Anrufe (Incoming/Outgoing Public Switched Telephone Network).  <br/> |
|Beendete Anrufe  <br/> |Die Gesamtzahl der bereits beendeten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
|Eingehende/ausgehende Anrufe eingerichtet  <br/> |Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde eingerichtet.  <br/> |
   
**Konferenzinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Chatkonferenzen  <br/> |Gesamtzahl der laufenden Chatkonferenzen.  <br/> |
|Aktive Audio-/Videokonferenzen  <br/> |Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).  <br/> |
|Aktive Anwendungsfreigabekonferenzen  <br/> |Die Gesamtzahl der laufenden Anwendungsfreigabekonferenzen.  <br/> |
|Anzahl der Teilnehmer  <br/> |Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.  <br/> |
|Konferenzplanfehler  <br/> |Gesamtanzahl der Fehler beim Planen einer Konferenz.  <br/> |
|Teilnahme an Konferenzfehlern  <br/> |Gesamtanzahl der Fehler beim Versuch, eine Verbindung mit einer Konferenz herzustellen.  <br/> |
   
**UCWA-Clientzähler**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Gesamtanzahl der erfolgreich abgeschlossenen IMMCU-Verknüpfungen  <br/> |Die Gesamtzahl der chatten Konferenzen, die beigetreten sind.  <br/> |
|Gesamtanzahl der erfolgreichen DMCU-Verknüpfungen  <br/> |Die Gesamtzahl der angetretenen A/V-Konferenzen.  <br/> |
   

