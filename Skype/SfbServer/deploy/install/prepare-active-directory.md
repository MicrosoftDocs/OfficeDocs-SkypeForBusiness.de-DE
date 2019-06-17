---
title: Vorbereiten von Active Directory für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Active Directory-Domäne für eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: e15431cf08925920f4f7ec223d9983d3dc3e35c7
ms.sourcegitcommit: 46fb558814cb6bd7d70729eac590afd51fc6606e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2019
ms.locfileid: "35002845"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Vorbereiten von Active Directory für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Active Directory-Domäne für eine Installation von Skype for Business Server vorbereiten. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory-Domäne für die Zusammenarbeit mit Skype for Business Server vorbereiten. Dieser Vorgang wird im Bereitstellungs-Assistenten durchgeführt und erfolgt nur einmal für die Domäne. Der Grund hierfür ist, dass der Prozessgruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal tun. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Das Vorbereiten von Active Directory ist Schritt 4 von 8. Weitere Informationen zum Planen von Active Directory finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) -oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Übersichtsdiagramm](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Vorbereiten von Active Directory

Skype for Business Server ist eng in die Active Directory-Domänendienste (AD DS) integriert. Bevor Sie Skype for Business Server zum ersten Mal installieren können, muss Active Directory vorbereitet sein. Der Abschnitt des Bereitstellungs-Assistenten mit dem Titel **Prepare Active Directory** bereitet die Active Directory-Umgebung für die Verwendung mit Skype for Business Server vor.
  
> [!NOTE]
> Skype for Business Server verwendet (AD DS), um alle Server in einer Topologie zu überwachen und mit Ihnen zu kommunizieren. Jeder Server muss mit der Domäne verbunden sein, damit Skype for Business Server ordnungsgemäß funktionieren kann. 
  
> [!IMPORTANT]
> Das Verfahren zur Vorbereitung von Active Directory muss nur einmal für jede Domäne in der Bereitstellung durchgeführt werden. 
  
Schauen Sie sich das Video mit den Schritten zum **Vorbereiten von Active Directory** an:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Vorbereiten von Active Directory mithilfe des Bereitstellungs-Assistenten

1. Melden Sie sich als Benutzer mit den Anmeldeinformationen für den Schemaadministrator der Active Directory-Domäne an.
    
2. Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.
    
    > [!TIP]
    > Wenn Sie die Protokolldateien überprüfen möchten, die vom Bereitstellungs-Assistenten für Skype for Business Server erstellt wurden, können Sie diese auf dem Computer finden, auf dem der Bereitstellungs-Assistent ausgeführt wurde, und zwar im Verzeichnis Benutzer des AD DS-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne "contoso. local" anmeldet, befinden sich die Protokolldateien in: C:\users\administrator.Contoso\AppData\Local\Temp. 
  
3. Klicken Sie auf den Link **Active Directory vorbereiten**.
    
4. **Schritt 1: Schema vorbereiten**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 1, zu dem Sie über das Dropdownmenü unter dem Titel „Schritt 1“ gelangen.
    
    b. Klicken Sie in Schritt 1 auf **Ausführen**, um den Assistenten zum Vorbereiten des Schemas zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Nach der Vorbereitung des Schemas können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    e. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten des Schemas zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
5. **Schritt 2: Replikation der Schemapartition überprüfen**
    
    a. Melden Sie sich beim Domänencontroller der Domäne an.
    
    b. Öffnen Sie im Dropdownmenü **Extras** im **Server-Manager** die Option **ADSI-Editor**.
    
    c. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
    d. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.
    
    e. Suchen Sie unter dem Schemacontainer nach **CN=ms-RTC-SIP-SchemaVersion**. Wenn dieses Objekt vorhanden ist sowie der Wert des Attributs **rangeUpper** 1150 und der Wert des Attributs **rangeLower** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht diesen Werten entsprechen, wurde das Schema nicht geändert oder repliziert.
    
6. **Schritt 3: Aktuelle Gesamtstruktur vorbereiten**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 3, zu der Sie über das Dropdownmenü unter dem Titel „Schritt 3“ gelangen.
    
    b. Klicken Sie in Schritt 3 auf **Ausführen**, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Geben Sie die Domäne an, in der die universellen Gruppen erstellt werden. Wenn der Server Teil der Domäne ist, können Sie **lokale Domäne**auswählen und auf **weiter**klicken.
    
    e. Nach der Vorbereitung der Gesamtstruktur können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    f. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
    g. Klicken Sie auf der Seite " **apps** " auf **Skype for Business Server-Verwaltungsshell** , um PowerShell zu starten.
    
    h. Geben Sie den Befehl Get-CsAdForest ein, und drücken **Sie die Eingabe**Taste.
    
    Ich. Wenn das Ergebnis **LC_FORESTSETTINGS_STATE_READY**ist, wurde die Gesamtstruktur erfolgreich vorbereitet, wie in der Abbildung dargestellt.
    
     ![Replikation der Gesamtstruktur überprüfen.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Schritt 4: Replikation des globalen Katalogs überprüfen**
    
    a. Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.
    
    b. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
    c. Klicken Sie im linken Fensterbereich auf den Container **Users** und navigieren Sie im rechten Fensterbereich zur universellen Gruppe **CsAdministrator**. Wenn die Gruppe „CsAdministrator“ vorhanden ist (neben acht weiteren neuen universellen Gruppen, deren Namen mit „Cs“ beginnen), war die Replikation von Active Directory erfolgreich.
    
    d. Wenn die Gruppen nicht vorhanden sind, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Fensterbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
8. **Schritt 5: Aktuelle Domäne vorbereiten**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 5.
    
    b. Klicken Sie in Schritt 5 auf **Ausführen**, um den Assistenten zum Vorbereiten der aktuellen Domäne zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Domäne in der Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Nach der Vorbereitung der Domäne können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    e. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten der aktuellen Domäne zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
    Diese Schritte müssen in jeder Domäne, in der Skype for Business Server-Objekte gefunden werden, ausgeführt werden, da andernfalls Dienste möglicherweise nicht gestartet werden. Dazu gehören alle Typen von Active Directory-Objekten wie Benutzer, Kontaktobjekte, administrative Gruppen oder andere Objekttypen. Sie können mithilfe von "CsUserReplicatorConfiguration-ADDomainNamingContextList" nur die Domänen mit Skype for Business Server-Objekten hinzufügen, falls erforderlich.
    
9. **Schritt 6: Replikation in der Domäne überprüfen**
    
    a. Klicken Sie auf der Seite " **apps** " auf die **Skype for Business Server-Verwaltungsshell** , um PowerShell zu starten.
    
    b. Verwenden Sie den Befehl Get-CsAdDomain, um die Replikation innerhalb der Domäne zu überprüfen.
    
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
  
    c. Wenn das Ergebnis **LC_DOMAINSETTINGS_STATE_READY**ist, wurde die Domäne erfolgreich repliziert.
    
10. **Schritt 7: Benutzer hinzufügen, um den Administratorzugriff auf die Skype for Business Server-Systemsteuerung zu ermöglichen**
    
    a. Melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ oder „RTCUniversalServerAdmins“ an.
    
    b. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne und klicken Sie auf den Container **Users**. Klicken Sie dann mit der rechten Maustaste auf „CSAdministrator“ und wählen Sie **Eigenschaften** aus.
    
    c. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
    d. Klicken Sie auf der Registerkarte **Mitglieder** auf **Hinzufügen**. Suchen Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen**die Option **Geben Sie die zu wählenden Objektnamen ein**. Geben Sie den Benutzernamen oder die Gruppennamen ein, die Sie der Gruppe CSAdministrators hinzufügen möchten. Klicken Sie auf **OK**.
    
    e. Überprüfen Sie auf der Registerkarte **Mitglieder** , ob die ausgewählten Benutzer oder Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
    > [!CAUTION]
    > Das Skype for Business Server Control Panel ist ein rollenbasiertes Zugriffs Steuerungstool. Die Mitgliedschaft in der CsAdministrator-Gruppe gibt Benutzern, die das Skype for Business Server Control Panel verwenden, Vollzugriff für alle verfügbaren Konfigurationsfunktionen. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Einzelheiten zu den verfügbaren Rollen finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) -oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Beachten Sie, dass Benutzer nicht für Skype for Business Server aktiviert sein müssen, um Mitglieder der Verwaltungsgruppen zu werden. 
  
    > [!CAUTION]
    > Um die Integrität von Sicherheit und rollenbasierter Zugriffssteuerung zu erhalten, fügen Sie Benutzer zu den Gruppen hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server-Bereitstellung übernimmt. 
  
11. Melden Sie sich ab, und melden Sie sich dann wieder bei Windows an, damit Ihr Sicherheitstoken mit der neuen Skype for Business Server-Sicherheitsgruppe aktualisiert wird, und öffnen Sie dann den Bereitstellungs-Assistenten erneut.
    
12. Vergewissern Sie sich, dass neben " **Active Directory vorbereiten** " ein grünes Häkchen angezeigt wird, um den Erfolg zu bestätigen, wie in der Abbildung dargestellt.
    
     ![Vorbereiten von Active Directory abgeschlossen.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Siehe auch
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
