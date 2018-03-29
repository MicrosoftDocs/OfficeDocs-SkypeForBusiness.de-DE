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
description: 'Zusammenfassung: Informationen Sie zum Vorbereiten der Active Directory-Domäne für eine Installation von Skype für Business Server 2015. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: c9e563a745f5bfb94b971dc1d5d38964ac76eb8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Vorbereiten von Active Directory für Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Vorbereiten der Active Directory-Domäne für eine Installation von Skype für Business Server 2015. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype für Business Server arbeitet eng mit Active Directory. Sie müssen Active Directory-Domäne zur Arbeit mit Skype für Business Server vorbereiten. Dieser Prozess wird im Bereitstellungs-Assistenten erreicht und erfolgt nur einmal für die Domäne. Dies ist, da der Prozess Gruppen erstellt und ändert die Domäne, und die erforderlich ist, nur einmal. Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen. Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden. Vorbereiten von Active Directory ist Schritt 4 von 8. Weitere Informationen zur Planung von Active Directory finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![Übersichtsdiagramm](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Vorbereiten von Active Directory

Skype für Business Server 2015 ist eng in Active Directory-Domänendienste (AD DS) integriert. Bevor Skype für Business Server 2015 zum ersten Mal installiert werden kann, muss der Active Directory vorbereitet werden. Der Abschnitt des Assistenten-Bereitstellung **Vorbereiten von Active Directory** mit dem Titel wird Active Directory-Umgebung für die Verwendung mit Skype für Business Server vorbereitet.
  
> [!NOTE]
> Skype für Business Server 2015 wird (AD DS) verwendet, um nachzuverfolgen und zu kommunizieren mit allen Servern in einer Topologie. Jeder Server muss mit der Domäne verknüpft werden, damit Skype für Business Server ordnungsgemäß ausgeführt werden kann. 
  
> [!IMPORTANT]
> Das Verfahren zur Vorbereitung von Active Directory muss nur einmal für jede Domäne in der Bereitstellung durchgeführt werden. 
  
Schauen Sie sich das Video mit den Schritten zum **Vorbereiten von Active Directory** an:
  
![Ihr Browser unterstützt kein Video. Installieren von Microsoft Silverlight, Adobe Flash Player oder Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Vorbereiten von Active Directory mithilfe des Bereitstellungs-Assistenten

1. Melden Sie sich als Benutzer mit den Anmeldeinformationen für den Schemaadministrator der Active Directory-Domäne an.
    
2. Skype für Business Server-Bereitstellungs-Assistenten zu öffnen.
    
    > [!TIP]
    > Wenn Sie die Protokolldateien, die durch die Skype für Business Server-Bereitstellungs-Assistenten erstellt werden, prüfen möchten, können Sie diese auf dem Computer finden, in dem Bereitstellungs-Assistenten ausgeführt wurde, im Verzeichnis Benutzer des Benutzers AD DS, die im Schritt ausgeführt hat. Angenommen, wenn der Benutzer angemeldet als Domänenadministrator in der Domäne, contoso.local, die Protokolldateien befinden sich im: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Klicken Sie auf den Link **Active Directory vorbereiten**.
    
4. **Schritt 1: Vorbereiten des Schemas**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 1, zu dem Sie über das Dropdownmenü unter dem Titel „Schritt 1“ gelangen.
    
    b. Klicken Sie in Schritt 1 auf **Ausführen**, um den Assistenten zum Vorbereiten des Schemas zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Nach der Vorbereitung des Schemas können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    e. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten des Schemas zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
5. **Schritt 2: Überprüfen der Replikation der Schemapartition**
    
    a. Melden Sie sich beim Domänencontroller der Domäne an.
    
    b. Öffnen Sie im Dropdownmenü **Extras** im **Server-Manager** die Option **ADSI-Editor**.
    
    c. Klicken Sie im Menü **Aktion** auf **Verbinden mit**.
    
    d. Wählen Sie im Dialogfeld **Verbindungseinstellungen** unter **Bekannten Namenskontext auswählen** die Option **Schema** aus und klicken Sie dann auf **OK**.
    
    e. Suchen Sie unter dem Schemacontainer nach **CN=ms-RTC-SIP-SchemaVersion**. Wenn dieses Objekt vorhanden ist sowie der Wert des Attributs **rangeUpper** 1150 und der Wert des Attributs **rangeLower** 3 ist, wurde das Schema erfolgreich aktualisiert und repliziert. Wenn dieses Objekt nicht vorhanden ist oder die Werte der Attribute **rangeUpper** und **rangeLower** nicht diesen Werten entsprechen, wurde das Schema nicht geändert oder repliziert.
    
6. **Schritt 3: Aktuelle Gesamtstruktur vorbereiten**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 3, zu der Sie über das Dropdownmenü unter dem Titel „Schritt 3“ gelangen.
    
    b. Klicken Sie in Schritt 3 auf **Ausführen**, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Geben Sie die Domäne, in dem die universellen Gruppen erstellt wird. Wenn der Server Teil der Domäne ist, können Sie wählen Sie **lokale Domäne**, und klicken Sie auf **Weiter**.
    
    e. Nach der Vorbereitung der Gesamtstruktur können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    f. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten der aktuellen Gesamtstruktur zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
    g. Klicken Sie auf der Seite " **Apps** " So starten Sie PowerShell **Skype für Business Server-Verwaltungsshell** .
    
    h. Geben Sie den Befehl Get-CsAdForest, und drücken Sie die **EINGABETASTE**.
    
    Ich. Wenn das Ergebnis **LC_FORESTSETTINGS_STATE_READY**ist, wurde die Gesamtstruktur erfolgreich vorbereitet wurde wie in der Abbildung dargestellt.
    
     ![Replikation der Gesamtstruktur überprüfen.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Schritt 4: Überprüfen der Replikation des globalen Katalogs**
    
    a. Öffnen Sie **Active Directory-Benutzer und -Computer** auf einem Domänencontroller (vorzugsweise an einem Remotestandort gegenüber den anderen Domänencontrollern) in der Gesamtstruktur, in der die Gesamtstrukturvorbereitung durchgeführt wurde.
    
    b. Erweitern Sie in **Active Directory-Benutzer und -Computer** den Domänennamen Ihrer Gesamtstruktur oder einer untergeordneten Domäne.
    
    c. Klicken Sie im linken Fensterbereich auf den Container **Users** und navigieren Sie im rechten Fensterbereich zur universellen Gruppe **CsAdministrator**. Wenn die Gruppe „CsAdministrator“ vorhanden ist (neben acht weiteren neuen universellen Gruppen, deren Namen mit „Cs“ beginnen), war die Replikation von Active Directory erfolgreich.
    
    d. Wenn die Gruppen nicht vorhanden sind, können Sie die Replikation erzwingen oder 15 Minuten warten und den rechten Fensterbereich aktualisieren. Die Replikation ist abgeschlossen, wenn die Gruppen vorhanden sind.
    
8. **Schritt 5: Aktuelle Domäne vorbereiten**
    
    a. Überprüfen Sie die Voraussetzungen für Schritt 5.
    
    b. Klicken Sie in Schritt 5 auf **Ausführen**, um den Assistenten zum Vorbereiten der aktuellen Domäne zu öffnen.
    
    c. Dieses Verfahren muss nur einmal für jede Domäne in der Bereitstellung durchgeführt werden. Klicken Sie dann auf **Weiter**.
    
    d. Nach der Vorbereitung der Domäne können Sie das Protokoll anzeigen, indem Sie auf **Protokoll anzeigen** klicken. 
    
    e. Klicken Sie auf **Fertig stellen**, um den Assistenten zum Vorbereiten der aktuellen Domäne zu schließen, und kehren Sie zu den Schritten für die Vorbereitung von Active Directory zurück.
    
    Diese Schritte ausgeführt werden müssen, in jeder Domäne, in dem Skype für Business Server Objekte gefunden werden, andernfalls möglicherweise Dienste, nicht gestartet werden. Dies umfasst alle Active Directory-Objekt, wie Benutzer, Contact-Objekte, administrative Gruppen oder eine andere Art des Objekts. Set-CsUserReplicatorConfiguration - ADDomainNamingContextList können Sie nur die Domänen mit Skype für Business Server-Objekte hinzufügen, falls erforderlich.
    
9. **Schritt 6: Überprüfen der Replikation in der Domäne**
    
    a. Klicken Sie auf die **Skype für Business Server-Verwaltungsshell** aus der Seite **Apps** um PowerShell zu starten.
    
    b. Verwenden Sie den Befehl Get-CsAdDomain zum Überprüfen der Replikation innerhalb der Domäne an.
    
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
  
    c. Wenn das Ergebnis **LC_DOMAINSETTINGS_STATE_READY**ist, hat die Domäne erfolgreich repliziert.
    
10. **Schritt 7: Hinzufügen von Benutzern zum administrativen Zugriff auf die Skype Business Server-Systemsteuerung zu ermöglichen.**
    
    a. Melden Sie sich als Mitglied der Gruppe „Domänen-Admins“ oder „RTCUniversalServerAdmins“ an.
    
    b. Öffnen Sie **Active Directory-Benutzer und -Computer**, erweitern Sie Ihre Domäne und klicken Sie auf den Container **Users**. Klicken Sie dann mit der rechten Maustaste auf „CSAdministrator“ und wählen Sie **Eigenschaften** aus.
    
    c. Klicken Sie im Fenster **CSAdministrator-Eigenschaften** auf die Registerkarte **Mitglieder**.
    
    d. Klicken Sie auf der Registerkarte **Mitglieder** auf **Hinzufügen**. Suchen Sie unter **Benutzer, Kontakte, Computer, Dienstkonten oder Gruppen auswählen** **Geben Sie die zu verwendenden Objektnamen ein**. Geben Sie den Benutzernamen oder den Namen der Gruppe Teilnehmer die Gruppe CSAdministrators hinzu. Klicken Sie anschließend auf **OK**.
    
    e. Vergewissern Sie sich, dass die Benutzer oder Gruppen, die von Ihnen gewählten vorhanden sind, auf die Registerkarte **Mitglieder** . Klicken Sie anschließend auf **OK**.
    
    > [!CAUTION]
    > Die Skype Business Server-Systemsteuerung ist ein rollenbasierten. Mitgliedschaft in der Gruppe CsAdministrator bietet ein Benutzer, der die Skype für Business Server-Systemsteuerung Vollzugriff auf alle verfügbaren Konfigurationsfunktionen verwendet wird. Es sind weitere Rollen verfügbar, die für spezifische Funktionen konzipiert sind. Informationen zu den verfügbaren Rollen finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Beachten Sie, dass Benutzer nicht für Skype für Business Server aktiviert werden soll, um die Mitglieder der Verwaltungsgruppen vorgenommen werden. 
  
    > [!CAUTION]
    > Um die Aufrechterhaltung von Sicherheit und Integrität der rollenbasierten-Steuerelement, Hinzufügen von Benutzern zu Gruppen, die definieren, welche Rolle der Benutzer bei der Verwaltung der der Skype für Business Server-Bereitstellung ausführt. 
  
11. Melden Sie sich ab, und melden Sie sich an Windows an, dass Ihre Sicherheitstoken mit der neuen Skype für Business Server-Sicherheitsgruppe aktualisiert wird, und öffnen Sie den Bereitstellungs-Assistenten klicken Sie dann erneut.
    
12. Vergewissern Sie sich, dass neben **Active Directory vorbereiten** ein grünes Häkchen angezeigt wird. Dies gibt an, dass der Vorgang erfolgreich war (siehe Abbildung).
    
     ![Vorbereiten von Active Directory abgeschlossen.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

