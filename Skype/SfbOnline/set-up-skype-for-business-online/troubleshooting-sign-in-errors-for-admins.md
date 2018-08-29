---
title: Problembehandlung bei Skype für Business Online Anmeldefehlern für Administratoren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Hier erfahren Sie, häufige Ursachen für Skype für Business Online Anmelde-Fehler und Arbeit über diese Problembehandlung. '
ms.openlocfilehash: 88ff25ab4603810d41e92e25a62bfecb3c376246
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255787"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>Problembehandlung bei Skype für Business Online Anmeldefehlern für Administratoren

Um Skype Business Online Fehler zu beheben, starten Sie durch Vermeidung der häufigsten Ursachen der Anmeldung Probleme auftreten. Führen Sie bei Bedarf können Sie klicken Sie dann bestimmten Auflösung Schritte auf den Typ des Fehlers basieren. Wenn der Benutzer noch nicht anmelden kann, zusätzliche Informationen sammeln und dann seek zusätzliche Hilfe.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie tun?
<a name="top"> </a>

> [Kontrollkästchen für häufige Ursachen für Business Online Anmeldefehlern Skype](troubleshooting-sign-in-errors-for-admins.md#toc323194094)

> [Schritte für Lösung für einen bestimmten Fehler (nur Enterprise)](troubleshooting-sign-in-errors-for-admins.md#toc325626440)

> [Hinzufügen eines firewalleintrags für msoidsvc.exe auf den Proxyserver](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)

> [Aktualisieren von DNS-Einstellungen](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)

> [Installieren Sie ein Drittanbieter-SSL-Zertifikat auf dem AD FS-server](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)

> [Aktualisieren von Sicherheitsanmeldeinformationen](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)

> [Ändern Sie Registrierungsschlüssel TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)

> [Aktualisieren von Benutzereinstellungen in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)

> [Verwenden Sie die Microsoft-Supportmitarbeiter Handbuch zur Problembehandlung](troubleshooting-sign-in-errors-for-admins.md#toc325626447)

> [Weitere Informationen zu sammeln und seek zusätzliche Hilfe](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>Kontrollkästchen für häufige Ursachen für Business Online Anmeldefehlern Skype
<a name="toc323194094"> </a>

Die meisten Probleme auf eine kleine Anzahl von Ursachen zurückverfolgt werden können, und viele dieser einfach zu beheben sind. Die folgende Tabelle enthält einige häufige Ursachen für Anmeldefehlern und einige Schritte, mit denen Sie oder die Benutzer zu deren Lösung beschrieben.

|**Mögliche Ursache**|**Lösung**|
|:-----|:-----|
|Anmeldung, ein Dialogfeld wird angezeigt, die den folgenden Ausdruck enthält: **kann nicht überprüft, dass der Server für Ihre Anmeldeadresse vertrauenswürdig ist. Trotzdem verbinden?** <br/> |Stellen Sie sicher, dass der Domänenname im Dialogfeld einen vertrauenswürdigen Server in Ihrer Organisation ist – beispielsweise **domainName.contoso.com**. Bitten Sie den Benutzer das Kontrollkästchen **immer diesen Server vertrauen** aus, und klicken Sie auf **Verbinden**. <br/> Unternehmenskunden können verhindern, dass diese Meldung angezeigt wird, wenn ein Benutzer zum ersten Mal anmeldet durch Ändern der Windows-Registrierung auf dem Computer des Benutzers. Weitere Informationen hierzu finden Sie unter [Registrierungsschlüssel TrustModelData ändern](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry).<br/> |
|Geschriebene Anmeldeadresse, Benutzername oder das Kennwort  <br/> | Vergewissern Sie sich, dass Anmeldenamen und das Kennwort des Benutzers richtig sind. <br/>  Stellen Sie sicher, dass der Anmeldename des Benutzers wie folgt formatiert ist: **bobk@contoso.com**. Dies kann aus dem Format anders lauten, die Sie zur Anmeldung bei des Netzwerks Ihrer Organisation verwenden.  <br/>  Bitten Sie den Benutzer, versuchen erneut, sich anzumelden. <br/> |
|Kennwort vergessen?  <br/> |Das Kennwort des Benutzers zurücksetzen und ihn oder das neue temporäre Kennwort zu benachrichtigen.  <br/> |
|Keine Lizenz für Business Online Skype verwenden  <br/> |Vergewissern Sie sich, dass der Benutzer als einen Skype für Business Online Benutzer registriert ist. Wenn dies nicht der Fall ist, registrieren Sie den Benutzer, und klicken Sie dann bitten Sie ihn erneut anmelden.  <br/> |
|Falsche Version von Skype für Business Online installiert  <br/> |Dieses Problem ist in der Regel zugeordnet, mit einer Fehlermeldung, die den folgenden Ausdruck enthält: **der Authentifizierungsdienst ist möglicherweise mit dieser Version des Programms nicht kompatibel**.  <br/> Bitten Sie den Benutzer zum Deinstallieren und Neuinstallieren von Skype für Business Online über das Office 365-Portal.  <br/> |
|Problem Erwerb ein persönliches Zertifikat, das für die Anmeldung erforderlich ist  <br/> |Wenn die Adresse des Benutzers anmelden zuletzt geändert hat, müssen sie möglicherweise zwischengespeicherte Daten zu löschen. Fordern Sie Benutzer auf Abmelden klicken Sie auf Löschen Meine Info-Anmeldung auf dem Bildschirm Anmeldung verknüpfen, und versuchen Sie es erneut.  <br/> |
|Sie richten Sie einen benutzerdefinierten Domänennamen, und die Änderungen möglicherweise nicht durch das System verbreitet abgeschlossen haben.  <br/> |Stellen Sie zunächst sicher, dass Sie die Datensätze Service DNS (Domain Name), um die Änderung geändert haben.  <br/> Wenn Sie bereits die erforderlichen DNS-Änderungen vorgenommen haben, empfehlen Sie den Benutzer, versuchen später, sich anzumelden. DNS-Änderungen können im gesamten System widergespiegelt werden bis zu 72 Stunden dauern.  <br/> |
|Systemuhr synchron mit der Uhr des Servers  <br/> |Stellen Sie sicher, dass Ihr Netzwerk-Domänencontroller mit einem zuverlässigen externen Uhr synchronisiert werden. Weitere Informationen hierzu finden Sie unter der Microsoft Knowledge Base-Artikel 816042, [wie Sie einen autorisierenden Zeitserver in Windows Server konfigurieren](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042).<br/> |

Um Skype Business Online Fehler zu beheben, starten Sie durch Vermeidung der häufigsten Ursachen der Anmeldung Probleme auftreten. Führen Sie bei Bedarf können Sie klicken Sie dann bestimmten Auflösung Schritte auf den Typ des Fehlers basieren. Wenn der Benutzer noch nicht anmelden kann, zusätzliche Informationen sammeln und dann seek zusätzliche Hilfe.

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>Schritte für Lösung für einen bestimmten Fehler (nur Enterprise)
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  Diese Anweisungen sind in erster Linie für Microsoft Office 365-Plan-E-Kunden vorgesehen. Wenn Sie ein Office 365 Planen von P-Kunde sind, weiterhin im folgenden Abschnitt,[Weitere Informationen zu sammeln und seek zusätzliche Hilfe ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information).

Wenn der Benutzer nicht anmelden kann, nachdem Sie die Vorschläge im vorherigen Abschnitt versucht haben, können Sie tun, zusätzliche Hinweise zur Problembehandlung, basierend auf den Typ des Fehlers. Die folgende Tabelle enthält die häufigsten Fehlermeldungen und mögliche Ursachen. Unter der Tabelle werden die ausführlichen Verfahren zum jedes Problem zu beheben.

|**Fehlermeldung**|**Mögliche Ursache**|**Lösung**|
|:-----|:-----|:-----|
|Anmeldeadresse nicht gefunden  <br/> |Anmeldeanforderungen aus dem Microsoft Online Services Sign-On-Assistenten (msoidsvc.exe) sollte werden nicht über die externe Firewall oder der Proxyserver.  <br/> |[Hinzufügen eines firewalleintrags für msoidsvc.exe auf den Proxyserver](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|Server ist vorübergehend nicht verfügbar  <br/> |Wenn Ihre Organisation eine benutzerdefinierte Domäne verfügt, können die erforderlichen Einstellungen für Domain Name System (DNS) fehlenden oder falschen sein.  <br/> |[Aktualisieren von DNS-Einstellungen](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|Server ist vorübergehend nicht verfügbar  <br/> |Wenn Ihre Organisation einmaliges Anmelden mit Active Directory Federation Services (ADFS) verwendet, können Sie ein selbstsigniertes Zertifikat Secure Socket Layer (SSL) statt eine von einer Zertifizierungsstelle eines Drittanbieters verwendet haben.  <br/> |[Installieren Sie ein Drittanbieter-SSL-Zertifikat auf dem AD FS-server](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|Problem Erwerb ein persönliches Zertifikat, das für die Anmeldung erforderlich ist  <br/> |Wenn Sie bereits entfernt haben die zwischengespeicherten Daten verwendet, so melden Sie sich und der Fehler weiterhin angezeigt wird, Security-Anmeldeinformationen des Benutzers ist beschädigt oder ein RSA-Ordner auf dem Computer des Benutzers blockiert möglicherweise Authentifizierung.  <br/> |[Aktualisieren von Sicherheitsanmeldeinformationen](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|Ein Zertifikat vertrauen-Dialogfeld wird angezeigt, wenn ein Benutzer zum ersten Mal anmeldet.  <br/> |Dieses Dialogfeld wird angezeigt, wenn Ihre Skype für Business Server noch nicht in den Registrierungsschlüssel **TrustModelData** aufgeführt ist. <br/> |[Ändern Sie Registrierungsschlüssel TrustModelData](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|Benutzer ist kein SIP-aktiviert  <br/> |Wenn Ihre Organisation eine frühere Installation von Microsoft Office Communications Server oder Microsoft Lync Server 2010 hatten, Sie möglicherweise nicht die Benutzer vom Server gelöscht vor der Außerbetriebnahme es. Daher wird das Attribut **MsRTCSIP-UserEnabled** noch auf **"false"** in Active Directory-Domänendiensten festgelegt. <br/> |[Aktualisieren von Benutzereinstellungen in Active Directory](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>Hinzufügen eines firewalleintrags für msoidsvc.exe auf den Proxyserver
<a name="add-a-firewall"> </a>

Dieses Verfahren ist eine mögliche Lösung für die folgende Fehlermeldung angezeigt: **Anmeldeadresse wurde nicht gefunden**.

> [!NOTE]
> Die folgenden Schritte wird davon ausgegangen, dass Sie Microsoft Forefront Threat Management Gateway (TMG) 2010 verwenden. Wenn Sie eine anderen Web-Gateway-Lösung haben, verwenden Sie die Einstellungen, die in Schritt 4 unten beschrieben.


Gehen Sie folgendermaßen vor, um einen Eintrag einer Anwendung für Msoidsvc.exe in Forefront TMG 2010 zu erstellen:

1. Klicken Sie im linken Bereich Forefront auf **Netzwerk**.

2. Klicken Sie auf die Registerkarte **Netzwerk** . Klicken Sie auf der Registerkarte **Aufgaben** im rechten Bereich auf **Forefront TMG-Clienteinstellungen konfigurieren**.

3. Klicken Sie im Dialogfeld **Forefront TMG-Clienteinstellungen** auf **neu**.

4. Klicken Sie im Dialogfeld **Eintrag die Einstellung** konfigurieren Sie die folgenden Regeln:

|**Anwendung**|**Schlüssel**|**Wert**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Deaktivieren  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

Weitere Informationen hierzu finden Sie im Microsoft Knowledge Base-Artikel 2409256, [Skype für Business Online Herstellen einer Verbindung ist nicht möglich, da eine lokale Firewall die Verbindung blockiert](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256).

### <a name="update-dns-settings"></a>Aktualisieren von DNS-Einstellungen
<a name="update-dns-service"> </a>

Wenn Ihre Organisation eine benutzerdefinierte Domäne verfügt, wird dieses Verfahren ist eine mögliche Lösung für die folgende Fehlermeldung angezeigt: **Server ist vorübergehend nicht verfügbar**.

- Informationen zum Hinzufügen von des folgenden CNAME-Eintrags für Ihre Domäne erhalten Sie Ihrer Registrierungsstelle für Domänennamen:

  - **DNS-Datensatztyp**: CNAME

  - **Name**: sip

  - **Wert/Ziel**: sipdir.online.microsoft.com

Weitere Informationen hierzu finden Sie im Microsoft Knowledge Base-Artikel 2566790, [Problembehandlung Skype für Business Online DNS-Konfigurationsprobleme in Office 365](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790).

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>Installieren Sie ein Drittanbieter-SSL-Zertifikat auf dem AD FS-server
<a name="verify-upn-and"> </a>

Gehen Sie folgendermaßen vor, um ein Drittanbieter-SSL-Zertifikat auf dem Server aktiven Domäne Federation Services (ADFS) zu installieren:

1. Ein SSL-Zertifikat von einer Zertifizierungsstelle eines Drittanbieters wie VeriSign oder Thawte zu erhalten.

2. Installieren Sie das Zertifikat auf Ihrem AD FS-Server mithilfe der AD FS-Verwaltungskonsole.

### <a name="update-security-credentials"></a>Aktualisieren von Sicherheitsanmeldeinformationen
<a name="update-security-credentials"> </a>

Dieses Verfahren ist eine mögliche Lösung für die Fehlermeldung **Problem Erwerb ein persönliches Zertifikat für die Anmeldung erforderlich**.

Um mögliche Zertifikat oder Anmeldeinformationen Probleme zu vermeiden, müssen Sie zuerst erneuern Sie das Zertifikat des Benutzers in der Windows-Zertifikatverwaltung. Gehen Sie hierzu folgendermaßen vor:

1. Öffnen Sie Windows-Zertifikatverwaltung. Zu diesem Zweck klicken Sie auf **Start**, klicken Sie auf **Ausführen**, geben Sie **certmgr.msc ein**, und klicken Sie dann auf **OK**.

2. Doppelklicken Sie auf **Persönlich**, und doppelklicken Sie dann auf **Zertifikate**.

3. Sortieren nach der Spalte **Ausgestellt von** , und klicken Sie dann suchen Sie nach ein Zertifikat, das von Communications Server ausgestellt wurde.

4. Maustaste auf das Zertifikat, und klicken Sie dann auf **Löschen**.

Wenn der Benutzer Windows 7 ausgeführt wird, entfernen Sie ihre gespeicherten Anmeldeinformationen im nächsten Schritt im Windows-Anmeldeinformations-Manager. Gehen Sie hierzu folgendermaßen vor:

1. Klicken Sie auf **Start**, klicken Sie auf **Systemsteuerung**, und klicken Sie dann auf **Anmeldeinformations-Manager**.

2. Suchen Sie nach der Satz von Anmeldeinformationen, der für die Verbindung Skype für Business Online verwendet wird.

3. Erweitern Sie den Satz von Anmeldeinformationen, und klicken Sie dann auf **Entfernen aus Vault**.

4. Dann erneut melden Sie an, und geben Sie die Anmeldeinformationen des Benutzers erneut ein.

Schließlich, wenn der Benutzer noch nicht anmelden kann, nachdem Sie ihre Anmeldeinformationen aktualisiert haben, versuchen Sie den RSA-Ordner auf dem Computer des Benutzers, löschen, da er den Benutzerauthentifizierungsprozess durchgearbeitet blockiert werden konnte:

1. Melden Sie sich bei dem Computer des Benutzers mit einem Administratorkonto an.

2. Aktivieren Sie bei Bedarf die Ordner Ansichtsoption **Ausgeblendete Dateien anzeigen**.

3. Geben Sie Folgendes in die Adressleiste von Dateiexplorer: **C:\\Dokumente und Einstellungen\\UserName\\Anwendungsdaten\\Microsoft\\Kryptografie\\RSA**, wobei ***Benutzername*** der Anmeldename für Windows ist.

4. Löschen Sie alle Ordner, die mit dem Namen beginnt **S-1-5-21 -** gefolgt von einer Zeichenfolge aus Zahlen.

### <a name="modify-trustmodeldata-registry-keys"></a>Ändern Sie Registrierungsschlüssel TrustModelData
<a name="modify-trustmodeldata-registry"> </a>

Wenn ein Benutzer zum ersten Mal anmeldet, erhalten sie ein Dialogfeld an, die etwa Folgendes enthält: **kann nicht überprüft, dass der Server für Ihre Anmeldeadresse vertrauenswürdig ist. Trotzdem verbinden?** Dies ist eine Sicherheitsfunktion und nicht um einen Fehler. Jedoch können Sie verhindern, dass die im Dialogfeld angezeigt wird, mithilfe einer Gruppenrichtlinienobjekt (GPO) auf den um Computern von Benutzern mit dem Namen Ihrer Domäne zu aktualisieren, bevor sie zum ersten Mal anmelden. Gehen Sie wie folgt vor, um dies zu erreichen:

- Erstellen und Bereitstellen ein Gruppenrichtlinienobjekts, die Ihre Skype für Business Domänennamen anfügt – beispielsweise domainName.contoso.com—to der aktuelle Wert der HKEY_LOCAL_MACHINE\\Software\\Richtlinien\\Microsoft\\Communicator\\ TrustModelData.

> [!IMPORTANT]
>  Sie müssen *Fügen Sie* Ihren Domänennamen zu dem vorhandenen Wert, ersetzen Sie ihn nicht einfach.

Weitere Informationen hierzu finden Sie im Microsoft Knowledge Base-Artikel 2531068, [Skype für Unternehmen (Lync) nicht überprüft werden kann, dass der Server für Ihre Anmeldeadresse vertrauenswürdig ist](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068).

### <a name="update-user-settings-in-active-directory"></a>Aktualisieren von Benutzereinstellungen in Active Directory
<a name="update-user-settings"> </a>

Wenn Ihre Organisation eine frühere Installation von Microsoft Office Communications Server oder Microsoft Lync Server 2010 hatten, Sie möglicherweise nicht die Benutzer vom Server gelöscht vor der Außerbetriebnahme es. Daher wird das Attribut **MsRTCSIP-UserEnabled** noch auf **"false"** in Active Directory-Domänendiensten festgelegt.

Gehen Sie folgendermaßen vor, um dieses Problem zu beheben:

1. Aktualisieren Sie das Attribut **MsRTCSIP-UserEnabled** für alle betroffenen Benutzer auf **true fest**.

2. Führen Sie das Microsoft Online Services-Verzeichnissynchronisierungstool (DirSync) erneut aus. Weitere Informationen hierzu finden Sie unter [AIntegrate Ihre lokale Verzeichnisse mit Azure Active Directory](https://technet.microsoft.com/en-us/library/hh967642.aspx).

Um Skype Business Online Fehler zu beheben, starten Sie durch Vermeidung der häufigsten Ursachen der Anmeldung Probleme auftreten. Führen Sie bei Bedarf können Sie klicken Sie dann bestimmten Auflösung Schritte auf den Typ des Fehlers basieren. Wenn der Benutzer noch nicht anmelden kann, zusätzliche Informationen sammeln und dann seek zusätzliche Hilfe.
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>Verwenden Sie die Microsoft-Supportmitarbeiter Handbuch zur Problembehandlung
<a name="toc325626447"> </a>

Wenn Sie immer noch keine des Benutzers-Anmeldung Probleme zu beheben sind, überprüfen Sie die Vorschläge im Microsoft Knowledge Base-Artikel 2541980, [Behandlung von Anmeldeproblemen in Skype für Business Online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980).

## <a name="collect-more-information-and-seek-additional-help"></a>Weitere Informationen zu sammeln und seek zusätzliche Hilfe
<a name="collect-more-information"> </a>

Wenn Sie die oben genannten Anweisungen befolgt haben und Ihre Registrierungsprobleme weiterhin können nicht aufgelöst werden, müssen Sie zusätzliche Informationen sammeln und Kontaktieren des technischen Supports. Gehen Sie hierzu folgendermaßen vor:

1. Die Protokolldateien und Protokolldetails Windows-Ereignis von dem Computer des Benutzers abrufen. Schrittweise Anweisungen finden Sie unter der Endbenutzer Hilfethema [Fehlerprotokolle in Lync aktivieren](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c).

2. Senden Sie die Protokolldateien und ausführliche Informationen zu dem Fehler an den technischen Support von Microsoft.

Möglicherweise müssen zusätzliche Diagnoseinformationen durch Installieren von Microsoft Online Services-Diagnose und Logging (MOSDAL) Support-Toolkit auf dem Computer des betroffenen Benutzers bereitgestellt. Weitere Informationen hierzu finden Sie unter [Verwenden von dem MOSDAL Support Toolkit](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72).

Um Skype Business Online Fehler zu beheben, starten Sie durch Vermeidung der häufigsten Ursachen der Anmeldung Probleme auftreten. Führen Sie bei Bedarf können Sie klicken Sie dann bestimmten Auflösung Schritte auf den Typ des Fehlers basieren. Wenn der Benutzer noch nicht anmelden kann, zusätzliche Informationen sammeln und dann seek zusätzliche Hilfe.

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)


