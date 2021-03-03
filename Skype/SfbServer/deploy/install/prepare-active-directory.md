---
title: Vorbereiten von Active Directory für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Active Directory-Domäne für eine Installation von Skype for Business Server vorbereiten. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server herunter.'
ms.openlocfilehash: 6196855ffeaf33fbea11c47d56c620e3df9195ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801675"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Vorbereiten von Active Directory für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Active Directory-Domäne für eine Installation von Skype for Business Server vorbereiten. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center herunter.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory-Domäne für die Zusammenarbeit mit Skype for Business Server vorbereiten. Dieser Vorgang wird im Bereitstellungsassistenten ausgeführt und nur einmal für die Domäne ausgeführt. Dies liegt daran, dass der Prozess Gruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal tun. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Vorbereitung von Active Directory ist Schritt 4 von 8. Weitere Informationen zum Planen von Active Directory finden Sie unter Umgebungsanforderungen für [Skype for Business Server-](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Serveranforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Übersichtsdiagramm](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Vorbereitung von Active Directory

Skype for Business Server ist eng in Active Directory Domain Services (AD DS) integriert. Bevor Skype for Business Server zum ersten Mal installiert werden kann, muss Active Directory vorbereitet werden. Der Abschnitt des Bereitstellungs-Assistenten mit dem Titel **"Vorbereiten von Active Directory"** bereitet die Active Directory-Umgebung für die Verwendung mit Skype for Business Server vor.
  
> [!NOTE]
> Skype for Business Server verwendet (AD DS) zum Nachverfolgen und Kommunizieren mit allen Servern in einer Topologie. Der Großteil dieser Server muss der Domäne beigetreten sein, damit Skype for Business Server ordnungsgemäß funktionieren kann. Beachten Sie, dass Server wie Edge und Reverseproxy nicht einer Domäne beigetreten sein sollten.
  
> [!IMPORTANT]
> Das Verfahren zum Vorbereiten von Active Directory sollte nur einmal für jede Domäne in der Bereitstellung ausgeführt werden. 
  
Sehen Sie sich die Videoschritte für **die Vorbereitung von Active Directory an:**
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Vorbereiten von Active Directory über den Bereitstellungsassistenten

1. Melden Sie sich als Benutzer mit den Anmeldeinformationen der Schemaadministratoren für die Active Directory-Domäne an.
    
2. Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.
    
    > [!TIP]
    > Wenn Sie die vom Skype for Business Server-Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen möchten, finden Sie diese auf dem Computer, auf dem der Bereitstellungsassistent ausgeführt wurde, im Verzeichnis "Users" des AD DS-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne "contoso.local" angemeldet hat, befinden sich die Protokolldateien unter: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Klicken Sie auf den **Link "Active Directory vorbereiten".**
    
4. **Schritt 1: Vorbereiten des Schemas**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 1, auf die sie zugreifen können, indem Sie auf das Dropdown unter dem Titel "Schritt 1" klicken.
    
    b. Klicken **Sie auf "Ausführen"** in Schritt 1, um den Assistenten zum Vorbereiten des Schemas zu starten.
    
    c. Beachten Sie, dass das Verfahren nur einmal für jede Bereitstellung ausgeführt werden soll, und klicken Sie dann auf **Weiter**.
    
    d. Nachdem das Schema vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf **"Protokoll anzeigen" klicken.** 
    
    e. Klicken **Sie auf "Fertig** stellen", um den Assistenten zum Vorbereiten des Schemas zu schließen, und kehren Sie zu den Schritten zum Vorbereiten von Active Directory zurück.
    
5. **Schritt 2: Überprüfen der Replikation der Schemapartition**
    
    a. Melden Sie sich am Domänencontroller für die Domäne an.
    
    b. Öffnen **Sie die ADSI-Bearbeitung** im **Dropdownmenü** "Extras" im **Server-Manager.**
    
    c. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
    d. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus, und klicken Sie auf **OK**.
    
    e. Suchen Sie im Schemacontainer nach **CN=ms-RTC-SIP-SchemaVersion**. Wenn dieses Objekt vorhanden ist und der Wert des **rangeUpper-Attributs** 1150 ist und der Wert des **rangeLower-Attributs** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der **Attribute "rangeUpper"** und **"rangeLower"** nicht wie angegeben sind, wurde das Schema nicht geändert oder nicht repliziert.
    
6. **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 3, auf den Sie zugreifen können, indem Sie auf das Dropdown unter dem Titel "Schritt 3" klicken.
    
    b. Klicken **Sie auf "Ausführen"** in Schritt 3, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu starten.
    
    c. Beachten Sie, dass das Verfahren nur einmal pro Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **"Weiter".**
    
    d. Geben Sie die Domäne an, in der die universellen Gruppen erstellt werden. Wenn der Server Teil der Domäne ist, können Sie **"Lokale Domäne"** auswählen und auf **"Weiter" klicken.**
    
    e. Nachdem die Gesamtstruktur vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf **"Protokoll anzeigen" klicken.** 
    
    f. Klicken **Sie auf "Fertig** stellen", um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu schließen, und kehren Sie zu den Schritten zum Vorbereiten von Active Directory zurück.
    
    g. Klicken Sie auf der Seite **"Apps" auf** der Skype for Business **Server-Verwaltungsshell,** um PowerShell zu starten.
    
    h. Geben Sie den Befehl "Get-CsAdForest" ein, und drücken Sie die **EINGABETASTE.**
    
    i. Wenn das Ergebnis **LC_FORESTSETTINGS_STATE_READY** ist, wurde die Gesamtstruktur erfolgreich vorbereitet, wie in der Abbildung dargestellt.
    
     ![Überprüfen Sie die Gesamtstrukturreplikation.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Schritt 4: Überprüfen der Replikation des globalen Katalogs**
    
    a. Öffnen Sie auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde, **Active Directory-Benutzer und -Computer**.
    
    b. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
    c. Klicken Sie **im** linken Bereich auf den Container "Benutzer", und suchen Sie im rechten Bereich nach der universellen Gruppe **"CsAdministrator".** Wenn "CsAdministrator" (neben anderen neuen universellen Gruppen, die mit "Cs" beginnen) vorhanden ist, war die Active Directory-Replikation erfolgreich.
    
    d. Wenn die Gruppen noch nicht vorhanden sind, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Seitenbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
8. **Schritt 5: Vorbereiten der aktuellen Domäne**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 5.
    
    b. Klicken **Sie in Schritt** 5 auf "Ausführen", um den Assistenten zum Vorbereiten der aktuellen Domäne zu starten.
    
    c. Beachten Sie, dass das Verfahren nur einmal für jede Domäne in der Bereitstellung ausgeführt werden soll, und klicken Sie dann auf **"Weiter".**
    
    d. Nachdem die Domäne vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf **"Protokoll anzeigen" klicken.** 
    
    e. Klicken **Sie auf "Fertig** stellen", um den Assistenten zum Vorbereiten der aktuellen Domäne zu schließen, und kehren Sie zu den Schritten zum Vorbereiten von Active Directory zurück.
    
    Diese Schritte müssen in jeder Domäne ausgeführt werden, in der Skype for Business Server-Objekte gefunden werden, andernfalls werden die Dienste möglicherweise nicht gestartet. Dazu gehören alle Typen von Active Directory-Objekten, z. B. Benutzer, Kontaktobjekte, administrative Gruppen oder andere Objekttypen. Sie können die Set-CsUserReplicatorConfiguration -ADDomainNamingContextList verwenden, um bei Bedarf nur die Domänen mit Skype for Business Server-Objekten hinzuzufügen.
    
9. **Schritt 6: Überprüfen der Replikation in der Domäne**
    
    a. Klicken Sie **auf der Seite "Apps" auf die Skype for Business Server-Verwaltungsshell,** um PowerShell zu starten. 
    
    b. Verwenden Sie den befehls Get-CsAdDomain, um die Replikation innerhalb der Domäne zu überprüfen.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Wenn Sie den Parameter "Domain" nicht angeben, wird die lokale Domäne verwendet. 
  
    Beispiel für die Ausführung des Befehls für die Domäne "contoso.local":
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Mit dem Parameter "GlobalSettingsDomainController" können Sie angeben, wo globale Einstellungen gespeichert werden. Wenn Ihre Einstellungen im Systemcontainer gespeichert werden (dies ist typisch für Upgradebereitstellungen, bei denen die globale Einstellung nicht zum Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stammverzeichnis Ihrer AD DS-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    c. Wenn das Ergebnis **LC_DOMAINSETTINGS_STATE_READY** wird, wurde die Domäne erfolgreich repliziert.
    
10. **Schritt 7: Hinzufügen von Benutzern zur Bereitstellung von Administratorzugriff auf die Skype for Business Server-Systemsteuerung**
    
    a. Melden Sie sich als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
    b. Öffnen **Sie Active Directory-Benutzer und -Computer,** erweitern Sie Ihre Domäne, klicken Sie auf **den** Container "Users", klicken Sie mit der rechten Maustaste auf "CSAdministrator", und wählen Sie **"Eigenschaften" aus.**
    
    c. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
    d. Klicken Sie auf der Registerkarte **Mitglieder** auf **Hinzufügen**. Suchen **Sie in "Benutzer auswählen", "Kontakte", "Computer", "Dienstkonten"** oder "Gruppen" die Zu wählende **Objektnamen eingeben.** Geben Sie die Benutzernamen oder Gruppennamen ein, die der Gruppe "CSAdministrators" hinzugefügt werden. Klicken Sie auf **OK**.
    
    e. Vergewissern Sie **sich auf** der Registerkarte "Mitglieder", dass die ausgewählten Benutzer oder Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
    > [!CAUTION]
    > Die Skype for Business Server-Systemsteuerung ist ein rollenbasiertes Zugriffssteuerungstool. Die Mitgliedschaft in der Gruppe "CsAdministrator" gibt einem Benutzer, der die Skype for Business Server-Systemsteuerung verwendet, voll kontrolle über alle verfügbaren Konfigurationsfunktionen. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Weitere Informationen zu den verfügbaren Rollen finden Sie unter "Umgebungsanforderungen für [Skype for Business Server-](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Serveranforderungen für Skype for Business Server 2019".](../../../SfBServer2019/plan/system-requirements.md) Beachten Sie, dass Benutzer nicht für Skype for Business Server aktiviert werden müssen, um Mitglied der Verwaltungsgruppen zu werden. 
  
    > [!CAUTION]
    > Um die Sicherheit und die rollenbasierte Zugriffssteuerungsintegrität zu erhalten, fügen Sie Benutzer zu den Gruppen hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server-Bereitstellung übernimmt. 
  
11. Melden Sie sich ab, und melden Sie sich dann wieder bei Windows an, damit Ihr Sicherheitstoken mit der neuen Skype for Business Server-Sicherheitsgruppe aktualisiert wird, und öffnen Sie dann den Bereitstellungs-Assistenten erneut.
    
12. Stellen Sie sicher, dass neben **"Active Directory** vorbereiten" ein grünes Häkchen angezeigt wird, um den Erfolg zu bestätigen, wie in der Abbildung dargestellt.
    
     ![Vorbereiten von Active Directory abgeschlossen.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Weitere Informationen
 
[Active Directory Domain Services for Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
