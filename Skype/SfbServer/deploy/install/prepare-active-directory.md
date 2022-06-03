---
title: 'Skype for Business Server: Vorbereiten von Active Directory'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Active Directory-Domäne für eine Installation von Skype for Business Server vorbereiten.'
ms.openlocfilehash: b40eccab3d2f71e5211a1c67342440a86497023d
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860573"
---
# <a name="skype-for-business-server-prepare-active-directory"></a>Skype for Business Server: Vorbereiten von Active Directory
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Active Directory-Domäne für eine Installation von Skype for Business Server vorbereiten.
  
Skype for Business Server arbeitet eng mit Active Directory zusammen. Sie müssen die Active Directory-Domäne für die Arbeit mit Skype for Business Server vorbereiten. Dieser Vorgang wird im Bereitstellungs-Assistenten ausgeführt und nur einmal für die Domäne ausgeführt. Dies liegt daran, dass der Prozess Gruppen erstellt und die Domäne ändert, und Sie müssen dies nur einmal tun. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Die Vorbereitung von Active Directory ist Schritt 4 von 8. Weitere Informationen zur Planung von Active Directory finden Sie unter [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![Übersichtsdiagramm.](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Vorbereitung von Active Directory

Skype for Business Server ist eng in Active Directory Domain Services (AD DS) integriert. Bevor Skype for Business Server zum ersten Mal installiert werden kann, muss Active Directory vorbereitet werden. Im Abschnitt des Bereitstellungs-Assistenten mit dem Titel **"Vorbereiten von Active Directory**" wird die Active Directory-Umgebung für die Verwendung mit Skype for Business Server vorbereitet.
  
> [!NOTE]
> Skype for Business Server verwendet (AD DS) zum Nachverfolgen und Kommunizieren mit allen Servern in einer Topologie. Der Großteil dieser Server muss der Domäne beigetreten sein, damit Skype for Business Server ordnungsgemäß funktionieren können. Denken Sie daran, dass Server wie Edge und Reverseproxy nicht in die Domäne eingebunden werden sollten.
  
> [!IMPORTANT]
> Die Active Directory-Prozedur "Vorbereiten" sollte nur einmal für jede Domäne in der Bereitstellung ausgeführt werden. 
  
Schauen Sie sich die Videoschritte für **die Vorbereitung von Active Directory** an:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Vorbereiten von Active Directory über den Bereitstellungs-Assistenten

1. Melden Sie sich als Benutzer mit den Anmeldeinformationen von Schemaadministratoren für die Active Directory-Domäne an.
    
2. Öffnen Sie Skype for Business Server Bereitstellungs-Assistenten.
    
    > [!TIP]
    > Wenn Sie die Vom Skype for Business Server-Bereitstellungs-Assistenten erstellten Protokolldateien überprüfen möchten, finden Sie sie auf dem Computer, auf dem der Bereitstellungs-Assistent ausgeführt wurde, im Verzeichnis "Benutzer" des AD DS-Benutzers, der den Schritt ausgeführt hat. Wenn sich der Benutzer beispielsweise als Domänenadministrator in der Domäne "contoso.local" angemeldet hat, befinden sich die Protokolldateien unter: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Klicken Sie auf den Link **"Active Directory vorbereiten** ".
    
4. **Schritt 1: Vorbereiten des Schemas**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 1, auf die Sie zugreifen können, indem Sie auf die Dropdownliste unter dem Titel "Schritt 1" klicken.
    
    b. Klicken Sie in Schritt 1 auf **"Ausführen** ", um den Assistenten "Schema vorbereiten" zu starten.
    
    c. Beachten Sie, dass die Prozedur nur einmal für jede Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **Weiter**.
    
    d. Nachdem das Schema vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf " **Protokoll anzeigen"** klicken. 
    
    e. Klicken Sie auf **"Fertig stellen** ", um den Assistenten "Schema vorbereiten" zu schließen und zu den Schritten zum Vorbereiten von Active Directory zurückzukehren.
    
5. **Schritt 2: Überprüfen der Replikation der Schemapartition**
    
    a. Melden Sie sich beim Domänencontroller für die Domäne an.
    
    b. Öffnen **Sie die ADSI-Bearbeitung** im Dropdownmenü "**Extras**" in **Server-Manager**.
    
    c. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
    d. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus, und klicken Sie auf **OK**.
    
    e. Suchen Sie im Schemacontainer nach **CN=ms-RTC-SIP-SchemaVersion**. Wenn dieses Objekt vorhanden ist und der Wert des **rangeUpper-Attributs** 1150 und der Wert des **rangeLower-Attributs** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der **Attribute "rangeUpper** " und " **rangeLower** " nicht wie angegeben sind, wurde das Schema nicht geändert oder nicht repliziert.
    
6. **Schritt 3: Vorbereiten der aktuellen Gesamtstruktur**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 3, auf die Sie zugreifen können, indem Sie auf die Dropdownliste unter dem Titel "Schritt 3" klicken.
    
    b. Klicken Sie in Schritt 3 auf **"Ausführen** ", um den Assistenten "Aktuelle Gesamtstruktur vorbereiten" zu starten.
    
    c. Beachten Sie, dass die Prozedur nur einmal pro Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **Weiter**.
    
    d. Geben Sie die Domäne an, in der die universellen Gruppen erstellt werden. Wenn der Server Teil der Domäne ist, können Sie **"Lokale Domäne**" auswählen und auf **"Weiter**" klicken.
    
    e. Nachdem die Gesamtstruktur vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf " **Protokoll anzeigen"** klicken. 
    
    f. Klicken Sie auf **"Fertig stellen** ", um den Assistenten "Aktuelle Gesamtstruktur vorbereiten" zu schließen und zu den Schritten zum Vorbereiten von Active Directory zurückzukehren.
    
    g. Klicken Sie auf der Seite **"Apps**" auf **Skype for Business Server Verwaltungsshell**, um PowerShell zu starten.
    
    h. Geben Sie den Befehl "Get-CsAdForest" ein, und drücken **Sie die EINGABETASTE**.
    
    i. Wenn das Ergebnis **LC_FORESTSETTINGS_STATE_READY** ist, wurde die Gesamtstruktur erfolgreich vorbereitet, wie in der Abbildung dargestellt.
    
     ![Überprüfen der Gesamtstrukturreplikation.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Schritt 4: Überprüfen der Replikation des globalen Katalogs**
    
    a. Öffnen Sie auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde, **Active Directory-Benutzer und -Computer**.
    
    b. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
    c. Klicken Sie im linken Bereich auf den Container **"Benutzer** ", und suchen Sie im rechten Seitenbereich nach der universellen Gruppe **"CsAdministrator** ". Wenn CsAdministrator (unter anderen neuen universellen Gruppen, die mit Cs beginnen) vorhanden ist, war die Active Directory-Replikation erfolgreich.
    
    d. Wenn die Gruppen noch nicht vorhanden sind, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Bereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
8. **Schritt 5: Vorbereiten der aktuellen Domäne**
    
    a. Überprüfen Sie die Informationen zu den Voraussetzungen für Schritt 5.
    
    b. Klicken Sie in Schritt 5 auf **"Ausführen** ", um den Assistenten "Aktuelle Domäne vorbereiten" zu starten.
    
    c. Beachten Sie, dass die Prozedur nur einmal für jede Domäne in der Bereitstellung ausgeführt werden sollte, und klicken Sie dann auf **"Weiter**".
    
    d. Nachdem die Domäne vorbereitet wurde, können Sie das Protokoll anzeigen, indem Sie auf " **Protokoll anzeigen"** klicken. 
    
    e. Klicken Sie auf **"Fertig stellen** ", um den Assistenten "Aktuelle Domäne vorbereiten" zu schließen und zu den Schritten zum Vorbereiten von Active Directory zurückzukehren.
    
    Diese Schritte müssen in jeder Domäne ausgeführt werden, in der Skype for Business Server Objekte gefunden werden, andernfalls werden Dienste möglicherweise nicht gestartet. Dazu gehören alle Arten von Active Directory-Objekten, z. B. Benutzer, Kontaktobjekte, administrative Gruppen oder andere Objekttypen. Sie können Set-CsUserReplicatorConfiguration -ADDomainNamingContextList verwenden, um bei Bedarf nur die Domänen mit Skype for Business Server Objekten hinzuzufügen.
    
9. **Schritt 6: Überprüfen der Replikation in der Domäne**
    
    a. Klicken Sie auf der Seite **"Apps**" auf die **Skype for Business Server Verwaltungsshell**, um PowerShell zu starten.
    
    b. Verwenden Sie den Befehl Get-CsAdDomain, um die Replikation innerhalb der Domäne zu überprüfen.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Wenn Sie den Parameter "Domain" nicht angeben, wird die lokale Domäne verwendet. 
  
    Beispiel für das Ausführen des Befehls für die Domäne "contoso.local":
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Mithilfe des Parameters GlobalSettingsDomainController können Sie angeben, wo globale Einstellungen gespeichert werden. Wenn Ihre Einstellungen im Systemcontainer gespeichert sind (dies ist typisch für Upgradebereitstellungen, bei denen die globale Einstellung nicht in den Konfigurationscontainer migriert wurde), definieren Sie einen Domänencontroller im Stamm ihrer AD DS-Gesamtstruktur. Wenn sich die globalen Einstellungen im Konfigurationscontainer befinden (dies ist bei neuen Bereitstellungen oder Upgradebereitstellungen typisch, bei denen die Einstellungen zum Konfigurationscontainer migriert wurden), definieren Sie einen beliebigen Domänencontroller in der Gesamtstruktur. Wenn Sie diesen Parameter nicht angeben, geht das Cmdlet davon aus, dass die Einstellungen im Konfigurationscontainer gespeichert sind, und verweist auf einen beliebigen Domänencontroller in Active Directory. 
  
    c. Wenn das Ergebnis **LC_DOMAINSETTINGS_STATE_READY** ist, wurde die Domäne erfolgreich repliziert.
    
10. **Schritt 7: Hinzufügen von Benutzern zum Bereitstellen des administrativen Zugriffs auf die Skype for Business Server Systemsteuerung**
    
    a. Melden Sie sich als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.
    
    b. Öffnen **Sie Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne, klicken Sie auf den Container **"Benutzer**", klicken Sie mit der rechten Maustaste auf "CSAdministrator", und wählen Sie **"Eigenschaften"** aus.
    
    c. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
    d. Klicken Sie auf der Registerkarte **Mitglieder** auf **Hinzufügen**. **Suchen Sie in "Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen**" die **Option "Objektnamen eingeben", die Sie auswählen möchten**. Geben Sie die Benutzernamen oder Gruppennamen ein, die der Gruppe "CSAdministrators" hinzugefügt werden sollen. Klicken Sie auf **OK**.
    
    e. Vergewissern Sie sich auf der Registerkarte " **Mitglieder** ", dass die ausgewählten Benutzer oder Gruppen vorhanden sind. Klicken Sie auf **OK**.
    
    > [!CAUTION]
    > Die Skype for Business Server Systemsteuerung ist ein rollenbasiertes Zugriffssteuerungstool. Die Mitgliedschaft in der CsAdministrator-Gruppe gibt einem Benutzer, der die Skype for Business Server Systemsteuerung Vollzugriff auf alle verfügbaren Konfigurationsfunktionen verwendet. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Ausführliche Informationen zu den verfügbaren Rollen finden Sie unter [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Beachten Sie, dass Benutzer nicht für Skype for Business Server aktiviert werden müssen, um Mitglieder der Verwaltungsgruppen zu werden. 
  
    > [!CAUTION]
    > Um die Integrität der Sicherheits- und rollenbasierten Zugriffssteuerung beizubehalten, fügen Sie den Gruppen Benutzer hinzu, die definieren, welche Rolle der Benutzer bei der Verwaltung der Skype for Business Server Bereitstellung ausführt. 
  
11. Melden Sie sich ab, und melden Sie sich dann wieder bei Windows an, damit Ihr Sicherheitstoken mit der neuen Skype for Business Server Sicherheitsgruppe aktualisiert wird, und öffnen Sie dann den Bereitstellungs-Assistenten erneut.
    
12. Stellen Sie sicher, dass neben **"Active Directory** vorbereiten" ein grünes Häkchen angezeigt wird, um den Erfolg zu bestätigen, wie in der Abbildung dargestellt.
    
     ![Vorbereiten von Active Directory abgeschlossen.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Siehe auch
 
[Active Directory Domain Services für Skype for Business Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
