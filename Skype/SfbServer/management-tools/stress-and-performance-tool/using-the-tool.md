---
title: Using the Skype for Business Server 2015 Stress and Performance Tool
ms.author: heidip
author: microsoftheidi
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 93f42230-24a2-418d-9770-bf4670a9d78f
description: To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
ms.openlocfilehash: 5f73ef6733c2f09cdf3e06bc8a6495c743d8b423
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="using-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Using the Skype for Business Server 2015 Stress and Performance Tool
 
To run the Skype for Business Server 2015 Stress and Performance Tool, you'll need to be able to manage both users, contacts and user profiles, configure the tool for running, and then review the output or results that are produced by the tool.
  
There are four areas involved with running the Skype for Business Server 2015 Stress and Performance Tool (the executable is LyncPerfTool.exe):
  
- [Create Users and Contacts](using-the-tool.md#BKMK_CreateUsersAndContacts)
    
- [Configure User Profile](using-the-tool.md#BKMK_UserProfile)
    
- [Run LyncPerfTool](using-the-tool.md#BKMK_RunTool)
    
- [Interpreting the Results](using-the-tool.md#BKMK_Interpret)
    
## <a name="create-users-and-contacts"></a>Create Users and Contacts
<a name="BKMK_CreateUsersAndContacts"> </a>

You need to use the Skype for Business Server 2015 (SB 2015) User Provisioning Tool (UserProvisioningTool.exe) to create users and contacts for your stress and performance testing.
  
This is a list of helpful terms that might be useful as you read through the topics:
  
- **Organizational Unit** - The Active Directory Domain Services (AD DS) organizational unit (OU).
    
- **Federated / Cross Pool** - Users who can communicate with users from other Instant Messaging (IM) services.
    
- **Distribution Lists** - Or DLs. These are objects in AD DS that contain a list of AD DS users. They're used to facilitate communications across groups of people.
    
- **Location Info Service** - The Skype for Business Server 2015 service that, when it's enabled and configured per phone, allows for the retrieval of physical location for Enhanced 911 (E911) services.
    
- **U.S. Phone Numbers** - Phone numbers assigned to user in addition to the SIP URI that's used for routing inbound and outbound calls in Reverse Number Lookup (RNL).
    
### <a name="create-users-and-contacts-by-using-userprovisioningtoolexe"></a>Create Users and Contacts by using UserProvisioningTool.exe

> [!NOTE]
> Before you even begin, be absolutely sure you're logged in as a member of the Domain Admins security group to run this tool. You need to do this, because you're going to be creating Active Directory users. 
  
You have to use the Skype for Business Server User Provisioning Tool to create users and contacts for load simulation.
  
The **Skype for Business Server User Provisioning Tool** is installed with the **Skype for Business Server Stress and Performance Tool** package. Be sure that the package installer (CapacityPlanningTool.msi) has been run on the Front End Server or the Standard Edition server you intend to test.
  
You can start the Skype for Business Server User Provisioning Tool by running the file UserProvisioningTool.exe (located at %InstalledDirectory%LyncStressAndPerfTool\LyncStress) on the Front End Server or on the Standard Edition server.
  
> [!IMPORTANT]
> When you create a large number of users (for example, 10,000 or more), run the UserProvisioningTool.exe. You'll need to do this because the tool will be creating and configuring  *new*  AD users.
  
When the User Provisioning Tool opens, click Configuration and select the Load Configuration. 
  
To begin configuring users and contacts, load the default file included with the package, called "SampleData.xml". This will prepopulate fields with sample data that you'll need to change to make it relevant for your deployment.
  
If you have a preconfigured XML file that already contains your customized settings, you can load that file instead. Fill in the fields in the User Provisioning Tool, as described in the sections below.
  
### <a name="to-configure-server-options"></a>To configure server options:

1. In the **Front End Pool FQDN** field, type the fully qualified domain name (FQDN) of the Standard Edition server, or the Front End pool where you want to host the users.
    
2. In the **User Name Prefix** field, type a prefix that you want to use to bust your user names for testing purposes (such as "TestUser").
    
3. In the **Password** field, type a password that will be used across all the test user accounts.
    
4. In the **Account Domain** field, type the domain name of your current AD domain (the one in which you want to create your test users).
    
5. In the **Organizational Unit** field, type the name of the AD domain where you want to create these test users. (If the OU doesn't already exist, it'll be created for you).
    
6. In the **Phone Area Code** field, type the three-digit area code to be used across all test user accounts. Make certain that the area code you chose doesn't conflict with other users' area codes in AD.
    
7. Click to select the **Voice Enabled** check box, if you want to enable the test users for Enterprise Voice.
    
8. In the **Number of Users** field, give the total number of test users you want to create.
    
9. In the **Start Index** field, give the starting number that'll be used as a suffix to the user name prefix (for example, the prefix is "TestUser", and the first name will end in "0" in the example below.)
    
     ![Benutzerbereitstellungstool mit der Registerkarte für die Erstellung von Benutzern](../../media/591d8280-8979-4a8c-83bc-af126e87bf29.png)
  
#### <a name="create-users-button"></a>Schaltfläche für Benutzer erstellen

When you click on the **Create Users** button, the input parameters you've entered are validated. If there are any validation errors, you'll be prompted to fix them. Or, if all the values are correct, users will start appearing in AD (in whichever OU you specified). You'll see a progress bar at the bottom of the tool as it runs. Don't close the application while the progress bar is active.
  
User creation takes time, so please plan accordingly. This process can take anywhere from several minutes for a few users, to a few hours for a large number of users.
  
If you don't have access to the AD Domain Controller in your test environment, you can still validate user creation by logging in as one of the users in the range of users you specified to create. Remember to use the prefix, and the suffix, along with the @sipDomain as the username. Here is an example:  *TestUser20@contoso.net*  .
  
> [!NOTE]
> If the users already exist, clicking the Create Users button will update them with any configuration changes. 
  
#### <a name="delete-users-button"></a>Delete Users button

When you click on the **Delete Users** button, the tab's input parameters will be validated. If there are validation errors, you'll be prompted to fix them, and if the input values are correct, the specified test users will be disabled and deleted from Active Directory. Again, a progress bar will appear on the bottom of this tab, and you shouldn't close the application while the progress bar is active.
  
> [!NOTE]
> Only U.S.-formatted phone numbers are supported. Rufnummern werden immer, die Benutzern zugewiesen, und alle Benutzer, UserProvisioningTool.exe erstellt für Enterprise-VoIP standardmäßig aktiviert sind. Any scenarios that use the phone number, such as Conferencing Auto Attendant or UC-PSTN calls, use this phone number to properly route calls. For this reason,  *every user*  must have a *unique phone number*  .
  
> [!NOTE]
> **If you have to create users twice, the command will fail unless you use a different area code, or if the previous users have been disabled by using the Disable-CsUser cmdlet.**
  
> [!IMPORTANT]
> Before you create contacts, you first need to complete user replication (which is done from the Users tab). 
  
> [!IMPORTANT]
> If you've just created your users, you'll need to wait until Skype for Business Server replication completes and populates the user accounts in the database. **If the users haven't finished replicating, you'll see an error.** You'll know when users have finished replicating if the Skype for Business Server 2015 Front End service has started, or by successfully running the Get-CsUser cmdlet on the last user of the total number you specified.
  
#### <a name="contacts-creation-tab"></a>Erstellen der Registerkarte Kontakte

Auf dieser Registerkarte können Sie Details zu den Kontakten der Benutzer für die Tests geben.
  
![Das Benutzerbereitstellungstool zeigt die Registerkarte für die Erstellung von Inhalten.](../../media/dfb7fdf1-fb97-4e8e-8608-c4995f95dd5b.png)
  
### <a name="to-configure-users-contacts-do-the-following"></a>Zum Konfigurieren der Kontakte der Benutzer folgendermaßen Sie vor:

1. In the **Average Contacts per User** field, enter the average number of contacts to populate in contact lists for each user.
    
2. Aktivieren Sie das Kontrollkästchen **feste** , wenn Sie die gleiche Anzahl von Kontakten für jeden Benutzer erstellen möchten. Wenn Sie die Anzahl von Kontakten für Benutzer erstellt variieren möchten, deaktivieren Sie das Kontrollkästchen.
    
3. Geben Sie im Feld **Durchschnittliche Kontaktgruppen pro Benutzer** die Anzahl der Kontaktgruppen pro Benutzer. This number needs to be smaller than **Average Contacts per User**.
    
4. In the **Federated / Cross Pool Contacts Percentage** field, give a number between 0 and 100. Dieser Prozentsatz der Kontakte werden die Verbundbenutzer erstellt.
    
5. In the **Federated / Cross Pool User Prefix** field, give the username for federated users that will be added to the contact lists of local users.
    
6. Geben Sie im Feld **Federated / schneidet Pool Benutzer-SIP-Domäne** den SIP-Domänennamen des die Verbundbenutzer.
    
7. Registerkarte für **Die Erstellung des Benutzers** stellen Sie sicher, dass die Informationen korrekt sind. Ihre Kontakte werden von Werten auf der Registerkarte für die Erstellung des Benutzers erstellt.
    
8. Klicken Sie auf **Kontakte erstellen** , um die Erstellung Kontakt zu beginnen. Dieser Vorgang kann einige Minuten dauern. Nach Abschluss der ein Dialogfeld wird angezeigt, mit der Meldung "Vorgang wurde erfolgreich abgeschlossen." Sie können die Kontakte überprüfen, die erstellt wurden, indem Sie Anmelden als Benutzer, der über die Registerkarte für die Erstellung des Benutzers erstellt wurde.
    
> [!NOTE]
> Nachdem die Kontakte erstellt wurden, wird dieses Tool-Front-End-Servern im Zielpool neu gestartet. Es dauert länger (bis zu 2 Stunden) für den Front-End-Servern gestartet werden, abhängig davon, wie viele Kontakte durch diesen Vorgang erstellt wurden. 
  
#### <a name="distribution-list"></a>Verteilerliste

Die Skype für Business Server 2015 Stress and Performance-Tool können Sie die Funktion zur Erweiterung der Verteilung Liste (DL) in die Skype für Business 2015 Client simulieren. Sie können diesen Schritt überspringen, wenn Sie nicht die Erweiterung der Verteilerliste im Tool Benutzerbereitstellung aktivieren möchten.
  
![Benutzerbereitstellungstool zeigt Registerkarte für die Erstellung von Verteilerlisten](../../media/4b689306-70c4-4569-9842-15c73f038eb6.png)
  
Die Registerkarte Verteilerliste können Sie Verteilerlisten erstellen, die den Stress and Performance-Tool für die Erweiterung der Verteilerliste-Feature verwenden. Vor dem Erstellen von Verteilerlisten, muss Skype für Business Server 2015 bereitgestellt werden, einschließlich Ausführen von ForestPrep. Wenn dies nicht zur Verfügung, werden die DL-Attribute in Active Directory-Schema, damit das Tool zum Erstellen von Verteilerlisten nicht kann nicht vorhanden.
  
### <a name="to-configure-distribution-lists"></a>So konfigurieren Sie die Verteilerlisten:

1. Geben Sie im Feld **Anzahl der Verteilerlisten** die Gesamtzahl der Verteilerlisten, die Sie erstellen möchten (Hier wird empfohlen, dass Sie mit einem Wert beginnen, das Doppelte der Anzahl der Benutzer ist Ihnen.).
    
2. Geben Sie im Feld **Verteilung Liste Präfix** ein Präfix, die alle Verteilerlisten, die Sie erstellen müssen, beispielsweise *TestDL* aus. Das bedeutet, dass; auf 100 Verteilerlisten Ihre Namen DL werden wie folgt aussehen: testDL0, testDL1, bis zu testDL99.
    
3. Geben Sie im Feld **Minimale Elemente in einer Liste Verteilung** die minimale Anzahl von Benutzern in jeder DL platzieren.
    
4. Geben Sie im Feld **Maximale Anzahl von Elementen in einer Liste Verteilung** die maximale Anzahl von Benutzern in jeder DL hinzu.
    
#### <a name="create-distribution-lists-button"></a>Erstellen von Verteilerlisten Schaltfläche

Wenn Sie die Verteilerlisten erstellen-Schaltfläche klicken, fragt das Tool Active Directory, um festzustellen, ob entsprechen Verteilerlisten, das Präfix und Zahlen bereits vorhanden. Das Tool erstellt alle Verteilerlisten, die noch nicht vorhanden sind. Beim Hinzufügen von Mitgliedern zur diese neu erstellten Verteilerlisten wird es die Benutzer wählen Sie aus dem Bereich auf der Registerkarte für die Erstellung des Benutzers angegeben.
  
#### <a name="location-info-service-config-tab"></a>Dienstkonfiguration Info-Registerkarte Speicherort

Die Skype für Business Server 2015 Stress and Performance-Tool kann auch simulierte Konfigurationsdateien für den Standortinformationsdienst erstellen. Beachten Sie, dass die Standortinformationsdienst in der Regel beträchtliche Auswirkung auf den Servern nicht. 
  
![Benutzerbereitstellungstool zeigt die Registerkarte für die Konfiguration des Standortinformationsdiensts](../../media/227662a2-e0c3-4e34-ab54-5f1459344f30.png)
  
Wenn Sie zum Testen dieses Feature auswählen, füllen Sie die Werte im Formular, und klicken Sie auf die Schaltfläche LIS-Config-Dateien zu generieren, die erstellt wird. CSV-Dateien aufgerufen:
  
- LIS_Subnet.csv
    
- LIS_Switches.csv
    
- LIS_Ports.csv
    
- LIS_WAP.csv
    
Verwenden zum Importieren dieser Dateien in die LIS-Datenbank diese PowerShell-Cmdlets:
  
- Set-CsLisSubnet
    
- Set-CsLisSwitch
    
- Set-CsLisPort
    
- Set-CsWirelessAccessPoint
    
## <a name="configure-user-profile"></a>Konfigurieren des Benutzerprofils
<a name="BKMK_UserProfile"> </a>

Nachdem Ihre Benutzer (über die Benutzer Creation Tool) erstellt werden können Sie mit der Skype Business Server 2015 Load Konfigurationstool (UserProfileGenerator.exe) für Benutzerprofile konfigurieren.
  
### <a name="running-the-skype-for-business-server-2015-load-configuration-tool"></a>Ausführen der Skype Business Server 2015 Load-Konfigurationstools

Starten Sie das Konfigurationstool für Load (UserProfileGenerator.exe), und füllen Sie die Registerkarten. Dieses Tool erstellt ein Verzeichnis für die einzelnen Client Computern, die Sie benötigen, um Ihre Simulationen auszuführen. Im Lieferumfang von jedem Clientverzeichnis ist ein Skript zum Starten der Skype für Business Server 2015 Stress and Performance-Tool (LyncPerfTool.exe). In den folgenden Abschnitten werden Beispiele zum Ausfüllen der Felder auf den einzelnen Registerkarten von der Skype Business Server 2015 Load-Konfigurationstool für übergeben.
  
> [!IMPORTANT]
> Die benutzerspezifische Werte in das Load-Konfigurationstool (UserProfileGenerator.exe) verwendet, müssen die in der Skype für Business Server 2015 Benutzer Creation Tool (UserProvisioningTool.exe) angegebenen Werte für den Pool übereinstimmen. 
  
#### <a name="common-configuration-tab"></a>Registerkarte für allgemeine Konfiguration

Nachfolgend finden Sie die Registerkarte **Allgemeine Konfiguration** des Load-Konfigurationstools. Füllen Sie die Felder der Registerkarte Allgemeine Konfiguration, wie in den folgenden Schritten beschrieben.
  
![Die Registerkarte „Benutzerbereitstellung“ zeigt die Registerkarte für die allgemeine Konfiguration.](../../media/c25df343-3550-47fb-88e0-29194338fee2.png)
  
1. Geben Sie im Feld **Anzahl der verfügbaren Computer** die Anzahl der Computer, den, die Sie verwenden, um den Stress and Performance-Tool (LyncPerfTool.exe) ausführen möchten. Es wird empfohlen, dass Sie über einen Computer für jede 4500 Benutzer aus, die Sie benötigen simulieren werden verfügen, aber diese Nummer kann variieren, wenn Sie die Auslastung reduzieren, oder verwenden nur eine Teilmenge des Tools verfügbaren Features (– Auslastungsstufen werden auf der Registerkarte Allgemein Szenarien festgelegt).
    
2. Geben Sie im Feld **Präfix für den Benutzernamen** ein Präfix für im Benutzernamefeld aller Benutzer. In Uniform Resource Identifier (URI) protokolliert werden: *UserPrefix [Benutzer starten Index... (Anzahl der Benutzer-1)] @User Domäne* , z. B. myUser009@Contoso.com.
    
3. Geben Sie im Feld Kennwort **Kennwort für alle Benutzer** das Kennwort bei der Erstellung der Benutzer verwendet. Wenn Sie dieses Feld leer lassen wird als das Kennwort der Benutzernamen festgelegt.
    
4. Geben Sie im Feld **Benutzer starten Index** den Index des ersten Benutzers konfiguriert werden soll. Sie können unterschiedliche Bereiche für verschiedene Typen oder auslastungsebenen konfigurieren, aber einmal pro Bereich Sie konfigurieren möchten, führen Sie das Tool Load-Konfiguration (UserProfileGenerator.exe) muss.
    
5. Geben Sie im Feld **Anzahl der Benutzer** die Gesamtzahl der Benutzer, den, die Sie konfigurieren möchten.
    
6. Geben Sie im Feld **Domäne** die Domäne für den SIP-URI ein. Dies wird verwendet, um den SIP-URI der einzelnen Benutzer zur Anmeldung bei der Skype für Business Server 2015 Front-End-Server oder Standard Edition-Server zu erstellen, und kann von der Kontendomäne abweichen.
    
7. Geben Sie im Feld **Kontodomäne** der AD DS-Domäne anmelden.
    
8. Geben Sie im Feld **Prozentsatz MPOP** (Multiple Point of Presence Prozentsatz) den Wert für den Prozentsatz der Benutzer, die aus mehreren Computern oder Geräten, beispielsweise 10 Prozent angemeldet sind.
    
9. Geben Sie die maximale Anzahl von gleichzeitigen Endpunkte im Feld **Anmelden pro Sekunde (pro Instanz)** aus. Dies ist die maximale Anzahl der für Ihre Benutzer anzumelden und wird empfohlen, einen Satz von weniger als / gleich 2 pro Sekunde (< = 2).
    
10. Geben Sie im Feld **Zugriffsproxy oder Pool-FQDN** den vollqualifizierten Domänennamen (FQDN) des Servers den Clients für die Verbindung verwendet werden sollen. Wenn die Benutzer extern anmelden, müssen Sie den Zugriffsproxy geben. Wenn der Benutzer interne sind, geben Sie den FQDN des Enterprise-Pool oder Standard Edition-Servers.
    
11. Geben Sie im Feld **Port** den Port, die Sie Benutzer für SIP verwenden möchten (der Standardwert ist Port 5061).
    
12. Bereitstellen Sie für das Feld **Externen Netzwerk servereinstellungen** Zugriffsproxy oder FQDN des Pools und, erneut, den **Port**. Diese Einstellungen werden nur für externe Endpunkte Load Simulation verwendet.
    
#### <a name="general-scenarios-tab"></a>Registerkarte Allgemein Szenarien

![Lastkonfigurationstool zeigt Registerkarte „Allgemeine Szenarien“](../../media/45792e57-4322-4c20-956f-fe480b0de1a7.png)
  
Sie können die Parameter und – Auslastungsstufen konfigurieren, für jedes der allgemeinen Szenarien angebotenen bestimmen verfügbare ausgeführt oder deaktiviert lassen. Hier sind die allgemeinen Optionen aus:
  
> [!NOTE]
> Load Werte für alle Felder außer lokalen Informationsdienste sind **deaktiviert**, **Niedrig**, **Mittel**, **Hoch**oder **Benutzerdefiniert**. Wenn Sie eine beliebige Einstellung jedoch deaktiviert auswählen, werden Konfigurationen für jeden Client generiert. Besonders führt die maximale unterstützte Last auf dem Server. Mittel ist 60 % der hoher Last. niedriger ist 30 %. 
  
- **Instant Messaging-** Dazu gehören das Peer-zu-Peer- und Konferenzen. Wählen Sie den entsprechenden Wert für Auslastung.
    
- **Audiokonferenzen-** Wählen Sie eine Auslastung für Audiokonferenzen *nur* ein. Peer-zu-Peer-Anrufe werden etwas später im Abschnitt **VoIP-Szenarios** durchgeführt werden müssen. Öffnen Sie die Registerkarte **Erweitert** , um MultiView zu aktivieren.
    
- **Anwendungsfreigabe-** Wählen Sie eine Auslastung für die Anwendungsfreigabe.
    
- **Zusammenarbeit an Daten-** Wählen Sie eine Auslastung für die Zusammenarbeit an Daten, die Datenkonferenzen enthält.
    
- **Verteilerlistenerweiterung-** Klicken Sie auf die Schaltfläche **Erweitert** , und geben Sie in das Feld die gleichen Werte auf der Registerkarte DL des Tools erstellen Benutzer (UserProvisioningTool.exe) konfiguriert. Wählen Sie eine Auslastung.
    
- **Adressbuch-Webabfragedienst-** Dies ist der Lookup Adressbuchdienst statt-Datei herunterladen des Adressbuchs. Wenn Sie möchten, aktivieren Sie diese Option für adressbuchdownloads-Datei, klicken Sie auf die Schaltfläche **Erweitert** und **EnableABSDownload** auf True festgelegt. Geben Sie den Wert für die Auslastung.
    
- **Der Reaktionsgruppendienst-** Klicken Sie auf die Schaltfläche **Erweitert** , und geben Sie die URIs der reaktionsgruppen, die Sie bereits erstellt haben, wenn Sie die Reaktionsgruppendienst-Agents bereitgestellt. Sie müssen mindestens eine reaktionsgruppe auswählen. Wenn mehr verwenden möchten, trennen Sie die reaktionsgruppen durch Semikolons. Aktualisieren Sie den tatsächlichen Werten **RGSUriSuffixStartIndex** und **RGSUriSuffixEndIndex** . Wählen Sie eine Auslastung.
    
- **Speicherort von Informationsdiensten-** Wählen Sie eine Zugriffsebene Load entweder aktiviert oder deaktiviert.
    
> [!NOTE]
> Jedes der Szenarien verfügt über eine erweiterte Schaltfläche angezeigt wird, und eine Reihe von Kontrollkästchen, mit denen Variationen auf die Standardeinstellung. 
  
- Auswählen von *Ad-hoc-* ansetzt, kann das Tool zum Generieren von Simulation der Konferenzen, die die Stunde erstellt werden.
    
- Auswählen der Option *Große Conf* bedeutet, dass eine große Konferenz Szenario wird simuliert werden.
    
-  *Externe* weist das Tool können Sie auch das externe Benutzer.
    
Diese Schaltflächen und Kontrollkästchen wird sind zusätzliche Werte, die speziell für jedes Szenario und Ändern des Verhaltens der der Stress and Performance-Tool und Anpassung möglich.
  
Für jedes Szenario auf der Registerkarte Allgemein Szenarien (mit Ausnahme der Location Information Services) ist der Wert der Auslastung **benutzerdefinierte**, wird die Unterhaltung Rate berechnet verwenden das entsprechende Feld in im Dialogfeld Erweitert. Der Name des Felds abweichen, je nach Szenario, festlegen, sondern im Beschreibungsfeld wird: *Hinweis Diese Nummer wird nur verwendet werden, wenn aus dem Dropdown - Menü die Option Benutzerdefiniert ausgewählt ist* .
  
Die Werte **Hoch**, **Mittel**und **Niedrig**, werden die Unterhaltung Sätze pro Modalität in einer Reihe mit dem Benutzermodell ändern, die ein Gleichgewicht aller Szenarien ist. Ist die Auslastung pro Modalität wegen eines Unterschieds bei erwartete Verwendung ändern müssen, verwenden Sie eine benutzerdefinierte Unterhaltung Rate.
  
#### <a name="voice-scenarios-tab"></a>Registerkarte für VoIP-Szenarios

Dies ist die Registerkarte für die Konfiguration aller VoIP-bezogene Szenarien.
  
![Lastkonfigurationstool, Registerkarte für VoIP-Szenarien](../../media/042e406f-5156-4095-a4eb-6298f24bb51f.png)
  
Die Optionen sind:
  
- **VoIP-** Klicken Sie auf die Schaltfläche **Erweitert** , und fügen Sie Werte für die PhoneAreaCode und LocationProfile (Wählplan) Felder hinzu. Sie können auch einen Wert für Auslastung zuweisen. Wenn Sie eine Auslastung für VoIP oder UC-PSTN-Gateway aktiviert ist, klicken Sie dann eine Public switched Telephone Network (Telefonfestnetz PSTN), die unified Communications (UC) auswählen wird Konfigurationsdatei generiert, um externe Anrufe simulieren.
    
- **UC-PSTN-Gateway-** Sie müssen einen Wert Auslastung auswählen, und wenn Sie nichts auswählen andere als deaktiviert, haben Sie auch einen Wert für PSTN-Vorwahl angeben, indem Sie auf die Schaltfläche **Erweiterte** . Klicken Sie unter dem Vermittlungsserver und PSTN auf **Hinzufügen** . Stellen Sie sicher, dass Sie eine Route für die Ortskennzahl konfiguriert haben.
    
    > [!TIP]
    > Entweder der Skype können für Business-Systemsteuerung oder Skype für Business-Verwaltungsshell Sie Ihre VoIP-Route-Konfiguration überprüfen. 
  
- **Die Konferenzzentrale-** Geben Sie einen Wert für die Auslastung. Ein anderen Wert als deaktiviert das Feld **Telefonnummer** zu aktivieren. Geben Sie die Telefonnummer der automatischen Telefonzentrale, die Sie verwenden möchten. Klicken Sie auf **Erweitert** , und geben Sie einen Wert für das **LocationProfile** dar.
    
- **Parkplatz-Dienst - aufrufen** Hier geben Sie eine Auslastung.
    
- **Vermittlungsserver und PSTN-** Jeder Vermittlungsserver, die Sie verwenden möchten benötigt einen eigenen PSTN Simulator. Nachdem Sie den Client Sie nun für den Simulator verwenden ermittelt haben, Konfiguration Ihrer Mediation Server weitergeleitet Aufrufe von diesem Computer auf dem PSTN-Simulator Sie konfiguriert. Klicken Sie auf die Schaltfläche **Hinzufügen** , um einen Wert für den Vermittlungsserver konfigurieren.
    
    > [!NOTE]
    > Jedes Szenario verfügt über eine Schaltfläche Erweitert neben es sich befindet. Erweiterte Dialogfelder enthalten speziell für jedes Szenario Einstellungen, die das Verhalten von der Stress and Performance-Tool ändern und Anpassung aktivieren. > Für jedes Szenario auf der Registerkarte VoIP-Szenarien ist der Wert der Auslastung **benutzerdefinierte**, wird dann die Unterhaltung Rate berechnet mithilfe der im Dialogfeld Erweitert das entsprechende Feld. Der Name des Felds abweichen, je nach Szenario, festlegen, sondern im Beschreibungsfeld wird: *Hinweis Diese Nummer wird nur verwendet werden, wenn aus dem Dropdown - Menü die Option Benutzerdefiniert ausgewählt ist* .
  
#### <a name="web-app-tab"></a>Registerkarte für Web-App

![Lastkonfigurationstool, Registerkarte „Web App“](../../media/505b54ef-8140-4dec-a43e-08091f592b34.png)
  
Web App unterstützt konferenzszenarien über den Unified Communications Web API (UCWA)-Server, der auf einem Front-End-Server installiert ist. Verwenden Sie die Registerkarte Web App, um alle Web app-bezogenen Szenarien konfigurieren. Optionen sind verfügbar:
  
- **Allgemeine Web App-Einstellungen-** Klicken Sie auf **Weitere Einstellungen** , und legen Sie die **ReachTargetServerUrl** zum Verzeichnis Pool virtuelle IP (VIP) des Front-End-Pools VIP-Adresse.
    
- **Anwendungsfreigabe-** Wählen Sie einen Wert für die Auslastung.
    
- **Zusammenarbeit an Daten-** Wählen Sie einen Wert für die Auslastung.
    
- **Instant Messaging-** Wählen Sie einen Wert für die Auslastung.
    
- **Sprachkonferenzen-** Wählen Sie einen Wert für die Auslastung.
    
> [!NOTE]
> Jedes der Szenarien verfügt über eine Schaltfläche **Erweitert** neben es sich befindet. Erweiterte Dialogfenster enthalten Werte speziell für jedes Szenario, die das Verhalten der Stress and Performance-Tool zu ändern und aktivieren Sie Anpassung. > für jedes der Szenarien Web App, wenn die Auslastung **benutzerdefinierte**, ist dann der Wert angegeben in der ** ConversationsPerHour** Feld anstatt vom standardmäßigen verwendet wird.
  
#### <a name="mobility-tab"></a>Registerkarte für Mobilität

Mithilfe dieser Registerkarte Konfigurieren Sie alle der Mobilität bezogene Szenarien.
  
![Lastkonfigurationstool, Registerkarte für Mobilität](../../media/30af39c2-50ea-476a-8a56-ce2ddf08517e.png)
  
Die hier aufgeführten Optionen sind:
  
- **Allgemeine Mobilitätseinstellungen-** Klicken Sie auf **Zusätzliche Einstellungen** , und legen Sie das Feld UcwaTargetServerUrl auf Director-Pool virtuelle IP-Adresse (VIP) oder Front-End-Pool VIP-Adresse.
    
- **Anwesenheits- und Audio/P2P Instant Messaging-** Wählen Sie einen Wert für die Auslastung die Mobilität Simulation aktivieren.
    
> [!NOTE]
> Jedes der Szenarien verfügt über eine Schaltfläche **Erweitert** neben es sich befindet. Erweiterte Dialogfenster enthalten Werte speziell für jedes Szenario, die das Verhalten der Stress and Performance-Tool zu ändern und aktivieren Sie Anpassung. > für jedes der Szenarien Mobilität, wenn die Auslastung **benutzerdefinierte**, ist dann der Wert angegeben in der ** ConversationsPerHour** Feld anstatt vom standardmäßigen verwendet wird.
  
#### <a name="summary-tab"></a>Registerkarte "Zusammenfassung"

Die Registerkarte Zusammenfassung gibt an, welche Benutzer, die für jedes der Szenarien verwendet werden.
  
![Lastkonfigurationstool, Registerkarte „Zusammenfassung“](../../media/436fb3f2-d73e-402d-bc6e-e8a6740819d2.png)
  
Die Registerkarte Zusammenfassung gibt an, welche Benutzer, die für jedes der Szenarien verwendet werden. 
  
Es ist möglich, manuell konfigurieren Nummernbereiche Benutzer auswählen das Kontrollkästchen **Benutzerdefinierte Benutzer Bereich Generation aktivieren** , indem und klicken Sie dann auf das Szenario in der Tabelle, die der Benutzer Bereich aufweist, die Sie anpassen möchten.
  
Überprüfen Sie **(RunClient.bat)-Add - in Verzögerung beim Starten** , um Verzögerungen in der generierten Batchdateien entsprechen der Anmeldung Rate einschließen. Dies ist hilfreich, Server Überladung zu verhindern, dass bei der Anmeldung in eine große Anzahl von Benutzern.
  
Klicken Sie auf **Dateien zu generieren** , und wählen Sie den Ordner, in dem Sie die Konfiguration zu generieren möchten. Ein Dialogfeld wird angezeigt, wenn die Dateien erfolgreich erstellt wurden.
  
![Das Nachrichtenfeld „Lastkonfigurationsdateien erfolgreich erstellt“. Klicken Sie einfach auf „OK“.](../../media/c3c1d4a0-cb44-4837-8124-03354f5d9d8c.png)
  
## <a name="run-lyncperftool"></a>Führen Sie LyncPerfTool
<a name="BKMK_RunTool"> </a>

Sie müssen die Benutzer, Kontakte und Szenarien vor dem Ausführen der Skype für Business Server 2015 Stress and Performance-Tool (LyncPerfTool.exe) zu erstellen. Weitere Informationen zur Verwendung der Tools zur Durchführung dieser Aktionen finden Sie unter [Erstellen von Benutzern und Kontakten](using-the-tool.md#BKMK_CreateUsersAndContacts) und [Konfigurieren des Benutzerprofils](using-the-tool.md#BKMK_UserProfile) zuvor in diesem Artikel. Mit diesen Tools wird auch eine Datei generiert, die als Teil einer Batchdatei mit den erforderlichen Parametern enthalten mit der Stress and Performance-Tool ausgeführt wird.
  
### <a name="running-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Ausführen der Skype für Business Server 2015 Stress and Performance-tool

Das Load-Konfigurationstool (UserProfileGenerator.exe) erstellt eine Batchdatei, die Sie zu das Stress and Performance-Tool (LyncPerfTool.exe) von Leistungsindikatoren registriert, und laden die XML-Konfigurationsdatei ausführen kann. Die Batchdatei führt eine Instanz des LyncPerfTool.exe pro Konfigurationsdatei. Zum Ausführen die Batchdatei gehen Sie folgendermaßen vor:
  
### <a name="run-the-stress-and-performance-test"></a>Führen Sie den Stress and Performance test

1. Kopieren Sie den Ordner mit den Ordnern und Dateien innerhalb, zu dem Verzeichnis, das auf jedem Clientcomputer LyncPerfTool.exe verfügt. (Z. B., wenn Sie die Konfigurationsdateien im Ordner mit dem Namen 1.28_13.16.16 generiert, kopieren Sie diesen Ordner in den Ordner mit LyncPerfTool.exe darin. Hierzu auf jedem Client.)
    
2. Navigieren Sie zum Clientordner, und führen Sie die Batchdatei **RunClient** . Können Sie die Batchdatei in Windows Explorer doppelklicken, und es werden alle Konfigurationsdateien für den Client ausgeführt. Sie können auch das Skript aus einem Clientordner ausführen, mithilfe der folgenden Syntax:
    
  ```
  RunClient0.bat "C:\Program Files\Skype for Business Server 2015\LyncStressAndPerfTool\LyncStress" 
  ```

Zu das Stress and Performance-Tool direkt ausgeführt, öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie den folgenden Befehl an der Befehlszeile (und zum ersten Mal dabei unbedingt die Leistungsindikatoren registrieren `regsvr32 /i /n /s LyncPerfToolPerf.dll`, wie im Hinweis weiter unten in diesem Thema beschrieben):
  
```
LyncPerfTool.exe /file:IM_client0.xml
```

Wenn Sie das Tool die Werte in der Konfigurationsdatei angezeigt werden, gehören die `/displayfile` Parameter mit dem vorstehenden Befehl, so wie folgt aussieht:
  
```
LyncPerfTool.exe /file:IM_client0.xml /displayfile
```

Bis zum *Ende* des Prozesses drücken Sie STRG + C.
  
> [!NOTE]
> Bevor Sie das Stress and Performance-Tool direkt ausführen, müssen Sie die Leistungsindikatoren über den folgenden Befehl registrieren:`regsvr32 /i /n /s LyncPerfToolPerf.dll`
  
> [!NOTE]
> Jede Instanz der Stress and Performance-Tool, das gestartet werden sofort Anmelden bei Benutzern, die in der Regel mit einer Rate von einem Benutzer pro Sekunde. 
  
Peak Benutzer anmelden Rate für den Pool ist, etwa 12 pro Sekunde. Dies bedeutet, dass Sie nicht mehr als 12 LyncPerfTool.exe Instanzen gleichzeitig starten sollte während Benutzer weiterhin anmelden. Tausend Benutzer dauert ungefähr 20 Minuten vollständig anmelden über einen pro Sekunde.
  
## <a name="interpreting-the-results"></a>Ergebnisse interpretieren
<a name="BKMK_Interpret"> </a>

Die Skype für Business Server 2015 Stress and Performance-Tool hat viele Leistungsindikatoren, mit denen Sie wissen, was macht der Client und gibt an, ob es Probleme aufgetreten ist.
  
### <a name="client-counters"></a>Client-Leistungsindikatoren

Jede Instanz von LyncPerfTool.exe ausgeführt hat, eine separate Instanz der Leistungsindikatoren. Jede Instanz von dessen Prozess-ID mit dem Namen Andere Probleme können auftreten, wenn Clients überladenen sind. Um diese Probleme zu vermeiden:
  
- Überwachen der Verwendung von CPU und Arbeitsspeicher auf den Clientcomputern. Wenn die CPU über 90 Prozent liegt, reduzieren Sie die Anzahl der Benutzer.
    
- Wenn der Arbeitsspeicherbedarf hoch ist, können Sie Probleme auftreten ausführen, wenn die Auslagerungsdatei nicht mehr genügend Speicherplatz beginnt. Stellen Sie sicher, dass die Belastung Commit den Grenzwert auf dem Computer nicht erreichen ist. Wenn Sie in den Arbeitsspeicher-Grenzwerte ausführen sollten Sie die Größe der Auslagerungsdatei erhöhen oder verringern die Anzahl der Benutzer.
    
Hier wird eine Liste der wichtigsten Leistungsindikatoren:
  
**Allgemeine Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Zeit in Minuten  <br/> |Verstrichene Zeit seit dem Start des Prozesses.  <br/> |
|Active-Endpunkten  <br/> |Anzahl der Endpunkte, die aktuell auf dem Server verbunden sind.  <br/> |
|Fehlgeschlagene Anmeldeversuche  <br/> |Die Gesamtzahl der Endpunkt-Anmeldung Fehler.  <br/> |
|Anmeldeversuche  <br/> |Gesamtzahl der Endpunkt Anmeldeversuche.  <br/> |
|Endpunkte getrennt  <br/> |Die Gesamtzahl der Endpunkte, die getrennt wurden.  <br/> |
   
**Anwesenheitsinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|SetPresence Anrufe  <br/> |Gesamtanzahl der Anwesenheit ändern Versuche. Für verschiedene Typen von Anwesenheitsinformationen geändert wird finden Sie unter der Leistungsindikator Anrufe SetPresence (Anwesenheit Typ).  <br/> |
|NNN Antworten für SetPresence  <br/> |Gesamtzahl der Nnn-Antwortcodes vom Server empfangen.  <br/> |
|GetPresence Anrufe  <br/> |Gesamtanzahl der Get Anwesenheit Anforderung Versuche.  <br/> |
|NNN Antworten für GetPresence  <br/> |Gesamtzahl der Nnn-Antwortcodes vom Server empfangen.  <br/> |
   
**Adressbuchdienst-Informationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|ABS Full/Delta Dateidownloads versucht  <br/> |Gesamtzahl der vollständig oder Delta-Datei herunterladen Anforderungen versucht.  <br/> |
|ABS Full/Delta Dateidownloads erfolgreich  <br/> |Gesamtzahl der vollständig oder Delta-Datei herunterladen Anforderungen versucht.  <br/> |
|Adressbuch-Webabfrage Service weiterführende Leistungsindikatoren  <br/> |Adressbuch-Datei herunterladen zugehörige Leistungsindikatoren.  <br/> |
|ABS WS Anrufe versucht  <br/> |Gesamtzahl der Adressbuch-Webabfragedienst Serviceanfragen versucht.  <br/> |
|ABS WS-Aufrufe erfolgreich  <br/> |Gesamtzahl der Adressbuch-Webabfragedienst Anfragen, die einen erfolgreiche Antwortcode zurückgegeben.  <br/> |
|ABS WS Anrufe fehlgeschlagen  <br/> |Gesamtzahl der Adressbuch-Webabfragedienst Anfragen, die einen Fehler Antwortcode zurückgegeben.  <br/> |
   
> [!NOTE]
> Diese Kategorie umfasst Leistungsindikatoren zur Überwachung der Adressbuch-Dienst (ABS) Dateidownloads und Adressbuch-Webabfragedienst Serviceanfragen. 
  
**-Verteilerlisteninformationen (DL)**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Anrufe versucht  <br/> |Gesamtzahl der Verteilung Liste Erweiterung (DLX) webdienstanforderungen versucht.  <br/> |
|Erfolgreiche Anrufe  <br/> |Gesamtzahl der DLX webdienstanforderungen, die einen erfolgreiche Antwortcode zurückgegeben.  <br/> |
|Fehler bei  <br/> |Gesamtzahl der DLX webdienstanforderungen, die einen Fehler Antwortcode zurückgegeben.  <br/> |
   

  
> [!NOTE]
> Die Leistungsindikatoren unten aufgeführten Bericht Zahlen für alle VoIP über IP (VoIP) Aufrufe, einschließlich Anrufe auf Vermittlungsserver, A / V Conferencing Server, Edge-Server, reaktionsgruppenanwendung und die automatische Konferenztelefonzentrale, wenn diese Szenarien aktiviert sind. 
  
**Informationen zur VoIP Basic**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der eingehend/ausgehend VoIP Aufrufe aktuell laufenden.  <br/> |
|Anrufe beendet  <br/> |Gesamtzahl der eingehend/ausgehend Sprachanrufe bereits beendet.  <br/> |
|Anrufe abgelehnt  <br/> |Gesamtanzahl der eingehenden Sprachanrufe wurde abgelehnt.  <br/> |
|Eingehender/ausgehender Anrufe versucht  <br/> |Gesamtzahl der eingehend/ausgehend-VoIP-Anrufe versucht.  <br/> |
|Eingehender/ausgehender Anrufe eingerichtet  <br/> |Gesamtzahl der eingehend/ausgehend Sprachanrufe hergestellt.  <br/> |
|Empfangene Anrufe-NNN  <br/> |Gesamtzahl der Nnn-Antwortcodes vom Server empfangen.  <br/> |
|Übergeben Sie VoIP-Rate (%)  <br/> |Insgesamt ruft eingerichtet/insgesamt Anrufe versucht.  <br/> |
   
**Reaktionsgruppendienst Call Information**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtanzahl der aktiven Anrufe an die Anwendung "Reaktionsgruppe".  <br/> |
|Anrufe versucht  <br/> |Die Gesamtzahl der Anrufe versucht.  <br/> |
   
**Instant Messaging (IM) Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der laufenden eingehend/ausgehend instant messaging Anrufe.  <br/> |
|Anrufe beendet  <br/> |Gesamtzahl der instant messaging-Anrufe eingehend/ausgehend bereits beendet.  <br/> |
|Empfangene Anrufe-NNN  <br/> |Gesamtzahl der Nnn-Antwortcodes vom Server empfangen.  <br/> |
|Sofortnachrichten empfangen/gesendet.  <br/> |Gesamtzahl der Nachrichten empfangene oder gesendete für alle Sitzungen.  <br/> |
|Eingehender/ausgehender Anrufe versucht  <br/> |Gesamtzahl der eingehend/ausgehend instant messaging Anrufe versucht.  <br/> |
|Eingehender/ausgehender Anrufe eingerichtet  <br/> |Gesamtzahl der eingehend/ausgehend Sofortnachricht Anrufe eingerichtet.  <br/> |
   
**Informationen zur Freigabe App Anruf**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der laufenden eingehend/ausgehend Anwendungsfreigabe Anrufe.  <br/> |
|Anrufe beendet  <br/> |Gesamtzahl der eingehend/ausgehend Anwendungsfreigabe Anrufe bereits beendet.  <br/> |
|Empfangene Anrufe-NNN  <br/> |Gesamtzahl der Nnn-Antwortcodes vom Server empfangen.  <br/> |
|Eingehender/ausgehender Anrufe versucht  <br/> |Gesamtzahl der eingehend/ausgehend Anwendungsfreigabe Anrufe versucht.  <br/> |
|Eingehender/ausgehender Anrufe eingerichtet  <br/> |Gesamtzahl der eingehend/ausgehend Anwendungsfreigabe Anrufe eingerichtet.  <br/> |
   
**CAA Anrufinformationen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Anrufe  <br/> |Gesamtzahl der eingehend/ausgehend Telefonfestnetz (PSTN) Aufrufe aktuell laufenden.  <br/> |
|Anrufe beendet  <br/> |Gesamtzahl der PSTN-Anrufe eingehend/ausgehend bereits beendet.  <br/> |
|Eingehender/ausgehender Anrufe versucht  <br/> |Gesamtzahl der eingehende/ausgehende PSTN-Anrufe versucht.  <br/> |
|Eingehender/ausgehender Anrufe eingerichtet  <br/> |Gesamtzahl der eingehende/ausgehende PSTN-Anrufe eingerichtet.  <br/> |
   
**Informationen zu Konferenzen**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Aktive Instant Messaging-Konferenzen  <br/> |Gesamtzahl der laufende instant messaging-Konferenzen.  <br/> |
|Aktiven Audio-/Videokonferenzen  <br/> |Gesamtzahl der laufenden Audio/Video (A / V) Konferenzen.  <br/> |
|Aktive Anwendung Freigeben von Konferenzen  <br/> |Gesamtzahl der laufende Konferenzen mit Anwendungsfreigabe.  <br/> |
|Die Anzahl der Teilnehmer  <br/> |Gesamtzahl der Teilnehmer, die aktuell mit Konferenzen verbunden sind.  <br/> |
|Konferenz Zeitplan Fehler  <br/> |Die Gesamtzahl der Fehler beim Versuch, eine Konferenz zu planen.  <br/> |
|Ausfall der Konferenz teilnehmen  <br/> |Die Gesamtzahl der Fehler beim Versuch, eine Verbindung zu einer Konferenz.  <br/> |
   
**UCWA-Client-Leistungsindikatoren**

|**Leistungsindikator**|**Beschreibung**|
|:-----|:-----|
|Gesamtzahl der IMMCU Joins erfolgreich  <br/> |Gesamtzahl der instant messaging-Konferenzen verbunden.  <br/> |
|Gesamtzahl der DMCU Joins erfolgreich  <br/> |Gesamtzahl der A / V-Konferenzen beigetreten ist.  <br/> |
   

