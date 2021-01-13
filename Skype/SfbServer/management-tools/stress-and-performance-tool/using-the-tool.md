---
title: Verwenden des Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/13/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: Um das Skype for Business Server 2015 Stress and Performance Tool ausführen zu können, müssen Sie in der Lage sein, sowohl Benutzer, Kontakte und Benutzerprofile zu verwalten, das Tool für die Ausführung zu konfigurieren und dann die Vom Tool erzeugten Ausgaben oder Ergebnisse zu überprüfen.
ms.openlocfilehash: e008a85d22753a4e649da8501bd387675bb9b536
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814945"
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Verwenden des Skype for Business Server 2015 Stress and Performance Tool
 
Um das Skype for Business Server 2015 Stress and Performance Tool ausführen zu können, müssen Sie in der Lage sein, sowohl Benutzer, Kontakte und Benutzerprofile zu verwalten, das Tool für die Ausführung zu konfigurieren und dann die Vom Tool erzeugten Ausgaben oder Ergebnisse zu überprüfen.
  
Es gibt vier Bereiche, die mit der Ausführung des Skype for Business Server 2015 Stress and Performance Tool (die ausführbare Datei ist LyncPerfTool.exe):
  
- [Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Konfigurieren des Benutzerprofils](using-the-tool.md#BKMK_UserProfile)
    
- [Ausführen von LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpretieren der Ergebnisse](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Erstellen von Benutzern und Kontakten
<a name="BKMK_CreateUsersAndContacts"> </a>

Sie müssen das Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) verwenden, um Benutzer und Kontakte für Stress- und Leistungstests zu erstellen.
  
Dies ist eine Liste hilfreicher Begriffe, die beim Durchlesen der Themen hilfreich sein können:
  
- **Organisationseinheit** – Die Organisationseinheit (Organizational Unit, OU) der Active Directory Domain Services (AD DS).
    
- **Partner/Poolübergreifende** Benutzer, die mit Benutzern aus anderen Chatdiensten kommunizieren können.
    
- **Verteilerlisten –** oder DLs. Dies sind Objekte in AD DS, die eine Liste von AD DS-Benutzern enthalten. Sie werden verwendet, um die Kommunikation zwischen Personengruppen zu erleichtern.
    
- **Standortinformationsdienst** – Der Skype for Business Server 2015-Dienst, der, wenn er aktiviert und pro Telefon konfiguriert ist, das Abrufen des physischen Standorts für Erweiterte 911 (E911)-Dienste ermöglicht.
    
- **US-Telefonnummern** – Telefonnummern, die dem Benutzer zusätzlich zu dem SIP-URI zugewiesen sind, der für die Weiterleitung eingehender und ausgehender Anrufe in der RNL (Reverse Number Lookup) verwendet wird.
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Erstellen von Benutzern und Kontakten mithilfe UserProvisioningTool.exe

> [!NOTE]
> Bevor Sie beginnen, müssen Sie unbedingt als Mitglied der Sicherheitsgruppe "Domänen-Admins" angemeldet sein, um dieses Tool ausführen zu können. Sie müssen dies tun, da Sie Active Directory-Benutzer erstellen werden. 
  
Sie müssen das Skype for Business Server-Benutzerbereitstellungstool verwenden, um Benutzer und Kontakte für die Auslastungssimulation zu erstellen.
  
Das **Skype for Business Server User Provisioning Tool** wird mit dem Skype for Business Server Stress and Performance **Tool-Paket** installiert. Stellen Sie sicher, dass das Paketinstallationsprogramm (CapacityPlanningTool.msi) auf dem Front-End-Server oder dem Standard Edition-Server ausgeführt wurde, den Sie testen möchten.
  
Sie können das Skype for Business Server-Benutzerbereitstellungstool starten, indem Sie die Datei UserProvisioningTool.exe (unter %InstalledDirectory%LyncStressAndPerfTool\LyncStress) auf dem Front-End-Server oder auf dem Standard Edition-Server ausführen.
  
> [!IMPORTANT]
> Wenn Sie eine große Anzahl von Benutzern erstellen (z. B. 10.000 oder mehr), führen Sie die UserProvisioningTool.exe. Sie müssen dies tun, da das Tool neue AD-Benutzer  *erstellt*  und konfiguriert.
  
Wenn das Tool für die Benutzerbereitstellung geöffnet wird, klicken Sie auf "Konfiguration", und wählen Sie die Ladekonfiguration aus. 
  
Laden Sie zum Konfigurieren von Benutzern und Kontakten die im Paket enthaltene Standarddatei namens "SampleData.xml". Dadurch werden Felder vorab mit Beispieldaten aufgefüllt, die Sie ändern müssen, um sie für Ihre Bereitstellung relevant zu machen.
  
Wenn Sie über eine vorkonfigurierte XML-Datei verfügen, die bereits Ihre benutzerdefinierten Einstellungen enthält, können Sie diese Datei stattdessen laden. Füllen Sie die Felder im Benutzerbereitstellungstool aus, wie in den folgenden Abschnitten beschrieben.
  
### <a name="to-configure-server-options"></a>So konfigurieren Sie Serveroptionen:

1. Geben Sie im **Feld FQDN** des Front-End-Pools den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Standard Edition-Servers oder den Front-End-Pool ein, in dem sie die Benutzer hosten möchten.
    
2. Geben Sie **im Feld "Benutzername-Präfix"** ein Präfix ein, das Sie verwenden möchten, um Ihre Benutzernamen zu Testzwecken zu vollst nen (z. B. "TestUser").
    
3. Geben Sie **im Feld "Kennwort"** ein Kennwort ein, das für alle Testbenutzerkonten verwendet wird.
    
4. Geben Sie **im Feld "Kontodomäne"** den Domänennamen Ihrer aktuellen AD-Domäne ein (die Domäne, in der Sie Ihre Testbenutzer erstellen möchten).
    
5. Geben Sie **im Feld Organisationseinheit** den Namen der AD-Domäne ein, in der Sie diese Testbenutzer erstellen möchten. (Wenn die Organisationseinheit noch nicht vorhanden ist, wird sie für Sie erstellt).)
    
6. Geben Sie **im Feld "Telefonbereichscode"** die dreistellige Vorwahl ein, die für alle Testbenutzerkonten verwendet werden soll. Stellen Sie sicher, dass die von Ihnen gewählten Ortscodes nicht mit den Vorwahlen anderer Benutzer in AD in Konflikt stehen.
    
7. Aktivieren Sie das Kontrollkästchen **"Sprach** aktiviert", wenn Sie die Testbenutzer für die Enterprise-VoIP.
    
8. Geben Sie **im Feld "Anzahl der Benutzer"** die Gesamtzahl der Testbenutzer an, die Sie erstellen möchten.
    
9. Geben  Sie im Startindexfeld die Startnummer, die als Suffix verwendet wird, dem Benutzernamenpräfix zu (z. B. ist das Präfix "TestUser", und der Vorname endet im folgenden Beispiel mit "0".)
    
     ![Benutzerbereitstellungstool mit der Registerkarte "Benutzererstellung".](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Schaltfläche "Benutzer erstellen"

Wenn Sie auf die Schaltfläche "Benutzer **erstellen"** klicken, werden die eingegebenen Eingabeparameter überprüft. Wenn Überprüfungsfehler auftreten, werden Sie aufgefordert, diese zu beheben. Wenn alle Werte korrekt sind, werden die Benutzer auch in AD angezeigt (in der von Ihnen angegebenen OU). Unten im Tool wird eine Statusleiste angezeigt, während sie ausgeführt wird. Schließen Sie die Anwendung nicht, während die Statusleiste aktiv ist.
  
Die Erstellung des Benutzers dauert, planen Sie daher entsprechend. Dieser Vorgang kann für einige wenige Benutzer eine beliebige Zeit von mehreren Minuten bis hin zu einigen Stunden für eine große Anzahl von Benutzern dauern.
  
Wenn Sie in Ihrer Testumgebung keinen Zugriff auf den AD-Domänencontroller haben, können Sie die Benutzererstellung dennoch überprüfen, indem Sie sich als einer der Benutzer im Bereich der Benutzer anmelden, die Sie erstellen möchten. Denken Sie daran, das Präfix und das Suffix zusammen mit dem @sipDomain Benutzernamen zu verwenden. Hier ist ein Beispiel:  <em>TestUser20@contoso.net</em>  .
  
> [!NOTE]
> Wenn die Benutzer bereits vorhanden sind, werden sie durch Klicken auf die Schaltfläche "Benutzer erstellen" mit konfigurationsänderungen aktualisiert. 
  
#### <a name="delete-users-button"></a>Schaltfläche "Benutzer löschen"

Wenn Sie auf die Schaltfläche **"Benutzer löschen"** klicken, werden die Eingabeparameter der Registerkarte überprüft. Wenn Überprüfungsfehler auftreten, werden Sie aufgefordert, diese zu beheben. Wenn die Eingabewerte korrekt sind, werden die angegebenen Testbenutzer deaktiviert und aus Active Directory gelöscht. Auch hier wird unten auf dieser Registerkarte eine Statusleiste angezeigt, und Sie sollten die Anwendung nicht schließen, während die Statusleiste aktiv ist.
  
> [!NOTE]
> Nur in den USA formatierte Telefonnummern werden unterstützt. Telefonnummern werden immer Benutzern zugewiesen, und alle von UserProvisioningTool.exe erstellten Benutzer sind standardmäßig Enterprise-VoIP aktiviert. Alle Szenarien, in denen die Telefonnummer verwendet wird, z. B. Konferenz- automatische Telefonzentrale oder UC-PSTN-Anrufe, verwenden diese Telefonnummer, um Anrufe ordnungsgemäß weiter zu routen. Aus diesem Grund *muss jeder Benutzer* über eine eindeutige Telefonnummer *verfügen.*
  
> [!NOTE]
> **Wenn Sie zweimal Benutzer erstellen müssen, kann der Befehl nicht ausgeführt werden, es sei denn, Sie verwenden eine andere Vorwahl, oder die vorherigen Benutzer wurden mithilfe des cmdlets Disable-CsUser deaktiviert.**
  
> [!IMPORTANT]
> Bevor Sie Kontakte erstellen, müssen Sie zunächst die Benutzerreplikation abschließen (dies erfolgt über die Registerkarte "Benutzer"). 
  
> [!IMPORTANT]
> Wenn Sie gerade Ihre Benutzer erstellt haben, müssen Sie warten, bis die Skype for Business Server-Replikation abgeschlossen ist, und die Benutzerkonten in der Datenbank auffüllen. **Wenn die Replikation der Benutzer noch nicht abgeschlossen ist, wird ein Fehler angezeigt.** Sie wissen, wann Benutzer die Replikation abgeschlossen haben, wenn der Skype for Business Server 2015-Front-End-Dienst gestartet wurde, oder indem Sie das Cmdlet Get-CsUser für den letzten Benutzer der angegebenen Gesamtzahl erfolgreich ausführen.
  
#### <a name="contacts-creation-tab"></a>Registerkarte "Kontakte erstellen"

Auf dieser Registerkarte können Sie die Kontaktdetails der Benutzer zu Testzwecken zur Verfügung stellen.
  
![Benutzerbereitstellungstool mit der Registerkarte "Inhaltserstellung".](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Gehen Sie wie folgt vor, um die Kontakte von Benutzern zu konfigurieren:

1. Geben Sie im Feld "Durchschnittliche Kontakte pro **Benutzer"** die durchschnittliche Anzahl von Kontakten ein, die in Kontaktlisten für jeden Benutzer auffüllt werden soll.
    
2. Aktivieren Sie **das Kontrollkästchen Feste,** wenn Sie eine gleiche Anzahl von Kontakten für jeden Benutzer erstellen möchten. Wenn Sie die Anzahl der für Benutzer erstellten Kontakte variieren möchten, aktivieren Sie dieses Kontrollkästchen.
    
3. Geben Sie **im Feld "Durchschnittliche Kontaktgruppen pro Benutzer"** die Anzahl der Kontaktgruppen pro Benutzer ein. Diese Anzahl muss kleiner als **"Durchschnittliche Kontakte pro Benutzer" sein.**
    
4. Geben Sie **im Feld "Prozentsatz der Partnerkontakte/Poolübergreifende** Kontakte" eine Zahl zwischen 0 und 100 an. Dieser Prozentsatz der Kontakte wird mit den Verbundbenutzern erstellt.
    
5. Geben Sie **im Feld "Partner-/Poolübergreifendes** Benutzerpräfix" den Benutzernamen für Verbundbenutzer an, der den Kontaktlisten lokaler Benutzer hinzugefügt wird.
    
6. Geben Sie **im Feld "Partner-/Poolübergreifende Benutzer-SIP-Domäne"** den Namen der SIP-Domäne der Verbundbenutzer an.
    
7. Stellen **Sie auf der** Registerkarte "Benutzererstellung" sicher, dass die Informationen korrekt sind. Ihre Kontakte werden aus Werten auf der Registerkarte "Benutzererstellung" erstellt.
    
8. Klicken **Sie auf "Kontakte erstellen",** um mit der Erstellung des Kontakts zu beginnen. Dieser Vorgang kann mehrere Minuten dauern. Nach Abschluss des Vorgangs wird ein Dialogfeld mit der Meldung "Der Vorgang wurde erfolgreich abgeschlossen" angezeigt. Sie können die Kontakte überprüfen, die durch die Anmeldung als Benutzer erstellt wurden, der über die Registerkarte "Benutzererstellung" erstellt wurde.
    
    > [!NOTE]
    > Nachdem die Kontakte erstellt wurden, startet dieses Tool alle Front-End-Server im Zielpool neu. Je nachdem, wie viele Kontakte durch diesen Vorgang erstellt wurden, kann es länger (bis zu 2 Stunden) dauern, bis die Front-End-Server gestartet wurden. 
  
#### <a name="distribution-list"></a>Verteilerliste

Das Skype for Business Server 2015 Stress and Performance Tool kann die Verteilerlistenerweiterungsfunktion im Skype for Business 2015-Client simulieren. Sie können diesen Schritt überspringen, wenn Sie nicht beabsichtigen, die Erweiterung der Verteilerliste im Tool für die Benutzerbereitstellung zu aktivieren.
  
![Benutzerbereitstellungstool mit der Registerkarte "Erstellung von Verteilerlisten".](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
Auf der Registerkarte "Verteilerliste" können Sie DLs erstellen, die vom Stress and Performance Tool für das Feature "Verteilerlistenerweiterung" verwendet werden. Vor dem Erstellen von DLs muss Skype for Business Server 2015 bereitgestellt werden, einschließlich der Ausführung von ForestPrep. Wenn dies nicht geschieht, sind die DL-Attribute nicht im AD-Schema vorhanden, sodass das Tool keine DLs erstellen kann.
  
### <a name="to-configure-distribution-lists"></a>So konfigurieren Sie Verteilerlisten:

1. Geben Sie **im** Feld "Anzahl der Verteilerlisten" die Gesamtzahl der DLs an, die Sie erstellen möchten (hier wird empfohlen, mit einem Wert zu beginnen, der doppelt so viele Benutzer wie sie hat).
    
2. Geben Sie **im Feld "Verteilerlistenpräfix"** ein Präfix ein, das alle von Ihnen erstellten DLs enthalten, z. B. *testDL*  . Das heißt, bei 100 DLs sehen Ihre DL-Namen so aus: testDL0, testDL1 bis testDL99.
    
3. Geben Sie in das Feld "Minimale Elemente **in einem Dist.** List"-Feld die Mindestanzahl von Benutzern ein, die in jede DL aufgenommen werden soll.
    
4. Geben Sie im Feld "Maximale Anzahl Elemente **in einem Verteilerlistenfeld"** die maximale Anzahl von Benutzern ein, die in jeder DL hinzugefügt werden soll.
    
#### <a name="create-distribution-lists-button"></a>Schaltfläche "Verteilerlisten erstellen"

Wenn Sie auf die Schaltfläche "Verteilerlisten erstellen" klicken, fragt das Tool Active Directory ab, um zu sehen, ob Verteilerlisten, die mit dem Präfix und den Nummern übereinstimmen, bereits vorhanden sind. Das Tool erstellt alle DLs, die noch nicht vorhanden sind. Beim Hinzufügen von Mitgliedern zu diesen neu erstellten Verteilerlisten wählen sie die Benutzer aus dem Bereich aus, der auf der Registerkarte "Benutzererstellung" angegeben ist.
  
#### <a name="location-info-service-config-tab"></a>Registerkarte "Konfiguration des Standortinformationsdiensts"

Das Skype for Business Server 2015 Stress and Performance Tool kann auch Dummykonfigurationsdateien für den Standortinformationsdienst generieren. Beachten Sie, dass der Standortinformationsdienst in der Regel keine wesentlichen Auswirkungen auf die Leistung auf den Servern hat. 
  
![Benutzerbereitstellungstool mit der Registerkarte "Konfiguration des Standortinformationsdiensts".](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Wenn Sie dieses Feature testen möchten, füllen Sie die Werte im Formular aus, und klicken Sie auf die Schaltfläche "LIS-Konfigurationsdateien generieren", die erstellt wird. CSV-Dateien, die aufgerufen werden:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Verwenden Sie zum Importieren dieser Dateien in die LIS-Datenbank die folgenden PowerShell-Cmdlets:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Konfigurieren des Benutzerprofils
<a name="BKMK_UserProfile"> </a>

Nachdem Ihre Benutzer erstellt wurden (über das Benutzererstellungstool), können Sie Benutzerprofile mit dem Skype for Business Server 2015 Load Configuration Tool (UserProfileGenerator.exe) konfigurieren.
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ausführen des Tools für die Skype for Business Server 2015-Ladekonfiguration

Starten Sie das Ladekonfigurationstool (UserProfileGenerator.exe), und füllen Sie die Registerkarten aus. Dieses Tool erstellt ein Verzeichnis für jeden Clientcomputer, den Sie zum Ausführen der Simulationen benötigen. Jedes Clientverzeichnis enthält ein Skript zum Starten des Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe). Die folgenden Abschnitte enthalten Beispiele für das Ausfüllen der Felder auf den einzelnen Registerkarten des Skype for Business Server 2015 Load Configuration-Tools.
  
> [!IMPORTANT]
> Die im Tool für die Ladekonfiguration (UserProfileGenerator.exe) verwendeten benutzerspezifischen Werte müssen mit den im Skype for Business Server 2015 User Creation Tool (UserProvisioningTool.exe) für den Pool angegebenen Werten übereinstimmen. 
  
#### <a name="common-configuration-tab"></a>Registerkarte "Allgemeine Konfiguration"

Die **Registerkarte "Allgemeine Konfiguration"** des Tools zum Laden der Konfiguration wird unten angezeigt. Füllen Sie die Felder der Registerkarte "Allgemeine Konfiguration" aus, wie in den folgenden Schritten beschrieben.
  
![Die Registerkarte "Benutzerbereitstellung" mit der Registerkarte "Allgemeine Konfiguration".](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Geben Sie **im Feld** Anzahl der verfügbaren Computer die Anzahl der Computer ein, die Sie zum Ausführen des Stress and Performance Tool (LyncPerfTool.exe) verwenden möchten. Es wird empfohlen, einen Computer pro 4.500 Benutzer zu verwenden, der simuliert wird. Diese Anzahl kann jedoch variieren, wenn Sie die Auslastung verringern oder nur eine Teilmenge der verfügbaren Features des Tools verwenden (Ladeebenen werden auf der Registerkarte "Allgemeine Szenarien" festgelegt).
    
2. Geben Sie **im Feld "Präfix** für Benutzernamen" ein Präfix für das Feld "Benutzername" aller Benutzer ein. Der URI (Uniform Resource Identifier) für die Anmeldung ist: *UserPrefix[User Start Index... (Anzahl der Benutzer-1)] @User Domäne,*  z. B. myUser009@Contoso.com.
    
3. Geben Sie **im Feld "Kennwort für alle Benutzer"** das Kennwort ein, das beim Erstellen der Benutzer verwendet wird. Wenn Sie dieses Feld leer lassen, wird der Benutzername als Kennwort festgelegt.
    
4. Geben Sie **im Feld "Benutzerstartindex"** den Index des ersten zu konfigurierende Benutzers ein. Sie können unterschiedliche Bereiche für unterschiedliche Lasttypen oder Ladeebenen konfigurieren, aber Sie müssen das Tool für die Ladekonfiguration (UserProfileGenerator.exe) einmal für den bereich ausführen, den Sie konfigurieren möchten.
    
5. Geben Sie **im Feld "Anzahl der Benutzer"** die Gesamtzahl der Benutzer ein, die Sie konfigurieren möchten.
    
6. Geben Sie **im Feld "Benutzerdomäne"** die Domäne ein, die für den SIP-URI verwendet wird. Dies wird verwendet, um den SIP-URI jedes Benutzers für die Anmeldung beim Skype for Business Server 2015-Front-End-Server oder Standard Edition-Server zu erstellen, und kann sich von der Kontodomäne unterscheiden.
    
7. Geben Sie **im Feld "Kontodomäne"** die AD DS-Domänenanmeldung ein.
    
8. Geben Sie im Feld **"MPOP-Prozentsatz** ( Prozentsatz mehrerer Anwesenheitsteilnehmer) einen Wert für den Prozentsatz der Benutzer an, die von mehreren Computern oder Geräten angemeldet sind, z. B. 10 %.
    
9. Geben Sie die maximale Anzahl gleichzeitiger Endpunkte im Feld **"Pro Sekunde anmelden" (pro Instanz)** ein. Dies ist die maximale Anzahl von Anmeldungen für Ihre Benutzer, und die Empfehlung ist eine Rate von weniger als/gleich 2 pro Sekunde (<=2).
    
10. Geben Sie im Feld "Zugriffsproxy oder **Pool-FQDN"** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Servers ein, mit dem die Clients eine Verbindung herstellen möchten. Wenn sich die Benutzer extern anmelden, müssen Sie den Zugriffsproxy eingeben. Wenn die Benutzer intern sind, geben Sie den FQDN des Unternehmenspools oder Standard Edition-Servers an.
    
11. Geben Sie **im Feld "Port"** den Port ein, den Benutzer für SIP verwenden möchten (die Standardeinstellung ist hier 5061).
    
12. Geben Sie **für das Feld Einstellungen des externen** Netzwerkservers den Zugriffsproxy- oder Pool-FQDN und erneut den Port **an.** Diese Einstellungen werden nur für die Auslastungssimulation externer Endpunkte verwendet.
    
#### <a name="general-scenarios-tab"></a>Registerkarte "Allgemeine Szenarien"

![Load Configuration Tool mit der Registerkarte "Allgemeine Szenarien".](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Sie können die Ladeebenen und Parameter für jedes der allgemeinen Szenarien konfigurieren, indem Sie bestimmen, was Sie ausführen oder deaktivieren möchten. Hier sind Ihre allgemeinen Optionen:
  
> [!NOTE]
> Load level values for all fields but Local Information Services are **Disabled**, **Low**, **Medium**, **High**, or **Custom**. Wenn Sie eine Einstellung mit der Option "Deaktiviert" auswählen, werden konfigurationen für jeden Client generiert. Hohe Ergebnisse in der maximalen unterstützten Last auf dem Server; mittel ist 60 % der hohen Last; niedrig ist 30 %. 
  
- **Instant Messaging –** Dazu gehören Peer-zu-Peer- und Konferenzen. wählen Sie den entsprechenden Wert für "Ladeebene" aus.
    
- **Audiokonferenzen –** Wählen Sie eine Ladeebene nur für *Audiokonferenzen aus.* Peer-zu-Peer-Anrufe werden etwas später im Abschnitt **"Sprachszenarien"** erläutert. Öffnen Sie die **Registerkarte "Erweitert",** um MultiView zu aktivieren.
    
- **Anwendungsfreigabe –** Wählen Sie eine Ladeebene für die Anwendungsfreigabe aus.
    
- **Datenzusammenarbeit –** Wählen Sie eine Ladeebene für die Datenzusammenarbeit aus, einschließlich Datenkonferenzen.
    
- **Verteilerlistenerweiterung –** Klicken Sie **auf die** Schaltfläche "Erweitert", und füllen Sie das Feld mit denselben Werten aus, die auf der Registerkarte "DL" des Benutzererstellungstools (User Creation Tool, UserProvisioningTool.exe). Wählen Sie eine Ladeebene aus.
    
- **Adressbuchwebabfrage –** Dies ist der Adressbuch-Suchdienst und nicht der Download der Adressbuchdatei. Wenn Sie dies für Downloads von Adressbuchdatei aktivieren möchten, klicken Sie auf die Schaltfläche **"Erweitert",** und legen Sie **"EnableABSDownload"** auf "True" festgelegt. Geben Sie einen Wert für die Ladeebene an.
    
- **Reaktionsgruppendienst -** Klicken Sie **auf die Schaltfläche** "Erweitert", und geben Sie die URIs der Reaktionsgruppen an, die Sie bereits bei der Bereitstellung Reaktionsgruppendienst erstellt haben. Sie müssen mindestens eine Reaktionsgruppe auswählen. Trennen Sie die Reaktionsgruppen durch Semikolons, um mehr zu verwenden. Aktualisieren **Sie RGSUriSuffixStartIndex** und **RGSUriSuffixEndIndex** auf die tatsächlichen Werte. Wählen Sie eine Ladeebene aus.
    
- **Standortinformationsdienste –** Wählen Sie die Ladeebene "Aktiviert" oder "Deaktiviert" aus.
    
> [!NOTE]
> Jedes Szenario verfügt über eine Schaltfläche "Erweitert" und eine Reihe von Kontrollkästchen, die Variationen zur Standardeinstellung ermöglichen. 
  
- Wenn Sie  *Ad-hoc-Sitzungen*  auswählen, kann das Tool eine Simulation von Konferenzen generieren, die während der gesamten Stunde erstellt werden.
    
- Die Auswahl  *von "Large Conf"*  bedeutet, dass ein Großes Konferenzszenario simuliert wird.
    
-  *External*  weist das Tool an, auch externe Benutzer zu simulieren.
    
Diese Schaltflächen und Kontrollkästchen sind zusätzliche Werte, die für jedes Szenario spezifisch sind und das Verhalten des Stress and Performance Tool ändern und Anpassungen ermöglichen.
  
Wenn für jedes Szenario auf der Registerkarte "Allgemeine Szenarien" (mit Ausnahme der Standortinformationsdienste) der Wert "Auslastungsstufe" "Benutzerdefiniert" festgelegt **ist,** wird die Unterhaltungsrate mithilfe des entsprechenden Felds im Dialogfeld "Erweitert" berechnet. Der Feldname kann je nach Szenario variieren, aber die Feldbeschreibung gibt an: HINWEIS Diese Nummer wird nur verwendet, wenn "Benutzerdefiniert" im *Dropdownmenü ausgewählt ist.*
  
Die Werte **"Hoch",** **"Mittel"** und **"Niedrig"** ändern die Unterhaltungsraten pro Modalität im Einklang mit dem Benutzermodell, das eine Balance aller Szenarien ist. Wenn aufgrund eines Unterschieds bei der erwarteten Nutzung die Auslastungsstufe pro Modalität geändert werden muss, verwenden Sie eine benutzerdefinierte Unterhaltungsrate.
  
#### <a name="voice-scenarios-tab"></a>Registerkarte "Sprachszenarien"

Dies ist die Registerkarte für die Konfiguration aller Sprachszenarien.
  
![Registerkarte "Voice scenarios" des Ladekonfigurationstools.](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Folgende Optionen sind verfügbar:
  
- **VoIP –** Klicken Sie **auf die Schaltfläche** "Erweitert", und fügen Sie Werte für die Felder "PhoneAreaCode" und "LocationProfile" (Wählplan) hinzu. Sie geben auch einen Wert für den Ladeebenenwert an. Wenn Sie eine Auslastungsstufe für VoIP oder UC/PSTN-Gateway auswählen, wird eine Konfigurationsdatei für das Telefonnetz (Public Switched Telephone Network, PSTN) zu Unified Communications (UC) generiert, um externe Anrufe zu simulieren.
    
- **UC/PSTN-Gateway –** Sie müssen einen Wert für die Ladeebene auswählen, und wenn Sie einen anderen Wert als "Deaktiviert" auswählen, müssen Sie auch einen Wert für die Vorwahl für den Festnetzbereich durch Klicken auf die Schaltfläche "Erweitert" **eingeben.** Klicken **Sie unter vermittlungsserver** und PSTN auf "Hinzufügen". Stellen Sie sicher, dass eine Route für die Ortswahl konfiguriert ist.
    
    > [!TIP]
    > Sie können entweder die Skype for Business-Systemsteuerung oder die Skype for Business-Verwaltungsshell verwenden, um Ihre Konfiguration der Sprachroute zu überprüfen. 
  
- **Konferenz attendant -** Gibt einen Wert für die Ladeebene an. Durch einen anderen Wert als "Deaktiviert" wird das Feld **"Telefonnummer"** aktiviert. Geben Sie die Telefonnummer des automatische Telefonzentrale ein, das Sie verwenden möchten. Klicken **Sie auf "Erweitert",** und geben Sie einen Wert für das Feld **"LocationProfile"** ein.
    
- **Dienst zum Parken von Anrufen –** Hier müssen Sie eine Ladeebene liefern.
    
- **Vermittlungsserver und PSTN –** Jeder Vermittlungsserver, den Sie verwenden möchten, benötigt einen eigenen PSTN-Simulator. Nachdem Sie ermittelt haben, welchen Client Sie für den Simulator verwenden möchten, konfigurieren Sie Ihren Vermittlungsserver so, dass Anrufe an diesen Computer im konfigurierten PSTN-Simulator geroutet werden. Klicken Sie auf **die** Schaltfläche "Hinzufügen", um einen Wert für den Vermittlungsserver zu konfigurieren.
    
    > [!NOTE]
    > Neben jedem Szenario befindet sich eine Schaltfläche "Erweitert". Erweiterte Dialogfelder enthalten Einstellungen, die für jedes Szenario spezifisch sind und das Verhalten des Stress and Performance Tool ändern und anpassungen ermöglichen. > Für jedes Szenario auf der Registerkarte "Sprachszenarien" wird die Unterhaltungsrate mithilfe des entsprechenden Felds im Dialogfeld "Erweitert" berechnet, wenn der Wert der Auslastungsstufe "Benutzerdefiniert" ist. Der Feldname kann je nach Szenario variieren, aber die Feldbeschreibung gibt an: HINWEIS Diese Nummer wird nur verwendet, wenn "Benutzerdefiniert" im *Dropdownmenü ausgewählt ist.*
  
#### <a name="web-app-tab"></a>Registerkarte "Web App"

![Ladekonfigurationstool, Web-App-Registerkarte.](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App unterstützt Konferenzszenarien über den Unified Communications Web API (UCWA)-Server, der auf einem Front-End-Server installiert ist. Verwenden Sie die Registerkarte "Web App", um alle Web App-bezogenen Szenarien zu konfigurieren. Mögliche Optionen sind:
  
- **Allgemeine Web App-Einstellungen –** Klicken Sie **auf die Schaltfläche "Zusätzliche** Einstellungen", und legen Sie **"ReachTargetServerUrl"** auf die virtuelle IP (VIP) des Verzeichnispools der VIP des Front-End-Pools.
    
- **Anwendungsfreigabe –** Wählen Sie einen Wert für die Ladeebene aus.
    
- **Datenzusammenarbeit –** Wählen Sie einen Wert für die Ladeebene aus.
    
- **Instant Messaging –** Wählen Sie einen Wert für die Ladeebene aus.
    
- **Sprachkonferenzen –** Wählen Sie einen Wert für die Ladeebene aus.
    
> [!NOTE]
> Neben jedem Szenario befindet sich eine **Schaltfläche** "Erweitert". Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Stress and Performance Tool ändern und die Anpassung aktivieren.> Bei jedem Web App-Szenario wird der im Feld **"ConversationsPerHour"** angegebene Wert anstelle des Standardwerts verwendet, wenn die Ladeebene **"Benutzerdefiniert"** ist.
  
#### <a name="mobility-tab"></a>Registerkarte "Mobilität"

Verwenden Sie diese Registerkarte, um alle mobilitätsbezogenen Szenarien zu konfigurieren.
  
![Registerkarte "Mobilität" des Ladekonfigurationstools.](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Die folgenden Optionen stehen zur Verfügung:
  
- **Allgemeine Mobilitätseinstellungen –** Klicken **Sie auf zusätzliche Einstellungen,** und legen Sie das Feld "UcwaTargetServerUrl" auf die virtuelle IP (VIP) des Directorpools oder die VIP des Front-End-Pools.
    
- **Anwesenheit und P2P Instant Messaging/Audio –** Wählen Sie einen Wert für "Ladeebene" aus, um die Mobilitätssimulation zu aktivieren.
    
> [!NOTE]
> Neben jedem Szenario befindet sich eine **Schaltfläche** "Erweitert". Erweiterte Dialogfelder enthalten für jedes Szenario spezifische Werte, die das Verhalten des Belastungs- und Leistungstools ändern und die Anpassung aktivieren.> Wenn die Auslastungsstufe für jedes Mobilitätsszenario **"Benutzerdefiniert"** ist, wird der im Feld **"ConversationsPerHour"** angegebene Wert anstelle des Standardwerts verwendet.
  
#### <a name="summary-tab"></a>Registerkarte "Zusammenfassung"

Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für jedes der Szenarien verwendet werden sollen.
  
![Registerkarte "Zusammenfassung" des Tools "Konfiguration laden".](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
Die Registerkarte "Zusammenfassung" gibt an, welche Benutzer für jedes der Szenarien verwendet werden sollen. 
  
Es ist möglich, Benutzernummerbereiche manuell  zu konfigurieren, indem Sie das Kontrollkästchen "Benutzerdefinierte Benutzerbereichsgenerierung aktivieren" aktivieren und dann in der Tabelle mit dem Benutzerbereich, den Sie anpassen möchten, auf das Szenario doppelklicken.
  
Überprüfen **(RunClient.bat) Fügen** Sie beim Start die Anmeldeverzögerung hinzu, um Verzögerungen in den generierten Batchdateien zu enthalten, die der Anmelderate entsprechen. Dies ist hilfreich, um eine Serverüberlastung beim Anmelden einer großen Anzahl von Benutzern zu verhindern.
  
Klicken **Sie auf "Dateien** generieren", und wählen Sie den Ordner aus, in dem Sie die Konfiguration generieren möchten. Wenn Ihre Dateien erfolgreich erstellt wurden, wird ein Dialogfeld angezeigt.
  
![Das Meldungsfeld "Erfolgreich generierte Konfigurationsdateien laden". Klicken Sie einfach auf "OK".](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Ausführen von LyncPerfTool
<a name="BKMK_RunTool"> </a>

Sie müssen Benutzer, Kontakte und Szenarien erstellen, bevor Sie das Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool.exe) ausführen. Weitere Informationen zur Verwendung der Tools [](using-the-tool.md#BKMK_CreateUsersAndContacts) zum Ausführen dieser Aktionen finden Sie unter "Erstellen von Benutzern und Kontakten und Konfigurieren von [Benutzerprofilen"](using-the-tool.md#BKMK_UserProfile) weiter zuvor in diesem Artikel. Durch ausführen dieser Tools wird auch eine Datei generiert, die mit dem Stress and Performance Tool als Teil einer Batchdatei mit den erforderlichen Parametern ausgeführt wird.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ausführen des Skype for Business Server 2015 Stress and Performance-Tools

Das Tool für die Ladekonfiguration (UserProfileGenerator.exe) erstellt eine Batchdatei, mit der Sie das Stress and Performance Tool (LyncPerfTool.exe) ausführen können, indem Sie Leistungsindikatoren registrieren und die XML-Konfigurationsdatei laden. Die Batchdatei führt eine Instanz von LyncPerfTool.exe pro Konfigurationsdatei aus. Führen Sie zum Ausführen der Batchdatei die folgenden Schritte aus:
  
### <a name="run-the-stress-and-performance-test"></a>Ausführen des Stress- und Leistungstests

1. Kopieren Sie den Ordner mit den Konfigurationsordnern und -dateien in das Verzeichnis, LyncPerfTool.exe clientcomputer installiert ist. (Wenn Sie beispielsweise die Konfigurationsdateien im Ordner mit dem Namen 1.28_13.16.16 generiert haben, kopieren Sie diesen Ordner in den Ordner mit LyncPerfTool.exe Ordner. Tun Sie dies auf jedem Client.)
    
2. Navigieren Sie zum Clientordner, und führen Sie das **Batchskript "RunClient"** aus. Sie können in Windows Explorer auf die Batchdatei doppelklicken und alle Konfigurationsdateien für diesen Client ausführen. Sie können das Skript auch in einem Clientordner mit der folgenden Syntax ausführen:
    
   ```console
   RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
   ```

Um das Stress and Performance Tool direkt auszuführen, öffnen Sie eine Eingabeaufforderung, und geben Sie den folgenden Befehl an der Befehlszeile ein (und registrieren Sie die Leistungsindikatoren, wenn Sie dies zum ersten Mal tun, wie im Hinweis weiter unten in diesem Thema  `regsvr32 /i /n /s LyncPerfToolPerf.dll` gezeigt):
  
```console
LyncPerfTool.exe /file:IM_client0.xml
```

Damit das Tool die Werte in der Konfigurationsdatei anzeigen kann, fügen Sie den Parameter im vorherigen Befehl ein, damit er  `/displayfile` wie hier dargestellt aussieht:
  
```console
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Drücken Sie STRG+C, um den Vorgang zu beenden. 
  
> [!NOTE]
> Bevor Sie das Stress and Performance Tool direkt ausführen, müssen Sie die Leistungsindikatoren über den folgenden Befehl registrieren:  `regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Jede Instanz des Stress and Performance-Tools, das Sie starten, beginnt sofort mit der Anmeldung von Benutzern, in der Regel mit einer Rate von einem Benutzer pro Sekunde. 
  
Die Maximale Benutzer-Anmelderate für den Pool beträgt ca. 12 pro Sekunde. Dies bedeutet, dass Sie nicht mehr als 12 LyncPerfTool.exe gleichzeitig starten sollten, während sich Benutzer noch anmelden. 1.000 Benutzer müssen sich mit einer Sekunde vollständig anmelden.
  
## <a name="interpreting-the-results"></a>Interpretieren der Ergebnisse
<a name="BKMK_Interpret"> </a>

Das Skype for Business Server 2015 Stress and Performance Tool verfügt über viele Leistungsindikatoren, mit deren Hilfe Sie verstehen können, was der Client macht und ob Probleme auftreten.
  
### <a name="client-counters"></a>Clientindikatoren

Jede Instanz LyncPerfTool.exe ausgeführten Instanz verfügt über eine separate Instanz der Leistungsindikatoren. Jede Instanz wird nach ihrer Prozess-ID benannt. Wenn Clients überlastet sind, können weitere Probleme auftreten. So verhindern Sie diese Probleme:
  
- Überwachen Sie die CPU- und Speicherauslastung auf den Clientcomputern. Wenn die CPU konsistent über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.
    
- Wenn der Speicherbedarf hoch ist, können Probleme auftreten, wenn der Speicherplatz für die Seitendatei nicht mehr verfügbar ist. Stellen Sie sicher, dass die "Commit-Gebühr" nicht den Grenzwert auf dem Computer erreicht. Wenn arbeitsspeicherbeschränkungen gelten, sollten Sie die Größe der Seitendatei erhöhen oder die Anzahl der Benutzer reduzieren.
    
Hier ist eine Liste der wichtigsten Leistungsindikatoren:
  
**Allgemeine Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Zeit in Minuten  <br/> |Zeit, die seit dem Start des Prozesses auf sich gelaufen ist.  <br/> |
|Aktive Endpunkte  <br/> |Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.  <br/> |
|Fehlgeschlagene Anmeldungen  <br/> |Gesamtanzahl der Endpunkt-Anmeldefehler.  <br/> |
|Anmeldeversuche  <br/> |Gesamtanzahl der Endpunkt-Anmeldeversuche.  <br/> |
|Endpunkte getrennt  <br/> |Gesamtanzahl der Endpunkte, die getrennt wurden.  <br/> |
   
**Anwesenheitsinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|SetPresence Calls  <br/> |Gesamtanzahl der Anwesenheitsänderungsversuche. Informationen zu verschiedenen Arten von Anwesenheitsänderungen finden Sie im Leistungsindikator "SetPresence (Presence Type) Calls Performance Counter".  <br/> |
|NNN-Antworten für SetPresence  <br/> |Gesamtanzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|GetPresence Calls  <br/> |Gesamtanzahl der Anforderungsversuche beim Anfordern von Anwesenheitsversuchen.  <br/> |
|NNN-Antworten für GetPresence  <br/> |Gesamtanzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
   
**Informationen zum Adressbuchdienst**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|ABS Full/Delta File Downloads Attempted  <br/> |Gesamtanzahl der versuchten vollständigen oder Delta-Dateidownloadanforderungen.  <br/> |
|ABS Full/Delta File Downloads Succeeded  <br/> |Gesamtanzahl der versuchten vollständigen oder Delta-Dateidownloadanforderungen.  <br/> |
|Webdienstbezogene Leistungsindikatoren des Adressbuchwebabfragediensts  <br/> |Leistungsindikatoren zum Herunterladen von Adressbuchdatei.  <br/> |
|Versuchte WS-WS-Aufrufe  <br/> |Gesamtanzahl der versuchten Adressbuch-Webabfrage-Dienstanforderungen.  <br/> |
|ABS WS Calls Succeeded  <br/> |Gesamtanzahl der Anforderungen des Adressbuch-Webabfragediensts, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|Fehler bei ABS-WS-Aufrufen  <br/> |Gesamtanzahl der Anforderungen des Adressbuch-Webabfragediensts, die einen Fehlerantwortcode zurückgegeben haben.  <br/> |
   
> [!NOTE]
> Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Downloads von Adressbuchdienst-Dateien und Anforderungen des Adressbuch-Webabfragediensts verwendet werden. 
  
**Informationen zur Verteilerliste (DL)**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Versuchte Anrufe  <br/> |Gesamtanzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung( DLX).  <br/> |
|Anrufe erfolgreich  <br/> |Die Gesamtzahl der DLX-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.  <br/> |
|Fehler bei Anrufen  <br/> |Die Gesamtzahl der DLX-Webdienstanforderungen, die einen Fehlerantwortcode zurückgegeben haben.  <br/> |
   

  
> [!NOTE]
> Die unten aufgeführten Leistungsindikatoren melden Nummern für alle Voice over IP (VoIP)-Anrufe, einschließlich Anrufe an vermittlungsserver, A/V-Konferenzserver, Edgeserver, Reaktiongruppenanwendung und Konferenz-automatische Telefonzentrale, wenn diese Szenarien aktiviert sind. 
  
**Grundlegende Informationen zu VoIP**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtanzahl der derzeit laufenden eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Beendete Anrufe  <br/> |Gesamtanzahl der bereits beendeten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Abgelehnte Anrufe  <br/> |Die Gesamtzahl der eingehenden Sprachanrufe wurde abgelehnt.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Sprachanrufe.  <br/> |
|Eingehende/ausgehende Anrufe hergestellt  <br/> |Gesamtanzahl der eingehenden/ausgehenden Sprachanrufe, die eingerichtet wurden.  <br/> |
|Empfangene Anrufe NNN  <br/> |Gesamtanzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|VoIP-Passrate (%)  <br/> |Gesamtzahl der eingerichteten Anrufe/Gesamtzahl der versuchten Anrufe.  <br/> |
   
**Anrufinformationen des Reaktionsgruppesdiensts**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Die Gesamtzahl der aktiven Anrufe an die Reaktiongruppenanwendung.  <br/> |
|Versuchte Anrufe  <br/> |Gesamtanzahl der versuchten Anrufe.  <br/> |
   
**Chatanrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtanzahl der laufenden eingehenden/ausgehenden Sofortnachrichtenanrufe.  <br/> |
|Beendete Anrufe  <br/> |Gesamtanzahl der bereits beendeten eingehenden/ausgehenden Sofortnachrichtenanrufe.  <br/> |
|Empfangene Anrufe NNN  <br/> |Gesamtanzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|Empfangene/gesendete Nachrichten im Nachrichtennachrichten-E-Mail-Nachrichten  <br/> |Gesamtanzahl der empfangenen oder gesendeten Nachrichten für alle Sitzungen.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Chatanrufe.  <br/> |
|Eingehende/ausgehende Anrufe hergestellt  <br/> |Gesamtanzahl der eingehenden/ausgehenden Sofortnachrichtenanrufe, die eingerichtet wurden.  <br/> |
   
**Anrufinformationen zur App-Freigabe**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtanzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Beendete Anrufe  <br/> |Gesamtanzahl der bereits beendeten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Empfangene Anrufe NNN  <br/> |Gesamtanzahl der nnn-Antwortcodes, die vom Server empfangen wurden.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
|Eingehende/ausgehende Anrufe hergestellt  <br/> |Gesamtanzahl der eingehenden/ausgehenden Anwendungsfreigabeanrufe.  <br/> |
   
**Anrufinformationen für die Zertifizierungsstelle**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtanzahl der derzeit laufenden eingehenden/ausgehenden Festnetzanrufe.  <br/> |
|Beendete Anrufe  <br/> |Gesamtanzahl der bereits beendeten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
|Eingehende/ausgehende Anrufe versucht  <br/> |Gesamtanzahl der versuchten eingehenden/ausgehenden PSTN-Anrufe.  <br/> |
|Eingehende/ausgehende Anrufe hergestellt  <br/> |Gesamtanzahl der eingehenden/ausgehenden PSTN-Anrufe, die eingerichtet wurden.  <br/> |
   
**Konferenzinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Chatkonferenzen  <br/> |Gesamtanzahl der laufenden Chatkonferenzen.  <br/> |
|Aktive Audio-/Videokonferenzen  <br/> |Gesamtanzahl der laufenden Audio-/Videokonferenzen (A/V).  <br/> |
|Aktive Anwendungsfreigabekonferenzen  <br/> |Gesamtanzahl der laufenden Anwendungsfreigabekonferenzen.  <br/> |
|Anzahl der Teilnehmer  <br/> |Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.  <br/> |
|Fehler beim Konferenzzeitplan  <br/> |Gesamtanzahl der Fehler beim Planen einer Konferenz.  <br/> |
|Fehler beim Beitreten zu Einer Konferenz  <br/> |Gesamtanzahl der Fehler beim Versuch, eine Verbindung mit einer Konferenz herzustellen.  <br/> |
   
**UCWA Client Counters**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Gesamtanzahl der erfolgreichen IMMCU-Verknüpfungen  <br/> |Gesamtanzahl der instant Messaging-Konferenzen, die beigetreten sind.  <br/> |
|Gesamtanzahl der erfolgreichen DMCU-Verknüpfungen  <br/> |Gesamtanzahl der A/V-Konferenzen, die beigetreten sind.  <br/> |
   

