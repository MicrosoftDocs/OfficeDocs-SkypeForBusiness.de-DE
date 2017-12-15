---
title: "Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren

> [!NOTE]
> Skype for Business-Partnerverbund ist für Organisationen, die Office 365 (betrieben von 21Vianet) oder Office 365 Deutschland verwenden, nicht verfügbar. 
  
Führen Sie die Schritte in diesem Artikel in folgenden Fällen aus:
  
- In Ihrem Unternehmen befinden sich Benutzer in verschiedenen Domänen. Beispiel: Rob@ContosoEast.com und Ann@ContosoWest.com.
    
- Sie möchten den Personen in Ihrer Organisation die Möglichkeit geben, Skype for Business zu verwenden, um Personen in bestimmten Unternehmen außerhalb Ihrer Organisation zu kontaktieren.
    
- ODER Sie möchten, dass alle anderen Skype for Business-Benutzer aus aller Welt Sie anhand Ihrer E-Mail-Adresse finden und Kontakt zu Ihnen aufnehmen können. Wenn Sie und die anderen Benutzer die Standardeinstellungen für Skype for Business verwenden, funktioniert dies automatisch. Anderenfalls müssen sie sicherstellen, dass Ihre Domäne nicht durch ihre Konfiguration blockiert wird.
    
## Aktivieren der Business-to-Business-Kommunikation für die Benutzer
<a name="bk_preview"> </a>

Sie benötigen [Informationen zu Administratorrollen von Office 365](about-office-365-admin-roles.md) in Office 365 zu diesem Zweck.
  
1. Melden Sie sich mit Ihrem Office 365-Administratorkonto an. 
    
2. Gehen Sie im Office 365 Admin Center zu **Admin Center** > **Skype for Business**.
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. Wählen Sie unter **Skype for Business Admin Center**die Option **Organisation** > **Externe Kommunikation** aus.
    
4. Um die Kommunikation mit einem bestimmten Unternehmen oder mit Benutzern in einer anderen Domäne einzurichten, wählen Sie im Dropdownfeld die Option **Nur für zulässige Domänen aktivieren** aus.
    
    ODER wählen Sie, wenn Sie die Kommunikation mit allen anderen Unternehmen aktivieren möchten, die über offene Skype for Business-Richtlinien verfügen, die Option **Aktivieren mit Ausnahme der blockierten Domänen** aus. Dies ist die Standardeinstellung.
    
5. Wählen Sie unter **Blockierte oder zulässige Domänen** die Option **+** aus, und fügen Sie den Namen der Domäne hinzu, die Sie zulassen möchten.
    
6. Sorgen Sie nun dafür, dass der Administrator in der anderen Organisation in seinem **Skype for Business Admin Center**die gleichen Schritte ausführt. Beispiel: In der Liste der **zulässigen Domänen** muss der Administrator der anderen Organisation die Domäne für Ihr Unternehmen eingeben.
    
7. Wenn Sie die Windows-Firewall verwenden, öffnet Skype for Business die erforderlichen Ports automatisch.
    
    Wenn Ihre Organisation die Internetverbindung von Computern in Ihrem Netzwerk mit einer anderen Firewall-Lösung einschränkt, vergewissern Sie sich, dass Ihre Clientcomputer auf die folgenden [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) zugreifen können. Dafür müssen Sie möglicherweise die FQDNs der Liste für zugelassene ausgehende Verbindungen in Ihrer Firewall oder Proxy-Infrastrukturkonfiguration hinzufügen: **„*.api.skype.com", „*.users.storage.live.com" und „graph.skype.com"**. Anweisungen zum Öffnen dieser Ports in Ihrer Firewall finden Sie in der zugehörigen Dokumentation.
    
    Eine Liste aller Ports, die Sie öffnen müssen, finden Sie unter [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo) im Artikel[URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
8. **WARTEN SIE MIT DEM TEST BIS ZU 24 STUNDEN**. Bei jeder Änderung der Einstellungen für externe Kommunikation kann es bis zu 24 Stunden dauern, bis die Änderungen in allen Rechenzentren übernommen wurden.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Sie können Ihren Benutzern jetzt die Möglichkeit geben, nach beliebigen Benutzern von Skype, der kostenlosen Heimanwender-App, zu suchen und Chatnachrichten mit ihnen auszutauschen! Weitere Informationen finden Sie unter[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).
  
## Tests und Problembehandlung
<a name="bk_preview"> </a>

 **Am häufigsten haben Benutzer beim Einrichten der Kommunikation zwischen Unternehmen Probleme damit, die [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) richtig festzulegen.**
  
Um Ihr Setup zu testen, benötigen Sie einen Kontakt in Skype for Business, der sich nicht hinter der Firewall Ihrer Firma befindet.
  
1. Warten Sie nach einer Änderung der Einstellungen für externe Kommunikation **BIS ZU 24 STUNDEN, BEVOR SIE TESTS DURCHFÜHREN**.
    
2. Suchen Sie in Skype for Business nach Ihrem Kontakt in Skype for Business, und senden Sie eine Chatanfrage.
    
    Wenn Sie durch eine Meldung informiert werden, dass die Anfrage aufgrund einer Unternehmensrichtlinie nicht gesendet werden konnte, müssen Sie Ihre [URLs und IP-Adressbereiche von Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) nochmals überprüfen.
    
3. Bitten Sie Ihren Skype for Business-Kontakt, Ihnen eine Chatanfrage zu senden. Wenn Sie die Anfrage nicht erhalten, stellen die Firewalleinstellungen das Problem dar (dabei wird angenommen, dass der Kontakt bereits die Richtigkeit seiner Firewalleinstellungen überprüft hat).
    
4. Eine weitere Möglichkeit, zu testen, ob die Firewall das Problem darstellt: Gehen Sie zu einem Ort mit WLAN, der sich nicht hinter Ihrer Firewall befindet (zum Beispiel in ein Café), und senden Sie mit Skype for Business eine Chatanfrage an Ihren Kontakt. Wenn die Nachricht dort gesendet wird, an Ihrem Arbeitsplatz aber nicht, wissen Sie, dass die Firewall das Problem darstellt.
    
## Beim Herstellen einer Verbindung mit einem anderen Unternehmen andere Personen finden und selbst gefunden werden
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation mit anderen Skype for Business-Benutzern aktiviert haben, können Ihre Benutzer Skype for Business-Partnerbenutzer finden, indem sie nach ihrem Anmeldenamen suchen, zum Beispiel Rob@contoso.com. Anschließend müssen sie die Person zu ihrer Kontaktliste hinzufügen.
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## Tipps zum Einrichten der Kommunikation mit Partnerunternehmen
<a name="bk_preview"> </a>

- Informationen zum Konfigurieren des Verbunds zwischen Skype for Business 2015 und Skype for Business Online finden Sie in folgendem TechNet-Artikel: [Konfigurieren eines Partnerverbunds in Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Informationen zum Konfigurieren des Verbunds zwischen Lync und Skype for Business Online finden Sie in folgendem TechNet-Artikel: [Konfigurieren der Unterstützung für einen Partnerverbund mit einem Lync Online-Kunden](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Wenn zwei Skype for Business-Benutzer in Office 365 auf verschiedenen Domänen miteinander kommunizieren, können sie nur Skype for Business-Funktionen nutzen, die in beiden Organisationen aktiviert wurden (zum Beispiel Videounterhaltung oder Desktopfreigabe).
    
- Wenn für einen Skype for Business-Benutzer in Ihrer Organisation ein In-Situ-Speicher oder Beweissicherungsverfahren aktiviert wird, werden alle Chatunterhaltungen zwischen diesem Benutzer und anderen Benutzern von Skype for Business oder Skype in seinem Postfach unter **Wiederherstellbare Elemente** gespeichert. Diese Unterhaltungen werden nicht im Ordner **Aufgezeichnete Unterhaltungen** im jeweiligen Postfach gespeichert.
    
## Externe Kommunikation für bestimmte Personen deaktivieren
<a name="bk_preview"> </a>

Nachdem Sie die externe Kommunikation für Ihr gesamtes Unternehmen aktiviert haben, können Sie sie für bestimmte Personen deaktivieren.
  
1. Melden Sie sich mit Ihrem Office 365-Administratorkonto an.
    
2. Gehen Sie im Office 365 Admin Center zu **Benutzer** > **Aktive Benutzer**.
    
3. Wählen Sie den Benutzer in der Liste der Benutzer aus, und klicken Sie dann unter **Weitere Einstellungen** auf **Edit Skype for Business properties** (Skype for Business-Eigenschaften bearbeiten).
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Wählen Sie im **Skype for Business Admin Center** die Option **Externe Kommunikation** aus.
    
    Auf der Seite **Optionen** sind alle Optionen ausgewählt. Heben Sie die Auswahl der Kommunikationsoptionen auf, die Sie deaktivieren möchten. Die folgende Abbildung zeigt, dass Jakob mit Personen in anderen vertrauenswürdigen Unternehmen kommunizieren kann, aber nicht mit anderen Skype-Benutzern.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Wählen Sie **Speichern** aus.
    
> [!NOTE]
> Sie müssen ggf. bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden. 
  
## 
<a name="bk_preview"> </a>

 *Letzte Aktualisierung: Donnerstag, 23. März 2017* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![Symbol für LinkedIn Learning](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Neu bei Office 365?**         Entdecken Sie kostenlose Videokurse für **Office 365-Administratoren und IT-Experten**, bereitgestellt von LinkedIn Learning. |
   
## Verwandte Themen
<a name="bk_preview"> </a>

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
  

