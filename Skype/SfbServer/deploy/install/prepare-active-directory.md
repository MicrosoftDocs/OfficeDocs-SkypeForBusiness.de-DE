---
title: Vorbereiten von Active Directory für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Summary: Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Vorbereiten von Active Directory für Skype for Business Server 2015
 
**Summary:** Learn how to prepare your Active Directory domain for an installation of Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype for Business Server works closely with Active Directory. You must prepare the Active Directory domain to work with Skype for Business Server. This process is accomplished in the Deployment Wizard and is only done once for the domain. This is because the process creates groups and modifies the domain, and you need to do that only once. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Preparing Active Directory is step 4 of 8. For more information about planning for Active Directory, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![Übersichtsdiagramm](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Vorbereiten von Active Directory

Skype for Business Server 2015 is tightly integrated with Active Directory Domain Services (AD DS). Before Skype for Business Server 2015 can be installed for the first time, Active Directory must be prepared. The section of the Deployment Wizard titled **Prepare Active Directory** prepares the Active Directory environment for use with Skype for Business Server.
  
> [!NOTE]
> Skype for Business Server 2015 uses (AD DS) to track and communicate with all of the servers in a topology. Every server must be joined to the domain so that Skype for Business Server can work properly. 
  
> [!IMPORTANT]
> Das Verfahren zur Vorbereitung von Active Directory muss nur einmal für jede Domäne in der Bereitstellung durchgeführt werden. 
  
Schauen Sie sich das Video mit den Schritten zum **Vorbereiten von Active Directory** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Vorbereiten von Active Directory mithilfe des Bereitstellungs-Assistenten

1. Melden Sie sich als Benutzer mit den Anmeldeinformationen für den Schemaadministrator der Active Directory-Domäne an.
    
2. Open Skype for Business Server Deployment Wizard.
    
    > [!TIP]
    > If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the AD DS user who ran the step. For example, if the user logged on as the domain administrator in the domain, contoso.local, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Klicken Sie auf den Link **Active Directory vorbereiten**.
    
4. **Step 1: Prepare schema**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 1, zu dem Sie über das Dropdownmenü unter dem Titel „Schritt 1“ gelangen.
    
    b. Klicken Sie in Schritt 1 auf **Ausführen**, um den Assistenten zum Vorbereiten des Schemas zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Nach der Vorbereitung des Schemas können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    e. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten des Schemas zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
5. **Step 2: Verify replication of schema partition**
    
    a. Melden Sie sich beim Domänencontroller der Domäne an.
    
    b. Öffnen Sie im Dropdownmenü **Extras** im **Server-Manager** die Option **ADSI-Editor**.
    
    c. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
    d. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.
    
    e. Suchen Sie unter dem Schemacontainer nach **CN=ms-RTC-SIP-SchemaVersion**. Wenn dieses Objekt vorhanden ist sowie der Wert des Attributs **rangeUpper** 1150 und der Wert des Attributs **rangeLower** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht diesen Werten entsprechen, wurde das Schema nicht geändert oder repliziert.
    
6. **Step 3: Prepare current forest**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 3, zu der Sie über das Dropdownmenü unter dem Titel „Schritt 3“ gelangen.
    
    b. Klicken Sie in Schritt 3 auf **Ausführen**, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Specify the domain where the universal groups will be created. If the server is part of the domain, you can choose **Local domain**, and click **Next**.
    
    e. Nach der Vorbereitung der Gesamtstruktur können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    f. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
    g. Click **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    h. Type the command Get-CsAdForest, and press **Enter**.
    
    i. If the result is **LC_FORESTSETTINGS_STATE_READY**, the forest has successfully been prepared, as shown in the figure.
    
     ![Replikation der Gesamtstruktur überprüfen.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Step 4: Verify replication of the global catalog**
    
    a. Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.
    
    b. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
    c. Klicken Sie im linken Fensterbereich auf den Container **Users** und navigieren Sie im rechten Fensterbereich zur universellen Gruppe **CsAdministrator**. Wenn die Gruppe „CsAdministrator“ vorhanden ist (neben acht weiteren neuen universellen Gruppen, deren Namen mit „Cs“ beginnen), war die Replikation von Active Directory erfolgreich.
    
    d. Wenn die Gruppen nicht vorhanden sind, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Fensterbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
8. **Step 5: Prepare the current domain**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 5.
    
    b. Klicken Sie in Schritt 5 auf **Ausführen**, um den Assistenten zum Vorbereiten der aktuellen Domäne zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Domäne in der Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Nach der Vorbereitung der Domäne können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    e. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten der aktuellen Domäne zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
    These steps must be completed in every domain where Skype for Business Server objects are found, otherwise services might not start. This includes any type of Active Directory object, such as users, contact objects, administrative groups, or any other type of object. You can use Set-CsUserReplicatorConfiguration -ADDomainNamingContextList to add only the domains with Skype for Business Server objects, if needed.
    
9. **Step 6: Verify replication in the domain**
    
    a. Click the **Skype for Business Server Management Shell** from the **Apps** page to launch PowerShell.
    
    b. Use the command Get-CsAdDomain to verify replication within the domain.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Wenn Sie den Parameter „Domain“ nicht angeben, wird die lokale Domäne verwendet. 
  
    Beispiel für die Ausführung des Befehls für die Domäne „contoso.local“:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > Mit dem Parameter „GlobalSettingsDomainController“ können Sie den Speicherort der globalen Einstellungen angeben. Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist bei Upgradebereitstellungen typisch, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer Gesamtstruktur der Active Directory-Domänendienste. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    c. If the result is **LC_DOMAINSETTINGS_STATE_READY**, the domain has successfully replicated.
    
10. **Step 7: Add users to provide administrative access to the Skype for Business Server Control Panel**
    
    a. Melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ oder „RTCUniversalServerAdmins“ an.
    
    b. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne und klicken Sie auf den Container **Users**. Klicken Sie dann mit der rechten Maustaste auf „CSAdministrator“ und wählen Sie **Eigenschaften** aus.
    
    c. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
    d. On the **Members** tab, click **Add**. In **Select Users, Contacts, Computers, Service Accounts, or Groups**, locate the **Enter the object names to select**. Type the user name(s) or group name(s) to add to the group CSAdministrators. Klicken Sie anschließend auf **OK**.
    
    e. On the **Members** tab, confirm that the users or groups that you selected are present. Klicken Sie anschließend auf **OK**.
    
    > [!CAUTION]
    > The Skype for Business Server Control Panel is a role-based access control tool. Membership in the CsAdministrator group gives a user who is using the Skype for Business Server Control Panel full control for all configuration functions available. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. For details on the roles available, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Note that users do not have to be enabled for Skype for Business Server in order to be made members of the management groups. 
  
    > [!CAUTION]
    > To help retain security and role-based access control integrity, add users to the groups that define what role the user performs in management of the Skype for Business Server deployment. 
  
11. Log off, and then log back on to Windows so that your security token is updated with the new Skype for Business Server security group, and then reopen the Deployment Wizard.
    
12. Vergewissern Sie sich, dass neben **Active Directory vorbereiten** ein grünes Häkchen angezeigt wird. Dies gibt an, dass der Vorgang erfolgreich war (siehe Abbildung).
    
     ![Vorbereiten von Active Directory abgeschlossen.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

