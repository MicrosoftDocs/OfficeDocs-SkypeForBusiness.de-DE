---
title: "Problembehebung von Anmeldefehlern (Administratoren) in Skype for Business Online"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# Problembehebung von Anmeldefehlern (Administratoren) in Skype for Business Online

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#MT_Footer).  
  
Starten Sie Skype for Business Online-Anmeldefehler zur Problembehandlung, durch die häufigsten Ursachen der Anmeldung Probleme beseitigen. Bei Bedarf können Sie dann bestimmte Schritte auf den Typ des Fehlers entsprechend Auflösung folgen. Wenn der Benutzer trotzdem nicht anmelden kann, sammeln Sie zusätzlicher Informationen und dann anfordern Sie weiterer Unterstützung.
  
## Was möchten Sie tun?
<a name="__top"> </a>

> [Prüfen der häufigsten Ursachen für Skype for Business Online-Anmeldefehler](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [Ausführen von Lösungsschritten bei einem bestimmten Fehler (nur Unternehmen)](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [Hinzufügen eines Firewall-Eintrags für "msoidsvc.exe" auf dem Proxyserver](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [Aktualisieren der DNS-Einstellungen](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [Installieren eines Zertifikats einer Drittanbieter-Zertifizierungsstelle auf dem ADFS-Server](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [Aktualisieren der Sicherheitsanmeldeinformationen](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [Ändern des Registrierungsschlüssels "TrustModelData"](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [Aktualisieren der Benutzereinstellungen in Active Directory.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [Verwenden des Problembehandlungsleitfadens von Microsoft Support](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [Sammeln zusätzlicher Informationen und Anfordern weiterer Unterstützung](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## Prüfen der häufigsten Ursachen für Skype for Business Online-Anmeldefehler
<a name="__toc323194094"> </a>

Die meisten Probleme beim Anmelden mit wenigen Ursachen verfolgt werden können, und viele dieser Probleme einfach zu korrigieren. Die folgende Tabelle enthält einige häufige Ursachen für Anmeldefehler und einige Schritte, die Sie oder die Benutzer ergreifen können, um diese zu beheben.
  
|**Mögliche Ursache**|**Lösung**|
|:-----|:-----|
|Bei der Anmeldung wird ein Dialogfeld angezeigt, die folgendem Wortlaut: **kann nicht bestätigt werden, dass der Server für Ihre Anmeldeadresse vertrauenswürdig ist. Trotzdem verbinden?** <br/> |Vergewissern Sie sich, dass der Domänenname im Dialogfeld einen vertrauenswürdigen Server in Ihrer Organisation angibt, z. B. **Domänenname.contoso.com**. Bitten Sie den Benutzer, das Kontrollkästchen **Immer diesem Server vertrauen** zu aktivieren und dann auf **Verbinden zu klicken**. <br/> Unternehmenskunden können verhindern, dass diese Meldung angezeigt wird, wenn ein Benutzer sich zum ersten Mal anmeldet, indem sie die Windows-Registrierung auf dem Computer eines jeden Benutzers ändern. Einzelheiten hierzu finden Sie unter [Ändern des Registrierungsschlüssels "TrustModelData"](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry).  <br/> |
|Schreibfehler in Anmeldeadresse, Benutzernamen oder Kennwort  <br/> | Stellen Sie sicher, dass Anmeldeadresse, Benutzername und Kennwort richtig geschrieben sind. <br/>  Vergewissern Sie sich, dass der Anmeldename des Benutzers wie folgt formatiert ist: **bobk@contoso.com**. Möglicherweise unterscheidet sich dieses Format von dem, das Sie für die Anmeldung beim Netzwerk Ihrer Organisation verwenden.  <br/>  Bitten Sie den Benutzer, versuchen erneut, sich anzumelden. <br/> |
|Kennwort vergessen  <br/> |Setzen Sie das Kennwort des Benutzers zurück, und teilen Sie dem Benutzer sein neues, temporäres Kennwort mit.  <br/> |
|Keine Lizenz Skype for Business Online  <br/> |Bestätigen Sie, dass der Benutzer als Skype for Business Online Benutzer registriert ist. Wenn dies nicht der Fall, Registrieren des Benutzers, und klicken Sie dann bitten Sie ihn erneut anmelden.  <br/> |
|Falsche Version von Skype for Business Online installiert  <br/> |Bei diesem Problem wird in der Regel eine Fehlermeldung mit folgendem Wortlaut angezeigt: **Der Authentifizierungsdienst ist mit dieser Version des Programms nicht kompatibel**.  <br/> Bitten Sie den Benutzer, zu deinstallieren und Skype for Business Online vom Office 365-Portal an.  <br/> |
|Beim Abrufen eines zum Anmelden erforderlichen persönlichen Zertifikats ist ein Problem aufgetreten.  <br/> |Wenn Anmeldeadresse des Benutzers zuletzt geändert hat, müssen sie möglicherweise zwischengespeicherte Daten löschen. Bitten Sie Benutzer abmelden, klicken Sie auf das Löschen Meine Infos Anmeldung auf dem Bildschirm Anmeldung verknüpfen, und versuchen Sie es dann erneut.  <br/> |
|Sie haben einen benutzerdefinierten Domänennamen eingerichtet, und die Änderungen wurden möglicherweise noch nicht im gesamten System übernommen.  <br/> |Zunächst stellen Sie sicher, dass Sie die Einträge Dienst DNS (Domain Name) die Änderung entsprechend geändert haben.  <br/> Wenn Sie die notwendigen DNS-Änderungen bereits vorgenommen haben, bitten Sie den Benutzer, sich später anzumelden. Bei DNS-Änderungen kann es bis zu 72 Stunden dauern, bis sie im gesamten System übernommen wurden.  <br/> |
|Systemuhr nicht synchron mit Serveruhr  <br/> |Stellen Sie sicher, dass Ihr Netzwerkdomänencontroller mit einer zuverlässigen externen Quelle synchronisiert wird. Ausführliche Informationen hierzu finden Sie im Microsoft Knowledge Base-Artikel 816042, [Konfigurieren eines autorisierenden Zeitservers in Windows Server](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).  <br/> |
   
[Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss. Die englische Version des Artikels ist als Referenz hier verfügbar: hierhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Starten Sie Skype for Business Online-Anmeldefehler zur Problembehandlung, durch die häufigsten Ursachen der Anmeldung Probleme beseitigen. Bei Bedarf können Sie dann bestimmte Schritte auf den Typ des Fehlers entsprechend Auflösung folgen. Wenn der Benutzer trotzdem nicht anmelden kann, sammeln Sie zusätzlicher Informationen und dann anfordern Sie weiterer Unterstützung.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Ausführen von Lösungsschritten bei einem bestimmten Fehler (nur Unternehmen)
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> Diese Anweisungen wenden sich in erster Linie an Kunden von Microsoft Office 365 Plan E. Wenn Sie ein Office 365 Plan P-Kunde sind, fahren Sie mit dem folgenden Abschnitt, [Sammeln zusätzlicher Informationen und Anfordern weiterer Unterstützung](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1), fort. 
  
Wenn die Vorschläge im obigen Abschnitt nicht zu einer Lösung des Problems geführt haben und sich der Benutzer noch nicht anmelden kann, können Sie auf Basis der Fehlerart weitere Problemlösungsstrategien anwenden. In der nachstehenden Tabelle werden die häufigsten Fehlermeldungen und mögliche Ursachen aufgelistet. Im Anschluss an die Tabelle sind die Prozeduren für jedes Problem im Detail beschrieben.
  
|**Fehlermeldung**|**Mögliche Ursache**|**Lösung**|
|:-----|:-----|:-----|
|Diese Anmeldeadresse wurde nicht gefunden.  <br/> |Anmeldeanforderungen vom Microsoft Online Services-Anmelde-Assistent (msoidsvc.exe) werden von der externen Firewall (oder dem Proxyserver) nicht durchgelassen.  <br/> |[Hinzufügen eines Firewall-Eintrags für "msoidsvc.exe" auf dem Proxyserver](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|Der Server ist vorübergehend nicht verfügbar.  <br/> |Wenn Ihre Organisation über eine benutzerdefinierte Domäne verfügt, fehlen möglicherweise DNS-Einstellungen (Domain Name System), oder die Einstellungen sind fehlerhaft.  <br/> |[Aktualisieren der DNS-Einstellungen](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|Der Server ist vorübergehend nicht verfügbar.  <br/> |Wenn Ihre Organisation das einmalige Anmelden mit ADFS (Active Directory Federation Services) nutzt, wurde möglicherweise anstelle eines Zertifikats von einer Drittanbieter-Zertifizierungsstelle ein selbstsigniertes SSL-Zertifikat (Secure Socket Layer) verwendet.  <br/> |[Installieren eines Zertifikats einer Drittanbieter-Zertifizierungsstelle auf dem ADFS-Server](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|Beim Abrufen eines zum Anmelden erforderlichen persönlichen Zertifikats ist ein Problem aufgetreten.  <br/> |Wenn Sie bereits entfernt haben die Cache Serverdaten verwendet, um melden Sie sich und die Fehlermeldung weiterhin angezeigt, Sicherheitsanmeldeinformationen des Benutzers ist möglicherweise beschädigt oder ein RSA-Ordner auf dem Computer des Benutzers blockiert möglicherweise Authentifizierung.  <br/> |[Aktualisieren der Sicherheitsanmeldeinformationen](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|Wenn sich der Benutzer zum ersten Mal anmeldet, wird ein Dialogfeld zur Vertrauenswürdigkeit des Zertifikats angezeigt.  <br/> |Dieses Dialogfeld wird angezeigt, wenn Ihre Skype for Business-Server noch nicht im Registrierungsschlüssel **TrustModelData** aufgeführt ist. <br/> |[Ändern des Registrierungsschlüssels "TrustModelData"](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|Der Benutzer verfügt über keine SIP-Aktivierung.  <br/> |Wenn Ihre Organisation vorher Microsoft Office Communications Server oder Microsoft Lync Server 2010 installiert hatte, haben Sie die Benutzer möglicherweise vor der Außerbetriebsetzung nicht vom Server gelöscht. Dementsprechend ist das Attribut **msRTCSIP-UserEnabled** in den Active Directory-Domänendiensten immer noch auf **FALSE** festgelegt. <br/> |[Aktualisieren der Benutzereinstellungen in Active Directory.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### Hinzufügen eines Firewall-Eintrags für "msoidsvc.exe" auf dem Proxyserver
<a name="__add_a_firewall"> </a>

Diese Prozedur kann möglicherweise auch bei folgender Fehlermeldung zum Erfolg führen: **Diese Anmeldeadresse wurde nicht gefunden**.
  
 **HINWEIS**: Bei den folgenden Schritten wird die Verwendung von Microsoft Forefront Threat Management Gateway (TMG) 2010 vorausgesetzt. Wenn Sie mit einer anderen Web-Gateway-Lösung arbeiten, verwenden Sie die nachstehend in Schritt 4 beschriebenen Einstellungen.
  
Führen Sie die folgenden Schritte aus, um einen Anwendungseintrag für "Msoidsvc.exe" in Forefront TMG 2010 zu erstellen:
  
1. Klicken Sie im linken Bereich von Forefront auf **Netzwerk**.
    
2. Klicken Sie auf die Registerkarte **Netzwerk**. Klicken Sie auf der Registerkarte **Tasks** im rechten Bereich auf **Forefront TMG - Clienteinstellungen konfigurieren**.
    
3. Klicken Sie im Dialogfeld **Forefront TMG - Clienteinstellungen** auf **Neu**.
    
4. Konfigurieren Sie im Dialogfeld **Anwendungseintragseinstellungen** die folgenden Regeln:
    
|****Anwendung****|****Schlüssel****|****Wert****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Deaktivieren  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
Weitere Informationen finden Sie im Microsoft Knowledge Base-Artikel 2409256, [keine Verbindung zu Skype für Business Online aufgrund einer lokalen die Verbindung Firewall](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).
  
### Aktualisieren der DNS-Einstellungen
<a name="__update_dns_service"> </a>

Wenn Ihre Organisation über eine benutzerdefinierte Domäne verfügt, kann diese Prozedur möglicherweise auch bei folgender Fehlermeldung zum Erfolg führen: **Der Server ist vorübergehend nicht verfügbar.**.
  
- Bitten Sie Ihre Domänenregistrierungsstelle um Informationen, wie Sie Ihrer Domäne den folgenden CNAME-Eintrag hinzufügen können:
    
  - **DNS-Eintragstyp**: CNAME
    
  - **Name**: sip
    
  - **Wert/Ziel**: sipdir.online.microsoft.com
    
Details finden Sie im Microsoft Knowledge Base-Artikel 2566790, [Problembehandlung Skype Konfigurationsprobleme Online DNS Business in Office 365](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)und Office 365 Wiki-Artikel, [um Ihr Netzwerk funktioniert mit Skype for Business (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156).
  
### Installieren eines Zertifikats einer Drittanbieter-Zertifizierungsstelle auf dem ADFS-Server
<a name="__verify_upn_and"> </a>

Führen Sie die folgenden Schritte aus, um ein SSL-Zertifikat eines Drittanbieters auf Ihrem ADFS-Server (Active Domain Federation Services) zu installieren:
  
1. Fordern Sie von einer Drittanbieter-Zertifizierungsstelle (z. B. VeriSign oder Thawte) ein SSL-Zertifikat an.
    
2. Installieren Sie das Zertifikat mithilfe der ADFS-Verwaltungskonsole auf dem ADFS-Server.
    
### Aktualisieren der Sicherheitsanmeldeinformationen
<a name="__update_security_credentials_1"> </a>

Diese Prozedur führt möglicherweise bei folgender Fehlermeldung zum Erfolg: **Problem beim Abrufen eines persönlichen Zertifikats, das zur Anmeldung erforderlich ist**.
  
Zum Beheben möglicher Probleme mit dem Zertifikat oder den Anmeldeinformationen erneuern Sie zuerst in der Windows-Zertifikatverwaltung das Benutzerzertifikat. Führen Sie dazu die folgenden Schritte aus:
  
1. Öffnen Sie die Windows-Zertifikatverwaltung. Klicken Sie dazu auf **Start**, klicken Sie auf **Ausführen**, geben Sie **certmgr.msc** ein, und klicken Sie dann auf **OK**.
    
2. Doppelklicken Sie auf **Eigene Zertifikate**, und doppelklicken Sie dann auf **Zertifikate**.
    
3. Sortieren Sie nach der Spalte **Ausgestellt von**, und suchen Sie dann nach einem Zertifikat, das von Communications Server ausgestellt wurde.
    
4. Klicken Sie mit der rechten Maustaste auf das Zertifikat, und klicken Sie dann auf **Löschen**.
    
Wenn der Benutzer mit Windows 7 arbeitet, entfernen Sie als Nächstes die gespeicherten Anmeldeinformationen in der Windows-Anmeldeinformationsverwaltung. Führen Sie dazu die folgenden Schritte aus:
  
1. Klicken Sie auf **Start**, klicken Sie auf **Systemsteuerung**, und klicken Sie dann auf **Anmeldeinformationsverwaltung**.
    
2. Suchen Sie nach den Satz Anmeldeinformationen, der Verbindung zu Skype for Business Online verwendet wird.
    
3. Erweitern Sie den Satz Anmeldeinformationen und klicken Sie dann auf **Aus Tresor entfernen**.
    
4. Melden Sie sich erneut, und geben Sie die Anmeldeinformationen des Benutzers erneut ein.
    
Wenn sich der Benutzer nach dem Aktualisieren seiner Anmeldeinformationen immer noch nicht anmelden kann, versuchen Sie, den RSA-Ordner auf dem Computer des Benutzers zu löschen, da er möglicherweise den Abschluss des Benutzerauthentifizierungsprozesses verhindert:
  
1. Melden Sie sich mit einem Administratorkonto auf dem Computer des Benutzers an.
    
2. Falls erforderlich, aktivieren Sie die Ordner Ansichtsoption **Anzeigen versteckter Dateien**.
    
3. Geben Sie die folgende Zeichenfolge in der Adressleiste von Datei-Explorer ein: **C:\\Dokumente und Einstellungen\\Benutzername\\Anwendungsdaten\\Microsoft\\Crypto\\RSA**, wobei ** *Benutzername* ** ** Ihr Windows-Anmeldename** ist.
    
4. Löschen Sie alle Ordner, deren Namen mit **S-1-5-21-** beginnen (gefolgt von einer Zahlenfolge).
    
### Ändern des Registrierungsschlüssels "TrustModelData"
<a name="__modify_trustmodeldata_registry"> </a>

Wenn sich der Benutzer zum ersten Mal anmeldet, diese erhalten möglicherweise ein Dialogfeld mit etwa wie folgt angezeigt: **kann nicht bestätigt werden, dass der Server für Ihre Anmeldeadresse vertrauenswürdig ist. Trotzdem verbinden?** Dies ist ein Sicherheitsfeature und nicht um einen Fehler. Allerdings können Sie verhindern, dass die im Dialogfeld angezeigt wird, mithilfe einer Gruppe Objekt (Gruppenrichtlinienobjekt) Computern von Benutzern mit Ihrem Domänennamen zu aktualisieren, bevor sie sich zum ersten Mal anmelden. Um dies zu erreichen, führen Sie folgende Schritte aus:
  
- Erstellen Sie ein Gruppenrichtlinienobjekt und stellen, die Ihren Domänennamen Skype for Business anfügt - beispielsweise domainName.contoso.comto den aktuellen Wert von "hkey_local_machine\\software\\policies\\microsoft\\communicator\\trustmodeldata" anfügt.
    
> [!IMPORTANT]
> Sie müssen Ihren Domänennamen an den vorhandenen Wert  *anhängen*  ; Sie können den Wert nicht einfach ersetzen.
  
Ausführliche Informationen hierzu finden Sie im Microsoft Knowledge Base-Artikel 2531068, [Skype for Business (Lync) kann nicht überprüfen, ob der Server für Ihre Anmeldeadresse als vertrauenswürdig eingestuft ist](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).
  
### Aktualisieren der Benutzereinstellungen in Active Directory.
<a name="__update_user_settings_1"> </a>

Wenn Ihre Organisation vorher Microsoft Office Communications Server oder Microsoft Lync Server 2010 installiert hatte, haben Sie die Benutzer möglicherweise vor der Außerbetriebsetzung nicht vom Server gelöscht. Dementsprechend ist das Attribut **msRTCSIP-UserEnabled** in den Active Directory-Domänendiensten immer noch auf **FALSE** festgelegt.
  
Zur Behebung des Problems führen Sie die folgenden Schritte aus:
  
1. Aktualisieren Sie das Attribut **msRTCSIP-UserEnabled** für alle betroffenen Benutzer mit dem Wert **TRUE**.
    
2. Führen Sie das Microsoft Online Services-Verzeichnis Synchronisierung Tool (DirSync) erneut aus. Details finden Sie unter [AIntegrate Ihrer lokalen Verzeichnissen mit Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).
    
[Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss. Die englische Version des Artikels ist als Referenz hier verfügbar: hierhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Starten Sie Skype for Business Online-Anmeldefehler zur Problembehandlung, durch die häufigsten Ursachen der Anmeldung Probleme beseitigen. Bei Bedarf können Sie dann bestimmte Schritte auf den Typ des Fehlers entsprechend Auflösung folgen. Wenn der Benutzer trotzdem nicht anmelden kann, sammeln Sie zusätzlicher Informationen und dann anfordern Sie weiterer Unterstützung.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## Verwenden des Problembehandlungsleitfadens von Microsoft Support
<a name="__toc325626447"> </a>

Wenn Sie danach immer noch nicht beheben Anmeldeprobleme des Benutzers sind, überprüfen Sie die Vorschläge im Microsoft Knowledge Base-Artikel 2541980, [Behandlung von Anmeldeproblemen in Skype für Business Online](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).
  
## Sammeln zusätzlicher Informationen und Anfordern weiterer Unterstützung
<a name="__collect_more_information_1"> </a>

Wenn Sie die oben angegebenen Anleitung durchgeführt haben und Ihre Anmeldeproblemen weiterhin können nicht aufgelöst werden, müssen Sie zusätzliche Informationen gesammelt und wenden Sie sich an den technischen Support. Gehen Sie dazu folgendermaßen vor:
  
1. Beziehen Sie die Protokolldateien und Windows Log Ereignisdetails aus dem Computer des Benutzers ein. Schrittweise Anweisungen finden Sie unter den Endbenutzer Hilfethema [Aktivieren der Fehlerprotokollierung in Skype for Business (Lync)](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).
    
2. Senden Sie die Protokolldateien und detaillierte Informationen zu dem Fehler an den technischen Support von Microsoft:
    
Möglicherweise werden Sie gebeten, zusätzliche Diagnoseinformationen bereitzustellen, indem Sie das MOSDAL-Support-Toolkit (Microsoft Online Services Diagnostic and Logging) auf dem Computer des betroffenen Benutzers installieren. Details finden Sie unter [Verwenden des MOSDAL-Support-Toolkits](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).
  
[Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss. Die englische Version des Artikels ist als Referenz hier verfügbar: hierhttps://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1. Starten Sie Skype for Business Online-Anmeldefehler zur Problembehandlung, durch die häufigsten Ursachen der Anmeldung Probleme beseitigen. Bei Bedarf können Sie dann bestimmte Schritte auf den Typ des Fehlers entsprechend Auflösung folgen. Wenn der Benutzer trotzdem nicht anmelden kann, sammeln Sie zusätzlicher Informationen und dann anfordern Sie weiterer Unterstützung.](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

