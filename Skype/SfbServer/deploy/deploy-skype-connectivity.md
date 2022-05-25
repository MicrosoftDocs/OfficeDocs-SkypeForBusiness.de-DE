---
title: Bereitstellen Skype Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Skype for Business Server mit Skype Verbraucher verbinden. Wird auch als Skype-Konnektivität bezeichnet.'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671681"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Bereitstellen Skype Konnektivität in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.
  
In diesem Artikel wird die Bereitstellung für Skype Connectivity erläutert.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype Connectivity Overview for IT Professionals

Skype Connectivity bietet Skype for Business Benutzern die Möglichkeit, nach Skype Benutzern zu suchen und diese hinzuzufügen. Skype Connectivity ist ein Feature von Skype for Business, mit dem Sie die Verbund- und Verzeichnissuche mit Skype Benutzern aktivieren können. Nachdem Sie Skype Connectivity aktiviert haben, können Ihre Skype for Business Benutzer nach Skype Benutzern suchen und diese hinzufügen.
  
## <a name="skype-directory-search"></a>Skype Verzeichnissuche

Skype Verzeichnissuche bietet Skype for Business Benutzern die Möglichkeit, nach Skype Kontakten zu suchen. Mithilfe der Suchfunktion können Benutzer folgendeRmaßen suchen:
  
- **Suche nach Anzeigename, Beispiel "John Doe"** – Dies könnte viele Ergebnisse zurückgeben, sodass Sie möglicherweise nicht finden, wonach Sie suchen.
    
- **Suche nach Anzeigename und Ort, Beispiel "John Doe in Barcelona"** – Dadurch werden die Ergebnisse der Suche erheblich eingeschränkt.
    
- **Suche per E-Mail, Beispiel "johndoe@outlook.com"** – Dies sollte in den meisten Fällen ein Ergebnis zurückgeben; diejenige, die genau mit der angegebenen E-Mail übereinstimmt. Wenn dieselbe E-Mail jedoch mehreren Konten zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Telefonnummer, Beispiel "123-123-1234"** – Dies sollte in den meisten Fällen ein Ergebnis zurückgeben; diejenige, die genau mit dem angegebenen Telefon übereinstimmt. Telefon Nummer muss die Landesvorwahl (d. h. 1-xxx-yyy-zzzz) enthalten. Wenn dieselbe Telefonnummer mehreren Konten zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Skype Namen, Beispiel "JohnDoe1456"** – Wenn eine genaue Übereinstimmung gefunden wird, wird sie als erstes Ergebnis zurückgegeben. Andere mögliche "Name"-Übereinstimmungen können zurückgegeben werden.
    
    > [!NOTE]
    > Skype Verzeichnissuche muss mit den folgenden IP-Adressen an Port 443 kommunizieren können: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungsmatrix für Skype Verzeichnissuche

In der folgenden Tabelle wird die Unterstützung für Skype Verzeichnissuche beschrieben.
  

|&nbsp;|Skype for Business Server Front-End|Lync Server 2013 (oder älter) Front-End|Kommentare|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |Unterstützt   |Nicht unterstützt   |Skype for Business Server und Edge sind Voraussetzungen für Skype Verzeichnissuche   |
|Skype for Business Server Edge + Lync Server 2013 Edge parallel bereitgestellt   |Unterstützt   |Nicht unterstützt   |Skype Datenverkehr der Verzeichnissuche fließt durch Skype for Business Server Edgeserver. Der Verbunddatenverkehr wird durch den vom Administrator konfigurierten Edgedatenverkehr geleitet. Beispielsweise könnte der Administrator festlegen, dass weiterhin Verbunddatenverkehr über Lync Server 2013-Edgeserver gesendet wird, die Skype Verzeichnissuche nicht unterstützen würden.   |
|Edge für Lync Server 2013 (oder älter)   |Nicht unterstützt   |Nicht unterstützt   ||
   
> [!NOTE]
> Der auf Skype for Business Server Front-End ausgeführte Adressbuchdienst findet den Edge anhand des Skype Suchports 4443 auf dem Edgeserver. 
  
> [!NOTE]
> Falls ein Kunde über mehrere Standorte in seiner lokalen Bereitstellung verfügt und wenn er nur einen Skype for Business Server Edgeserver/-pool bereitgestellt hat, durchläuft der Suchdatenverkehr von allen Websites den einzelnen verfügbaren Edgeserver. Der Administrator muss sicherstellen, dass die Pools von allen Websites auf die bereitgestellten Skype for Business Server Edgeserver/-pool zugreifen können. 
  
> [!NOTE]
> Skype Graph-Dienst drosselt Suchanfragen von lokalen oder Microsoft 365 oder Office 365 Kunden, wenn die Anforderungsrate 15 Anforderungen pro Sekunde überschreitet. 
  
> [!NOTE]
> Für lokale Großkunden müssen die Domänen einer Zulassungsliste mit dem Skype-Suchdienst hinzugefügt werden, um höhere Anforderungsraten zu ermöglichen.
  
> [!NOTE]
> Skype for Business Server drosselt eingehende Anforderungen, wenn zu viele ausstehende Anforderungen in der Warteschlange vorhanden sind. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Bereitstellen von Skype Connectivity für Skype for Business Online

Skype Connectivity ist auch ein Feature von Skype for Business Online, das Teil von Microsoft 365 und Office 365 ist. Sie können das Feature "Skype Connectivity" im Skype for Business Administration Center im Microsoft 365 Admin Center aktivieren.
  
For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Microsoft 365 Admin Center and navigate to the Skype for Business Administration Center. Wechseln Sie zu "Externe Kommunikation". Klicken Sie unter "Öffentliche Chatdienstanbieter" auf "Aktivieren". Wenn Sie den Zugriff einzelner Benutzer auf Skype Connectivity steuern möchten, können Sie dazu die Einstellungen für die externe Kommunikation einzelner Benutzer bearbeiten.
  
For Office 365 Small Business Premium: Sign in to Office 365, and go to Admin \> Service Einstellungen \> Instant Messaging, meetings and conferencing. Aktivieren Sie die externe Kommunikation. Der Schalter für externe Kommunikation aktiviert sowohl Skype Konnektivität als auch die Kommunikation mit anderen Organisationen, die Skype for Business verwenden.
  
Weitere Informationen zur Skype for Business Onlineverwaltung finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Was Sie versuchen sollten, wenn Sie externe Kontakte nicht Skype for Business oder Skype können](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Hinzufügen eines Kontakts in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administratoren: Konfigurieren Skype for Business Einstellungen für einzelne Benutzer](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Bereitstellen Skype Konnektivität für Skype for Business Server

Skype for Business Server verwendet die Verbundzugriffsarchitektur, um die Konnektivität mit Skype zu unterstützen. Diese Konnektivität ermöglicht es Ihren Skype for Business Server Benutzern, Skype hinzuzufügen. Skype Clients können ihrer Kontaktliste auch Skype for Business Benutzer hinzufügen. Basierend auf Denkrichtlinien, die in Skype for Business Server benutzer in der Lage sind, per Chat zu kommunizieren, die Anwesenheit des anderen zu sehen und Audio- und Videoanrufe zu initiieren. Skype Konnektivität ist auch ein Feature von Skype for Business Online und kann für Skype for Business Online-Kunden über das Skype for Business Administration Center innerhalb der Microsoft 365 Admin Center aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Verbindung mit Windows Messenger mithilfe von Pic (Public Instant Messaging Connectivity) konfiguriert ist, ist Ihre Bereitstellung bereits für Skype Konnektivität konfiguriert. Die einzige Änderung, die Sie möglicherweise in Betracht ziehen möchten, besteht darin, Ihren vorhandenen Messenger PIC-Eintrag in Skype umzubenennen. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Die Skype for Business Server Bereitstellungswebsite für öffentliche Chatkonnektivität ist nicht mehr verfügbar.

Der Standort, der früher zum manuellen Bereitstellen des Verbunds zwischen Skype for Business lokalen Bereitstellungen und Skype verwendet wurde, ist nicht mehr erforderlich und wird am 15.08.2019 beendet. Der Partnerverbund mit Skype verwendet jetzt die Partnersuche für Verbundpartner. Dies ist der gleiche Mechanismus, der für den Partnerverbund mit Skype for Business Online erforderlich ist.

Die Kommunikation zwischen jeder lokalen Skype for Business Bereitstellung und Skype Benutzern über die vorhandene Öffentliche Chatinfrastruktur erfordert jetzt, dass die lokale Edgeserverkonfiguration mit Skype for Business Online kompatibel ist.

> [!NOTE]
> Für die meisten Kunden ist keine Aktion erforderlich, einschließlich aller Bereitstellungen, die mit Skype for Business Online verbunden sind.
  
Lokale Bereitstellungen sind erforderlich, um einen DNS-SRV-Verbundeintrag für jede Domäne zu veröffentlichen, die sie hosten. Anleitungen sind in der [DNS-Planung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning) verfügbar. Jede Domäne muss durch DNS SRV-Abfrage in einen Edgeserver-FQDN aufgelöst werden, der eine Suffix-Übereinstimmung der obersten Ebene der Domäne erfüllt. Betrachten Sie beispielsweise die Domäne "contoso.com":

|**Gültige FQDNs**|**Kommentar**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In jedem Fall muss der genaue FQDN entweder im SN oder im SAN des externen Zertifikats vorhanden sein, das auf dem Edgeserver installiert ist.   |
|access.contoso.com   ||
|**Ungültige FQDNs**|**Grund**|
|sip.contoso-edge.com   |Keine Suffix-Übereinstimmung.  |
|sip.it.contoso.com   |Keine Suffix-Übereinstimmung auf oberster Ebene.   |

Weitere Anleitungen zu externen Zertifikaten finden Sie in der [Zertifikatplanung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Häufig gestellte Fragen

**Warum wird die Bereitstellungswebsite heruntergefahren?**
Der im Jahr 2006 bereitgestellte Bereitstellungsmechanismus für öffentliche Chatnachrichten (PIC) (pic.lync.com) kann nicht mehr verwendet werden und wird am 15.08.2019 beendet. Stattdessen geht der öffentliche Chatverbund von demselben Verbundmodell aus, das von Skype for Business Online verwendet wird, das als "Partnerermittlung" bezeichnet wird, wobei eine lokale Bereitstellung von den DNS-SRV-Einträgen des Partnerverbunds öffentlich auffindbar ist.

**Bedeutet diese Änderung, dass der Partnerverbund für öffentliche Chatnachrichten veraltet ist?**
Nein Der Öffentliche Chatverbund wird noch viele Jahre unterstützt, wahrscheinlich bis das Skype for Business lokale Produkt das Ende des Lebenszyklus erreicht.

**Unser Unternehmen hat eine Hybrid-Beziehung (shared address space) mit Skype for Business Online, sind wir betroffen?**
Nein, da Sie bereits mit Skype for Business Online verbunden sind, wirkt sich diese Änderung nicht auf Sie aus.
 
**Bedeutet diese Änderung, dass unser Unternehmen den Verbund mit Skype for Business Online aktivieren muss?**
Nein Wenn ihre Edgeserverproxyeinstellungen den Partnerverbund mit dem Skype for Business Onlinehostinganbieter (sipfed.online.lync.com) nicht aktivieren, wirkt sich diese Änderung nicht darauf aus. Die gleichen DNS- und Zertifikatanforderungen, die für das Verbunden mit Skype for Business Online gelten, gelten jetzt jedoch auch für das Verbunden mit Skype Benutzern.
 
**Unser Unternehmen ist groß und kann seine Edgekonfiguration aufgrund von Vorschriften/ Compliance / usw. nicht ändern ... Was können wir tun?**
Jede lokale Organisation, die ihre Edgeserverkonfiguration nicht wie angegeben ändern kann, sollte sich so bald wie möglich an den Produktsupport wenden.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren der Verbund- und öffentlichen Chatkonnektivität (PIC)

Konzentrieren Sie sich jetzt auf die Skype for Business Server Umgebung und administrative Aufgaben, die zum Konfigurieren Skype Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat, auch als Edgeserver bezeichnet. 
  
Es sind drei primäre Schritte erforderlich, um partnerverbund und PIC zu aktivieren. Diese sind:
  
1. Konfigurieren von Partnerverbund und PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern
    
3. Konfigurieren der Skype PIC-Anbietereinstellung
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren von Verbund und PIC

Der Partnerverbund ist erforderlich, damit Skype Benutzer mit Skype for Business Benutzern in Ihrer Organisation kommunizieren können. Pic (Public Instant Messaging Connectivity) ist eine Verbundklasse und muss so konfiguriert werden, dass Ihre Skype for Business Benutzer mit Skype Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe der Skype for Business Server Systemsteuerung konfiguriert.
  
> [!NOTE]
> PIC-Partnerverbund wird von Produktversionen vor Lync Server 2010 (Live Communication Server, Office Communications Server) nicht mehr unterstützt. Zu den unterstützten Plattformen für pic-Partnerverbund gehören Skype for Business Server, Lync Server 2013 und Lync Server 2010. 
  
Der Partnerverbund ist erforderlich, damit Skype Benutzer mit Skype for Business Benutzern in Ihrer Organisation kommunizieren können. Pic (Public Instant Messaging Connectivity) ist eine Verbundklasse und muss so konfiguriert werden, dass Ihre Skype for Business Server Benutzer mit Skype Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe des Edgekonfigurationsdialogfelds der Skype for Business Server Systemsteuerung wie in der Abbildung dargestellt konfiguriert.
  
![Definieren Sie einen neuen Edgepool.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Die Attribute "EnableSkypeIdRouting" und "EnableSkypeDirectorySearch" müssen in den Einstellungen des öffentlichen Anbieters auf "true" festgelegt werden (siehe spätere Anweisungen), damit die Suche funktioniert. 
  
Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie sind jetzt für Skype Connectivity eingerichtet.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs von Verbundbenutzern

Mithilfe der Skype for Business Server Systemsteuerung muss ein Administrator eine oder mehrere Zugriffsrichtlinien für externe Benutzer konfigurieren, um zu steuern, ob Skype Benutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren der Einstellung des Skype PIC-Anbieters

Mithilfe der Skype for Business Server-Verwaltungsshell muss ein Administrator die Skype for Business Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird. 
  
> [!NOTE]
> Benutzer der PIC-Dienstanbieter (Public Instant Messaging Connectivity) können erst dann an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) konfigurieren, um die Konnektivität öffentlicher Chatnachrichten zu unterstützen. 
  
Bei neuen Installationen können Sie Skype Connectivity konfigurieren, indem Sie einen Skype öffentlichen Anbieter mithilfe der Skype for Business Server Systemsteuerung wie in der Abbildung dargestellt aktivieren.
  
![SIP-Verbundanbieter.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Um beim Upgrade auf Skype for Business Server Skype Konnektivität zu konfigurieren, müssen Sie den vorhandenen Skype öffentlichen Anbieter entfernen und erneut hinzufügen. 
  
Das Konfigurieren Skype Konnektivität kann auch nur mithilfe von PowerShell erfolgen. So konfigurieren Sie Skype-Konnektivität mithilfe von PowerShell:
  
1. Öffnen Sie auf einem Skype for Business Server Front-End-Server die Skype for Business Server-Verwaltungsshell.
    
2. Führen Sie die folgenden beiden Befehle aus:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Wenn Sie noch keinen PIC-Anbieter in Ihrer Umgebung haben und einen neuen PIC-Anbieter erstellen, müssen Sie das cmdlet Remove-CsPublicProvider nicht ausführen. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Was machen die weniger offensichtlichen Parameter?
    
   - ProxyFqdn: Speicherort Skype Partnerverbund-Edge (im Besitz/verwaltet von Microsoft)
    
   - IconURL: Symbol, das vom Lync &amp; Skype for Business-Client verwendet wird, um Skype Kontakte visuell zu identifizieren
    
   - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: Wenn Sie diese festlegen, können Benutzer die MSAs Skype Benutzer eingeben, ohne sich über das "Dekorieren" von Nicht-Microsoft-Domänen mit "msn.com" informieren zu müssen. Dadurch entfällt die Notwendigkeit, "user(contoso.com)@msn.com" für alle Domänen einzugeben, die NICHT in der ExcludedDomainList enthalten sind. Der SfB-Client formatiert die MSA automatisch, wenn die Domäne NICHT in der Liste ausgeschlossen ist. Wir haben die am häufigsten verwendeten Microsoft-Kontodomänen zur ausgeschlossenen Liste hinzugefügt.
    
     > [!NOTE]
     > Der öffentliche Anbieter muss entfernt und neu hinzugefügt werden, wenn Änderungen vorgenommen werden. Es sind keine direkten Änderungen zulässig. 
  
     > [!NOTE]
     > Im Lync Server 2013 CU5 &amp; Lync-Desktopclient in Office 2013 SP1 hinzugefügt, verbessern nameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, dass Lync-Benutzer Skype Kontakte hinzufügen, die zum "Dekorieren" von Nicht-Microsoft-Domänen erforderlich sind, um sie zu identifizieren und an Skype weiterzuleiten (das Format von: user(contoso.com)@msn.com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der Eingabe des Adressbenutzers im Dialogfeld "Skype Kontakt hinzufügen" mit der NameDecorationRoutingDomain (die auf msn.com festgelegt werden sollte), wenn sie die Domänen in der NameDecorationExcludedDomainList nicht enthält (wir können derzeit msn.com, live.com, Hotmail.com outlook.com) unterstützen. 
  
3. Von einem Skype for Business-Client aus können Benutzer jetzt nach einem Skype Benutzer suchen und diese hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitätsmatrix

In der folgenden Tabelle wird der Status der Interoperabilität zwischen der neuesten Version von Skype Consumer und der neuesten Version von Skype for Business beschrieben.
  

|Skype Clients|Hinzufügen von Kontakten, Chatnachrichten, Anwesenheitsinformationen, Audio- und Videoanrufen|Kommentar|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7.6 oder höher, Windows XP und höher   |**NEU**: Unterstützung für Windows Skype Client hinzugefügt, der unter Windows XP und Windows Vista ausgeführt wird **(erfordert die neueste Clientversion 7.26 oder höher)**  |
|Skype Mobile – Android Telefon und Tablet   |6.19 oder höher mit Android Betriebssystemversion 4.0.3 oder höher   |Geräte mit niedriger Spezifikation unterstützen videoanrufe möglicherweise nicht   |
|Skype Mobile – iOS   |6.11 oder höher unter IOS 7 oder höher   |Nicht unterstützt werden iPhone 4 und früher, iPod 4. Generation und früher, iPad 1. Generation   |
|Skype Mac   |7,19 oder höher, auf Mac OS X 10,9 (Mavericks) oder höher   |Erfordert Mac OSX 10.9 oder höher   |
|Skype Universal Windows App (Windows 10) Desktop und Mobile   |Windows 10 (Redstone 1-Update oder höher)   |Windows Universelle App wird im Herbst 2016 aktualisiert, wodurch Interopunterstützung hinzugefügt wird   |
   
In der folgenden Tabelle wird der Status der Interoperabilität zwischen der neuesten Version von Skype for Business und der neuesten Version von Skype Consumer beschrieben. 
  
|Client|Skype Verzeichnissuche und Hinzufügen von Kontakten|Skype A/V, Chat-Interoperabilität|
|:-----|:-----|:-----|
|Skype for Business   |Ja   |Ja   |
|Skype for Business auf dem Mac   |Kann hinzufügen (keine Suche)   |Ja   |
|Lync Desktop 2013   |Kann hinzufügen (keine Suche)   |Ja   |
|Lync Web App – online und lokal   |Nicht zutreffend   |Nicht zutreffend   |
|Lync Mobile – Windows Phone   |In Kürze verfügbar   |Ja   |
|Lync Mobile – Android   |In Kürze verfügbar   |Ja   |
|Lync Mobile – iOS   |In Kürze verfügbar   |Ja   |
|Lync-Raumsystem   |In Kürze verfügbar   |Ja   |
|Moderne Lync-App (Win 8.1)   |Ja   |Ja   |
|Lync Mac 2011   |Kann hinzufügen (keine Suche)   |Ja   |
|Lync Desktop 2010   |Kann hinzufügen (keine Suche)   |Ja   |
|Lync Phone Edition   |Nicht zutreffend   |Nicht zutreffend   |
|Lync-Telefonzentrale   |Nicht zutreffend   |Nicht zutreffend   |
   
