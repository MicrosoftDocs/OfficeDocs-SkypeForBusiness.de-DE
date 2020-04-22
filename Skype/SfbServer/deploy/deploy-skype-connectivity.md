---
title: Bereitstellen der Skype-Konnektivität in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype Connectivity bezeichnet.'
ms.openlocfilehash: 2cf124c340218a352f55fa1c09302a0d0f1d972a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780064"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Bereitstellen der Skype-Konnektivität in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie Skype for Business Server mit Skype Consumer verbinden. Wird auch als Skype Connectivity bezeichnet.
  
In diesem Artikel wird die Bereitstellung für Skype-Konnektivität durchlaufen.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Übersicht über Skype-Konnektivität für IT-Experten

Skype Connectivity bietet Skype for Business Benutzern die Möglichkeit, nach Skype-Benutzern zu suchen und diese hinzuzufügen. Skype Connectivity ist ein Feature von Skype for Business, mit dem Sie die Partnerverbund-und Verzeichnissuche mit Skype-Benutzern aktivieren können. Nachdem Sie die Skype-Konnektivität aktiviert haben, können Skype for Business Benutzer nach Skype-Benutzern suchen und diese hinzufügen.
  
## <a name="skype-directory-search"></a>Skype-Verzeichnissuche

Die Skype-Verzeichnis Suchfunktion bietet Skype for Business Benutzern die Möglichkeit, nach Skype-Kontakten zu suchen. Mithilfe der Suchfunktion können Benutzer die folgenden Funktionen durchsuchen:
  
- **Suche nach Anzeigename, Beispiel "John Doe"** – Dies könnte viele Ergebnisse zurückgeben, sodass Sie möglicherweise nicht finden, wonach Sie suchen.
    
- **Suche nach Anzeigename Plus Standort, Beispiel "John Doe in Barcelona"** – dadurch werden die Ergebnisse der Suche erheblich eingeschränkt.
    
- **Suche per e-Mail, Beispiel "JohnDoe@Outlook.com"** -dies sollte in den meisten Fällen ein Ergebnis zurückgeben; diejenige, die genau mit der angegebenen e-Mail übereinstimmt. Wenn jedoch dieselbe e-Mail mehreren Konten zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Telefonnummer, Beispiel "123-123-1234"** -dies sollte in den meisten Fällen ein Ergebnis zurückgeben; diejenige, die genau mit dem angegebenen Telefon übereinstimmt. Die Telefonnummer muss den Landescode enthalten (d. h. 1-xxx-yyy-zzzz). Wenn dieselbe Telefonnummer mehr als einem Konto zugeordnet ist, werden möglicherweise mehrere Ergebnisse zurückgegeben.
    
- **Suche nach Skype Name, Beispiel "JohnDoe1456"** -wenn Exact Match gefunden wird, wird es als erstes Ergebnis zurückgegeben. Andere mögliche "Name"-Übereinstimmungen werden möglicherweise zurückgegeben.
    
    > [!NOTE]
    > Die Skype-Verzeichnissuche muss mit den folgenden IP-Adressen an Port 443 kommunizieren können: 104.40.75.246, 23.101.135.34 und 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Unterstützte Bereitstellungs Matrix für die Skype-Verzeichnissuche

In der folgenden Tabelle wird die Unterstützung für die Skype-Verzeichnissuche beschrieben.
  

||**Skype for Business Server-Front-End**|**Lync Server 2013 (oder älter) Front-End**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Kante  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Skype for Business Server und Edge sind Voraussetzungen für die Skype-Verzeichnissuche  <br/> |
|Skype for Business Server Edge + lync Server 2013 Edge nebeneinander bereitgestellt  <br/> |Unterstützt  <br/> |Nicht unterstützt  <br/> |Der Skype-Verzeichnis Such Datenverkehr fließt über Skype for Business Server Edgeserver. Der Verbunddatenverkehr wird durch den durch den Administrator konfigurierten Edge-Datenverkehr geleitet. Beispielsweise kann der Administrator auswählen, dass der Verbunddatenverkehr weiterhin über lync Server 2013 Edgeserver gesendet wird, die die Skype-Verzeichnissuche nicht unterstützen würden.  <br/> |
|Lync Server 2013 (oder älter) Edge  <br/> |Nicht unterstützt  <br/> |Nicht unterstützt  <br/> ||
   
> [!NOTE]
> Der Adressbuchdienst, der auf Skype for Business Server Front-End läuft, findet den Vorteil durch das vorhanden sein des Skype Search Port 4443 auf dem Edgeserver. 
  
> [!NOTE]
> Wenn ein Kunde über mehrere Standorte in der lokalen Bereitstellung verfügt und nur einen Skype for Business Server Edgeserver/-Pool bereitgestellt hat, wird der Such Datenverkehr von allen Standorten durch den einzelnen verfügbaren Edgeserver geleitet. Der Administrator muss sicherstellen, dass die Pools von allen Standorten auf den bereitgestellten Skype for Business Server-Edgeserver/-Pool zugreifen können. 
  
> [!NOTE]
> Der Skype Graph-Dienst wird Suchanforderungen von einem lokalen oder Microsoft 365-oder Office 365-Kunden Drosseln, wenn die Anforderungsrate 15 Anforderungen/Sekunde überschreitet. 
  
> [!NOTE]
> Für lokale Kunden großer Unternehmen müssen die Domänen mit dem Skype-Suchdienst auf der Whitelist stehen, um höhere Anforderungs Raten zu ermöglichen. 
  
> [!NOTE]
> Wenn in der Warteschlange zu viele ausstehende Anforderungen vorhanden sind, werden von Skype for Business Server eingehende Anforderungen gedrosselt. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Bereitstellen von Skype-Konnektivität für Skype for Business Online in Office 365

Die Skype-Konnektivität ist auch ein Feature von Skype for Business Online, das Teil von Office 365 ist. Sie können das Skype Connectivity-Feature in der Skype for Business Administration Center im Microsoft 365 Admin Center aktivieren.
  
Für Office 365 mittelständische Unternehmen, Office 365 Enterprise, Office 365 Bildung und Office 365 für Regierungen: Melden Sie sich beim Microsoft 365 Admin Center an, und navigieren Sie zum Skype for Business Verwaltungskonsole. Wechseln Sie zu externe Kommunikation. Klicken Sie unter öffentliche Sofortnachrichten-Dienstanbieter auf aktivieren. Wenn Sie den Zugriff einzelner Benutzer auf Skype-Konnektivität steuern möchten, können Sie dies tun, indem Sie die Einstellungen für die externe Kommunikation einzelner Benutzer bearbeiten.
  
Für Office 365 Small Business Premium: Melden Sie sich bei Office 365 an, und wechseln \> Sie zu \> Administrator Diensteinstellungen Chat, Besprechungen und Konferenzen. Aktivieren Sie die externe Kommunikation. Der Schalter für externe Kommunikation aktiviert die Skype-Konnektivität und die Kommunikation mit anderen Organisationen, die Skype for Business verwenden.
  
Weitere Informationen zur Skype for Business Online Verwaltung finden Sie unter:
  
- [Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Was Sie ausprobieren sollten, wenn Sie keine Chat Skype for Business oder externe Skype-Kontakte haben](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Hinzufügen eines Kontakts in Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administratoren: Konfigurieren Skype for Business Einstellungen für einzelne Benutzer](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Bereitstellen von Skype-Konnektivität für Skype for Business Server

Skype for Business Server verwendet die Verbund Zugriffs Architektur, um die Konnektivität mit Skype zu unterstützen. Diese Konnektivität ermöglicht es Ihren Skype for Business Server-Benutzern, Skype hinzuzufügen. Skype-Clients können auch Skype for Business Benutzer zu Ihrer Kontaktliste hinzufügen. Basierend auf Richtlinien, die in Skype for Business Server administrativ festgelegt sind, können Benutzer über Chatnachrichten kommunizieren, die Anwesenheit von einander anzeigen und Audio-und Videoanrufe initiieren. Die Skype-Konnektivität ist auch ein Feature von Skype for Business Online und kann für Skype for Business Online Kunden aus der Skype for Business Administration Center im Microsoft 365 Admin Center aktiviert werden.
  
> [!NOTE]
> Wenn Skype for Business Server bereits für die Verbindung mit Windows Messenger mithilfe der öffentlichen Instant Messaging-Konnektivität (PIC) konfiguriert ist, ist Ihre Bereitstellung bereits für Skype-Konnektivität konfiguriert. Die einzige Änderung, die Sie möglicherweise in Frage stellen sollten, ist, den vorhandenen Messenger PIC-Eintrag als Skype umzubenennen. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Die Skype for Business Server Bereitstellung von öffentlichen Instant Messaging-Konnektivitäts-Websites ist nicht mehr verfügbar.

Die Website, die früher zum manuellen Bereitstellen von Verbund zwischen Skype for Business lokalen Bereitstellungen und Skype verwendet wurde, ist nicht mehr erforderlich und wird auf 8/15/2019 heruntergefahren. Der Partnerverbund mit Skype verwendet jetzt die Ermittlung des Verbundpartners, was derselbe Mechanismus ist, der für den Verbund mit Skype for Business Online erforderlich ist.

Für die Kommunikation zwischen einer lokalen Skype for Business-Bereitstellung und Skype-Benutzern über die vorhandene öffentliche im-Infrastruktur muss die lokale Edgeserver-Konfiguration nun mit Skype for Business Online kompatibel sein.

> [!NOTE]
> Die meisten Kunden benötigen keine Aktion, einschließlich aller Bereitstellungen, die mit Skype for Business Online zusammenschließen.
  
Lokale Bereitstellungen sind erforderlich, um einen Verbund-DNS-SRV-Eintrag für jede Domäne zu veröffentlichen, die er hostet. Anleitungen stehen in der [DNS-Planung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)zur Verfügung. Jede Domäne muss durch DNS-SRV-Abfrage in einen Edgeserver-FQDN aufgelöst werden, der eine Nachsilben Übereinstimmung der Domäne auf oberster Ebene erfüllt. Nehmen wir beispielsweise die Domäne "contoso.com":

|**Gültige FQDNs**|**Kommentar**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |In jedem Fall muss der exakte FQDN entweder im SN oder im San des externen Zertifikats vorhanden sein, das auf dem Edge-Server installiert ist.   |
|access.contoso.com   ||
|**Ungültige FQDNs**|**Grund**|
|sip.contoso-edge.com   |Keine Suffix-Übereinstimmung.  |
|sip.it.contoso.com   |Es wird kein Suffix auf oberster Ebene gefunden.   |

Weitere Anleitungen zu externen Zertifikaten finden Sie unter [Zertifikatplanung](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>FAQs

**Warum wird die proprovisioning-Website heruntergefahren?**
Der in 2006 bereitgestellte öffentliche im (PIC)-Bereitstellungsmechanismus (PIC.lync.com) ist nicht mehr betriebsbereit und wird auf 8/15/2019 heruntergefahren. Stattdessen wird der öffentliche Sofortnachrichten Verbund das gleiche Verbundmodell annehmen, das von Skype for Business Online verwendet wird, die als "Partner Ermittlung" bezeichnet wird, wobei eine lokale Bereitstellung durch den DNS-SRV-Eintrag (en) der Verbunddienste öffentlich erkannt wird.

**Bedeutet diese Änderung, dass der öffentliche Sofortnachrichten Verbund veraltet ist?**
Nein. Der öffentliche Sofortnachrichten Verbund wird weiterhin viele Jahre unterstützt, wahrscheinlich bis das Skype for Business lokale Produkt das Ende der Lebensdauererreicht.

**Unser Unternehmen hat eine hybride Beziehung (freigegebener Adressraum) mit Skype for Business Online, sind wir davon betroffen?**
Nein, da Sie sich bereits mit Skype for Business Online verbünden, wirkt sich diese Änderung nicht auf Sie aus.
 
**Bedeutet diese Änderung, dass unser Unternehmen den Partnerverbund mit Skype for Business Online aktivieren muss?**
Nein. Wenn Ihre Edgeserver-Proxyeinstellungen den Partnerverbund nicht mit dem Skype for Business Online Hostinganbieter (sipfed.online.lync.com) aktivieren, wirkt sich diese Änderung nicht auf diesen aus. Allerdings gelten die gleichen DNS-und Zertifikatanforderungen für die Zusammenarbeit mit Skype for Business Online nun auch für die Zusammenarbeit mit Skype-Benutzern.
 
**Unser Unternehmen ist groß und kann seine Edge-Konfiguration aufgrund von regulatorischen/Compliance/etc-Gründen nicht ändern... Was können wir tun?**
Jede lokale Organisation, die ihre Edgeserver-Konfiguration nicht wie angegeben ändern kann, sollte den Produktsupport bei der frühestmöglichen Gelegenheit erreichen.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Aktivieren von Verbund-und Public Chat-Konnektivität (PIC)

Konzentrieren Sie sich jetzt auf die Skype for Business Server Umgebung und die administrativen Aufgaben, die zum Konfigurieren der Skype-Konnektivität erforderlich sind. In diesem Abschnitt wird davon ausgegangen, dass der Administrator Skype for Business Server bereitgestellt und den externen Zugriff konfiguriert hat, auch bekannt als Edgeserver. 
  
Es gibt drei primäre Schritte, die zum Aktivieren von Partnerverbund und PIC erforderlich sind. Diese sind:
  
1. Konfigurieren von Partnerverbund und PIC
    
2. Konfigurieren von mindestens einer Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer
    
3. Konfigurieren der Skype PIC-Anbieter Einstellung
    
#### <a name="1-configure-federation-and-pic"></a>1. Konfigurieren von Partnerverbund und PIC

Partnerverbund ist erforderlich, damit Skype-Benutzer mit Skype for Business Benutzern in Ihrer Organisation kommunizieren können. Die öffentliche Instant Messaging-Konnektivität (PIC) ist eine Klasse des Verbunds und muss so konfiguriert sein, dass Ihre Skype for Business-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe der Skype for Business Server-Systemsteuerung konfiguriert.
  
> [!NOTE]
> PIC Federation wird nicht mehr von Produktversionen vor lync Server 2010 (Live Communication Server, Office Communications Server) unterstützt. Die unterstützten Plattformen für den PIC-Verbund umfassen Skype for Business Server, lync Server 2013 und lync Server 2010. 
  
Partnerverbund ist erforderlich, damit Skype-Benutzer mit Skype for Business Benutzern in Ihrer Organisation kommunizieren können. Die öffentliche Instant Messaging-Konnektivität (PIC) ist eine Klasse des Verbunds und muss so konfiguriert sein, dass Ihre Skype for Business Server-Benutzer mit Skype-Benutzern kommunizieren können. Partnerverbund und PIC werden mithilfe des Dialogfelds Edge-Konfiguration in der Skype for Business Server-Systemsteuerung wie in der Abbildung dargestellt konfiguriert.
  
![Neuen Edge-Pool definieren](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> EnableSkypeIdRouting-und EnableSkypeDirectorySearch-Attribute müssen in den Einstellungen des öffentlichen Anbieters (siehe spätere Anweisungen) auf true festgelegt werden, damit die Suche funktioniert. 
  
Dadurch werden die administrativen Aufgaben abgeschlossen, die auf dem Server ausgeführt werden müssen. Sie haben jetzt die Möglichkeit, Skype-Konnektivität einzurichten.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Konfigurieren Sie mindestens eine Richtlinie zur Unterstützung des Zugriffs durch Verbundbenutzer.

Mithilfe der Skype for Business Server-Systemsteuerung muss ein Administrator eine oder mehrere Richtlinien für den externen Benutzer Zugriff konfigurieren, um zu steuern, ob Skype-Benutzer mit internen Skype for Business Server-Benutzern zusammenarbeiten können.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Konfigurieren der Skype PIC-Anbieter Einstellung

Mithilfe der Skype for Business Server-Verwaltungsshell muss ein Administrator die Skype for Business-Clientrichtlinie so konfigurieren, dass Skype als zusätzlicher PIC-Anbieter angezeigt wird. 
  
> [!NOTE]
> Benutzer von PIC-Dienstanbietern (Public Instant Messaging Connectivity) können nicht an Chatnachrichten oder Konferenzen in Ihrer Organisation teilnehmen, bis Sie auch mindestens eine Richtlinie (Schritt 2, weiter oben in diesem Verfahren) für die Unterstützung von Verbindungen mit öffentlichen Chat Diensten konfiguriert haben. 
  
Für neue Installationen können Sie die Skype-Konnektivität konfigurieren, indem Sie einen öffentlichen Skype-Anbieter mithilfe der Skype for Business Server-Systemsteuerung aktivieren, wie in der Abbildung dargestellt.
  
![SIP-Partnerverbundanbieter](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Um Skype-Konnektivität beim Upgrade auf Skype for Business Server zu konfigurieren, müssen Sie den vorhandenen öffentlichen Skype-Anbieter entfernen und erneut hinzufügen. 
  
Das Konfigurieren der Skype-Konnektivität kann auch nur mithilfe von PowerShell erfolgen. So konfigurieren Sie die Skype-Konnektivität mithilfe von PowerShell:
  
1. Öffnen Sie in einer Skype for Business Server Front-End-Server die Skype for Business Server Verwaltungsshell.
    
2. Führen Sie die folgenden zwei Befehle aus:
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Wenn in Ihrer Umgebung noch kein PIC-Anbieter vorhanden ist und Sie einen neuen PIC-Anbieter erstellen, müssen Sie das Cmdlet Remove-CsPublicProvider nicht ausführen. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Was tun die unauffälligsten Parameter?
    
   - ProxyFqdn: Standort von Skype Federation Edge (Besitzer/verwaltet von Microsoft)
    
   - IconURL: Symbol, das von &amp; lync Skype for Business-Client verwendet wird, um Skype-Kontakte visuell zu identifizieren
    
   - NameDecorationRoutingDomain und NameDecorationExcludedDomainList: mit dieser Einstellung können Benutzer die MSAS von Skype-Benutzern eingeben, ohne sich über das "dekorieren" von nicht-Microsoft-Domänen mit "MSN.com" informieren zu müssen. Dadurch entfällt die Eingabe von "User (contoso. com) @MSN. com" für alle Domänen, die sich nicht in der ExcludedDomainList befinden. Der SFB-Client formatiert die MSA automatisch, wenn sich die Domäne nicht in der ausgeschlossenen Liste befindet. Wir haben die am häufigsten verwendeten Microsoft-Kontodomänen zur ausgeschlossenen Liste hinzugefügt.
    
     > [!NOTE]
     > Öffentliche Anbieter müssen entfernt und neu hinzugefügt werden, wenn Änderungen vorgenommen werden. Es sind keine in-Place-Änderungen zulässig. 
  
     > [!NOTE]
     > In lync Server 2013 CU5 &amp; lync-Desktop-Client in Office 2013 SP1 hinzugefügt, verbessern NameDecorationRoutingDomain und NameDecorationExcludedDomainList die Situation, in der lync-Benutzer Skype-Kontakte hinzufügen, um nicht-Microsoft-Domänen zu "dekorieren", um diese zu identifizieren und an Skype weiterzuleiten (das Format: User (contoso. com) @MSN. com). Diese neuen Einstellungen ermöglichen die automatische Formatierung der Adresse des Benutzers eingeben im Dialogfeld "Skype-Kontakt hinzufügen" mit dem NameDecorationRoutingDomain (die auf MSN.com festgelegt werden sollte), wenn Sie nicht die Domänen im NameDecorationExcludedDomainList enthält (wir können derzeit MSN.com, Live.com, hotmail.com, Outlook.com) unterstützen. 
  
3. Von einem Skype for Business-Client können Benutzer nun nach einem Skype-Benutzer suchen und ihn hinzufügen.
    
## <a name="clients-and-interoperability-matrix"></a>Clients und Interoperabilitäts Matrix

In der folgenden Tabelle ist der Status der Interoperabilität zwischen der aktuellen Version von Skype Consumer und der neuesten Version von Skype for Business dargestellt.
  

|**Skype-Clients**|**Hinzufügen von Kontakten, Chatnachrichten, Anwesenheitsinformationen, Audio-und Videoanrufen**|**Kommentar**|
|:-----|:-----|:-----|
|Skype-Windows-Desktop  <br/> |7,6 oder höher, Windows XP und höher  <br/> |**Neu**: Unterstützung hinzugefügt für Windows Skype-Client, der unter Windows XP läuft, und Windows Vista **(erfordert die neueste Client Version 7,26 oder höher)** <br/> |
|Skype Mobile-Android-Telefon und-Tablet  <br/> |6,19 oder höher, Ausführung von Android OS Version 4.0.3 oder höher  <br/> |Geräte mit niedriger Spezifikation unterstützen möglicherweise keine Videoanrufe  <br/> |
|Skype Mobile – IOS  <br/> |6,11 oder höher, unter IOS 7 oder höher  <br/> |Nicht unterstützt iPhone 4 und älter, iPod 4. Generation und früher, iPad 1st Generation  <br/> |
|Skype-Mac  <br/> |7,19 oder höher, unter Mac OS X 10,9 (Mavericks) oder höher  <br/> |Erfordert Mac OSX 10,9 oder höher  <br/> |
|Skype universelle Windows-app (Windows 10) Desktop und Mobilgeräte  <br/> |Windows 10 (Redstone 1-Update oder höher)  <br/> |Windows universelle APP erhält Update im Herbst 2016 Hinzufügen von Interop-Unterstützung  <br/> |
   
In der folgenden Tabelle ist der Status der Interoperabilität zwischen der neuesten Version von Skype for Business und der neuesten Version von Skype Consumer aufgeführt. 
  
|**Client**|**Skype-Verzeichnissuche und Kontakte hinzufügen**|**Skype A/V, Chat-Interop**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |Ja  <br/> |Ja  <br/> |
|Skype for Business auf dem Mac  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2013  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Web App-Online und lokal  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
|Lync Mobile-Windows Phone  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync mobile-Android  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync Mobile-IOS  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Lync-Raumsystem  <br/> |In Kürze verfügbar  <br/> |Ja  <br/> |
|Moderne lync-app (Win 8,1)  <br/> |Ja  <br/> |Ja  <br/> |
|Lync Mac 2011  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Desktop 2010  <br/> |Kann hinzugefügt werden (keine Suche)  <br/> |Ja  <br/> |
|Lync Phone Edition  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
|Lync Attendant  <br/> |Nicht zutreffend  <br/> |Nicht zutreffend  <br/> |
   

