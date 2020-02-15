---
title: Vorbereiten Active Directory für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Active Directory Domäne für eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018176"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Vorbereiten Active Directory für Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Ihre Active Directory Domäne für eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory Domäne so vorbereiten, dass Sie mit Skype for Business Server arbeitet. Dieser Vorgang wird im Bereitstellungs-Assistenten ausgeführt und nur einmal für die Domäne ausgeführt. Dies liegt daran, dass der Prozessgruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal durchführen. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Vorbereiten Active Directory ist Schritt 4 von 8. Weitere Informationen zur Planung von Active Directory finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) -oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Übersicht Diagramm](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Vorbereiten von Active Directory

Skype for Business Server ist eng mit Active Directory-Domänendienste (AD DS) integriert. Bevor Skype for Business Server zum ersten Mal installiert werden kann, müssen Active Directory vorbereitet werden. Der Abschnitt mit dem Titel **Prepare Active Directory** bereitet die Active Directory Umgebung für die Verwendung mit Skype for Business Server vor.
  
> [!NOTE]
> Skype for Business Server verwendet (AD DS), um alle Server in einer Topologie nachzuverfolgen und mit Ihnen zu kommunizieren. Der Großteil dieser Server muss der Domäne beigetreten sein, damit Skype for Business Server ordnungsgemäß funktionieren kann. Beachten Sie, dass Server wie Edge und Reverse Proxy nicht einer Domäne angehören sollten.
  
> [!IMPORTANT]
> Die Vorbereitung Active Directory Prozedur sollte nur einmal für jede Domäne in der Bereitstellung ausgeführt werden. 
  
Video Schritte zum **vorbereiten Active Directory**:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Vorbereiten Active Directory aus dem Bereitstellungs-Assistenten

1. Melden Sie sich als Benutzer mit den Anmeldeinformationen des Schema Administrators für die Active Directory Domäne an.
    
2. Öffnen Sie Skype for Business Server Bereitstellungs-Assistenten.
    
    > [!TIP]
    > Wenn Sie die Protokolldateien überprüfen möchten, die vom Skype for Business Server-Bereitstellungs-Assistenten erstellt wurden, finden Sie diese auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Benutzerverzeichnis des AD DS Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne "contoso. local" angemeldet hat, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp. 
  
3. Klicken Sie auf den Link **Prepare Active Directory** .
    
4. **Schritt 1: Vorbereiten des Schemas**
    
    a. Lesen Sie die Voraussetzungen für Schritt 1, auf die zugegriffen werden kann, indem Sie auf die Dropdownliste unter dem Titel Schritt 1 klicken.
    
    b. Klicken Sie in Schritt 1 auf **Ausführen** , um den Assistenten zum Vorbereiten des Schemas zu starten.
    
    c. Beachten Sie, dass die Prozedur nur einmal für jede Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **weiter**.
    
    d. Nachdem das Schema erstellt wurde, können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen**klicken. 
    
    e. Klicken Sie auf **Fertig stellen** , um den Assistenten zum Vorbereiten des Schemas zu schließen, und kehren Sie zur Active Directory Schritte vorbereiten zurück.
    
5. **Schritt 2: Überprüfen der Replikation der Schemapartition**
    
    a. Melden Sie sich beim Domänencontroller für die Domäne an.
    
    b. Öffnen Sie die **ADSI-Bearbeitung** im Dropdownmenü **Tools** im **Server-Manager**.
    
    c. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
    d. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus, und klicken Sie auf **OK**.
    
    e. Suchen Sie unter dem Schemacontainer nach **CN = ms-RTC-SIP-Schemaversion**. Wenn dieses Objekt vorhanden ist und der Wert des **rangeUpper** -Attributs 1150 ist und der Wert des **rangeLower** -Attributs 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht wie angegeben sind, wurde das Schema nicht geändert oder nicht repliziert.
    
6. **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur**
    
    a. Lesen Sie die Voraussetzungen für Schritt 3, auf die zugegriffen werden kann, indem Sie auf die Dropdownliste unter dem Titel Schritt 3 klicken.
    
    b. Klicken Sie in Schritt 3 auf **Ausführen** , um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu starten.
    
    c. Beachten Sie, dass die Prozedur nur einmal pro Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **weiter**.
    
    d. Geben Sie die Domäne an, in der die universellen Gruppen erstellt werden sollen. Wenn der Server Teil der Domäne ist, können Sie die Option **lokale Domäne**auswählen und auf **weiter**klicken.
    
    e. Nachdem die Gesamtstruktur erstellt wurde, können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen**klicken. 
    
    f. Klicken Sie auf **Fertig stellen** , um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu schließen, und kehren Sie zur Active Directory Schritte vorbereiten zurück.
    
    g. Klicken Sie auf der Seite **apps** auf **Skype for Business Server Management Shell** , um PowerShell zu starten.
    
    h. Geben Sie den Befehl Get-CsAdForest ein, und drücken **Sie die EINGABETASTE**.
    
    Ich. Wenn das Ergebnis **LC_FORESTSETTINGS_STATE_READY**ist, wurde die Gesamtstruktur erfolgreich vorbereitet, wie in der Abbildung dargestellt.
    
     ![Überprüfen Sie die Gesamtstruktur Replikation.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Schritt 4: Überprüfen der Replikation des globalen Katalogs**
    
    a. Öffnen Sie auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde, **Active Directory-Benutzer und -Computer**.
    
    b. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
    c. Klicken Sie im linken Bereich auf den Container **Benutzer** , und suchen Sie im rechten Bereich nach der universellen Gruppe **CsAdministrator** . Wenn CsAdministrator (neben anderen neuen universellen Gruppen, die mit CS beginnen) vorhanden ist, wurde die Active Directory Replikation erfolgreich ausgeführt.
    
    d. Wenn die Gruppen noch nicht vorhanden sind, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Bereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
8. **Schritt 5: Vorbereiten der aktuellen Domäne**
    
    a. Lesen Sie die erforderlichen Informationen zu Schritt 5.
    
    b. Klicken Sie in Schritt 5 auf **Ausführen** , um den Assistenten zum Vorbereiten der aktuellen Domäne zu starten.
    
    c. Beachten Sie, dass die Prozedur nur einmal für jede Domäne in der Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **weiter**.
    
    d. Nachdem die Domäne vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen**klicken. 
    
    e. Klicken Sie auf **Fertig stellen** , um den Assistenten zum Vorbereiten der aktuellen Domäne zu schließen, und kehren Sie zur Active Directory Schritte vorbereiten zurück.
    
    Diese Schritte müssen in jeder Domäne abgeschlossen werden, in der Skype for Business Server-Objekte gefunden werden, andernfalls werden Dienste möglicherweise nicht gestartet. Dies umfasst alle Arten von Active Directory-Objekten wie Benutzer, Kontaktobjekte, administrative Gruppen oder andere Objekttypen. Bei Bedarf können Sie mithilfe von "CsUserReplicatorConfiguration-ADDomainNamingContextList" nur die Domänen mit Skype for Business Server-Objekten hinzufügen.
    
9. **Schritt 6: Überprüfen der Replikation in der Domäne**
    
    a. Klicken Sie auf der Seite **apps** auf die **Skype for Business Server Verwaltungsshell** , um PowerShell zu starten.
    
    b. Verwenden Sie den Befehl Get-CsAdDomain, um die Replikation innerhalb der Domäne zu überprüfen.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Wenn Sie den Parameter "Domain" nicht angeben, wird die lokale Domäne verwendet. 
  
    Beispiel für die Ausführung des Befehls für die Domäne "contoso. local":
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Mithilfe des Parameters "globalsettingsdomaincontroller" können Sie angeben, wo globale Einstellungen gespeichert werden. Wenn Ihre Einstellungen im System Container gespeichert sind (typisch bei Upgrade-Bereitstellungen, in denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis der AD DS Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    c. Wenn das Ergebnis **LC_DOMAINSETTINGS_STATE_READY**ist, wurde die Domäne erfolgreich repliziert.
    
10. **Schritt 7: Hinzufügen von Benutzern zum Bereitstellen von administrativem Zugriff auf die Skype for Business Server-Systemsteuerung**
    
    a. Melden Sie sich als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
    b. Öffnen Sie **Active Directory Benutzer und Computer**, erweitern Sie Ihre Domäne, klicken Sie auf den Container **Benutzer** , klicken Sie mit der rechten Maustaste auf CSAdministrator, und wählen Sie **Eigenschaften**aus.
    
    c. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
    d. Klicken Sie auf der Registerkarte **Mitglieder** auf **Hinzufügen**. Wählen Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen**die Option **Geben Sie die zu verwendenden Objektnamen ein ein**. Geben Sie die Benutzernamen oder Gruppennamen ein, die der Gruppe CSAdministrators hinzugefügt werden sollen. Klicken Sie auf **OK**.
    
    e. Überprüfen Sie auf der Registerkarte **Mitglieder** , ob die ausgewählten Benutzer oder Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
    > [!CAUTION]
    > Die Skype for Business Server-Systemsteuerung ist ein Tool für die rollenbasierte Zugriffssteuerung. Die Mitgliedschaft in der CsAdministrator-Gruppe gibt einem Benutzer, der die Skype for Business Server-Systemsteuerung für alle verfügbaren Konfigurationsfunktionen verwendet, den Vollzugriff. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Ausführliche Informationen zu den verfügbaren Rollen finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Beachten Sie, dass Benutzer nicht für Skype for Business Server aktiviert werden müssen, um Mitglieder der Verwaltungsgruppen zu sein. 
  
    > [!CAUTION]
    > Um die Integrität von Sicherheit und rollenbasierter Zugriffssteuerung zu verbleiben, fügen Sie Benutzer zu den Gruppen hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server-Bereitstellung ausführt. 
  
11. Melden Sie sich ab, und melden Sie sich dann wieder bei Windows an, damit Ihr Sicherheitstoken mit der neuen Skype for Business Server Sicherheitsgruppe aktualisiert wird, und öffnen Sie dann den Bereitstellungs-Assistenten erneut.
    
12. Stellen Sie sicher, dass Sie ein grünes Häkchen neben **Prepare Active Directory** , um den Erfolg zu bestätigen, wie in der Abbildung dargestellt sehen.
    
     ![Vorbereiten Active Directory abgeschlossen.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Siehe auch
 
[Active Directory-Domänendienste für Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
