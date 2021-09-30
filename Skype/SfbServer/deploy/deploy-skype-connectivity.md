---
title: Bereitstellen der Skype-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.'
ms.openlocfilehash: c63e476cc413bbf0a676c7b28d02519bbc6f223d
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013189"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Bereitstellen der Skype-Konnektivität in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype-Konnektivität bezeichnet.
  
Dieser Artikel führt Sie durch die Bereitstellung für Skype-Konnektivität.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype-Konnektivitätsübersicht für IT-Experten

Skype-Konnektivität bietet Skype for Business-Benutzern die Möglichkeit, nach Skype-Benutzern zu suchen und diese hinzuzufügen. Skype-Konnektivität ist ein Feature von Skype for Business, mit dem Sie die Partnerverbund- und Verzeichnissuche mit Skype-Benutzern aktivieren können. Nachdem Sie die Skype-Konnektivität aktiviert haben, können Ihre Skype for Business-Benutzer nach Skype-Benutzern suchen und diese hinzufügen.
  
## <a name="skype-directory-search"></a>Skype-Verzeichnissuche

Die Skype-Verzeichnissuche bietet Skype for Business-Benutzern die Möglichkeit, nach Skype-Kontakten zu suchen. Mit der Suchfunktion können Benutzer folgende Suchfunktionen verwenden:
  
- **Suche nach Anzeigename, z. B. "John Doe"** – Dies könnte viele Ergebnisse zurückgeben, sodass Sie möglicherweise nicht finden, wonach Sie suchen.
    
- **Suche nach Anzeigename und Ort, z. B. "John Doe in Einerde"** – Dadurch werden die Ergebnisse der Suche erheblich eingegrenzt.
    
- **Suche nach E-Mail, z. B. "johndoe@outlook.com":** Dies sollte in den meisten Fällen ein Ergebnis zurückgeben; die, die genau mit der angegebenen E-Mail übereinstimmt. Wenn jedoch dieselbe E-Mail mehreren Konten zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Telefonnummer, z. B. "123-123-1234":** Dies sollte in den meisten Fällen ein Ergebnis zurückgeben; das, das genau mit dem angegebenen Telefon übereinstimmt. Die Telefonnummer muss die Ländervorwahl (d. h. 1-xxx-yyy-zzzz) enthalten. Wenn dieselbe Telefonnummer mehreren Konten zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Skype-Name, Beispiel "JohnDoe1456":** Wenn eine genaue Übereinstimmung gefunden wird, wird sie als erstes Ergebnis zurückgegeben. Andere mögliche "Name"-Übereinstimmungen können zurückgegeben werden.
    
    > [!NOTE]
    > Die Skype-Verzeichnissuche muss mit den folgenden IP-Adressen an Port 443 kommunizieren können: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungsmatrix für die Skype-Verzeichnissuche

In der folgenden Tabelle wird die Unterstützung für die Skype-Verzeichnissuche beschrieben.
  

|&nbsp;|Skype for Business Server Front-End|Lync Server 2013 (oder älter) Front-End|Kommentare|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |Unterstützt   |Nicht unterstützt   |Skype for Business Server und Edge sind Voraussetzungen für die Skype-Verzeichnissuche.   |
|Skype for Business Server Edge + Lync Server 2013 Edge nebeneinander bereitgestellt   |Unterstützt   |Nicht unterstützt   |Der Datenverkehr der Skype-Verzeichnissuche fließt über skype for Business Server-Edgeserver. Der Verbunddatenverkehr durchläuft den vom Administrator konfigurierten Edgeserver. Beispielsweise könnte der Administrator weiterhin Verbunddatenverkehr über Lync Server 2013-Edgeserver senden, die die Skype-Verzeichnissuche nicht unterstützen würden.   |
|Lync Server 2013 (oder älter) Edge   |Nicht unterstützt   |Nicht unterstützt   ||
   
> [!NOTE]
> Der Auf dem Skype for Business Server-Front-End ausgeführte Adressbuchdienst findet den Edge nach dem Vorhandensein des Skype Search-Ports 4443 auf dem Edgeserver. 
  
> [!NOTE]
> Wenn ein Kunde mehrere Standorte in seiner lokalen Bereitstellung hat und nur einen Skype for Business Server Edge-Server/-Pool bereitgestellt hat, wird der Suchdatenverkehr von allen Standorten über den einzelnen verfügbaren Edgeserver weitergeleitet. Der Administrator muss sicherstellen, dass die Pools von allen Standorten auf den bereitgestellten Skype for Business Server Edge-Server/-Pool zugreifen können. 
  
> [!NOTE]
> Der Skype Graph-Dienst drosselt Suchanfragen von lokalen oder Microsoft 365- oder Office 365-Kunden, wenn die Anforderungsrate 15 Anforderungen pro Sekunde überschreitet. 
  
> [!NOTE]
> Für lokale Kunden in großen Unternehmen müssen die Domänen einer Zulassungsliste mit dem Skype-Suchdienst hinzugefügt werden, um höhere Anforderungsraten zu ermöglichen.
  
> [!NOTE]
> Skype for Business Server drosselt eingehende Anforderungen, wenn zu viele ausstehende Anforderungen in der Warteschlange vorhanden sind. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Online

Skype Connectivity ist auch ein Feature von Skype for Business Online, das Teil von Microsoft 365 und Office 365 ist. Sie können die Skype-Konnektivitätsfunktion über das Skype for Business Administration Center im Microsoft 365 Admin Center aktivieren.
  
Für Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education und Office 365 for Government: Melden Sie sich beim Microsoft 365 Admin Center an, und navigieren Sie zum Skype for Business Administration Center. Wechseln Sie zu "Externe Kommunikation". Klicken Sie unter "Öffentliche Chatdienstanbieter" auf "Aktivieren". Wenn Sie den Zugriff einzelner Benutzer auf die Skype-Konnektivität steuern möchten, können Sie dazu die Einstellungen für die externe Kommunikation einzelner Benutzer bearbeiten.
  
Für Office 365 Small Business Premium: Melden Sie sich bei Office 365 an, und wechseln Sie zu \> Admin Service Settings Instant \> Messaging, Besprechungen und Konferenzen. Aktivieren Sie die externe Kommunikation. Der Schalter "Externe Kommunikation" aktiviert sowohl die Skype-Konnektivität als auch die Kommunikation mit anderen Organisationen, die Skype for Business verwenden.
  
Weitere Informationen zur Skype for Business Online-Verwaltung finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Was Sie ausprobieren können, wenn Sie keine externen Skype for Business- oder Skype-Kontakte chatten können](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Hinzufügen eines Kontakts in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administratoren: Konfigurieren von Skype for Business-Einstellungen für einzelne Benutzer](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Bereitstellen der Skype-Konnektivität für Skype for Business Server

Skype for Business Server verwendet die Verbundzugriffsarchitektur, um die Konnektivität mit Skype zu unterstützen. Diese Konnektivität ermöglicht Es Ihren Skype for Business Server-Benutzern, Skype hinzuzufügen. Skype-Clients können ihrer Kontaktliste auch Skype for Business-Benutzer hinzufügen. Basierend auf Richtlinien, die in Skype for Business Server administratorisch festgelegt sind, können Benutzer mithilfe von Chatnachrichten kommunizieren, die Anwesenheit der anderen anzeigen und Audio- und Videoanrufe initiieren. Die Skype-Konnektivität ist auch ein Feature von Skype for Business Online und kann für Skype for Business Online-Kunden über das Skype for Business Administration Center im Microsoft 365 Admin Center aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Verbindung mit Windows Messenger mithilfe von PIC (Public Instant Messaging Connectivity) konfiguriert ist, ist Ihre Bereitstellung bereits für die Skype-Konnektivität konfiguriert. Die einzige Änderung, die Sie berücksichtigen sollten, besteht darin, Ihren vorhandenen Messenger PIC-Eintrag in Skype umzubenennen. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Die Skype for Business Server-Bereitstellungswebsite für die Verbindung mit öffentlichen Chatdiensten ist nicht mehr verfügbar.

Der Standort, der früher zum manuellen Bereitstellen des Partnerverbunds zwischen lokalen Skype for Business-Bereitstellungen und Skype verwendet wurde, ist nicht mehr erforderlich und wird am 15.08.2019 beendet. Der Partnerverbund mit Skype nutzt jetzt die Partnerermittlung, die der gleiche Mechanismus ist, der für den Partnerverbund mit Skype for Business Online erforderlich ist.

Für die Kommunikation zwischen jeder lokalen Skype for Business-Bereitstellung und Skype-Benutzern über die vorhandene Infrastruktur für öffentliche Chatnachrichten muss jetzt die lokale Edgeserverkonfiguration mit Skype for Business Online kompatibel sein.

> [!NOTE]
> Die meisten Kunden benötigen keine Aktion, einschließlich aller Bereitstellungen, die mit Skype for Business Online verbunden sind.
  
Lokale Bereitstellungen sind erforderlich, um einen DNS-Verbund-SRV-Eintrag für jede Domäne zu veröffentlichen, die sie hosten. Anleitungen sind in der [DNS-Planung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)verfügbar. Jede Domäne muss durch die DNS-SRV-Abfrage in einen Edgeserver-FQDN aufgelöst werden, der eine Suffixübereinstimmung auf oberster Ebene der Domäne erfüllt. Betrachten Sie beispielsweise die Domäne "contoso.com":

|**Gültige FQDNs**|**Kommentar**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In jedem Fall muss der genaue FQDN entweder im SN oder im SAN des externen Zertifikats vorhanden sein, das auf dem Edgeserver installiert ist.   |
|access.contoso.com   ||
|**Ungültige FQDNs**|**Grund**|
|sip.contoso-edge.com   |Keine Suffixüberstimmung.  |
|sip.it.contoso.com   |Keine Übereinstimmung mit suffix auf oberster Ebene.   |

Weitere Anleitungen zu externen Zertifikaten finden Sie in der [Zertifikatplanung.](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)

#### <a name="faqs"></a>Häufig gestellte Fragen

**Warum wird die Bereitstellungswebsite heruntergefahren?**
Der öffentliche Pic-Bereitstellungsmechanismus (pic.lync.com), der 2006 bereitgestellt wurde, ist nicht mehr servicefähig und wird am 15.08.2019 beendet. Stattdessen wird vom Partnerverbund für öffentliche Chatnachrichten das gleiche Verbundmodell verwendet, das von Skype for Business Online verwendet wird, das als "Partnerermittlung" bezeichnet wird, wobei eine lokale Bereitstellung öffentlich durch den DNS-SRV-Verbundeintrag(n) auffindbar ist.

**Bedeutet diese Änderung, dass der Partnerverbund für öffentliche Chatnachrichten veraltet ist?**
Nein. Der Partnerverbund für öffentliche Chatnachrichten wird viele Jahre lang unterstützt, wahrscheinlich bis das lokale Skype for Business-Produkt das Ende der Lebensdauer erreicht.

**Unser Unternehmen hat eine Hybridbeziehung (freigegebener Adressraum) mit Skype for Business Online, sind wir betroffen?**
Nein, da Sie bereits mit Skype for Business Online verbunden sind, wirkt sich diese Änderung nicht auf Sie aus.
 
**Bedeutet diese Änderung, dass unser Unternehmen den Partnerverbund mit Skype for Business Online aktivieren muss?**
Nein. Wenn Ihre Edgeserverproxyeinstellungen den Partnerverbund mit dem Skype for Business Onlinehostinganbieter (sipfed.online.lync.com) nicht aktivieren, wirkt sich diese Änderung nicht darauf aus. Die gleichen DNS- und Zertifikatanforderungen, die auch für die Verbundsuche mit Skype for Business Online gelten, gelten jetzt auch für die Partnersuche mit Skype Benutzern.
 
**Unser Unternehmen ist groß und kann seine Edgekonfiguration aus gesetzlichen/Compliance-/usw. Gründen nicht ändern... Was können wir tun?**
Jede lokale Organisation, die ihre Edgeserverkonfiguration nicht wie angegeben ändern kann, sollte sich so bald wie möglich an den Produktsupport wenden.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten (PIC)

Konzentrieren Sie sich jetzt auf die Skype for Business Server Umgebung und administrative Aufgaben, die zum Konfigurieren Skype Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat, auch bekannt als Edgeserver. 
  
Es sind drei primäre Schritte erforderlich, um den Partnerverbund und PIC zu aktivieren. Diese sind:
  
1. Konfigurieren von Partnerverbund und PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Verbundbenutzerzugriffs
    
3. Konfigurieren der Einstellung Skype PIC-Anbieters
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren von Partnerverbund und PIC

Der Partnerverbund ist erforderlich, damit Skype Benutzer mit Skype for Business Benutzern in Ihrer Organisation kommunizieren können. Pic (Public Instant Messaging Connectivity) ist eine Verbundklasse und muss so konfiguriert sein, dass Ihre Skype for Business Benutzer mit Skype Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe der Skype for Business Server Systemsteuerung konfiguriert.
  
> [!NOTE]
> Der PIC-Partnerverbund wird von Produktversionen vor Lync Server 2010 (Live Communication Server, Office Communications Server) nicht mehr unterstützt. Zu den unterstützten Plattformen für PIC-Partnerverbund gehören Skype for Business Server, Lync Server 2013 und Lync Server 2010. 
  
Der Partnerverbund ist erforderlich, damit Skype Benutzer mit Skype for Business Benutzern in Ihrer Organisation kommunizieren können. Pic (Public Instant Messaging Connectivity) ist eine Verbundklasse und muss so konfiguriert sein, dass Ihre Skype for Business Server Benutzer mit Skype Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe des Edgekonfigurationsdialogfelds der Skype for Business Server Systemsteuerung konfiguriert, wie in der Abbildung dargestellt.
  
![Neuen Edgepool definieren.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Die Attribute "EnableSkypeIdRouting" und "EnableSkypeDirectorySearch" müssen in den Einstellungen des öffentlichen Anbieters auf "true" festgelegt werden (siehe spätere Anweisungen), damit die Suche funktioniert. 
  
Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie sind jetzt für Skype Konnektivität eingerichtet.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Verbundbenutzerzugriffs

Mithilfe der Skype for Business Server Systemsteuerung muss ein Administrator eine oder mehrere Zugriffsrichtlinien für externe Benutzer konfigurieren, um zu steuern, ob Skype Benutzer mit internen Skype for Business Server Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren der Einstellung Skype PIC-Anbieters

Mithilfe der Skype for Business Server Verwaltungsshell muss ein Administrator die Skype for Business Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird. 
  
> [!NOTE]
> Benutzer der PIC-Dienstanbieter (Public Instant Messaging Connectivity) können erst dann an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, wenn Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) zur Unterstützung der Verbindung mit öffentlichen Chatnachrichten konfiguriert haben. 
  
Für Neuinstallationen können Sie Skype Konnektivität konfigurieren, indem Sie einen Skype öffentlichen Anbieter mithilfe der Skype for Business Server Systemsteuerung aktivieren, wie in der Abbildung dargestellt.
  
![SIP-Partnerverbundanbieter.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Um beim Upgrade auf Skype for Business Server Skype Konnektivität zu konfigurieren, müssen Sie das vorhandene Skype öffentlichen Anbieter entfernen und erneut hinzufügen. 
  
Das Konfigurieren Skype Konnektivität kann auch nur mithilfe von PowerShell erfolgen. So konfigurieren Sie Skype Konnektivität mithilfe von PowerShell:
  
1. Öffnen Sie auf einem Skype for Business Server Front-End-Server die Skype for Business Server Verwaltungsshell.
    
2. Führen Sie die folgenden beiden Befehle aus:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Wenn Sie noch keinen PIC-Anbieter in Ihrer Umgebung haben und einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet Remove-CsPublicProvider nicht ausführen. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Was tun die weniger offensichtlichen Parameter?
    
   - ProxyFqdn: Standort Skype Partnerverbund-Edge (im Besitz/verwaltet von Microsoft)
    
   - IconURL: Symbol, das von Lync &amp; Skype for Business Client verwendet wird, um Skype Kontakte visuell zu identifizieren
    
   - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: Wenn Sie diese Einstellung festlegen, können Benutzer die MSAs Skype Benutzer eingeben, ohne wissen zu müssen, wie Nicht-Microsoft-Domänen mit "msn.com" decodiert werden müssen. Dadurch entfällt die Notwendigkeit, "user(contoso.com)@msn.com" für alle Domänen einzugeben, die NICHT in der ExcludedDomainList enthalten sind. Der SfB-Client formatieren die MSA automatisch, wenn die Domäne NICHT in der Liste ausgeschlossen ist. Wir haben die gängigsten Microsoft-Kontodomänen zur ausgeschlossenen Liste hinzugefügt.
    
     > [!NOTE]
     > Der öffentliche Anbieter muss entfernt und neu hinzugefügt werden, wenn Änderungen vorgenommen werden. Direkte Änderungen sind nicht zulässig. 
  
     > [!NOTE]
     > In Lync Server 2013 KU5 &amp; Lync-Desktopclient in Office 2013 SP1 hinzugefügt, verbessern nameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, in der Lync-Benutzer, die Skype Kontakte hinzufügen, nicht von Microsoft stammende Domänen "versehen" müssen, um sie zu identifizieren und an Skype (das Format von: user(contoso.com)@msn.com) weiterzuleiten. Diese neuen Einstellungen ermöglichen die automatische Formatierung der Eingabe des Adressbenutzers im Dialogfeld "Skype Kontakt hinzufügen" mit der NameDecorationRoutingDomain (die auf msn.com festgelegt werden sollte), wenn sie nicht die Domänen in NameDecorationExcludedDomainList enthält (derzeit können wir msn.com, live.com, Hotmail.com outlook.com unterstützen). 
  
3. Von einem Skype for Business können Clientbenutzer nun einen Skype Benutzer suchen und hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitätsmatrix

In der folgenden Tabelle wird der Status der Interoperabilität zwischen der neuesten Version von Skype Consumer und der neuesten Version von Skype for Business beschrieben.
  

|Skype Kunden|Hinzufügen von Kontakten, Chatnachrichten, Anwesenheitsinformationen, Audio- und Videoanrufen|Kommentar|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7.6 oder höher, Windows XP und höher   |**NEU:** Unterstützung für Windows Skype Client hinzugefügt, der auf Windows XP und Windows Vista ausgeführt wird **(erfordert die neueste Clientversion 7.26 oder höher)**  |
|Skype Mobil – Android Telefon und Tablet   |6.19 oder höher mit Android OS Version 4.0.3 oder höher   |Geräte mit niedriger Spezifikation unterstützen möglicherweise keine Videoanrufe   |
|Skype Mobil – iOS   |6.11 oder höher, auf IOS 7 oder höher   |Nicht unterstützt werden iPhone 4 und früher, iPod der 4. Generation und früher iPad 1. Generation.   |
|Skype Mac   |7.19 oder höher, unter Mac OS X 10.9 (Mavericks) oder höher   |Erfordert Mac OSX 10.9 oder höher   |
|Skype Universal Windows App (Windows 10) Desktop und Mobile   |Windows 10 (Redstone 1-Update oder höher)   |Windows Universelle App erhält update im Fall 2016 hinzufügen interop-Unterstützung   |
   
In der folgenden Tabelle wird der Status der Interoperabilität zwischen der neuesten Version von Skype for Business und der neuesten Version von Skype Consumer beschrieben. 
  
|Client|Skype Verzeichnissuche und Hinzufügen von Kontakten|Skype A/V, Chat-Interoperabilität|
|:-----|:-----|:-----|
|Skype for Business   |Ja   |Ja   |
|Skype for Business auf dem Mac   |Kann hinzugefügt werden (keine Suche)   |Ja   |
|Lync Desktop 2013   |Kann hinzugefügt werden (keine Suche)   |Ja   |
|Lync Web App – online und lokal   |Nicht zutreffend   |Nicht zutreffend   |
|Lync Mobile – Windows Phone   |In Kürze verfügbar   |Ja   |
|Lync Mobile – Android   |In Kürze verfügbar   |Ja   |
|Lync Mobile – iOS   |In Kürze verfügbar   |Ja   |
|Lync-Raumsystem   |In Kürze verfügbar   |Ja   |
|Lync Modern App (Win 8.1)   |Ja   |Ja   |
|Lync Mac 2011   |Kann hinzugefügt werden (keine Suche)   |Ja   |
|Lync Desktop 2010   |Kann hinzugefügt werden (keine Suche)   |Ja   |
|Lync Phone Edition   |Nicht zutreffend   |Nicht zutreffend   |
|Lync-Telefonzentrale   |Nicht zutreffend   |Nicht zutreffend   |
   
