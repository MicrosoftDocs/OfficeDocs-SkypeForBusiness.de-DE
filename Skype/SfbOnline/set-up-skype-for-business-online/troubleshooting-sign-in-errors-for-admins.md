---
title: Problembehandlung bei Skype for Business Online-Anmeldefehlern für Administratoren
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Setup
description: 'Erfahren Sie mehr über die Ursachen für Skype for Business Online-Anmeldefehler und die Problembehandlung. '
ms.openlocfilehash: edbddf940eeea36ecfdcf6966558b9632c729065
ms.sourcegitcommit: d7c8d03883d4ae4e37af88625dd74ab037eac914
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158963"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Problembehandlung bei Skype for Business Online-Anmeldefehlern für Administratoren

Um Probleme bei der Anmeldung bei Skype for Business Online zu beheben, müssen Sie zunächst die häufigsten Ursachen für Anmeldeprobleme beseitigen. Bei Bedarf können Sie dann bestimmte Lösungsschritte basierend auf der Art des Fehlers ausführen. Wenn sich der Benutzer immer noch nicht anmelden kann, sammeln Sie zusätzliche Informationen, und fordern Sie dann weitere Unterstützung an.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun?
<a name="top"> </a>

> [Überprüfen der häufigsten Ursachen für Anmeldefehler bei Skype for Business Online](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [Ausführen von Lösungsschritten bei einem bestimmten Fehler (nur Unternehmen)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [Hinzufügen eines Firewall-Eintrags für „msoidsvc.exe“ auf dem Proxyserver](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [Aktualisieren der DNS-Einstellungen](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [Installieren eines Zertifikats einer Drittanbieter-Zertifizierungsstelle auf dem ADFS-Server](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [Aktualisieren der Sicherheitsanmeldeinformationen](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [Ändern der TrustModelData-Registrierungsschlüssel](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [Aktualisieren der Benutzereinstellungen in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [Verwenden des Problembehandlungsleitfadens von Microsoft Support](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [Sammeln zusätzlicher Informationen und Anfordern weiterer Unterstützung](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Überprüfen der häufigsten Ursachen für Anmeldefehler bei Skype for Business Online
<a name="toc323194094"> </a>

Die meisten Anmeldeprobleme lassen sich auf eine kleine Anzahl von Ursachen zurückführen, und viele dieser Probleme können leicht behoben werden. In der folgenden Tabelle sind einige häufige Ursachen von Anmeldefehlern sowie einige Schritte aufgelistet, die Sie oder die Benutzer zur Behebung des Problems durchführen können.


| **Mögliche Ursache**                                                                                                                                                    | **Lösung**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Bei der Anmeldung wird ein Dialogfeld angezeigt, das den folgenden Satz enthält: **kann nicht überprüfen, ob der Server für Ihre Anmeldeadresse als vertrauenswürdig eingestuft ist. Verbindung trotzdem herstellen?** <br/> | Stellen Sie sicher, dass der Domänenname im Dialogfeld ein vertrauenswürdiger Server in Ihrer Organisation ist, z. B. **domainName.contoso.com**. Bitten Sie den Benutzer, das Kontrollkästchen **Diesem Server immer vertrauen** zu aktivieren, und klicken Sie dann auf **Verbinden**. <br/> Unternehmenskunden können verhindern, dass diese Meldung angezeigt wird, wenn ein Benutzer sich zum ersten Mal anmeldet, indem sie die Windows-Registrierung auf dem Computer eines jeden Benutzers ändern. Weitere Informationen finden Sie unter [Ändern der TrustModelData-Registrierungsschlüssel](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
| Schreibfehler in Anmeldeadresse, Benutzernamen oder Kennwort  <br/>                                                                                                               | Stellen Sie sicher, dass Anmeldeadresse, Benutzername und Kennwort richtig geschrieben sind. <br/>  Vergewissern Sie sich, dass der Anmeldename des Benutzers wie folgt formatiert ist: <strong>bobk@contoso.com</strong>. Möglicherweise unterscheidet sich dieses Format von dem, das Sie für die Anmeldung beim Netzwerk Ihrer Organisation verwenden.  <br/>  Bitten Sie den Benutzer, sich noch mal anzumelden. <br/>                                                                                                                                                                                                                             |
| Kennwort vergessen  <br/>                                                                                                                                             | Setzen Sie das Kennwort des Benutzers zurück und teilen Sie dem Benutzer sein neues, temporäres Kennwort mit.  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Nicht für die Nutzung von Skype for Business Online lizenziert  <br/>                                                                                                                  | Vergewissern Sie sich, dass der Benutzer als Benutzer von Skype for Business Online registriert ist. Wenn nicht, registrieren Sie den Benutzer, und bitten Sie ihn dann, sich noch mal anzumelden.  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| Falsche Version von Skype for Business Online installiert  <br/>                                                                                                           | Bei diesem Problem wird in der Regel eine Fehlermeldung mit folgendem Wortlaut angezeigt: **Der Authentifizierungsdienst ist mit dieser Version des Programms nicht kompatibel**.  <br/> Bitten Sie den Benutzer, Skype for Business Online zu deinstallieren und dann vom Office 365-Portal erneut zu installieren.  <br/>                                                                                                                                                                                                                                                    |
| Beim Abrufen eines zum Anmelden erforderlichen persönlichen Zertifikats ist ein Problem aufgetreten.  <br/>                                                                                           | Wenn die Anmeldeadresse des Benutzers kürzlich geändert wurde, müssen Sie möglicherweise zwischengespeicherte Anmeldedaten löschen. Bitten Sie die Benutzer, sich abzumelden, auf dem Anmeldebildschirm auf den Link „Meine Anmeldeinformationen löschen“ zu klicken, und es dann erneut zu versuchen.  <br/>                                                                                                                                                                                                                                                                                                                                |
| Sie haben einen benutzerdefinierten Domänennamen eingerichtet, und die Änderungen wurden möglicherweise noch nicht im gesamten System übernommen.  <br/>                                                         | Stellen Sie zuerst sicher, dass Sie die DNS-Einträge (Domain Name Service) geändert haben und die Änderung in den Einträgen enthalten ist.  <br/> Wenn Sie bereits die erforderlichen DNS-Änderungen vorgenommen haben, bitten Sie den Benutzer, sich später anzumelden. Es kann bis zu 72 Stunden dauern, bis DNS-Änderungen im gesamten System widergespiegelt werden.  <br/>                                                                                                                                                                                                                                                        |
| Systemuhr nicht synchron mit Serveruhr  <br/>                                                                                                                     | Stellen Sie sicher, dass der Netzwerkdomänencontroller mit einer zuverlässigen externen Zeitquelle synchronisiert wird. Weitere Informationen finden Sie im Microsoft Knowledge Base-Artikel 816042 [Konfigurieren eines autorisierenden Zeitservers in Windows Server](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/>                                                                                                                                                                                                                                          |

Um Probleme bei der Anmeldung bei Skype for Business Online zu beheben, müssen Sie zunächst die häufigsten Ursachen für Anmeldeprobleme beseitigen. Bei Bedarf können Sie dann bestimmte Lösungsschritte basierend auf der Art des Fehlers ausführen. Wenn sich der Benutzer immer noch nicht anmelden kann, sammeln Sie zusätzliche Informationen, und fordern Sie dann weitere Unterstützung an.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Ausführen von Lösungsschritten bei einem bestimmten Fehler (nur Unternehmen)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Diese Anweisungen richten sich in erster Linie an Kunden von Microsoft Office 365 Plan E. Wenn Sie ein Office 365 Plan P-Kunde sind, fahren Sie mit dem folgenden Abschnitt [Sammeln zusätzlicher Informationen und Anfordern weiterer Unterstützung](troubleshooting-sign-in-errors-for-admins.md#collect-more-information) fort. 

Wenn sich der Benutzer nicht anmelden kann, nachdem Sie die Vorschläge im vorherigen Abschnitt ausprobiert haben, können Sie basierend auf der Art des Fehlers eine zusätzliche Problembehandlung durchführen. In der folgenden Tabelle werden die am häufigsten auftretenden Fehlermeldungen und mögliche Ursachen aufgelistet. Im Anschluss an die Tabelle sind die detaillierten Verfahren zur Behebung des jeweiligen Problems aufgeführt.

|**Fehlermeldung**|**Mögliche Ursache**|**Lösung**|
|:-----|:-----|:-----|
|Diese Anmeldeadresse wurde nicht gefunden.  <br/> |Anmeldeanforderungen vom Microsoft Online Services-Anmelde-Assistent (msoidsvc.exe) werden von der externen Firewall (oder dem Proxyserver) nicht durchgelassen.  <br/> |[Fügen Sie dem Proxyserver einen Firewall-Eintrag für msoidsvc.exe hinzu.](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Der Server ist vorübergehend nicht verfügbar.  <br/> |Wenn Ihre Organisation über eine benutzerdefinierte Domäne verfügt, fehlen möglicherweise DNS-Einstellungen (Domain Name System), oder die Einstellungen sind fehlerhaft.  <br/> |[Aktualisieren der DNS-Einstellungen](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Der Server ist vorübergehend nicht verfügbar.  <br/> |Wenn Ihre Organisation das einmalige Anmelden mit ADFS (Active Directory Federation Services) nutzt, wurde möglicherweise anstelle eines Zertifikats von einer Drittanbieter-Zertifizierungsstelle ein selbstsigniertes SSL-Zertifikat (Secure Socket Layer) verwendet.  <br/> |[Installieren Sie ein Zertifikat einer Drittanbieter-Zertifizierungsstelle auf dem ADFS-Server.](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Beim Abrufen eines zum Anmelden erforderlichen persönlichen Zertifikats ist ein Problem aufgetreten.  <br/> |Wenn Sie die im Zwischenspeicher befindlichen Serverdaten, die für die Anmeldung verwendet werden, bereits entfernt haben und der Fehler weiterhin auftritt, sind die Sicherheitsanmeldeinformationen des Benutzers vielleicht beschädigt, oder ein RSA-Ordner auf dem Computer des Benutzers könnte die Authentifizierung blockieren.  <br/> |[Aktualisieren der Sicherheitsanmeldeinformationen](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Wenn sich der Benutzer zum ersten Mal anmeldet, wird ein Dialogfeld zur Vertrauenswürdigkeit des Zertifikats angezeigt.  <br/> |Dieses Dialogfeld wird angezeigt, wenn der Skype for Business Online-Server noch nicht im Registrierungsschlüssel **TrustModelData** aufgeführt wird. <br/> |[Ändern der TrustModelData-Registrierungsschlüssel](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|Der Benutzer verfügt über keine SIP-Aktivierung.  <br/> |Wenn Ihre Organisation vorher Microsoft Office Communications Server oder Microsoft Lync Server 2010 installiert hatte, haben Sie die Benutzer möglicherweise vor der Außerbetriebsetzung nicht vom Server gelöscht. Dementsprechend ist das Attribut **msRTCSIP-UserEnabled** in den Active Directory-Domänendiensten immer noch auf **FALSE** festgelegt. <br/> |[Aktualisieren der Benutzereinstellungen in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Hinzufügen eines Firewall-Eintrags für "msoidsvc.exe" auf dem Proxyserver
<a name="add-a-firewall"> </a>

Diese Prozedur kann möglicherweise auch bei folgender Fehlermeldung zum Erfolg führen: **Diese Anmeldeadresse wurde nicht gefunden**.

> [!NOTE]
> Bei den folgenden Schritten wird vorausgesetzt, dass Sie Microsoft Forefront Threat Management Gateway (TMG) 2010 verwenden. Wenn Sie über eine andere Webgatewaylösung verfügen, verwenden Sie die in Schritt 4 weiter unten beschriebenen Einstellungen.


Führen Sie die folgenden Schritte aus, um einen Anwendungseintrag für "Msoidsvc.exe" in Forefront TMG 2010 zu erstellen:

1. Klicken Sie im linken Bereich von Forefront auf **Netzwerk**.

2. Klicken Sie auf die Registerkarte **Netzwerk**. Klicken Sie auf der Registerkarte **Tasks** im rechten Bereich auf **Forefront TMG - Clienteinstellungen konfigurieren**.

3. Klicken Sie im Dialogfeld **Forefront TMG – Clienteinstellungen** auf **Neu**.

4. Konfigurieren Sie im Dialogfeld **Anwendungseintragseinstellungen** die folgenden Regeln:

|**Anwendung**|**Schlüssel**|**Wert**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Deaktivieren  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Ausführliche Informationen hierzu finden Sie im Microsoft Knowledge Base-Artikel 2409256, [Keine Verbindung zu Skype for Business Online aufgrund einer lokalen Firewall](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Aktualisieren der DNS-Einstellungen
<a name="update-dns-service"> </a>

Wenn Ihre Organisation über eine benutzerdefinierte Domäne verfügt, kann diese Prozedur möglicherweise auch bei folgender Fehlermeldung zum Erfolg führen: **Der Server ist vorübergehend nicht verfügbar.**.

- Bitten Sie Ihre Domänenregistrierungsstelle um Informationen, wie Sie Ihrer Domäne den folgenden CNAME-Eintrag hinzufügen können:

  - **DNS-Eintragstyp**: CNAME

  - **Name**: sip

  - **Wert/Ziel**: sipdir.online.lync.com

Ausführliche Informationen finden Sie im Microsoft Knowledge Base-Artikel 2566790 [Problembehandlung von DNS-Konfigurationsproblemen bei Skype for Business Online DNS in Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installieren eines Zertifikats einer Drittanbieter-Zertifizierungsstelle auf dem ADFS-Server
<a name="verify-upn-and"> </a>

Führen Sie die folgenden Schritte aus, um ein SSL-Zertifikat eines Drittanbieters auf Ihrem ADFS-Server (Active Domain Federation Services) zu installieren:

1. Fordern Sie von einer Drittanbieter-Zertifizierungsstelle (z. B. VeriSign oder Thawte) ein SSL-Zertifikat an.

2. Installieren Sie das Zertifikat auf Ihrem ADFS-Server mithilfe der ADFS-Verwaltungskonsole.

### <a name="update-security-credentials"></a>Aktualisieren der Sicherheitsanmeldeinformationen
<a name="update-security-credentials"> </a>

Diese Prozedur führt möglicherweise bei folgender Fehlermeldung zum Erfolg: **Problem beim Abrufen eines persönlichen Zertifikats, das zur Anmeldung erforderlich ist**.

Zum Beheben möglicher Probleme mit dem Zertifikat oder den Anmeldeinformationen erneuern Sie zuerst in der Windows-Zertifikatverwaltung das Benutzerzertifikat. Führen Sie hierzu folgende Schritte aus:

1. Öffnen Sie den Windows-Zertifikat-Manager. Klicken Sie hierfür im Startmenü auf **Start**, auf **Ausführen**, geben Sie **certmgr.msc** ein, und klicken Sie dann auf **OK**.

2. Doppelklicken Sie auf **Eigene Zertifikate**, und doppelklicken Sie dann auf **Zertifikate**.

3. Sortieren Sie nach der Spalte **Ausgestellt von**, und suchen Sie dann nach einem Zertifikat, das von Communications Server ausgestellt wurde.

4. Klicken Sie mit der rechten Maustaste auf das Zertifikat, und klicken Sie dann auf **Löschen**.

Wenn der Benutzer mit Windows 7 arbeitet, entfernen Sie als Nächstes die gespeicherten Anmeldeinformationen in der Windows-Anmeldeinformationsverwaltung. Führen Sie hierzu folgende Schritte aus:

1. Klicken Sie auf **Start**, klicken Sie auf **Systemsteuerung**, und klicken Sie dann auf **Anmeldeinformationsverwaltung**.

2. Suchen Sie nach dem Satz Anmeldeinformationen, der für die Skype for Business Online verwendet wird.

3. Erweitern Sie den Satz Anmeldeinformationen, und klicken Sie dann auf **Aus Tresor entfernen**.

4. Melden Sie sich erneut bei Skype for Business Online an, und geben Sie die Anmeldeinformationen des Benutzers neu ein.

Wenn sich der Benutzer nach dem Aktualisieren seiner Anmeldeinformationen immer noch nicht anmelden kann, versuchen Sie, den RSA-Ordner auf dem Computer des Benutzers zu löschen, da er möglicherweise den Abschluss des Benutzerauthentifizierungsprozesses verhindert:

1. Melden Sie sich mit einem Administratorkonto auf dem Computer des Benutzers an.

2. Aktivieren Sie bei Bedarf die Option **Versteckte Dateien anzeigen**.

3. Geben Sie die folgende Zeichenfolge in der Adressleiste von Datei-Explorer ein: **C:\\Dokumente und Einstellungen\\Benutzername\\Anwendungsdaten\\Microsoft\\Crypto\\RSA**, wobei ***Benutzername*** Ihr Windows-Anmeldename ist.

4. Löschen Sie alle Ordner, deren Namen mit **S-1-5-21-** beginnen (gefolgt von einer Zahlenfolge).

### <a name="modify-trustmodeldata-registry-keys"></a>Ändern des Registrierungsschlüssels "TrustModelData"
<a name="modify-trustmodeldata-registry"> </a>

Wenn sich ein Benutzer zum ersten Mal anmeldet, wird möglicherweise ein Dialogfeld angezeigt, das eine Meldung wie die Folgende enthält: **Es kann nicht überprüft werden, ob der Server für Ihre Anmeldeadresse als vertrauenswürdig eingestuft ist. Verbindung dennoch herstellen?** Hierbei handelt es sich um ein Sicherheitsfeature und nicht um einen Fehler. Sie können jedoch verhindern, dass das Dialogfeld angezeigt wird, indem Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) verwenden, um die Computer der Benutzer mit Ihrem Domänennamen zu aktualisieren, bevor Sie sich zum ersten Mal anmelden. Führen Sie dazu die folgenden Schritte aus:

- Erstellen Sie ein GPO, mit dem Ihr Skype for Business-Domänenname, z. B. domainName.contoso.com, an den aktuellen Wert von „HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData angehängt wird, und implementieren Sie es.

> [!IMPORTANT]
>  Sie müssen Ihren Domänennamen an den vorhandenen Wert *anhängen*; Sie können den Wert nicht einfach ersetzen.

Einzelheiten hierzu finden Sie im Microsoft Knowledge Base-Artikel 2531068 [Skype for Business (Lync) kann nicht überprüfen, ob der Server für Ihre Anmeldeadresse als vertrauenswürdig eingestuft ist](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Aktualisieren von Benutzereinstellungen in Active Directory
<a name="update-user-settings"> </a>

Wenn Ihre Organisation vorher Microsoft Office Communications Server oder Microsoft Lync Server 2010 installiert hatte, haben Sie die Benutzer möglicherweise vor der Außerbetriebsetzung nicht vom Server gelöscht. Dementsprechend ist das Attribut **msRTCSIP-UserEnabled** in den Active Directory-Domänendiensten immer noch auf **FALSE** festgelegt.

Führen Sie zum Beheben dieses Problems die folgenden Schritte aus:

1. Aktualisieren Sie das Attribut **msRTCSIP-UserEnabled** für alle betroffenen Benutzer mit dem Wert **TRUE**.

2. Verwenden Sie das Microsoft Online Services-Verzeichnissynchronisierungstool (DirSync). Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://technet.microsoft.com/de-DE/library/hh967642.aspx).

Um Probleme bei der Anmeldung bei Skype for Business Online zu beheben, müssen Sie zunächst die häufigsten Ursachen für Anmeldeprobleme beseitigen. Bei Bedarf können Sie dann bestimmte Lösungsschritte basierend auf der Art des Fehlers ausführen. Wenn sich der Benutzer immer noch nicht anmelden kann, sammeln Sie zusätzliche Informationen, und fordern Sie dann weitere Unterstützung an.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Verwenden des Problembehandlungsleitfadens von Microsoft Support
<a name="toc325626447"> </a>

Wenn Sie weiterhin nicht in der Lage sind, die Anmeldeprobleme der Benutzer zu beheben, lesen Sie die Vorschläge im Microsoft Knowledge Base-Artikel 2541980 [So beheben Sie Probleme mit der Authentifizierung und der Verbindung in Skype for Business Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Sammeln zusätzlicher Informationen und Anfordern weiterer Unterstützung
<a name="collect-more-information"> </a>

Wenn Sie mithilfe der obigen Anleitungen das Problem mit der Anmeldung nicht lösen konnten, müssen Sie zusätzliche Informationen sammeln und sich an den technischen Support wenden. Führen Sie hierzu folgende Schritte aus:

1. Rufen Sie die Protokolldateien und die Windows-Ereignsprotiokolldetails auf dem Computer des Benutzers ab. Eine schrittweise Anleitung finden Sie im Hilfethema [Informationen zur Protokollierung in Lync](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Senden Sie die Protokolldateien und detaillierte Informationen zu dem Fehler an den technischen Support von Microsoft.

Möglicherweise werden Sie gebeten, zusätzliche Diagnoseinformationen bereitzustellen, indem Sie das MOSDAL-Support-Toolkit (Microsoft Online Services Diagnostic and Logging) auf dem Computer des betroffenen Benutzers installieren. Details finden Sie unter [Verwenden des MOSDAL-Support-Toolkits](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Um Probleme bei der Anmeldung bei Skype for Business Online zu beheben, müssen Sie zunächst die häufigsten Ursachen für Anmeldeprobleme beseitigen. Bei Bedarf können Sie dann bestimmte Lösungsschritte basierend auf der Art des Fehlers ausführen. Wenn sich der Benutzer immer noch nicht anmelden kann, sammeln Sie zusätzliche Informationen, und fordern Sie dann weitere Unterstützung an.

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)


